# Context: AI Autonomy Framework / AI Patterns Sprint

Transcribed from a real internal deck, "AI Patterns Sprint Update" (Sept 2025), photographed in `case studies/converted/IMG_5008-5035.jpg`. DRI: Kade Dalton (CD). PDs: Andrew Lyons, Engly Chang, Roger Yan, Ian Mcnamara. Champion: Espen Tuft.

This is the source material behind `src/content/case-studies/ai-autonomy-framework.md` — kept here for reference since the deck contained more detail than fit in the case study itself.

## The framework itself

Risk org launched the **AI Responsibility Framework** (built by AI4C, evangelized by a peer referred to as "Michel"): six stages (0–5) defining human/AI roles, tooling expectations, and qualification criteria at each level of automation. Uses a self-driving car analogy throughout to make each stage concrete:

- **Stage 0 — No automation**: Human full control, AI not present. *("You're driving the car yourself with no tech.")*
- **Stage 1 — Human assistance**: Human exercises expert judgment; AI provides helpful information. *("Car provides beeping lane warning, but/or speed and brake.")*
- **Stage 2 — Approval required**: Human applies nuanced judgment to accept/reject AI proposals. *("Car assists with steering and/or speed, but must keep hands on wheel.")*
- **Stage 3 — Conditional automation**: AI completes tasks within human-approved swimlanes, escalates complex/novel issues. *("Car drives itself in traffic, but you must take over if it gets confused.")*
- **Stage 4 — High automation**: AI sustains quality performance at the project level; only escalating/novel tasks return to humans. *("Robotaxi runs on its own, but a remote operator may guide it out of a jam.")*
- **Stage 5 — Full automation**: AI completes all operations; humans audit asynchronously. *("No driver, no steering wheel — fully autonomous.")*

## The problem (org-level, pre-sprint)

Without a guiding design system, patterns, and principles, it was difficult for teams to deploy AI consistent with craft and quality across the Risk org. The lack of guardrails forced teams to make their own determinations about how advanced AI features should be within product experiences — teams were incentivized to strive for highly mature AI features but had no support to gracefully migrate from no/low-AI to highly intelligent features. Feature rollouts frequently outpaced model accuracy, user confidence in AI, and general design hygiene. Without centralized patterns, teams diverged in implementation — creating inconsistent, unreliable, unpredictable experiences for users encountering AI across many surfaces, and leaving teams to bend or break XDS (the design system) components.

A "Before" slide showed four real, shipped AI features side by side — a Metamate resource-recommendation panel, a WhatsApp Reels "Move to Top" sticker-prefill feature, a self-certification-audit "AI-guided evidence description" input checker, and an audit summarizer — captioned: "A sample of various features and their expression of AI. They all look, feel and perform differently."

## The atomic capability model (Kade's framing device)

"Although it's natural from a workflow perspective to say we have dozens of AI features across our portfolio, research engineers helped us understand that all current AI features can be broken down into 4 fundamental capabilities":

1. **Classification** — e.g. what risk factors apply
2. **Search** — e.g. find relevant documents
3. **Generate** — e.g. project summary
4. **Feedback loop** — e.g. was AI accurate?

"In our sprint, we found that decomposing the AI feature portfolio into these 4 atomic abilities helped accelerate our understanding of AI, the work, and needs."

## The feature coverage map

Cross-referenced the 4 capabilities against the framework's 5 stages (stages 4–5 out of scope for this sprint) to visualize health (consistency) and coverage of design patterns. Before the sprint: Classification and Search were largely "Missing" at Stage 1; most cells were "Partial coverage" or "Partially covered — inconsistent patterns" at Stages 2–3; Generate and Feedback loop had some early coverage. After the sprint: **+60% coverage**, with several cells moving to "Proposal ready" or "Covered." A note flagged that "many features from H1 would not qualify for stage 3 in retrospect" and asked "how might we offer graceful migration to stage 1 or 2?"

## Investment

"In Q3, [a PM] brought together a collective of ICs pursuing better/faster AI-first patterns based on AI-Design crit insights. We also asked ourselves 'how might this tie back to Autonomy Framework and AI Tooling' in flight." Structure: 3-day AI-sprint (to start and grow a pattern library) + ~4 weeks of piloting, testing, and iterating on early patterns, across 5+ different workstreams.

