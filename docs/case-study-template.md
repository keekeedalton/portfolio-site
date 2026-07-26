# Case Study Template

Transcribed from `case-study-template.md`, as drafted in a chat with "John" (an AI agent used as a thinking partner). Two versions were photographed — a first draft (`case studies/converted/IMG_1406-1420.jpg`) and a cleaner, refined rewrite about 90 minutes later (`IMG_1446-1457.jpg`). This doc reflects the **later, refined version**, which is functionally the same structure with clearer prompts and length targets. Both should be considered the same template, not competing options.

## Purpose

A structure for portfolio case studies that works across project types — pre-AI systems work, 0-to-1 product builds, AI agents, frameworks, and patterns. Calibrated for a senior content designer audience: design leadership, hiring managers, cross-functional (XFN) reviewers.

## How to use this template

- **Length target**: 1–2 pages per case study. Resist the urge to include everything — pick the load-bearing details.
- **Voice**: First person. Specific verbs. Name decisions explicitly ("I decided X because Y") rather than passively ("X was decided").
- **Show your work**: Include process artifacts (the framework, the IA diagram, the decision matrix, the system prompt) — not just final deliverables. The thinking is more senior-coded than the polish.
- **Curation rule**: Every section should answer the prompt sharply. If a section reads as filler, cut it. The reader's attention budget is short.
- **Honesty**: Include what didn't work. A short "what I'd do differently" makes the rest of the case study more credible, not less.

## Template structure

### HEADER

- Project Title
- Year(s) — Org / Team
- Role: your specific role, e.g. "Led content design, co-led product design"
- Scope: one line — what you owned, what you influenced
- Hook: one sentence, written for a reader who has 5 seconds

**Strong hook example**: *"Replaced a manual support workflow with an AI agent that took resolution rates from 7% to 21%+ in three months and freed an org from 12% of its Help Cases load."*

**Weak hook example**: *"Worked on improving the Risk Review support experience using AI."*

The strong version names the specific change, the measurable outcome, and the strategic consequence. The weak version names the topic but not the impact.

### SECTION 1: CONTEXT (~3–5 sentences)

What was the situation when you walked in? What was broken or missing?

Prompts to answer:
- What was the state of the world before this project? (Current process, current tooling, current pain.)
- Who were the primary users, and what were they trying to do?
- What constraints shaped the design space? (Legal, regulatory, technical, time, organizational, political.)
- Why was this project happening *now*?

### SECTION 2: REFRAMING (~3–5 sentences)

What was the brief you got versus the question you decided to answer? This is where senior judgment shows.

Prompts to answer:
- What did stakeholders initially ask for?
- What did you discover that changed the question?
- How did you reframe the problem upstream of execution?

**Why this section matters**: Senior designers don't just answer the brief — they reframe. If a project genuinely had no reframing, say so explicitly rather than fabricate one; honesty is itself a senior signal. Don't force a reframing narrative onto a project that didn't have one.

### SECTION 3: DECISIONS (2–3 decisions, each 2–4 sentences; avoid more than 3)

The 2–3 most consequential calls you made on this project. For each: what was the call, what was the alternative, why did you choose this one?

Prompts to answer:
- What was the most consequential decision in this project? Why was it hard?
- What alternative did you consider and reject? Why?
- Were there decisions you negotiated with cross-functional partners where you held the line (or moved)?

**Why this section matters**: This is the highest-signal section for senior readers. Trade-off thinking, named alternatives, and stated rationale show judgment in a way that polished outcomes never can. Capping at 3 is itself a curation move — more than 3 dilutes the signal.

**Strong example** (decision-writing pattern): *Decision: Use anchored LLM-as-judge instead of pattern matching for evaluating tone. Alternative: Keyword-based pattern matching, which would have been deterministic and cheaper to run. Why this call: Tone is too multi-dimensional for keyword matching to capture without false positives. Anchored examples calibrate the judge against actual rubric definitions, which we needed for reviewer trust. Trade-off: higher cost per evaluation, but acceptable given the volume.*

### SECTION 4: WHAT SHIPPED (bulleted list, specific — count things)

The concrete deliverables. Include both the visible surface (copy, screens, components, agent behavior) and the underlying thinking artifacts (frameworks, content models, terminology systems, IA diagrams, system prompts, evaluation rubrics).

Prompts to answer:
- What did the user actually see or use?
- What underlying artifacts did you produce that supported the work?
- What patterns or systems did this project create that other people could reuse?

**Why this section matters**: Senior content design includes the substrate, not just the surface. Showing the framework or content model alongside the screens reinforces that the work is systemic, not a one-off.

### SECTION 5: OUTCOMES (bulleted list, separated into Measured / Qualitative / Downstream)

