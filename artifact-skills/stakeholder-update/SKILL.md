---
name: stakeholder-update
description: Translate the same underlying project status into audience-appropriate versions (exec-brief, engineering-detail, customer-facing) without changing the underlying facts. Use when a PM needs to write a status update, especially when the same update needs to go to multiple different audiences. Pairs with when-to-not-message-the-customer for the customer-facing variant specifically: decide whether to send before drafting it.
---

# Stakeholder Update

## What this does

Produces multiple honest versions of the same status, tuned to what each audience needs to act on, not multiple *stories*. The facts must be identical across versions; only altitude and detail change.

## Process

1. **Write the ground truth first, once, before any audience-specific version.** One paragraph: what happened, what's at risk, what's needed. Every audience version derives from this, so contradictions between versions are impossible by construction.
2. **For each audience, ask what they need to decide or do, not just what they'd find interesting.**
   - Exec: risk to timeline/budget/strategic bet, and whether a decision is needed from them
   - Engineering: technical specifics, blockers, what unblocks them
   - Customer-facing (if applicable, run `when-to-not-message-the-customer` first): only what affects them, not internal cause detail
3. **Never let severity shift between versions.** A risk described as "manageable" to engineering and "on track" to execs, when it's actually neither, is the classic failure mode this skill exists to prevent. If it's a risk, it's a risk in every version. Only the technical depth changes, not the honesty level.

## Output structure

```
## Ground Truth
[One paragraph, audience-neutral, the source of everything below]

## Exec Version
[Risk/decision-focused, minimal jargon, states if a decision is needed]

## Engineering Version
[Technical detail, specific blockers, specific asks]

## Customer Version (only if when-to-not-message-the-customer says to send one)
[Only what affects them]
```