## Base component

"Here is the core XDS gen AI card. We started by building on this. We established as a founding principle to support and grow the XDS system, instead of deviating from it without great justification. This way, we can stress test the existing components and contribute to their expansion and improvement." Shown as a real prompt/AI-interaction card component (Ask follow up, Ask Custom, Refine, Discard/Insert affordances). Real comments on this slide: Jen Da and Isha Shu ("Love this clarity") both with 2 hearts.

## Extending the patterns

"Extending the AI patterns — Compliance and autonomy level oriented expansion of base patterns." Shows AI-generated Guidance and Suggestions panels grounded in real project documents — piloted against an actual WhatsApp iOS app feature ("Move to Top" action for favorite Reels stickers), referencing real internal doc IDs (D69953719, D69953719).

## Discussion / friction (real Workplace comments)

- **Nihan Brunton, Sep 17, 2025**: "Is this 60% ... after the sprint, what coverage..." and separately, on the next-steps slide: "And how do we know these are good patterns? Do we have more to do to determine the bar?" (+1 from another reviewer)
- **Andrew, Sep 18**: "Thanks @niha and @ishashu... we had these ready at the e[nd]..."

## User pain points (cited UXR research)

- POs' adoption of AI features is hindered by perceived slowness, inhibitive number of interactions, and general caution
- Users prefer human POCs in some workflows because they're perceived as faster than AI solutions
- Users encountered higher-than-expected friction when trying to access AI help and guidance
- Users are conservative or avoidant when it comes to engaging AI for important decisions, like selecting risk factors
- Users often rely on manual validation before fully embracing AI — trust is built only after users can validate AI answers, and track records define trust over time
- Citations: "Insights (Project Creation & Intake UX) - CS 2.0 Usability Study with Project Owners, May 2025"; "Compliance AI Tools Principles"

## Success criteria defined

**Product-level** (graceful, not linear): if a workflow is at stage n and successfully achieves criteria for n+1 by end of year, that counts as AI-first design success even if the workflow doesn't reach full automation. Symmetrically, if a workflow at stage n fails to meet criteria and gracefully gets pulled back to a lower stage instead of getting pulled entirely, that also counts as AI-first design success — "we consider this rightsizing AI to meet users' needs," not failure. "We plan not to measure success by linear advancements in AI features, but by correct alignment with the autonomy [framework]."

**Program-level**: (1) Adoption — n% of AI features launched are covered; (2) Efficiency — patterns can quickly be adopted at appropriate stages; (3) Visibility — patterns are easily referenced; (4) Consistency — compliance AI features look and feel similar; (5) Velocity — these patterns speed up time to land AI features.

## Constraints (retrospective, later slide)

Design system constraints shape the feel of compliance AI: different tools, different workflows, different needs result in high divergence risk and more generic components; adhering to XDS exerts several limitations. Early compliance AI features overshot their products' stage of AI readiness — in retrospect, most attempted what the framework would now call "Stage 3." There is some degree of retroactive, non-plug-and-play design work needed to consolidate these.

## Next steps (as of this deck)

**Immediately**: continue increasing design coverage on the AI framework; continue patching practical pattern gaps in stage 1 and 2; focus on enabling teams to land early meaningful AI features.
**Soon**: consolidate and standardize stage 3 patterns.
**Future**: vision work to support stage 4 and 5 AI.

**Broader-level options considered**: ship the coverage grid and evangelize it as a shared visual roadmap, landing via a product compliance system with strong documentation ("this is the beginning of a library"); or ship in support of a program (e.g. Design with and for AI, Connection with Areas, AI4C product marketing channels); or simply continue the foundational design work, help teams achieve or gracefully pull back from stage 3, then begin vision work for stages 4–5.

**What actually happened** (per the user, confirmed after this deck): the framework and patterns were routinely referenced and adopted by many product and engineering teams in the following months. The "land via product compliance system" path specifically never happened — it was superseded by a later overhaul of the org's design component systems.