Quantitative metrics, qualitative signals, and downstream effects. Be honest about what's measured and what's inferred.

Prompts to answer:
- What measurable outcomes did this project produce? (CSAT, time saved, error reduction, adoption.)
- What qualitative signals confirmed (or complicated) the metrics? (User feedback, stakeholder reactions.)
- What downstream effects did the work unlock? (Other teams adopting patterns, organizational decisions, oncall changes.)
- For things you can't measure: what would you measure if you could?

**Why this section matters**: Outcomes are how impact gets read, but over-claiming is more damaging than under-claiming. Be specific about what's attributable to your work and what's a contributing factor.

**Honest-example pattern**: *Measured: 1,200 hours per year saved by Finance Managers (estimated based on workflow time studies). Qualitative: Three Finance Directors reported that they could now self-serve budget reporting without tagging in their analyst. Downstream: Finance Data Enablement Council established as a result; standardized metric definitions across Org Tool. Caveat: Adoption metrics not fully available until Q1 2025 pilot completes.*

### SECTION 6: BRIDGE / WHAT I LEARNED (2–4 sentences)

What did this project teach you that still applies? For older projects, this is the explicit bridge to current/AI work — what's transferable to whatever's next.

Prompts to answer:
- What did this project teach you that you didn't know before?
- What insight from this work do you apply now, even in different domains?
- For pre-AI projects specifically: how does this work inform how you approach AI design?

**Why this section matters**: This is what makes older case studies earn their place in a 2026 portfolio. A pre-AI project with a clear "this taught me X that I now apply to AI" coda becomes a foundational case study. Without it, the same project reads as dated. Don't strain for this — if a project genuinely doesn't have a transferable insight, that's a signal it might not belong in the curated portfolio.

**Strong bridge example** (for a 2022 project): *Building the two-status system taught me that the hardest part of designing for confused users isn't the copy — it's recognizing when the underlying data model is conflating two distinct concepts, where one "case status" field was trying to communicate both AI confidence and human review state. Splitting them was what made me push back on the original data model instead of just doing work around it.*

## Optional appendix sections

Use only when they add load-bearing context — skip otherwise.

- **Artifacts available**: A list of what you can actually show — screen recordings, before/after screenshots, framework diagrams, decision logs, system prompts. Helps you (and reviewers) know what visual material exists.
- **People involved**: Cross-functional partners, leadership reviewers, key stakeholders. Useful for credibility and for showing collaboration scope.
- **What I'd do differently**: If you have a real reflection — not just "I'd document better" but a specific lesson from a failure or close call. This builds credibility, but only if the reflection is genuine.

## What this template is NOT

- Not a PRD. It's a portfolio artifact, not a product spec — lean on judgment, not requirements.
- Not a self-review. Self-reviews are for performance evaluation; this is for portfolio storytelling. The framing is different even when the underlying project is the same.
- Not a case study deck. This is the document version. A talk or presentation built from this would compress harder and lean more visual.
- Not exhaustive. Pick the load-bearing details. The reader's attention budget is short.

## Quality checklist before publishing a case study

- [ ] The hook is specific and outcomes-named
- [ ] The reframing section names a real reframing (or honestly says there wasn't one)
- [ ] At least 2 decisions are explicit, with named alternatives and reasons
- [ ] Outcomes are honest (no over-claiming, caveats where attribution is partial)
- [ ] The bridge section names a transferable insight that's specific to your current work
- [ ] You can show the artifacts referenced (or note where you can't)
- [ ] Total length is 1–2 pages — if longer, cut

## Two example openings (shape, not content — from the earlier draft)

**Example: foundation case study (pre-AI)**
> **Two-Status Framework**
> 2022 — Enterprise Products
> Role: Lead content designer
> Scope: Audited statuses across EP, designed a new system, drove adoption with EP Product System Council
>
> Hook: Conflated status concepts across Enterprise Products were confusing users on Close Platform; I bifurcated "progress" and "health" into a two-status system that became the EP-wide design pattern and is now standardized for new product teams.
>
> Context: Close Platform was adding a feature that depended on statuses, and I noticed the existing status field was trying to communicate two unrelated things at once...

**Example: AI-era case study**
> **Risk Review Help Cases AI Agent**
> 2025 — Privacy Foundations
> Role: Led content design, co-led product design integration
> Scope: 0-to-1 redesign of the Risk Review support experience including AI agent integration
>
> Hook: Replaced a manual Tasks/Butterfly forms support workflow with an AI agent that took AI-assisted resolution rates from 7% to 21%+ in three months, contributed to a 12% Q4 reduction in Help Cases, and freed PRPM resources for reallocation.
>
> Context: PRPMs were drowning in Help Cases. The legacy Tasks + Butterfly workflow had no triage, no self-serve, and no learning loop...
