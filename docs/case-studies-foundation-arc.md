# Case Studies: Foundation Arc

Transcribed verbatim (as closely as photo quality allows) from `case-studies-foundation-arc.md`, found in source photos `case studies/converted/IMG_1674-1693.jpg`. Per the user: these are **finished drafts**, not specs — described as "actual copy that requires very few changes, if any." Framing note from the source doc: "Pre-AI case studies that prove the systems-thinking practice predates AI by years and matured at scale before the AI pivot."

These have been transferred into the live site at `src/content/case-studies/two-status-framework.md`, `connected-planning-process-map.md`, and `product-naming-framework.md`. This file is the archival source transcription.

---

## Case Study 1 — Two-Status Framework

**2022 — Enterprise Products / Accounting**
**Role:** Lead content designer; designed and drove adoption end-to-end
**Scope:** Audited statuses across Enterprise Products, designed a two-status system, drove cross-product adoption and EP Product System Council interest in standardization

**TL;DR:** Statuses across Enterprise Products were quietly conflating two unrelated concepts — progress and health — and shipping that confusion to users. I audited the field across the org, separated the two, published the system, and watched it get picked up by seven product teams and the EP Product System Council inside a year. The lesson — that the hardest part of fixing UX is recognizing when the underlying data model is wrong — is the same instinct I use today on AI agent design.

### What was broken

Close Platform was adding a feature that depended on statuses. While auditing existing statuses across Enterprise Products in preparation, I noticed something nobody had named yet: every product was using a single status field to communicate two completely different things — progress (where is this in the workflow?) and health (is this in good shape?) were collapsed into one column, and users were guessing which one a given status meant.

This wasn't a copy problem. It was a model problem masquerading as a copy problem.

### What I decided to fix

The brief was "revise statuses for Close Platform." The reframing was: every Enterprise Product has the same problem; the right move is the system, not the screen.

Two decisions I held the line on:
- **Bifurcate, don't consolidate.** The intuitive instinct from PM partners was to find the "right" combined status. I argued the opposite — that no single field could communicate both axes without structurally confusing them. Splitting them was the only structurally honest fix. Trade-off: more visual real estate, more complexity. Worth it.
- **Publish the system, not just the implementation.** I could have shipped Close Platform's revised statuses and called it done. Instead I wrote it up as a Workplace note designed for other CDs and PDs to apply to their own products. That's what made it scale beyond the original brief.

### What shipped

- The bifurcated status model in production on Close Platform (implementation screenshots in EPS Pattern Audit board)
- The cross-product audit doc — every status pattern across Enterprise Products, mapped against the two axes (sheet)
- The two-status system, written up as a Workplace note (note)
- Lightning talk to EP Design
- Direct consultation with seven product teams: Cases, Flux Analysis, FAAM, Touchless Billing, Commissary Logistics Tool, Journals, Core Products

### Outcomes

**Shipped in production:**
- Close Platform implemented the bifurcated status model in production (H1 2023 EPS pattern audit Figma board, with screenshots)
- Pivotal to Finance Connect's future-state design
- EP Product System Council moved to standardize the two-status model as a cross-EP design pattern

**Qualitative:**
> "Kade was able to extract from user interviews the role of statuses in both workflow management and in health indicators to truly serve user needs... Kade came up with the proposal to bifurcate statuses in progress and features Kade has founded have become a pivotal part of the Assurance product roadmap for 2023."
> — Product Designer for Finance Connect

**Reach signal:**
- 942 reads on the Workplace note; cited by other CDs as the reference for status work in Enterprise Products

**Downstream:**
- The pattern became the seed for my 2023 H1 work on Planning TG patterns and Dim Sum guidance — same move, larger surface

*(What I learned that still applies — cut off in source photos; not fully captured.)*

---

## Case Study 2 — Connected Planning Process Map

**2022 — Enterprise Products / Financial Planning**
**Role:** Lead content designer; designed and ran the cross-functional roadshow
**Scope:** Designed a team-group-wide user journey map for Financial Planning; led XFN roadshow; surfaced underinvestment areas the org hadn't named two years later

