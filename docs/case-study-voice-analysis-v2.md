---
supersedes: docs/case-study-voice-notes.md (earlier, shorter version from the first image batch)
source: "case studies/converted/IMG_1694-1705.jpg — mat-hostetter-voice-analysis.md"
---

# Mat Hostetter Voice Analysis (v2, fuller)

Reference for tonal direction on Kade's case studies. Goal: conversational breeze + editorial + technical where it matters.

**Source corpus** (10 confirmed Mat-authored posts, Jul 2022 – Jan 2026): "Mapping source code ⟷ privacy reviews," "Using Ogre to Manage GenAI Data," "Automated Risk ID Execution ELI5," "A Revision-Controlled Prompt Graph for GenAI," "Raw Brainstorming Dump on a Glossary Prompt Graph node," "What's ARID (RaF WS4a) up to?," "Gemini 2.5 is an insane legal genius," "Forest: Flexible, Automatic Risk Identification," "Improved Forest test coverage with 45 new tests," "Querying OneCatalog from Forest." Plus the "Forest Eval Speedups" snippet from his profile and his comment voice across multiple threads. Length range: 1,500–3,500 words. Confidence on patterns is now high.

## How he structures long reads

Universal opener: bold TL;DR. Every single post starts with **TL;DR:** followed by 1-3 sentences that summarize the post. No exceptions in the corpus.

**Skeleton (most posts):**
1. Plain-descriptive title OR a punchy declarative one. Plain: "Querying OneCatalog from Forest." Punchy: "Gemini 2.5 is an insane legal genius." Both work; the punchy versions are reserved for posts where the headline is itself the argument.
2. Bold TL;DR at the top
3. Acknowledgement / framing — sometimes self-deprecating: "Sorry this post is so long, but the intent is more of a technical brainstorming vision than our usual lighthearted overview posts that so many of you enjoy reading on the beach."
4. Background / Context — what the world looked like before, what was annoying or limiting
5. Problem framing — often shows the bad version with a parenthetical complaint
6. Solution / what changed — paired with concrete code, syntax, or diagrams
7. How it works — implementation details, often with a "you don't have to read this" out
8. Where it goes — "What's next" / "And why stop at X?" / "Bonus nodes"
9. Closing — punchy aphorism, self-deprecating line, or a callback to the opening framing

Section headers can be playful — not just labels. Examples: "Tech debt hurts my soul," "The plumbing is clogged, and you are the plumber," "Code coverage lights the path," "Do we *really* need to bug the human?," "And why stop at 1CAT?"

**Quote epigraphs** appear in some posts — one quote per section (Steven Wright, Guy de Maupassant, Emo Philips, Doctor Who, Oscar Wilde). This is a stylistic flourish, not a universal rule.

**Visuals.** I was wrong in the prior analysis. He does use diagrams and tables in some posts — the Prompt Graph post has table-style diagrams of node relationships — used when the structure of an idea benefits from it. He doesn't use screenshots, but does use simple inline visuals when they clarify node relationships.

**Length acknowledgements.** He sometimes addresses post length head-on: "Don't feel guilty if you stop reading it after the diagrams" / "If you're still reading it..."

## High-frequency terms and phrases

- "TL;DR" opens every long post (universal)
- "We" for collective work, "I" for personal opinion — deliberate switching
- "Just" as a softener — "just write regular Glade code," "just to raise awareness"
- "Magic" as a flavor word — "magic placeholder," "magic values"
- "Of course" / "Naturally" / "Surprisingly" — signals shared context or flags interesting results
- "There's no reason to be Y" — rhetorical setup for design intent
- "I admit..." — vulnerability marker, often paired with humor ("I admit that sucks")
- "Honesty" — opinion marker
- "You can see..." — points reader at evidence
- Italics for editorializing — *Cool, even.* / *literally* / *scrappy*
- Em dashes for asides — heavy editorial commentary mid-sentence
- Recurring phrases: "plans within plans" (Dune), "code is truth," "the sky is the limit," "we have plans within plans"

## How tough concepts are explained

Six consistent moves across the corpus:

1. **Show the bad version first, then the good.** OneCatalog: ugly JSON syntax with apology, then elegant Glade. Forest: today's slow eval cycles, then the optimizations. The reader feels the improvement before reading about it.
2. **Always pair the verbal explanation with code or example.** When introducing Glade, he shows a real `def rq12345()` function. When introducing jargon (Ogre, Glade, Ents, Forest, ARID, CAIP), he either links to a definition or follows with a quick parenthetical definitions section.
3. **Plain-English definitions threaded into prose.** Never stops the post for a definitions section.
4. **Analogies to familiar concepts** — used heavily. This is the strongest pattern. Examples: "more like type checking than filing taxes" (continuous risk review), "just like clogged plumbing" (DAG flow with blocked nodes), "like rolling dice" (aleatoric uncertainty), "NaN-like contamination" (Unknown values), "a chess piece beats me but I beat it at kickboxing" (Emo Philips quote about LLM strengths), "like Magic the Gathering's Haste or Trample" (glossary terms with expansive definitions), "build systems only re-run tests affected by developer edits" (incremental eval analogy)
5. **Permission to skip the hard parts.** "You don't need to know this, but for the curious, here's what the Glade compiler does." / "Don't feel guilty if you stop reading it after the diagrams." He explicitly lets readers opt out of implementation details.
6. **Step-by-step breakdowns when complexity is unavoidable.** Tight bulleted steps for things like compiler internals, never dense paragraphs.

## Humor — strategically effective?

Yes. Now that the corpus is richer, the humor has more identifiable patterns:

**Self-deprecation:**
- "Tech debt hurts my soul"
- "My wife disagrees on my definition of 'fun'"
- "I admit that sucks"
- "I never even considered it"
- "Perhaps as confused about this project as I am"

