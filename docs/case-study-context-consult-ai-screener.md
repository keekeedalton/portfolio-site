# Context: Consult AI Screener

Transcribed from real Workplace posts, Figma prototype screenshots, and internal strategy docs (`[Canonical] AI for Consult`, `AI for Consult Metrics`, `Consult Phase 3: Decisions & Eng Planning`), photographed in `case studies/converted/IMG_5053-5054.jpg` and `IMG_5057-5096.jpg`.

## Pod structure

"AI for Consult" pod. Track Lead: Chris Adams. QB: Shayna Fader, Jimmy Zeng (Privacy). Builders: Elizabeth Ruggiero, Jimmy Zeng (Privacy), Joel Bassanguen, Kade Dalton, Viktoria Stashok, Channie Wang, Grace Li. XFN: Andie Millan, Erika Barrios, Samrawit Ayele, Mannat Sharma, Cathy Nguyen.

## Background (from the canonical strategy doc)

Consult is a critical touchpoint where product teams get live advice from Legal and PRPM (Privacy Review Program Manager). It serves three jobs: (1) Novel Risk Identification, (2) Non-IDP Risk Coverage (risk domains not yet covered by standard requirements — civil rights, IP, contracts, consumer protection), (3) General Guidance.

As AI accelerates product development volume/speed, Consult risked becoming a bottleneck, and wasn't scalable as-is: Legal sees a high volume of low-risk launches (70% only have IDP'ed risks, 52% result in self-cert) — legal bandwidth wasn't optimized for the most critical projects; risks not detected/mitigated in Risk Review had to be manually checked via Consult; legal advice wasn't well recorded, preventing analysis and automation.

## Timeline

- **Q1 2026 (Feb-March)**: Developed an agentic approach. Aligned with leads on 3-phase rollout (paper pilot, tooling pilot, PO-facing launch). Built a series of agents (1 topline, 2 sub-agents). Ran a paper pilot with Monetization. Integrated AI recommendations into the Consult Tool for Legal; kicked off an in-tool pilot with 15 lawyers.
- **8-week sprint (April-May 2026)**: Two workstreams in parallel — Consult Screener and Ops Workstream — run by representatives across key Consult stakeholder groups. Objectives: [P0] Reduce unnecessary Consults by 80% (at 80% recall); [P0] Decrease average Consult duration from 8 business days to <3 business days.
- **Mid-May**: "Consult Phase 3: Decisions & Eng Planning" — detailed alignment post on UX/eng decisions before building, authored by a PM with Kade as design owner on several sections (Initial Assessment eligibility timing, AI agent failure handling, legal guidance visibility).
- **Result**: 84% recall (target 80%, exceeded), TNR 55% (target >80%, missed), N=539. Consult model paused pending a 5/19 risk+legal leadership review.

## Defining "unnecessary"

A Consult is "unnecessary" if it meets either: no non-IDP risks are present, or no novel/high-risk issues are present that would require manual review. Conservative estimate (L28 data, as of Mar 26, 2026, sample of 13 consults from higher-risk areas): ~60% of Consults are unnecessary. Breakdown: 38% (5 of 13) send teams to manual review; 31% (4 of 13) have non-IDP domains; 38% (5 of 13) meet neither criteria → unnecessary.

## Metrics framework (Kade co-owned; DS: Channie Wang, DE: Grace Li)

Recall = % of all Consults that truly do need a manual Consult, what % did AI catch. Low recall = AI missing valid Consults (bad — this is the safety-critical direction).
FPR (False Positive Rate) = % of all Consults that can be automated, what % did AI incorrectly say needed a Consult. High FPR = AI over-prescribing Consult (costs efficiency, not safety).

Two calculation approaches considered:
- **Option A (Simple, binary per-Consult)**: Did Legal identify any non-IDP or novel risk requiring manual Consult? Did AI also identify any of those risks (not comparing risk-by-risk — just whether AI and Legal agree on the end outcome)? Recommended as **topline metric**. Pros: simple, mimics longer-term Consult goals (binary outcome). Cons: outcome-focused not analysis-focused — credits the AI right by luck (e.g., AI flags IP risk correctly but for a risk domain Legal didn't actually flag — still "counted right" under this metric).
- **Option B (Complex, per-risk)**: Compares the AI's identified risks against Legal's at the individual risk level. Recommended for **internal tracking / guardrail**. Recall = % of Legal-confirmed non-IDP/novel risks correctly flagged by AI; FPR = % of AI-flagged non-IDP/novel risks that turned out inaccurate in Legal audit. Pros: risk-specific breakdown shows if the AI's routing decision AND underlying risk analysis were both right; critical to actually improving the agent. Cons: high dependency on accurate data entry from Legal (need to log each domain and AI's identification per domain).

Worked example for Option B: AI flags IP, News, Sanctions in risk domain analysis. Legal selects IP, News, Civil Rights in Q6/Q7. Agree on IP, News (2); AI misses Civil Rights (1); AI overprescribes Sanctions (1). AI flags Privacy; Legal selects Privacy in Q7. Agree on Privacy (1); AI misses none (0); AI overprescribes none (0). Recall for this consult = Agree on (3) / Legal confirmed (5) = 60%. FPR for this consult = AI overprescribes (1) / Total AI recs (4) = 25%.

## Kade's specific contributions (from peer feedback, self-review, and Figma artifacts)

