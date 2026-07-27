---
title: "Annual Planning, 0-to-1"
summary: "Before this, Annual Planning ran on countless spreadsheets and a legacy tool with almost no insight into the process. Three-plus years later, it saves Mission Control 1,000+ hours a cycle, with 99% of position updates happening in-product instead of in a spreadsheet."
discipline: "product"
role: "Content designer"
date: 2023-10-01
tags: ["0-to-1", "product"]
draft: false
---

**Scope:** End-to-end content design for a 0-to-1 Annual Planning product — flows, error states, NUX, emails, terminology, and support content — built with EEs, SWEs, PM, PD, Mission Control, Finance, and business stakeholders

**Hook:** Before this, Annual Planning ran on countless spreadsheets, propped up by heavy manual effort to clean data and reconcile it across orgs, plus a legacy tool that gave almost no insight into the process itself. Three-plus years later, it's saved Mission Control 1,000+ hours a cycle, and 99% of position updates now happen in-product instead of in a spreadsheet.

## Context

Before this product existed, annual planning ran on countless spreadsheets, propped up by heavy manual, human effort to clean data and reconcile it across orgs, plus a legacy tool that gave planners and Mission Control little to no insight into the process as it happened.

## Reframing

I don't have a crisp memory of the initial ask versus what this grew into — but whatever the starting scope was, it didn't stay narrow. What shipped covers the full planning surface: plan creation, goal creation, headcount debt calculation, organizational effectiveness metrics and benchmarks, position creation, cross-org reorg capabilities, and admin features like changelogs and approval flows.

## Decisions

**Untangling consolidated statuses.** The old process's status fields ambiguated due dates, progress, and category all at once — one field trying to answer three different questions. Starting from the simple goal of organizing states, I extrapolated the distinct attributes we actually needed to track for every plan. That attribute list is what pushed the design toward clean metric tiles, sortable tables, and badges that surfaced urgent or important data instead of burying it in a status string.

## What shipped

- Core flows: plan creation, goal creation, headcount debt calculation, organizational effectiveness metrics and benchmarks, position creation, cross-org reorg capabilities
- Admin features: changelogs, approval flows, reorg operationalization support (position movement, redistribution, production-issue resolution)
- 50+ error messages, 15 new-user-experience flows, and 10 email notifications (including hand-built HTML)
- A full terminology system, in-product user guide, and support content
- No-freeze planning with in-tool merge notifications, Line of Credit visibility, and multi-year rate card transitions

## Outcomes

- **Measured:** 1,000+ hours of Mission Control time saved per cycle by reducing reliance on spreadsheets; 3,327 position changes operationalized in 2024, nearly doubling to 6,225 in 2025 — goals handled grew from 66 to 127 over the same period, with no corresponding increase in user count; 99% of position updates now initiated through the product UI rather than a spreadsheet; the 2025 cycle alone created 5,324 position changes, supported 127 targets across roughly 55 orgs and 297 locations, and touched close to $1B in headcount growth and reduction
- **Qualitative:** *"I have to say, this planning tool is one of the best tools that came out in the last couple of years (since I've been with Meta). Good job to the team and thank you."* — Infra Allocation Captain. Hypercare quality held up under real load too: of 52 hypercare issues raised in one cycle, every high-priority one was resolved within 12 hours, with minimal user impact.
- **Downstream:** the tool has run every annual planning cycle for multiple years running — not a one-off launch, but the standing system of record.

## Bridge / what this taught me

Processes collect clutter, and people are wary of relinquishing them — there's always a rationalization for complexity until you can prove an easier way exists. We had to manage change over several years, not just at MV1 launch: a phased rollout slowly won down the manual workarounds people were protective of when the tool first shipped. What actually built trust was small and cumulative — terminology that simplified ideas, cutthroat simplicity in small UX moments — and users bought in for two reasons: the tool felt complementary to their existing process rather than a hostile replacement of it, and each of those small moments quietly made the case that this was easier than a spreadsheet, one interaction at a time.
