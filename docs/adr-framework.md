---
title: Obsidian Agent ADR Framework
date: 2026-06-06
status: draft
scope: Christophe MyCVHVault Obsidian agent setup
---

# Obsidian Agent ADR Framework

This document is the working decision filter for choosing what Christophe and Codex should adopt from current Obsidian agent systems.

It exists because the Obsidian + AI topic has too much signal, hype, and implementation surface to decide from vibes. Every candidate capability must pass through an ADR-style filter before it becomes part of Christophe's vault operating system.

## Source Inputs

- GitHub: `kepano/obsidian-skills`
- GitHub: `breferrari/obsidian-mind`
- GitHub: `eugeniughelbur/obsidian-second-brain`
- Local vault: `/Users/christophe/Documents/MyCVHVault`
- X bookmarks and live X search as practitioner-signal, not as final authority

## Core Decision Rule

Adopt the smallest capability that improves retrieval, continuity, or decision quality without turning the vault into an opaque auto-rewriting system.

Default stance:

- Adopt explicit file-format knowledge.
- Adapt lifecycle and retrieval patterns.
- Reject or postpone autonomous rewriting until trust and rollback exist.
- Prefer human-owned final decisions over agent-owned synthesis.

## ADR Template

```markdown
# ADR-NNN - <Decision title>

## Status

Proposed | Accepted | Superseded | Rejected

## Context

- What problem triggered this?
- What existing vault rule or pain does it touch?
- What evidence was checked?

## Options

1. <Option A>
2. <Option B>
3. <Option C>

## Decision

We will <chosen option>.

## Why

- <reason>
- <reason>
- <reason>

## Consequences

Positive:
- <benefit>

Negative:
- <cost or risk>

## Guardrails

- <write boundary>
- <review rule>
- <rollback path>

## Recursive Improvement Trigger

Revisit this ADR when:
- <observable failure>
- <new capability appears>
- <usage threshold is reached>

## Sources

- <repo/file/url>
- <local note>
```

## Recursive Improvement Loop

1. Observe: What failed, felt slow, duplicated work, or caused retrieval noise?
2. Classify: Is this a capture, retrieval, write-back, synthesis, or governance problem?
3. Compare: Which reference system has the smallest useful pattern for that class?
4. Decide: Write or update an ADR.
5. Implement: Change one layer only.
6. Verify: Try a real workflow, not a demo.
7. Preserve: Promote durable lessons to `04 Decisions` or `02 Topics`; leave experiments in project notes.

## Evaluation Axes

Score each candidate 0-3.

| Axis | 0 | 1 | 2 | 3 |
|---|---|---|---|---|
| Retrieval value | no help | minor | useful | core |
| Write safety | risky | unclear | manageable | safe by design |
| Fit with MyCVHVault | conflicts | needs rewrite | adapts | native fit |
| Setup cost | high | medium | low | already present |
| Reversibility | hard | partial | easy | no lock-in |
| Human ownership | agent-owned | mixed | human-reviewed | human-owned |

Adopt immediately only if total score is high and write safety is at least 2.