**Peer feedback (anonymized, role-only per site convention)** — a product designer on the pod:
- "End-to-end design ownership with real product impact: Kade fully re-factored the Consult tooling experience — converting it from a flat, text-based input experience into an interactive space where we could display AI-recommended risks and have users engage with them. He designed it to be user-friendly while also giving us the structured data labels needed to measure and improve our agents. The tool was rolled out to the vast majority of legal teams and became the de-facto consult experience for >60% of consults. He also ran leadership alignment on new flows via design crit, building conviction independently."
- "The 'AI builder' role in action: Kade bridged design and engineering wonderfully. He fully coded prototypes that made demoing seamless and eng handoffs faster — eliminating back-and-forth that typically slows delivery. He also contributed directly to agent performance, developing risk definitions and context that improved our agents' ability to detect risks and increase our recall. This combination of coded prototyping, prompt writing, and design craft is exactly what this emerging role should look like."
- "Strategic contributor beyond design lane: Kade contributed to broader pod strategy, not just his design lane. He brought product thinking to every conversation, leaned into the ambiguity of a role without precedent, iterated quickly on feedback, and consistently found ways to add value across all of our work."
- Opening framing from the reviewer: "Working with Kade on Consult was a pleasure — it was great to see him expand his skillset from CD to PD, and he made our pod meaningfully better."

**Self-review summary** ("Sole XFN AI builder for Consult Pod"):
"Operated as single design and content resource for Consult AI Pod across H1, owning full stack from UX research through coded prototypes, agent quality, PO experience, and production UI. Drove measurable improvements across 4 product surfaces — ultimately contributing to the decision to wind down Consult pod entirely, successfully moving resources to higher impact projects."

"Drove the Consult AI Screener from niche legal tool to full-breadth AI risk assessment (Feb-May): 84% recall (against 80% target); 7+ non-IDP risks surfaced where the original found zero; successfully moved resources to higher impact projects via pod wind-down. Led a 3-month campaign as sole designer on the pod's core deliverable — a ride-along agent experience for legal partners, giving each an opinionated list of risks and rationale. To support designs, proactively pushed the AI model further through independent research, prompt engineering, and iterative prototyping, expanding to full AI-powered risk assessment for POs with the goal of reducing 80% of unnecessary consults while maintaining 80%+ recall."

"Direction-setting: Identified that the screener's recall gap was a definitions problem, not an architecture problem. Independently took initiative using quant research tests against existing novel risk and non-IDP risk cases to train a small-dataset classification model that proved more effective at recall. That risk classification work was then integrated into the canonical prompt. Without this work, the agent would have remained essentially blind to non-IDP risks."

"AI impact: In side-by-side eval across 6 real projects, the original classifier found zero high-certainty non-IDP risks; updated definitions surfaced 7+ across 3 projects (Privacy, Consumer Protection). Authored improved classifier prompt shipped to A/B testing, delivering meaningful true negative rate lift with minimal recall loss."

"Business outcome: Drove pod to 84% recall against our 80% target. Prototypes became the eng handoff spec, eliminating the design-to-eng translation step and accelerating implementation. Pod's success effectively eliminated need for continued Consult investment."

## Real UI/UX artifacts seen in Figma prototypes ("AI screener for consult risk assessment — proposed UX")

Flow: Consult intake → Project info → Initial assessment → Schedule → Summary.

- **Initial assessment / shimmer state**: "Generating..." bar-chart loading animation while AI predicts risks; explicit disclaimer throughout: "These risks are AI-predicted. This is not a complete or validated risk assessment."
- **No-risk graceful path**: "No risks detected by AI" state still asks "Do you still wish to talk to product counsel (legal)?" (Yes/No) — respects PO autonomy even when the AI found nothing.
- **Risk cards**: categorized as "Recommended for legal consult" (e.g. Consumer Protections, Security, Privacy - Restricted Data, Transparency & Choice, Privacy - Consent, each with a "Why this was flagged" rationale) vs. "Not recommended for legal consult" ("Routine risks... covered by established guidance").
- **Product counsel (Legal) review surface**: assign product counsel; "Did the legal guidance provided lead to any change in the product/project plans?" outcome selector; "Legal risk assessment" with Accept/Reject controls per AI-detected risk; "AI rationale" explainer panel; "Guidance for the product team" free-text field; "Needs manual review" risk-area tagging; "Manually added risks" for anything the agent missed.
- **Next steps builder**: structured steps the PO should follow, each tied to an outcome selector and risk-area tags.
- **Real example consult used throughout prototypes**: "Banner Ads on Reels" / "IG Friends - Instagram Direct - Consult." AI-gathered context autonomously surfaced 3 additional linked documents (a data retention policy last updated 2025-11, a cross-border data transfer assessment, an internal AI model card for a recommendation engine) and synthesized real findings: a 180-day data retention window exceeding a proposed 90-day policy, a pending GDPR Article 35 DPIA for EU user data, and an unresolved bias audit flag from the model card.

## Phase 3 decision log (Kade CC'd/owned as design decision-maker)

- **Initial Assessment eligibility timing problem**: AI eligibility depends on product counsel assignment, which happens on the Schedule step — after Initial Assessment is shown. Two options weighed: scale the AI pilot to 100% (removing the chicken-and-egg problem entirely) vs. reorder steps so Initial Assessment comes after Schedule (respects current eligibility logic but feels backwards in the flow, and changes the Figma-designed step order).
- **Existing Phase 2 consults**: whether to upgrade in-flight consults to the new Phase 3 UI or let them finish on the old UI.
- **AI agent failure handling**: shimmer states, "AI-detected risks" vs. "Manually identified risks" grouping, what happens if the agent never completes.
- **Legal guidance visibility for PO**: how much of Legal's reasoning surfaces back to the project owner vs. stays internal to the legal review.

## Related, unrelated material found in the same photo batch (images 5053-5054)

Self-review bullets referencing other, separate H1 2026 work not part of this case study: "Redesigned Risk Review Web App's core interface (May-Jul)" and "Stood up GTM Hub v2: Risk Review Guide site (Jun-Jul)." Noted as a possible future case study, not used here.
