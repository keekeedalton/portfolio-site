---
status: draft-in-progress
source: "case studies/converted/IMG_1458-1465.jpg — chat with John, dated 2026-05-08"
---

# Draft: "Teaching an LLM to Write Accessibility Copy Without Sounding Like a Robot"

This is a **skeleton draft**, not a finished case study — transcribed as-is from a chat thread where "John" (an AI agent) drafted a first pass using only the 3-sentence self-review summary as source material. `[BRACKETED]` placeholders mark where real specifics are still needed. Treat this as a structural example of applying the template (see `docs/case-study-template.md`) to a real project, not as ready content.

## 2023 H2 — Enterprise Products / Content Design

**Role**: Independent contributor; designed and ran the work end-to-end
**Scope**: Trained iLlama via Metamate on Content Design standards — focus on accessibility and inclusion guidance

**TL;DR**: In 2023, before most of design had engaged with LLMs as collaborators, I trained an internal model to reproduce Content Design standards — specifically the accessibility and inclusion guidance that was fragmented across products and creating real legal, privacy, and quality risk. The training mostly worked. The lesson from doing it is the foundation for the AI work I do now.

### The state of the world in 2023

Content design guidance at Meta had been carrying a quiet structural problem for years: accessibility and inclusion guidance lived in too many places `[BRACKETED: which docs/products, what fragmentation looked like in practice]`. The result was that the same UI string might use one piece of guidance on one product and a contradictory one across the org, and most product teams didn't even know there **was** a single source of truth to find, let alone where.

This isn't just a tidiness problem. Accessibility copy carries legal weight. Inclusion language means inconsistency at scale means inconsistency in the things Meta tells people about what we are doing with their data, their identity, and their access.

### What I tried

Metamate had just opened up enough for me to train a model on internal content. I had a hunch: if I could feed iLlama the canonical Content Design standards plus enough labeled examples of "good" and "bad" copy, it could become the diffusion vector for guidance that humans had failed to scale.

Specifically:
- Wrote system prompts that anchored the model on `[BRACKETED: which standards docs/how the prompt was structured]`
- Provided labeled training examples — `[BRACKETED: roughly how many, what categories, where the examples came from]`
- Built a testing approach that compared model output against the rubric I'd written
- Documented the prompts, the labeled set, and the testing notes for handoff

### What surprised me

I admit the first round was `[BRACKETED: what actually happened — was it bad? promising? mixed?]`. The honest answer is that the model was good at reproducing the surface patterns of accessibility copy and bad at the underlying judgment that produced those patterns. It could not yet decide whether one screen reader description **looked** right versus **was** right — it needed me to articulate things I'd never had to articulate for years of doing this intuitively.

That gap turned out to be the actual lesson. Writing labeled examples forced me to operationalize craft I'd been doing intuitively for years. The training was as much about teaching myself how to teach models as it was about teaching the model.

### What I'd build differently now

`[BRACKETED: at least one specific lesson — e.g., "I'd build the eval loop first instead of last" or "I'd anchor on negative examples more heavily than positive ones"]`

### Why this still matters

The instinct that emerged from this work — that the hardest part of designing with AI isn't the prompt, it's the operationalization of judgment — is the foundation for everything I'm doing in 2026. The AI Autonomy Framework I co-authored, the Consult Screener, the rd-eval framework: each is a different version of the same move. Translate expert judgment into something a model can apply, then design the human-in-the-loop that keeps it honest.

In 2023 I thought I was training a model. In hindsight, I was teaching myself how to teach models. That turned out to be the real artifact.

## Notes on what was imported from Mat's style (per the voice research)

- TL;DR with the punchline included — not "here's what I did" but "here's what I learned"
- Bad-version-first framing — opens with the structural problem, not the project
- "I admit X" + honest gap acknowledgment — at the friction moment (round one didn't work)
- Statement-style section headers — "What I tried," "What surprised me," "Why this still matters," not "Solution"
- Italics for editorializing — "why"/"that"/"needed"
- Closing aphorism that's also a bridge — "I thought I was training a model. In hindsight, that turned out to be the real artifact." leaned on self-deprecation and analogy instead of pure metrics
- No fake humor or pop culture forced in — this draft intentionally has none, since the material didn't call for it

## What's needed to make this real

The bracketed placeholders are the load-bearing details. Without them, this is a structurally sound but generic case study. Specifically:

1. What docs/standards did you train iLlama on?
2. Roughly how many labeled examples? What categories?
3. What did the first round actually produce — was it bad, promising, mixed?
4. One concrete lesson for the "what I'd build differently" section
5. Any impact metric or qualitative signal — was it adopted? did anyone else use the model? did Metamate notice?