**TL;DR:** The Financial Planning team had inherited years of half-solved problems and no shared picture of where they fit. I designed a single user journey map across every planning function, ran it through every discipline on the team in a roadshow, and surfaced two specific underinvestment areas — the integration gap between Oracle EPM (vendor) and internal Org Tool — that were the anchor investments of the team's H2 Team Group roadmap two years later. By 2024, those exact two areas were the load-bearing investments of the Planning Products Team Group's H2 2024 roadmap — measured in tens of thousands of FM hours saved.

### What was broken

When I joined Planning, our PM Chris Tyler told the design team that 2021 research had surfaced pain points that were *still* unsolved going into 2022 — gathering financial data, formatting it, the manual repetition that ate the team's time. The pain was real and persistent, but the team had never built a shared picture of how the work actually flowed end-to-end.

The result: nobody on the XFN team could distinguish quick wins from long-term investments, and the roadmap reflected that. Effort went to whichever symptom shouted loudest, not whichever step in the user journey was actually load-bearing.

### What I decided to fix

The brief was implicit — "help us think about Planning." The reframing: the missing artifact isn't a research deck or a strategy doc. It's a single picture the whole team can stand around — one that names what's missing as clearly as what's there.

Two decisions:
- **Design the map to be roadshowed, not published.** The point of the artifact wasn't documentation. It was a forcing function — every discipline (PD, UXR, Eng, other CDs, PMs, stakeholders) had to look at it together and react. The map was the reason they ended up in the same room, not the file.
- **Map the gaps as explicitly as the flows.** Most process maps document what exists. Every underinvested area got visually legible treatment — every spot where the team didn't know what tool should own a process got a red "Tool?" annotation directly on the map. Vendor tools (Oracle EPM) and internal products, which made the integration gaps between them, were labeled by name on the cards, not glossed over. Naming the absences is harder than naming the presences, and impossible to miss — forced the team to confront them every time they returned to the map.

### What shipped

- The user journey map across every planning function — headcount, capacity, resource, HRBS, QA/performance, C&B — phase-columned from operationalization through continuous engagement (Figma)
- A multi-discipline roadshow (PD, UXR, Eng, CD, PM, stakeholders) that incorporated stakeholder feedback into the map iteratively
- A version of the map that explicitly named the two underinvestment areas the org would later build around: cross-process collaboration, and Oracle EPM ⟷ internal Org Tool integration

### Outcomes

**Strategic foresight (the load-bearing outcome):**

The two underinvestment areas the map named in 2022 became the load-bearing investments of the Planning Products Team Group's H2 2024 roadmap — two years later, after the team formalized as a Team Group and ran a 2023 FBP scorecard evaluation that surfaced the same gaps independently.

| What the map named in 2022 | What the H2 2024 Planning Products roadmap committed to |
|---|---|
| Collaboration across disconnected planning processes | "Bringing decentralized processes into structured systems" — entire framing of the doc |
| Oracle EPM (vendor) ⟷ internal Org Tool integration | Explicit H2 2024 strategic priority: "connecting workflows across third party and internal tools to deliver integrated end-to-end support of FBP processes" |
| Fragmented data, manual integration burden | FBP scorecard found "information silos across products requiring high manual effort to pull together" — listed as a primary driver of the new investments |

The downstream investments those gaps unlocked are measured in real hours: ~11k FM hours/year for self-service budget reporting, ~5k FM hours/year for accrual automation, ~1,200 hours of MC Planner effort for reorg operationalization. The proximate causes were the year-of-efficiency macro and the FBP scorecard evaluation two years before problems the right problems mattered.

I'm not claiming the map drove the H2 2024 roadmap. What the map did was see the *right* problems two years before the org's own scorecard validated which underinvested areas mattered.

**Qualitative (proximate):**
> "I think [the process map] would be helpful to [our PM] right now as he is working on the decks for roadmaps.... Timing is perfect."
> — Engineering Manager

