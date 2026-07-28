---
title: "AI Autonomy Framework"
order: 4
summary: "Risk had just launched a six-stage framework for AI autonomy, but no patterns to design against it. I led the sprint that closed 60% of the pattern gap in one pass — later routinely referenced and adopted across many product and engineering teams."
discipline: "system"
role: "Content designer; led the AI Patterns Sprint that translated the framework into a coverage-mapped pattern library"
date: 2025-09-01
tags: ["framework", "AI", "design systems"]
draft: false
---

**Scope:** Diagnosed and closed AI design-pattern gaps against the Risk org's newly launched AI Responsibility Framework, working with a cross-functional team of product designers and an AI4C champion

**TL;DR:** Risk had just launched a six-stage framework defining how much autonomy AI should have relative to humans. It told teams *what stage* they were at. It didn't tell anyone *how to design for it*. I broke every AI feature down into four atomic capabilities, mapped them against the framework's stages to find out exactly where the pattern library had coverage and where it didn't, and closed 60% of the gap in a single sprint.

## Context

Before this, four real AI features in production: a resource-recommending widget, a "Move to Top" prefill flow, a self-certification audit input-checker, a project summarizer. Each of these looked, felt, and behaved completely differently. There were no shared patterns and no guardrails, so teams self-determined how mature to make each AI feature — and whether or not a human should be in the loop at all. Rollouts kept outpacing models' actual accuracy and users' trust in them, and teams bent or broke the design system to compensate. Every divergence made the next one look more normal.

Risk org had just addressed half of this by launching the AI Responsibility Framework (built by AI4C, evangelized internally by a peer): six stages, from no automation to full automation, each with defined human/AI roles, tooling expectations, and qualification criteria. It gave everyone a shared vocabulary. It didn't give anyone a shared pattern library.

## Reframing

The brief, implicitly, was "help teams adopt the framework." I decided the missing piece wasn't more framework — it was patterns. It's the periodic-table move: instead of treating every AI feature as its own bespoke compound, I broke them into four atomic capabilities — classification, search, generate, feedback loop — on the theory that nearly every AI feature in the org was some combination of those four. Once features were legible as combinations of a small number of atoms, I could cross-reference each atom against each of the framework's five stages and see, cell by cell, exactly where real design coverage existed and where it didn't.

## Decisions

1. **Audit before building.** The instinct going in was to skip straight to shipping best-guess patterns for whichever stages felt most urgent. I pushed to spend the first part of the sprint building the coverage map instead — a grid of all four capabilities against all five stages, color-coded missing/partial/covered. Guessing at coverage without measuring it is how you patch problems that don't exist while missing the ones that do.
2. **Extend the existing design system, don't invent a parallel one.** The easy path was a bespoke, AI-native component built free of legacy constraints. I made "support and grow the XDS system, instead of deviating from it without great justification" a founding principle instead. The base "XDS gen AI card" pattern reuses the same underlying structure the rest of the design system already uses. That constrained what the AI card could visually do compared to something built from scratch — but it meant the pattern would actually survive contact with the rest of the product instead of becoming one more inconsistency for the next audit to find.

## What shipped

- The four-capability model (classification, search, generate, feedback loop) as the shared lens for describing any AI feature
- The feature coverage map — a visual audit crossing all four capabilities against the framework's five automation stages, used to prioritize the sprint and reported back as "+60% coverage after this sprint"
- The base XDS gen AI card pattern, plus guidance and suggestion extensions grounded in real project documentation (piloted against an actual WhatsApp Reels stickers feature)
- A 3-day AI-sprint followed by roughly four weeks of piloting, testing, and iterating on the early patterns with a team of designers across 5+ workstreams

## Outcomes

- **Measured:** +60% pattern coverage across the capability/stage grid in a single sprint — several cells moved from "missing" to "proposal ready," others from inconsistent to covered
- **Honest friction:** not everyone was convinced coverage alone meant quality. A colleague pushed back directly in the review: *"And how do we know these are good patterns? Do we have more to do to determine the bar?"* — a fair question, and one we didn't have a crisp answer to yet at the time.
- **Downstream:** the patterns were routinely referenced and adopted across many product and engineering teams in the months that followed. The plan to formally "land" this as a product compliance system never happened — a later overhaul of the org's design component systems superseded that path before it shipped.

## What this taught me

This is the same move I made years earlier mapping planning gaps instead of planning flows: name what's missing before you build for what exists. A framework tells you where you're supposed to be; a coverage map tells you where you actually are. The distance between those two is the real scope of the work — and it's usually bigger, and more specific, than the framework alone suggests.
