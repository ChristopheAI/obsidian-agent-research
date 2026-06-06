# Obsidian Agent Capability Map

Last updated: 2026-06-06

## Capability Classes

| Capability | What it enables | Evidence so far | Current stance |
|---|---|---|---|
| Obsidian Markdown skills | Agents write valid wikilinks, properties, embeds, callouts | `kepano/obsidian-skills` | Adopt |
| Obsidian Bases | Dashboard/query views over notes (table/cards/list/map, formulas, summaries, groupBy). Core plugin since 1.9. Beats Dataview perf at scale. Agent-writable `.base` YAML | `kepano/obsidian-skills`, Obsidian docs/changelog, exploration-2026-06-06 | Adopt as dashboard layer (H3) |
| JSON Canvas | Agent-created system maps and visual flows. MIT open format, multi-language libs | `kepano/obsidian-skills`, JSON Canvas spec | Adapt narrowly |
| Obsidian CLI | Official, v1.12+ native binary, 100+ commands. Markets "vault access without full-computer access" + headless sync. The sanctioned automation surface | obsidian.md/cli, `kepano/obsidian-skills` | Evaluate as primary access surface |
| Defuddle | Web-to-markdown extraction (powers official Web Clipper); `status: inbox` triage flow | `kepano/obsidian-skills`, obsidian.md/clipper | Adopt for source ingest |
| QMD semantic search | Meaning-based retrieval over vault notes | `breferrari/obsidian-mind` | Evaluate after basic retrieval map |
| MCP / Local REST API | Tool-level read/write/search access. Local REST API now ships a built-in MCP server; cyanheads server adds folder scoping + READ_ONLY kill switch (safest). Ecosystem has real command-injection/prompt-injection risks | exploration-2026-06-06, cyanheads, OX Security | Evaluate; scoped + read-only first |
| Git rollback (Obsidian Git) | Auto commit-and-sync: every agent edit is an atomic, revertible commit. The rollback substrate | Vinzent03/obsidian-git, exploration-2026-06-06 | Adopt before any write (H6) |
| Session lifecycle hooks | Startup context, message classification, write validation, wrap-up | `breferrari/obsidian-mind` | Adapt after policies exist |
| AI-first note rules | Self-contained notes for future agents | `obsidian-second-brain` | Adapt selectively |
| Self-rewriting vault | Sources rewrite existing pages, reconcile contradictions | `obsidian-second-brain` | Postpone |
| Scheduled agents | Nightly/weekly maintenance and synthesis | `obsidian-second-brain`, `obsidian-mind` | Postpone |

## Working Interpretation

The first useful system for Christophe is not a full autonomous second brain. It is an agent-operable Obsidian OS:

```text
Capture -> Source -> Topic -> Decision -> Project Memory -> Agent Retrieval -> Write-back
```

The first build should make this flow explicit, searchable, and safe.

## Confirmed facts (2026-06-06 deep pass)

Hard data pulled from the repos directly, not from summaries:

| Repo | Stars | Lang | Latest | Last push | Nature |
|---|---|---|---|---|---|
| `kepano/obsidian-skills` | ~34.6k | (md) | 5 skills | 2026-05-24 | Format layer only. No autonomous writing. Lowest risk. |
| `breferrari/obsidian-mind` | ~2.8k | TS | v6.2.1 | 2026-06-02 | Persistent memory + 5 lifecycle hooks + QMD (MCP semantic search) + ShardMind package manager. |
| `eugeniughelbur/obsidian-second-brain` | ~2.2k | Python | v0.10.0 | 2026-06-05 | 44 commands, self-rewriting vault, optional paid API keys. |

Two structural findings:

- **These are two categories, not three rivals.** kepano is a *format layer*;
  the other two are *operating frameworks* that should sit on top of it.
- **`obsidian-mind` is engineering / performance-review oriented** (competency
  notes, 1:1s, brag-docs, incident timelines, PR scans). That is a use-case
  mismatch for MyCVHVault (personal / legal / medical / career). Borrow its
  architecture ideas (`brain/` memory, SessionStart context injection,
  "a note without links is a bug"), not its domain modules.

- **Emerging signal:** all three repos received "Hermes Agent" integration
  requests - a new agent CLI worth watching, not acting on yet.

## Agent knowledge calibration (must verify, do not recall)

Honest limits of the agent's own Obsidian knowledge, so future sessions verify
instead of guessing:

- Solid: OFM syntax (wikilinks, callouts, properties, embeds), PKM methods,
  vault model.
- Thin / possibly stale (cutoff Jan 2026): exact `.base` syntax, Obsidian CLI
  commands and version-feature mapping. **Write these against the kepano skill
  or live docs, never from memory.**
- Not pre-existing knowledge (learned this session): QMD, ShardMind, defuddle
  internals, the three repos.

