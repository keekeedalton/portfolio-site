---
title: "Consult AI Screener"
order: 1
summary: "Legal review was a bottleneck — 70% of Consults only surfaced pre-identified risks, wasting expert bandwidth. As the pod's sole XFN AI builder, I found the real problem was a definitions gap, not an architecture gap. Recall hit 84% against an 80% target, and the pod's own success led to its wind-down."
discipline: "conversation"
role: "Content designer; sole cross-functional AI builder for the Consult pod — spanning UX research, coded prototypes, agent quality, and production UI"
date: 2026-03-01
tags: ["AI agent", "legal", "prompt engineering"]
draft: false
---

**Scope:** Redesigned the Consult AI screener end-to-end — UX, coded prototypes, risk-classification definitions, and the recall/FPR measurement framework — as the sole cross-functional AI builder on the pod

**TL;DR:** Legal "Consult" exists to catch novel, high-stakes risks — but <span class="secret-v2-highlight">70% of Consults only surfaced risks that were already identified elsewhere</span>, and over half resolved as routine self-certifications. As the Consult pod's sole cross-functional AI builder, I found that the screener's recall problem wasn't an architecture problem. It was a <span class="secret-v2-highlight">definitions problem</span>. <span class="secret-v2-highlight">Fixing it took recall to 84% against an 80% target</span>.

<div class="secret-v2-flow-banner banner-reframing">
  <div class="flow-chart">
    <div class="flow-node">Signals</div>
    <div class="flow-arrow">→</div>
    <div class="flow-node flow-node--highlight">Definitions gap</div>
    <div class="flow-arrow">→</div>
    <div class="flow-node">Updated taxonomy</div>
    <div class="flow-arrow">→</div>
    <div class="flow-node">Recall lift</div>
  </div>
</div>

## Context

Consult exists so product teams can get live advice from Legal and Privacy Review Program Managers on three kinds of problems: <span class="secret-v2-highlight">novel risks nobody's seen before, risk domains not yet covered by standard requirements, and general navigation of the risk process</span>. But as AI accelerated the pace of product development, Consult risked becoming the bottleneck: <span class="secret-v2-highlight">70% of Consults only had risks that were already identified elsewhere in Risk Review</span>, and 52% resolved as routine self-certifications — Legal's expertise was being spent on cases that didn't need it. Worse, <span class="secret-v2-highlight">legal advice wasn't recorded anywhere structured</span>, which meant there was no way to analyze it or build automation on top of it.

## Reframing

The pod's mandate was to build an AI screener that could tell whether a project actually needed a Consult. Early on, <span class="secret-v2-highlight">a stuck recall number read as an engineering problem</span> — not enough model sophistication. I didn't think that was right. Working through side-by-side evaluations across real projects, I found <span class="secret-v2-highlight">the original classifier wasn't missing non-IDP risks because the architecture couldn't find them</span>. It was missing them because nobody had precisely defined what those risk categories meant well enough for a model to apply them consistently. That reframe — from "improve the model" to <span class="secret-v2-highlight">improve the definitions</span> — is what actually moved the numbers.

<div class="secret-v2-flow-banner banner-decisions">
  <div class="flow-chart">
    <div class="flow-node">Research</div>
    <div class="flow-arrow">→</div>
    <div class="flow-node flow-node--highlight">Definitions rewrite</div>
    <div class="flow-arrow">→</div>
    <div class="flow-node">UI + labels</div>
    <div class="flow-arrow">→</div>
    <div class="flow-node">Measured outcomes</div>
  </div>
</div>

## Decisions

1. **<span class="secret-v2-highlight">Fix definitions before fixing architecture.</span>** Instead of pushing for a bigger or more complex model, I ran research against labeled novel-risk and non-IDP-risk cases, built a <span class="secret-v2-highlight">small-dataset classification approach that outperformed the existing one</span>, and folded that work directly into the canonical prompt. In a side-by-side eval across 6 real projects, <span class="secret-v2-highlight">the original classifier found zero high-certainty non-IDP risks</span>. My updated definitions surfaced 7+ across 3 projects, in Privacy and Consumer Protection.
2. **Design for structured data, not just usability.** I fully refactored the Consult intake from a flat, free-text input into an interactive experience where AI-recommended risks could be reviewed and acted on — built to be usable for POs and Legal, but just as importantly, built to produce the structured data labels the team needed to actually measure and improve the agent. The UI and the eval infrastructure were the same design decision, not two separate projects.
3. **Code the prototypes myself.** Rather than hand off static mocks to engineering, I built coded prototypes directly, which doubled as demo material and as the literal eng handoff spec — cutting out the design-to-eng translation step that normally slows this kind of work down.

