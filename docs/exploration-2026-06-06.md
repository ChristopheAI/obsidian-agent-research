# Exploration Digest — 2026-06-06

Hungry-curiosity sweep of "what can be / is being done with Obsidian" beyond the
three reference repos. Four parallel research agents (web/exa/GitHub). X.com not
covered this pass — the Chrome extension was not connected (see Gaps).

Evidence grades: A = official docs/repo/changelog; B = practitioner walkthrough
with concrete artifacts; C = hype/SEO/anecdote.

---

## Theme 1 — Bases is far more capable than this repo assumed

Bases shipped in Obsidian **1.9** (mid-2025) and is now a **core plugin**. Every
note with frontmatter is a row; `.base` files (YAML) hold filters, formulas,
summaries, views. Cells edit in place and write back to YAML.

- Views: table, cards, list, **map**; filters (global + per-view, AND); JS-like
  formulas; summaries (sum/avg/count); groupBy. (A — official syntax docs)
- 1.12.4 (Feb 2026): drag-drop import into Bases, search toolbar, row context
  menu, plugin view API. (A — changelog)
- **Performance beats Dataview** at 50k notes, especially mobile. (B — practicalpkm)
- Real builds people ship: solo-founder "OS" of 8 linked Bases (projects/tasks/
  CRM/revenue/content); People CRM with pipeline Kanban; agile project tracker
  (projects→epics→stories→tasks via `project contains this.file`); reading/media
  trackers; academic paper tracking with formula columns. (B)
- kepano's `obsidian-bases` Agent Skill generates spec-valid `.base` files; the
  YAML+JS syntax is LLM-friendly, so agents can author dashboards directly. (A)
- Limits vs Dataview: no inline `key::value`, no task/checkbox rollups across
  notes, no calendar/progress widgets; rows are always whole files. (B)
- Roadmap (NOT yet shipped): Kanban view (~May 2026), Bases search, Bases API. (A)
- ⚠️ Distortion: a 2026 "review" claims SQLite backend + relations/rollups/Kanban
  already ship — unverified, contradicts the official roadmap. Treat as C.

**Impact:** upgrades `H3`. Bases is a real, agent-writable, git-friendly dashboard
layer for MyCVHVault. The discipline shifts to clean, consistent frontmatter.

## Theme 2 — A whole MCP / programmatic-access landscape now exists

This is new ground for the repo (capability map had MCP as "revisit later").

- **Local REST API plugin now ships a built-in MCP server** — third-party servers
  "no longer necessary"; runs inside Obsidian, bearer-token auth, ~17 tools incl.
  surgical `vault_patch`. (A)
- **cyanheads/obsidian-mcp-server** (~577★, v3.2.4 2026-06): standout security —
  `OBSIDIAN_READ_PATHS`/`WRITE_PATHS` folder scoping + `OBSIDIAN_READ_ONLY` kill
  switch; refuses whole-file overwrite by default. Safest model seen. (A)
- **Official Obsidian CLI (v1.12+, native binary since 1.12.7, Mar 2026)**: 100+
  commands, IPC to a running app, autocompletion. Marketed explicitly as a way to
  "give agentic tools access to a vault without access to your full computer" +
  headless sync. The sanctioned automation surface. (A)
- **sokojh/obsidian-vault (`ov`)**: agent-first CLI — JSON-only I/O, `--dry-run`,
  schema introspection, path-traversal blocking. Cleanest scripted-agent safety. (B)
- **RAIT-09/obsidian-agent-client** (~1937★, 2026-04): Agent Client Protocol (Zed's
  ACP) brings Claude Code / Codex / Gemini CLI *inside* Obsidian. Most-starred. (A)
- Other servers vary: StevenStavrakis/obsidian-mcp (full CRUD, README says "backup
  your vault"), bitbonsai/mcpvault (path/symlink guards), yanxue06 (graph-aware,
  safe rename + backlink rewrite). (B)
- **Security warnings (real):** systemic STDIO MCP command-injection across the
  ecosystem (OX Security); RCE via prompt injection in Anthropic's mcp-server-git
  (The Hacker News, 2026-01); hardcoded creds in MCP configs. (A)

**Impact:** gives concrete answers for any future "safe write zone" ADR. Safest
model = **folder-scoped + read-only-by-default + dry-run + diff approval**.
Riskiest = CLI-subprocess agents with `--dangerously-skip-permissions` / YOLO.

## Theme 3 — Automation & the rollback substrate

- **Obsidian Git** (auto commit-and-sync): every agent edit becomes an atomic,
  revertible commit with history + diff views. This is the strong rollback the
  repo's guardrails require. Pair with a remote for off-site backup. (A)
- Defense-in-depth: combine git history with Syncthing `.stversions` or Obsidian
  Sync version history — two independent recovery paths. (B)
- Capture: official Web Clipper uses **Defuddle** (kepano) → clean markdown with
  `status: inbox` frontmatter → triage surface. Late-2025 Clipper also saves
  ChatGPT/Claude chats. (A)
- Voice: Whisper plugin (record→transcribe→LLM cleanup); local-Whisper for offline. (A)
- Spaced repetition plugin now ships FSRS + SM-2; markdown→Anki sync. (A)

**Impact:** directly satisfies the rollback requirement in `H4`/`ADR-002`. Git is
the precondition for ever allowing agent writes.

## Theme 4 — Direction signal: Obsidian is becoming an agent substrate

- The official posture is **open files + CLI + published Skills**, not an in-app
  "Ask AI" button (kepano deliberately rejected the latter). Agents read/write
  Markdown / `.base` / JSON Canvas directly. (A)
- JSON Canvas is an MIT open format with libraries in C/Dart/Go/Python/React/Rust/
  TS — durability bet for agent-generated artifacts. (A)
- Roadmap: real-time "multiplayer" collaboration expected late 2026. (B)
- Notable gap: **no first-party local inference** yet — AI stays external
  (Claude Code etc.). Privacy/cost remain the user's responsibility.

**Impact:** building around open formats + the CLI (not a plugin API) is the
durable bet. This validates the repo's whole premise.

---

## What this changes

- `H3` strengthened: Bases is the dashboard layer. Prototype a read-only `.base`.
- New `H5`: the safe agent access model is a folder-scoped MCP server or the
  official CLI with dry-run — not raw filesystem, not YOLO subprocess.
- New `H6`: Obsidian Git is the rollback substrate; set it up before any write.
- Capability map updated: Bases (Adopt-as-dashboard), MCP/REST/CLI (concrete
  options + safest model), git rollback.

## Gaps (honest)

- **X.com not covered.** The Chrome extension was not connected, so live X
  practitioner signal (the skill's mandated platform path) is missing this pass.
  Re-run once Chrome is paired.
- Most findings are README/changelog/walkthrough level; no long-term reliability
  data on the newer MCP servers.

## Sources

See `sources/source-ledger.md` (2026-06-06 exploration block).
