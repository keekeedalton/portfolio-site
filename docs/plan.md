# Handoff Plan: Text-First Portfolio Site

## Context

This is a personal portfolio for a content/product designer showcasing work across system design, product design, and conversation design, told largely in written prose (case studies and essays). The most important framing: this is a publication, not a web app. Content is the product; the site is a thin, fast, well-typeset reading surface around it.

The owner needs to be able to write and publish a new case study as easily as writing a doc — no code deploy — and to occasionally introduce a new kind of page without a rewrite.

**Locked stack:** Astro (static site generator) + Decap CMS (git-based CMS), with a self-hosted OAuth broker.

Rationale: Astro ships near-zero JS by default, has typed content collections that enforce the content model, and is genuinely simple for a text-first site. Decap CMS gives a web editing UI whose "publish" action just commits a Markdown file to git and triggers a rebuild — no database, content stays in version control.

**Owner decisions (locked):**
- Astro, not Next.js.
- Self-hosted OAuth broker, not Netlify Identity/git-gateway — host-agnostic and durable, at the cost of a little more setup (see Phase 4).
- All content is CMS-editable, including the singleton pages (home, about, contact), so upkeep and copy edits never require touching code.

## Hard Constraints (do NOT violate without asking)

- No database, no user accounts, no server runtime.
- No component library (MUI, Chakra, etc.). Typography and reading layout is the design; use a small custom CSS/design-token layer.
- Prefer a hosted service over a server for any dynamic need (forms, analytics, search).
- Content lives as Markdown/MDX files in git — the single source of truth.

## Phase 1: Define the Content Model (do this FIRST, before any code)

Decide and document the content model. There are two categories — repeatable collections (many items, same shape, listed/browsed) and singleton pages (one-of-a-kind). All are edited in the CMS. This schema is the backbone the templates and CMS both depend on.

**Repeatable collections:**
- `case-study` — core work artifact (evidence: "work I did and its outcome"). Fields: `title`, `summary`, `discipline` (`system` | `product` | `conversation`), `role`, `date`, `heroImage` (optional), `tags`, `draft` (bool), `body` (MDX).
- `essay` — standalone written perspective not tied to one project ("how I think"). Fields: `title`, `summary`, `tags`, `draft`, `body` (MDX).

**Singleton pages (one each, CMS-editable):**
- `home` — intro copy + which case studies to feature.
- `about` — bio/background.
- `contact` — contact copy + links.

Implement the collections as Astro content collections with a Zod schema so frontmatter is type-validated at build time (`discipline` as an enum powers taxonomy/browsing). Model the singletons as single-entry content/data files the templates read, so their copy is editable without code changes.

**CMS mapping:** repeatable collections become Decap folder collections; singleton pages become a Decap files collection (one file entry per singleton). See Phase 4.

## Phase 2: Rendering & Layout

Build a small set of templates:
- Home / index — brief intro + featured/recent case studies.
- Discipline landing pages — one per discipline value (problem → approach → artifacts → outcome). Generated from the `discipline` field, not hand-maintained.
- Case-study template — the reading view (problem → approach → artifacts → outcome).
- Essay template and generic page template.

**Reusable MDX components to build:**
- `ChatTranscript` — for conversation-design samples (speaker turns, annotations). This is the one genuinely custom component worth investing in.
- `Figure` / `Callout` — captioned images and asides for prose.

## Phase 3: Styling / Design System

- A strong typographic system: reading-width measure, a type scale, generous vertical rhythm, one display + one text face.
- Design tokens (CSS custom properties) for color, type, spacing.
- Mobile-first, fast, accessible (semantic HTML, focus states, alt text enforced via schema where practical).

## Phase 4: CMS Integration (Decap) — enables "new pages without code"

Delivery phasing (token-efficiency decision): the CMS is a convenience layer over Markdown files committed directly to the repo, not a dependency of the site. Ship the site fully working with Markdown-in-git first, then add Decap as a second delivery phase. This isolates the one genuinely stateful, deploy-coupled part of an otherwise static site, so the finicky auth work is optional and sequenced last instead of blocking the build.

**Critical principle:** the content model defines the CMS, not vice versa. Outline: 1. add a type + schema to the Astro content collection, 2. add a template, 3. add the matching CMS collection. Document this exact "how to add a new page type" workflow in the README.

### The auth chain (why this is the risky part)

Decap runs entirely in the browser and has no backend. "Publish" means it commits a Markdown file to the GitHub repo on the editor's behalf, which triggers a rebuild. To write to the repo it needs a token, and a token can't live in client-side JS — so a small server-side OAuth broker is required. The chain is:

`GitHub OAuth App → auth broker (serverless fn) → Decap config.yml → repo write perms`

If any link is misconfigured, login silently fails — each fix means deploy → test on the live URL → fix again. That deploy-loop is the main token sink; the breakdown below collapses it into one deliberate live session.

### Scaffolding: buildable now (non-regrettable) vs. deferred

The de-risking trick: push everything secret or URL-specific into environment variables and one config file, so scaffolding builds empty sockets rather than hardcoded assumptions.

