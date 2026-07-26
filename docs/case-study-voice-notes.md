# Voice & Tone Notes

Transcribed from a chat with "John" (an AI agent) analyzing the writing style of Mat Hostetter, a Meta engineer, as a reference model to adapt — not copy — for case study voice. Source photos: `case studies/converted/IMG_1438-1465.jpg`.

## The reference style (Mat Hostetter's writing)

Structural patterns identified:
- Length: 1,500–2,500 words for substantive technical posts
- Headers in `#` markdown
- Heavy use of bulleted lists and tables
- No images or diagrams in anything read from him — entirely prose
- Quote epigraphs sometimes used per section
- Section headers are statement-style, not label-style (e.g. "Code coverage lights the path" rather than "Solution")
- Self-deprecation is a major recurring pattern, not occasional — deployed at nearly every post's high-friction moments
- Pop-culture references are dense and consistent across nearly every post (Doctor Who, Dune, Monty Python/"Magic the Gathering", Steven Wright, Oscar Wilde, Always Sunny) — these work because they signal shared context with an engineering audience and calibrate tone
- Sometimes embeds jokes inside code examples/fake system prompts as a way to make long technical examples readable
- Uses a "length acknowledgment" move — a self-aware aside about the post's length that disarms the reader and earns permission to continue

High-frequency terms/phrases: "TL;DR" opens every long post; "we" for collective work vs. "I" for personal opinion (switches deliberately); "just" as a softener ("just write regular code"); "magic" as a flavor word for a placeholder concept; em dashes for asides mid-sentence; italics for editorializing; "of course"/"naturally" to signal shared context; "surprisingly" to flag counterintuitive results; "there's no reason to..." as a rhetorical setup for improvement; recurring aphorism-style phrases ("plans within plans," "code is truth").

Humor is used strategically, not gratuitously: each joke marks self-awareness about where the reader is about to encounter something hard, humanizes deeply technical material, and is deployed specifically at high-friction comprehension moments — not scattered throughout for its own sake.

## What to import into case study voice

- TL;DR at the top of each case study
- Plain, descriptive titles
- Show-bad-then-good structure (state the weak version, then the strong version) — directly mirrors the case study template's "strong hook / weak hook" pattern
- Concrete examples paired with every claim
- Italics for editorializing asides
- Closing aphorism or statement-style section headers ("A better way," not "Solution")

## What to leave behind or adapt (don't copy directly)

- **No-visuals constraint**: Mat's posts have no images. Case studies should bring visuals in — screenshots, framework diagrams — since portfolio readers expect to see the work, not just read about it.
- **Engineering-team "we"**: Mat's "we" carries his tight verbal relationship to a specific eng team. Case studies should default to first-person "I led X" / "I decided Y" — see the template's voice guidance — because the audience (design leadership, hiring managers) is evaluating individual judgment, not team output.
- **Implementation depth**: Mat's audience wants to trust his PRDs and can go deep on mechanics. Case study audience is design leadership and hiring managers — implementation depth should be about design mechanics and content models, not code.
- **His specific taste markers**: Develop your own recurring aphorisms rather than reusing his ("bananas," "cool, even"). The pattern is "have one or two phrases that become signature" — the content of those phrases should be yours, not borrowed.

## Meta-notes from the research process itself

A later message in the same thread noted a correction: the researcher initially said Mat "doesn't use diagrams" but revised this after reviewing a richer sample — he does use table-style diagrams of node relationships occasionally, when the structure of an idea benefits from it. Worth remembering as a general caution: first-pass pattern reads from a small sample can be wrong; a larger sample changed the conclusion here.