**Adoption (proximate):**
- XFN team used the map to reframe roadmap conversations around the underinvestment areas
- UXR used the map to onboard a new team member into the Planning space
- Engineering managers used it to highlight underdeveloped product areas to leadership

### What I learned that still applies

Mapping the gaps is harder — and more strategically valuable — than mapping the flows. Most process artifacts document what exists. That instinct shows up directly in 2025 in the AI Autonomy Framework: the framework doesn't just describe how AI components should behave when things work — it names the gaps in transparency, escalation, and handling that AI features tend to ignore. Same move at a different surface. Name the absence first; the work that follows.

---

## Case Study 3 — Product Naming Framework

**2022 — Enterprise Products**
**Role:** Lead content designer; piloted process, built reusable resources for other CDs
**Scope:** Led naming for Workstream; built a lightweight evaluation template and naming risk assessment framework; supported renames of 65+ products across Supply, Accounting, and EE

**TL;DR:** Naming at Meta is a small thing that's secretly enormous — stakeholder negotiation, a leadership review, a potential blocker. I led the Workstream naming effort, then turned what I learned into a lightweight evaluation template and a risk-assessment framework that other content designers used to rename 65+ products across multiple orgs. The reusable resources reached more people than the products actually did.

### What was broken

Naming work was treated as bespoke every time. Each content designer reinvented the wheel — the evaluation rubric, the leadership presentation deck, the way to surface and weigh stakeholder input. Instead I led the "name Workstream." The reframing: if I'm building the toolkit anyway, I should build it for the next ten naming projects, not just this one.

Downstream: bad names that had to be retired, leadership reviews that stalled, sprints that ate weeks because the work itself isn't hard. The meta-work — the framework for doing it consistently — was missing.

### What I decided to fix

The brief was "name Workstream." The reframing: if I'm building the toolkit anyway, I should build it for the next ten naming projects, not just this one.

Two decisions:
- **Codify the evaluation template the first time it works, not the third.** I could have refined the template privately across multiple projects before publishing. Instead I shared it after Close Platform and Financial Planning Center knowing the next CDs would help me iterate. Cost: rougher first version. Benefit: it actually showed up when other people needed it.
- **Treat the leadership-review part as the load-bearing artifact.** Most CDs treat the work and the lead presentation as the wrap-up. I treated it the other way — because his work reads is specifically about how to get leadership approval — because that's where naming projects actually die.

### What shipped

- Lightweight evaluation template — standardized via Close Platform and Financial Experiences renames. Shared with Core Experiences as a potential memorized CD resource.
- Workstream naming evaluation note (908 reads)
- CD resource for leadership approval on names (783 reads)
- Naming risk assessment framework (doc) — piloted in Supply and Accounting naming sprints; discussed with internal Foundation peers as a possible standardized framework
- Two product-specific naming notes for Close Platform and Financial Planning Center

### Outcomes

**Measured:**
- 783 + 908 + ~700 reads across the published notes
- Contributed to renames of 39 Supply products and 26 Accounting products (65 total)

**Qualitative:**
> "#thanks Kade Dalton for writing such an excellent note on product naming and reviews with so many great resources linked. Although I haven't engaged in either yet, I'm bookmarking this as the gold standard reference."
> — Content Designer

> "Glad I stumbled across this note — I'm coincidentally kicking off naming in the upcoming weeks 🎉"
> — Content Designer

> "#thanks Kade for your advocacy in finding the most effective name for our products. Naming is such a difficult thing because it's so visceral and everyone has an opinion, but you approach it with an inclusive and detail-minded framework, making it easy for people to rally behind!"
> — Stakeholder

**Downstream:**
- Established the practice of CDs publishing reusable resources from project-specific work
- Naming risk assessment framework discussed for standardization across Internal Foundation

### What I learned that still applies

The reusable resource will reach more people than the project will. Optimize accordingly.

This is the move that connects every system I've shipped since — the Pulse content system, the AI Autonomy Framework, the Risk Figma plugin, the rd-eval rubric. The instinct is the same: do the work for the project in front of you, but design the substrate for the next ten projects you'll never see. The compounding is what makes the work senior.