**Buildable now, no regret:**
- `public/admin/index.html` — static CMS entry page that loads Decap from CDN. No secrets.
- `public/admin/config.yml` — ~90% non-secret: `backend: github`, `repo: owner/name`, `branch`, and the collections. Repeatable types (`case-study`, `essay`) are a single-entry files collection with one entry each. Leave only the auth-dependent `base_url` as an env-injected placeholder.
- Auth broker function — the OAuth token-exchange code is boilerplate; it reads `OAUTH_CLIENT_ID`, `OAUTH_CLIENT_SECRET`, `OAUTH_REDIRECT_URI` (callback URL), `PUBLIC_CMS_AUTH_BASE_URL` (broker URL used by `config.yml`).
- `.env.example` — declare every variable the chain needs, with dummy values + comments.
- `SETUP.md` checklist — the highest-leverage artifact; converts the silent-fail loop into a linear runbook:
  1. Register a GitHub OAuth App (Settings → Developer settings → OAuth Apps).
  2. Copy Client ID + generate Client Secret.
  3. Set the Authorization callback URL to the deployed broker URL.
  4. Set the four env vars on the host.
  5. Deploy.
  6. Visit `/admin`, log in, confirm a test commit lands and the site rebuilds.

**Genuinely deferred (needs live specifics — cannot scaffold):**
- Registering the GitHub OAuth App and obtaining client id/secret (manual, GitHub UI).
- The real callback URL (depends on final deploy domain).
- Putting real secret values into the host's env.
- End-to-end login verification (only works once deployed).

One caveat that removes remaining regret: the auth broker is slightly host-coupled (Netlify function vs. Vercel vs. Cloudflare Worker differ in their wrappers around the same logic). Decide the host first, OR keep the token-exchange logic in a thin, host-agnostic handler and leave only the wrapper for later so the core stays reusable.

## Phase 5: Backend Substitutes (only as needed)

There is intentionally no backend. If these features are requested:
- Contact form → hosted form service (e.g. Formspree). Do not build a server.
- Search → static client-side index (e.g. Fuse.js over a generated JSON index).
- Analytics → hosted script (privacy-friendly option preferred).

## Phase 6: Hosting & Deploy

Static build output deployed to any static host (Vercel / Cloudflare Pages / GitHub Pages / CDN). Because the OAuth broker is self-hosted and host-agnostic, the deploy target is not tied to the CMS auth choice.
- Git push → auto build → CDN.
- The broker needs a serverless function runtime (e.g. Vercel/Cloudflare Functions). Keep the token-exchange logic in a thin, host-specific path (e.g. `netlify/functions/` or `api/`).
- **Open: confirm the specific static host + function runtime with owner before Phase 6.**

## Token-Efficient Build Order

Sequence the work so the cheap, high-confidence parts land first and the two token sinks (CMS auth, design polish) are isolated and optional.

1. **Scaffold + content model** — Astro init, `content/config.ts` schemas, one sample `.md` per type. High-confidence boilerplate.
2. **Templates + prose components** — layouts, `ChatTranscript`, `Figure`; render sample content. High-confidence preview loop (dev server + screenshots) — without it, design iteration is blind and expensive.
3. **Markdown-first publishing** — site is fully publishable by committing `.md` to git. Deploy here. This is a complete, shippable milestone with zero auth wiring.
4. **CMS scaffolding (non-regrettable stubs)** — `public/admin/`, `.env.example`, `SETUP.md`, all with env-placeholder sockets. No live deps.
5. **CMS go-live (single deliberate session)** — execute `SETUP.md`: register OAuth App, set env vars, deploy, verify login end to end.

Two cheap things that cut the most tokens: (a) give the implementing agent a working preview loop before any design work; (b) lock the three Open Questions below before handoff — mid-build indecision causes the rework that actually leaks tokens.

## Critical Files / Artifacts the Agent Will Create

- `src/content/config.ts` — content collection schemas (case-study, essay, + singleton data entries).
- `src/content/case-studies/`, `src/content/essays/` — repeatable content.
- `src/content/singletons/` (or data files) — home, about, contact.
- `src/pages/` — routes (home, about, contact, discipline landings).
- `src/layouts/` and `src/components/` — templates + prose components (`ChatTranscript`, `Figure`).
- `src/styles/tokens.css` — design tokens.
- `public/admin/index.html` — Decap CMS entry page (static, no secrets).
- `public/admin/config.yml` — Decap collection config; mirrors the schema.
- Auth broker function (host-specific path, e.g. `netlify/functions/` or `api/`) — declares `OAUTH_CLIENT_ID`, `OAUTH_CLIENT_SECRET`, `OAUTH_REDIRECT_URI`, `PUBLIC_CMS_AUTH_BASE_URL` — OAuth token exchange, reads secrets from env.
- `.env.example` — env-injected.
- `SETUP.md` — live CMS go-live checklist (deferred steps).
- `README.md` — includes the "add a new page type" workflow.

## Verification

- **Content model:** build fails loudly on invalid/missing frontmatter (schema works).
- **CMS round-trip:** create a draft case study in the CMS UI → confirm it publishes it → confirm it appears on the correct discipline landing page.
- **Text-first quality:** case-study pages read well at mobile and desktop widths; near-zero shipped JS on prose-only pages.
- **Extensibility:** follow the documented 3-step workflow to add one throwaway new page type and confirm it works end to end, then remove it.

## Resolved Decisions

1. Framework: Astro. ✓
2. CMS auth: self-hosted OAuth broker (not Netlify Identity). ✓
3. Content model: collections `case-study` + `essay`; CMS-editable singletons `home`, `about`, `contact`. ✓

## Remaining Open Questions

1. Static host + function runtime for deploy and the OAuth broker (e.g. Vercel, Cloudflare Pages+Functions, GitHub Pages+Functions). Needed before Phase 6.
2. Typography direction (typeface pairing / overall tone) — optional to decide up front, but a reference or two will cut design-iteration tokens.