<div class="secret-v2-flow-banner banner-shipped">
  <div class="flow-chart">
    <div class="flow-node">Intake</div>
    <div class="flow-arrow">→</div>
    <div class="flow-node">Risk review</div>
    <div class="flow-arrow">→</div>
    <div class="flow-node flow-node--highlight">AI rationale</div>
    <div class="flow-arrow">→</div>
    <div class="flow-node">Legal handoff</div>
  </div>
</div>

## What shipped

- A full AI screener flow — Consult intake, project info, initial assessment, scheduling, summary — including a "no risks detected" path that still lets a project owner escalate to Legal manually if they want to
- Risk cards categorized by type (Consumer Protections, Security, Privacy, Transparency & Choice, and others) with <span class="secret-v2-highlight">plain-language rationale for why each was flagged</span>
- A product counsel review surface: <span class="secret-v2-highlight">accept/reject controls on each AI-detected risk</span>, an AI-rationale explainer, free-text guidance for the product team, and a path for Legal to manually add risks the agent missed
- An <span class="secret-v2-highlight">AI-gathered-context feature</span> that autonomously surfaced linked documents — a data retention policy, a cross-border data transfer assessment, an internal model card — and synthesized real compliance findings from them
- <span class="secret-v2-highlight">The recall/false-positive-rate measurement framework itself</span>, including resolving a real methodology debate between a simple binary-per-Consult metric and a more complex per-risk metric, landing on the simple version as topline with the detailed version used to actually tune the agent
- The updated risk-classification definitions, folded into the canonical prompt

<div class="figure">
  <img src="/images/consult-ai-screener/overview.png" alt="Consult advisory overview screen, showing initiative details and AI-gathered context from linked documents" />
  <p class="figure-caption">The advisory overview. AI-gathered context surfaces linked documents — a data retention policy, a cross-border transfer assessment, a model card — and synthesizes real compliance findings from them, right where a reviewer is already looking.</p>
</div>

<div class="figure">
  <img src="/images/consult-ai-screener/counsel-review.png" alt="Product counsel review surface showing an AI-detected risk card with accept/reject controls, rationale, and a path to manually add missed risks" />
  <p class="figure-caption">The product counsel review surface. Accept/reject controls on each AI-detected risk, plus a path for legal to add risks the agent missed — the same interaction that produces the labeled data behind the recall/FPR measurement framework.</p>
</div>

<div class="figure">
  <img src="/images/consult-ai-screener/preliminary-review.png" alt="Consult preliminary review screen showing a no-advisory-required outcome with an option to still consult legal" />
  <p class="figure-caption">A "no advisory required" outcome — the null-state path that still lets a project owner escalate to legal manually if they want a human read.</p>
</div>

## Outcomes

- **Measured:** <span class="secret-v2-highlight">84% recall against an 80% target</span> (N=539); average Consult duration was being actively tracked against a goal of cutting 8 business days down to under 3
- **Honest gap:** true negative rate landed at 55%, short of the >80% target — the model was good at not missing real risks, less good at confidently clearing safe ones. That gap is real and unresolved; the Consult model was paused pending a leadership review rather than declared an unqualified win.
- **Qualitative:** peer feedback specifically called out the range of the role: *"This combination of coded prototyping, prompt writing, and design craft is exactly what this emerging role should look like."*
- **Downstream:** the screener's success was, in a real sense, self-eliminating — it worked well enough that leadership wound down the standalone Consult pod and reallocated its people to higher-impact projects.

## What this taught me

The instinct that mattered most here wasn't technical, it was diagnostic. Everyone assumed a stuck recall number meant the model needed to get smarter. It didn't — it needed better-defined categories to reason with in the first place. That's the move I make on every AI project now: before reaching for a bigger model, ask whether the humans on the project have actually agreed on what the categories mean.
