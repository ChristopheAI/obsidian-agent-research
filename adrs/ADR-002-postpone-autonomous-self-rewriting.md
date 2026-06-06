# ADR-002 - Postpone Autonomous Self-Rewriting

## Status

Proposed

## Context

`obsidian-second-brain` promotes a self-rewriting vault where sources update existing pages, contradictions reconcile, and scheduled agents maintain the system.

Christophe's current vault rules say core syntheses and final decisions remain human-owned. MyCVHVault also already has a large intake surface in `00 Discoveries`.

## Options

1. Adopt autonomous rewriting now.
2. Reject autonomous rewriting permanently.
3. Postpone and borrow only specific safety and note-quality rules.

## Decision

Postpone autonomous rewriting and adopt only selected safety patterns for now.

## Why

- Self-rewriting can silently corrupt meaning if retrieval, confidence, and rollback are weak.
- Christophe's current rules favor human-owned final decisions.
- More automation before promotion gates are visible may increase noise.

## Consequences

Positive:

- Lower risk of vault drift.
- Keeps human judgment central.
- Still lets us borrow useful rules like source URLs, confidence, and anti-fabrication.

Negative:

- Less immediate automation.
- More manual review in early phases.

## Guardrails

- No scheduled agent writes until there is a reviewed write policy.
- No rewrite of existing Topics or Decisions without explicit review.
- Experiments write to Agent Drafts or project notes first.

## Recursive Improvement Trigger

Revisit when:

- Safe write zones exist.
- Backups/rollback are proven.
- A narrow rewrite workflow succeeds on test material.

## Sources

- https://github.com/eugeniughelbur/obsidian-second-brain
- https://github.com/eugeniughelbur/obsidian-second-brain/blob/main/references/ai-first-rules.md

