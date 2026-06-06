# Current Hypotheses

Last updated: 2026-06-06

## H1 - MyCVHVault already has the right core ontology

The existing folders `00 Discoveries`, `06 Sources`, `02 Topics`, `04 Decisions`, and `03 Projects` map well to the desired flow. A repo template replacement is probably unnecessary.

Status: active

Needs evidence:

- Inspect whether frontmatter/properties are consistent enough for Bases.
- Test retrieval from current notes without semantic search.

## H2 - The first missing layer is governance, not content

The vault already contains many sources and decisions. The missing layer is root-level agent policy: what to read first, where to write, what not to touch, and when to promote.

Status: active

Needs evidence:

- Try one task with and without root `AGENTS.md`.
- Measure whether retrieval improves.

## H3 - Bases can become the practical dashboard layer

Bases may expose promotion queues, source status, active projects, and decisions without adopting Notion or adding heavy tooling.

Status: strengthened (2026-06-06) - see `docs/exploration-2026-06-06.md`

Evidence found:

- Bases is a core plugin since 1.9 with table/cards/list/map views, formulas,
  summaries, groupBy; outperforms Dataview at 50k notes.
- Real practitioners run multi-Base "operating systems"; kepano's skill generates
  valid `.base` files, so an agent can author dashboards directly.
- Caveat: no task/checkbox rollups or calendar widgets yet; Kanban/API are roadmap.

Still needs:

- Create a read-only prototype `.base` over Sources/Topics/Decisions.
- Verify frontmatter is consistent enough to filter on.

## H5 - The safe agent access model is scoped, not raw filesystem

The right way to let an agent touch the vault is a folder-scoped MCP server (e.g.
cyanheads with READ/WRITE_PATHS + READ_ONLY) or the official Obsidian CLI with
`--dry-run`, never raw filesystem access or a YOLO subprocess.

Status: active (new 2026-06-06)

Needs evidence:

- Compare official CLI vs a scoped MCP server for our workflow.
- Confirm scoping keeps private folders (e.g. `01 Daily`) out of agent reach.
- Test prompt-injection resistance with an adversarial note.

## H6 - Obsidian Git is the rollback substrate

Auto commit-and-sync makes every agent edit an atomic, revertible commit. This is
the precondition the guardrails in `ADR-002` / `failure-modes.md` require before
any write autonomy is allowed.

Status: active (new 2026-06-06)

Needs evidence:

- Decide: git on MyCVHVault directly, or a backup/mirror? (vault has private content)
- Verify auto-commit cadence does not fight Obsidian Sync / iCloud.

## H4 - Autonomous self-rewriting is too risky for phase 1

The self-rewriting vault concept is powerful but conflicts with Christophe's preference that final topics and decisions remain human-owned.

Status: strengthened (2026-06-06)

Evidence found - see `docs/failure-modes.md`:

- Practitioner failure modes confirmed: authorship contamination (FM-1),
  hallucination-becomes-canon with self-lint that cannot catch it (FM-2),
  meaning drift on rewrites (FM-3), catastrophic sync data loss (FM-4),
  prompt injection via note content (FM-5).
- Steph Ango (Obsidian CEO) himself advises keeping AI content in a separate
  vault (FM-6).

Rollback requirements for any future rewrite system (acceptance criteria):

- Git versioning + proven backup before any autonomous write.
- Deletion circuit breaker (abort if file count drops below threshold).
- Untrusted-content handling for ingested adversarial documents.
- Diff-first + do-not-edit list for `02 Topics` and `04 Decisions`.

