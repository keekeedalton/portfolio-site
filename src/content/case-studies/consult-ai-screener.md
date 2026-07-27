---
title: "Consult AI Screener"
summary: "Legal review was a bottleneck — 70% of Consults only surfaced pre-identified risks, wasting expert bandwidth. As the pod's sole XFN AI builder, I found the real problem was a definitions gap, not an architecture gap. Recall hit 84% against an 80% target, and the pod's own success led to its wind-down."
discipline: "conversation"
role: "Content designer; sole cross-functional AI builder for the Consult pod — spanning UX research, coded prototypes, agent quality, and production UI"
date: 2026-03-01
tags: ["AI agent", "legal", "prompt engineering"]
draft: false
---

**Scope:** Redesigned the Consult AI screener end-to-end — UX, coded prototypes, risk-classification definitions, and the recall/FPR measurement framework — as the sole cross-functional AI builder on the pod

**TL;DR:** Legal "Consult" exists to catch novel, high-stakes risks — but 70% of Consults only surfaced risks that were already identified elsewhere, and over half resolved as routine self-certifications. As the Consult pod's sole cross-functional AI builder, I found that the screener's recall problem wasn't an architecture problem. It was a definitions problem. Fixing it took recall to 84% against an 80% target.

## Context

Consult exists so product teams can get live advice from Legal and Privacy Review Program Managers on three kinds of problems: novel risks nobody's seen before, risk domains not yet covered by standard requirements, and general navigation of the risk process. But as AI accelerated the pace of product development, Consult risked becoming the bottleneck: 70% of Consults only had risks that were already identified elsewhere in Risk Review, and 52% resolved as routine self-certifications — Legal's expertise was being spent on cases that didn't need it. Worse, legal advice wasn't recorded anywhere structured, which meant there was no way to analyze it or build automation on top of it.

## Reframing

The pod's mandate was to build an AI screener that could tell whether a project actually needed a Consult. Early on, a stuck recall number read as an engineering problem — not enough model sophistication. I didn't think that was right. Working through side-by-side evaluations across real projects, I found the original classifier wasn't missing non-IDP risks because the architecture couldn't find them. It was missing them because nobody had precisely defined what those risk categories meant well enough for a model to apply them consistently. That reframe — from "improve the model" to "improve the definitions" — is what actually moved the numbers.

## Decisions

1. **Fix definitions before fixing architecture.** Instead of pushing for a bigger or more complex model, I ran research against labeled novel-risk and non-IDP-risk cases, built a small-dataset classification approach that outperformed the existing one, and folded that work directly into the canonical prompt. In a side-by-side eval across 6 real projects, the original classifier found zero high-certainty non-IDP risks. My updated definitions surfaced 7+ across 3 projects, in Privacy and Consumer Protection.
2. **Design for structured data, not just usability.** I fully refactored the Consult intake from a flat, free-text input into an interactive experience where AI-recommended risks could be reviewed and acted on — built to be usable for POs and Legal, but just as importantly, built to produce the structured data labels the team needed to actually measure and improve the agent. The UI and the eval infrastructure were the same design decision, not two separate projects.
3. **Code the prototypes myself.** Rather than hand off static mocks to engineering, I built coded prototypes directly, which doubled as demo material and as the literal eng handoff spec — cutting out the design-to-eng translation step that normally slows this kind of work down.

## What shipped

- A full AI screener flow — Consult intake, project info, initial assessment, scheduling, summary — including a "no risks detected" path that still lets a project owner escalate to Legal manually if they want to
- Risk cards categorized by type (Consumer Protections, Security, Privacy, Transparency & Choice, and others) with plain-language rationale for why each was flagged
- A product counsel review surface: accept/reject controls on each AI-detected risk, an AI-rationale explainer, free-text guidance for the product team, and a path for Legal to manually add risks the agent missed
- An AI-gathered-context feature that autonomously surfaced linked documents — a data retention policy, a cross-border data transfer assessment, an internal model card — and synthesized real compliance findings from them
- The recall/false-positive-rate measurement framework itself, including resolving a real methodology debate between a simple binary-per-Consult metric and a more complex per-risk metric, landing on the simple version as topline with the detailed version used to actually tune the agent
- The updated risk-classification definitions, folded into the canonical prompt

## Outcomes

- **Measured:** 84% recall against an 80% target (N=539); average Consult duration was being actively tracked against a goal of cutting 8 business days down to under 3
- **Honest gap:** true negative rate landed at 55%, short of the >80% target — the model was good at not missing real risks, less good at confidently clearing safe ones. That gap is real and unresolved; the Consult model was paused pending a leadership review rather than declared an unqualified win.
- **Qualitative:** peer feedback specifically called out the range of the role: *"This combination of coded prototyping, prompt writing, and design craft is exactly what this emerging role should look like."*
- **Downstream:** the screener's success was, in a real sense, self-eliminating — it worked well enough that leadership wound down the standalone Consult pod and reallocated its people to higher-impact projects.

## Bridge / what this taught me

The instinct that mattered most here wasn't technical, it was diagnostic. Everyone assumed a stuck recall number meant the model needed to get smarter. It didn't — it needed better-defined categories to reason with in the first place. That's the move I make on every AI project now: before reaching for a bigger model, ask whether the humans on the project have actually agreed on what the categories mean.
