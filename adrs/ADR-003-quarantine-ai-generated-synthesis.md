# ADR-003 - Quarantine AI-Generated Synthesis in a Dedicated Folder

## Status

Proposed

## Context

`failure-modes.md` FM-1 (authorship contamination) is the highest-relevance risk
for MyCVHVault: once AI-written prose is mixed into human thinking notes, you can
no longer tell which is which, and it cannot be cleanly removed. Steph Ango's own
advice is to keep AI output in a separate space (FM-6).

The CyrilXBT build guide (`sources/cyrilxbt-second-brain-guide.md`) demonstrates a
concrete pattern that implements exactly this: a dedicated `05-INTELLIGENCE/`
folder holding `connection-reports/`, `syntheses/`, and `patterns/` — all
agent-generated, none mixed into human-written permanent notes.

## Options

1. Let the agent write synthesis directly into Topics/Decisions (rejected by ADR-002).
2. Forbid AI-generated synthesis entirely.
3. Quarantine all agent-generated synthesis in a dedicated, regeneratable folder;
   keep human notes human-owned.

## Decision

Adopt option 3: a dedicated AI-output folder (e.g. `09 Agent Output/` with
`connection-reports/`, `syntheses/`, `patterns/`). Treat it as a regeneratable
cache, not a source of truth.

## Why

- Structurally solves FM-1: provenance is obvious by location.
- Matches Steph Ango's guidance (FM-6) and the "regeneratable cache" mitigation.
- Unblocks the SAFE read-only intelligence workflows (connection finder, synthesis,
  pattern detector, question answerer, contradiction detector) without risking the
  human knowledge layer.

## Consequences

Positive:

- Christophe can use agent synthesis without contaminating Topics/Decisions.
- The folder can be deleted and rebuilt anytime trust drops.

Negative:

- One more folder to keep tidy; agent outputs can pile up if not reviewed.
- Insight that proves durable must be deliberately promoted (human-rewritten) into
  `02 Topics` — by design, not automatically.

## Guardrails

- Agent writes synthesis ONLY into the quarantine folder.
- Promotion from quarantine into `02 Topics` / `04 Decisions` is a human,
  rewrite-in-own-words step (the friction is the point).
- The folder is git-tracked so every agent output is revertible (depends on H6).
- Never let an agent edit `02 Topics` or `04 Decisions` directly (do-not-edit list).

## Recursive Improvement Trigger

Revisit when:

- The quarantine folder is never reviewed (then the workflow is not earning its keep).
- A narrow, reviewed write-into-Topics workflow proves safe (may relax the rule).
- Bases can surface a "promotion queue" view over the quarantine folder.

## Sources

- `sources/cyrilxbt-second-brain-guide.md`
- `docs/failure-modes.md` (FM-1, FM-6)
- https://x.com/cyrilXBT/status/2063073652925505632
