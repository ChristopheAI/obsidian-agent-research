# Obsidian Agent Research

Research and decision repository for building Christophe's Obsidian setup as an agent-operable knowledge system.

The goal is not to collect every Obsidian + AI idea. The goal is to decide, with evidence, which capabilities Christophe and Codex should actually use.

## Scope

This repo tracks:

- Obsidian agent capabilities from GitHub, X, YouTube, docs, and practitioner posts
- ADRs for what to adopt, adapt, reject, or revisit
- Source notes and evidence quality
- Recursive improvement loops for Christophe's `MyCVHVault`
- Implementation plans before anything touches the real vault

This repo does not store private vault content by default. It stores decisions, public source summaries, and implementation guidance.

## Working Rule

Adopt the smallest capability that improves retrieval, continuity, or decision quality without turning the vault into an opaque auto-rewriting system.

## Repository Map

- `docs/capability-map.md` - what Obsidian can do today for agents
- `docs/adr-framework.md` - decision filter and recursive improvement loop
- `docs/current-hypotheses.md` - live hypotheses to test
- `adrs/` - accepted/proposed architectural decision records
- `sources/` - source ledger and source notes
- `research-queue.md` - what to inspect next from X, YouTube, GitHub, and docs
- `recursive-improvement-log.md` - what changed in our understanding over time

## Evidence Rules

- GitHub repos and official docs outrank X hype.
- X posts are practitioner signals, not final proof.
- YouTube videos are useful when they show workflows, screens, commands, or failures.
- Claims about current tooling need dates.
- Any proposed vault write behavior needs a rollback path.

