---
title: "Teaching an LLM to Write Accessibility Copy Without Sounding Like a Robot"
summary: "Trained an internal model (iLlama, via Metamate) on Content Design standards, before most of design had engaged with LLMs as collaborators."
discipline: "system"
role: "Independent contributor; designed and ran the work end-to-end"
date: 2023-09-01
tags: ["AI", "accessibility", "WIP"]
draft: false
---

*{WIP — fuller draft notes in docs/case-study-draft-illama.md. This is the condensed site version.}*

**Scope:** Trained iLlama via Metamate on Content Design standards — focus on accessibility and inclusion guidance

**Hook:** In 2023, before most of design had engaged with LLMs as collaborators, I trained an internal model to reproduce Content Design standards — specifically the accessibility and inclusion guidance that was fragmented across products and creating real legal, privacy, and quality risk.

## Context

Accessibility and inclusion guidance lived in too many places — {which docs/products, what fragmentation looked like in practice}. Inconsistency at scale meant inconsistency in what Meta told people about their data, identity, and access.

## Reframing

{What was the original ask vs. what you decided to build?}

## Decisions

1. Wrote system prompts anchored on {which standards docs/how structured}
2. Provided labeled training examples — {roughly how many, what categories}
3. Built a testing approach comparing model output against the rubric

## What shipped

- {System prompt(s)}
- Labeled training set + testing notes for handoff
- {Any documentation/rubric artifact}

## Outcomes

- **Measured:** {first-round results — was it bad, promising, mixed?}
- **Qualitative:** {model was good at surface patterns, weaker at underlying judgment — needs a concrete example}
- **Downstream:** {adoption — did Metamate notice? did anyone else use the model?}

## Bridge / what this taught me

The hardest part of designing with AI isn't the prompt — it's operationalizing judgment that was previously intuitive. This is the foundation for {AI Autonomy Framework / Consult Screener / rd-eval framework} in current work.
