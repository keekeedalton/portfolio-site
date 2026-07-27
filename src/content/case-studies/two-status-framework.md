---
title: "Two-Status Framework"
summary: "Enterprise Products was collapsing two unrelated concepts — progress and health — into a single status field. I split them, published the system, and watched seven product teams adopt it within a year."
discipline: "system"
role: "Lead content designer; designed and drove adoption end-to-end"
date: 2022-06-01
tags: ["design systems", "enterprise products", "foundation"]
draft: false
---

**Scope:** Audited statuses across Enterprise Products, designed a two-status system, drove cross-product adoption and EP Product System Council interest in standardization

**Hook:** Statuses across Enterprise Products were quietly conflating two unrelated concepts — progress and health — and shipping that confusion to users. I audited the field across the org, separated the two, published the system, and watched it get picked up by seven product teams and the EP Product System Council inside a year.

## Context

Close Platform was adding a feature that depended on statuses. While auditing existing statuses across Enterprise Products in preparation, I noticed something nobody had named yet: every product was using a single status field to communicate two completely different things — progress (where is this in the workflow?) and health (is this in good shape?) were collapsed into one column, and users were guessing which one a given status meant.

This wasn't a copy problem. It was a model problem masquerading as a copy problem.

## Reframing

The brief was "revise statuses for Close Platform." The reframing was: every Enterprise Product has the same problem; the right move is the system, not the screen.

## Decisions

1. **Bifurcate, don't consolidate.** The intuitive instinct from PM partners was to find the "right" combined status. I argued the opposite — that no single field could communicate both axes without structurally confusing them. Splitting them was the only structurally honest fix. Trade-off: more visual real estate, more complexity. Worth it.
2. **Publish the system, not just the implementation.** I could have shipped Close Platform's revised statuses and called it done. Instead I wrote it up as a Workplace note designed for other CDs and PDs to apply to their own products. That's what made it scale beyond the original brief.

## What shipped

- The bifurcated status model in production on Close Platform
- The cross-product audit doc — every status pattern across Enterprise Products, mapped against the two axes
- The two-status system, written up as a Workplace note
- A lightning talk to EP Design
- Direct consultation with seven product teams: Cases, Flux Analysis, FAAM, Touchless Billing, Commissary Logistics Tool, Journals, Core Products

## Outcomes

- **Measured:** Close Platform implemented the bifurcated status model in production (H1 2023 EPS pattern audit); pivotal to Finance Connect's future-state design; EP Product System Council moved to standardize the two-status model as a cross-EP design pattern; 942 reads on the Workplace note, cited by other CDs as the reference for status work in Enterprise Products
- **Qualitative:** *"Kade was able to extract from user interviews the role of statuses in both workflow management and in health indicators to truly serve user needs... features Kade has founded have become a pivotal part of the Assurance product roadmap for 2023."* — Product Designer for Finance Connect
- **Downstream:** The pattern became the seed for my 2023 H1 work on Planning TG patterns and Dim Sum guidance — same move, larger surface

## Bridge / what this taught me

The hardest part of fixing UX often isn't the copy — it's recognizing when the underlying data model is wrong. That instinct is the same one I use today on AI agent design: before touching the prompt or the interface, ask whether the model underneath is conflating two things that need to be separated.
