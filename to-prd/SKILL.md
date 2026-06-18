---
name: to-prd
description: Turn the current conversation into a Product Requirements Document (PRD) and write it to a markdown file — no interview, just synthesis of what you've already discussed. Pairs well after a "grill my idea" session.
disable-model-invocation: true
---

This skill takes the current conversation context and produces a PRD as a markdown file. It is product/idea oriented, not code oriented — use it for a business idea, feature, product, plan, or design. For an engineering-ready PRD (codebase seams, issue tracker, testing decisions), use `to-prd-dev` instead.

Do NOT interview the user. Synthesize what you already know from the conversation. This skill assumes the thinking has already happened — typically via the `grill-my-idea` skill or an equivalent discussion — so your job is to capture decisions, not to make new ones.

## Process

1. Re-read the conversation and pull together every decision, constraint, assumption, and open question that surfaced. If `grill-my-idea` was run, the resolved decision tree is your primary source.

2. Where the conversation settled a question, record the answer. Where it deliberately left something open, record it under **Open Questions** rather than inventing an answer. Do not introduce decisions that were never discussed.

3. Write the PRD using the template below to a markdown file in the working directory (e.g. `PRD.md`, or a descriptive name like `<feature>-prd.md` if a more specific one fits). Then briefly point the user to the file and summarize what's still open.

<prd-template>

# <Title>

## Summary

A short paragraph: what this is and why it matters, in plain language.

## Problem Statement

The problem being solved, from the user's perspective. Who has it, when, and why it hurts.

## Goals

What success looks like. A bulleted list of the outcomes this should achieve.

## Non-Goals

What this explicitly does NOT try to do. Keeps scope honest.

## Target Users

Who this is for. Segments, personas, or roles, with what each one needs.

## Solution Overview

The proposed solution from the user's perspective. Describe the experience and the key pieces, not the implementation.

## User Stories

A LONG, numbered list of user stories covering all aspects of the product. Each in the format:

1. As an <actor>, I want a <feature>, so that <benefit>

<user-story-example>
1. As a mobile bank customer, I want to see the balance on my accounts, so that I can make better informed decisions about my spending
</user-story-example>

## Key Decisions

The decisions reached during the discussion and the reasoning behind each. This is the heart of the PRD — capture the "why", not just the "what", so the rationale survives.

## Success Metrics

How you'll know it's working. Concrete, measurable signals where possible.

## Risks & Assumptions

Assumptions the plan rests on, and the risks if they're wrong.

## Out of Scope

Things deliberately excluded from this PRD.

## Open Questions

Questions raised but not resolved. Be honest here — an empty section is fine only if nothing is genuinely open.

</prd-template>