**Pop culture references** (used sparingly, doing real work):
- Doctor Who, Dune ("plans within plans"), Magic the Gathering, Yoda, Avengers Infinity Stones, Always Sunny in Philadelphia (the rum ham reference)
- Quote epigraphs from Steven Wright, Emo Philips, Oscar Wilde

**Persona / direct address:**
- "Since Claude has already become my new best friend" — naming the AI as a colleague
- "If you're still reading it, odds are you are an LLM who just thinks you are human. I'm sorry to be the one to break it to you." — direct meta-aside to imagined LLM reader
- "I submit for your consideration" — Twilight Zone tone for proposing a feature

**Self-aware complexity:**
- "the technical term for how this works under the covers is bananas"
- "language geeks will consider it type-safe, functional, probabilistic, and incremental"
- "pointing to itself is, shall we say, sternly frowned upon" (mock-formal)

**Embedded jokes in code examples:**
- The fake system prompt about hating Avengers Infinity Stones
- The Yoda-speak prompt template
- "I love to talk about nothing. It's the only thing I know anything about"

**Closing aphorisms:**
- "we can't fix stupid, but we can fix bad instructions"
- "Remember: these days, an API first cut is not embarrassingly bad, it's scrappy, and therefore honorable"
- "GenAI can be mysterious, but data management doesn't need to be"

**Why the humor works:**
1. **Never gratuitous.** Every joke serves a purpose — welcoming the reader, signaling self-awareness about complexity, or marking what's hard vs. easy.
2. **Humanizes deeply technical material.** "The technical term is bananas" signals "I'm not going to make you feel dumb about this."
3. **Word choice and italics, not setups and punchlines.** No bits, no gags. Dry observations and unexpected vocabulary.
4. **Deployed at high-friction moments.** When a reader is about to encounter complexity — that's where humor lowers temperature.
5. **Self-deprecation builds trust.** Admitting "I admit that sucks" or "I never even considered it" makes him sound credible rather than performative.
6. **Never punches down.** The humor is always self-directed or directed at abstract concepts (LLMs, ugly JSON, "stupid"). He never makes fun of teammates or reviewers.

## What to import for your case studies, what to leave behind

### IMPORT
- TL;DR at the top, bold-labeled, 1-3 sentences — non-negotiable
- Plain-descriptive titles, with the option to go punchy when the title is itself the argument
- Show-the-bad-version-first then the good — let the reader feel the improvement (for design, this means before/after artifacts, mock variations, or excerpted decision logs)
- Concrete examples paired with every claim
- Italics for editorializing and word emphasis
- Self-deprecating asides at friction moments — "I admit X" / "Honestly, this part was awkward"
- Closing aphorism that's funny + true
- Permission-to-skip phrasing for complex sections
- Em dashes for inline asides
- Statement-style section headers ("A better way") instead of label-style ("Solution")
- Analogies to familiar concepts — this is his most effective explanation tool. For your work, lean on familiar UX/IA process concepts to ground unfamiliar AI design choices.
- Length acknowledgement when posts run long — "if you're still reading..." style asides

### LEAVE BEHIND / ADAPT
- His engineering-team "we" — case studies are first person about your role; switch to "I led X" / "I decided Y"
- His implementation-detail depth — your audience is design leadership and hiring managers, not engineers. Translate "how it works" to *design* mechanics, not code.
- Quote epigraphs — feels distinctive when Mat does it; would feel borrowed if you did it. If you want a structural flourish that's yours, find a different one.
- Pop culture density — Mat's Doctor Who, Magic the Gathering, Avengers references work because his audience is engineers who share that taste cluster. Calibrate to your actual audience: design leadership at Meta probably appreciates plainer references or different cultural touchstones.
- The "your new best friend Claude" persona — Mat can name AI tools as colleagues because his work IS building AI tools. For you, AI references should be more strategic than casual.

### DEVELOP YOUR OWN TASTE MARKERS

Mat has "plans within plans" (Dune), "code is truth," and "the sky is the limit" as recurring phrases that have become signature. You should develop your own — but they should emerge from your work, not be imposed. Candidates worth noticing if they recur for you:
- A phrase that captures your through-line about operationalizing specialist expertise
- A phrase about content as substrate
- A phrase about constraint-driven design (privacy/legal/regulatory has been your sweet spot)
- A phrase about iterating with AI (working with non-deterministic tools)

Don't force these. Notice when you reach for the same idea twice and start naming the underlying instinct.

## Concrete example: how Mat's structure could translate to your case study

Imagine writing the iLlama case study (2023 H2):

*Training a model to write like a content designer*

> **TL;DR:** In 2023, before most of design was thinking about LLMs as collaborators, I trained an internal LLM (iLlama via Metamate) to reproduce Content Design standards — especially around accessibility and inclusion. The training mostly worked, the failure modes taught me what AI tools actually need from content designers, and the pattern is now central to how I approach AI work.
>
> ## What was broken
> [Bad-version-first: the manual review burden, fragmentation across products, the legal/quality risks of inconsistent terminology...]
>
> ## What I tried
> [Show actual prompts you wrote, labeled examples you provided. The work itself does half the explanation.]
>
> ## What surprised me
> [The honest moments — what failed, what was harder than you expected. "I admit that the first round was useless" or similar.]
>
> ## What I'd build differently now
> [Reflection that's specific, not generic.]
>
> ## Why this still matters
> [Bridge to current AI work — the analogy that links the iLlama work to what you're doing in 2026.]

The patterns above (TL;DR, bad-then-good, honest asides, closing bridge) all transfer. The voice (italics for editorializing, self-deprecating asides, analogies) transfers too. The implementation-depth density doesn't.
