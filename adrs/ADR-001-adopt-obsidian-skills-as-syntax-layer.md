# ADR-001 - Adopt Obsidian Skills as Syntax Layer

## Status

Proposed

## Context

Christophe wants Codex and other agents to understand Obsidian as more than loose markdown files.

The `kepano/obsidian-skills` repository provides agent skills for Obsidian Markdown, Bases, JSON Canvas, Obsidian CLI, and Defuddle. The repo states compatibility with Claude Code and Codex CLI.

## Options

1. Ignore agent skills and rely on generic markdown behavior.
2. Adopt `kepano/obsidian-skills` as a syntax/capability layer.
3. Install a full second-brain system that includes its own rules and commands.

## Decision

Adopt `kepano/obsidian-skills` as the syntax layer.

## Why

- It teaches agents Obsidian-specific file formats without taking over vault governance.
- It directly covers the capabilities Christophe is exploring: Markdown, Bases, Canvas, CLI, web extraction.
- It is lower risk than adopting a full autonomous vault framework.

## Consequences

Positive:

- Agents can write better Obsidian-native files.
- Future Bases and Canvas work becomes less fragile.

Negative:

- Skills do not solve governance, retrieval, or write policy by themselves.

## Guardrails

- MyCVHVault local rules remain higher authority.
- Use skills for syntax and file formats, not for deciding what belongs in the vault.
- Do not modify `.obsidian/` config unless explicitly required and reviewed.

## Recursive Improvement Trigger

Revisit when:

- Codex gains native Obsidian support.
- The skills change materially.
- We find that Bases/Canvas output does not render correctly.

## Sources

- https://github.com/kepano/obsidian-skills

