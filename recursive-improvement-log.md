# Recursive Improvement Log

## 2026-06-06

Initial learning:

- The container should be a GitHub repo, not loose `.md` files.
- The core work is not "install a second brain"; it is building a decision system for what to adopt.
- `kepano/obsidian-skills` looks safe as a syntax layer.
- `obsidian-mind` is useful as lifecycle inspiration.
- `obsidian-second-brain` contains powerful safety rules and commands, but broad self-rewriting is not phase-1 safe.

Next improvement:

- Push this repo to GitHub.
- Continue with GitHub source inspection.
- Add source notes for X posts and YouTube videos only when they change a decision.

## 2026-06-06 (deep pass, Claude Opus 4.8)

Second, deeper pass over the same three repos plus practitioner channels.

What changed in our understanding:

- The three repos are **two categories**, not three rivals: kepano is a format
  layer; the other two are operating frameworks that sit on top of it. This
  reframes the whole comparison.
- **`obsidian-mind` is a use-case mismatch**: it is built for software-engineering
  performance reviews (competencies, 1:1s, brag-docs). Borrow architecture, not
  domain modules. This was not visible from the first pass.
- **H4 is now evidence-backed**, not just a preference. Added
  `docs/failure-modes.md` with six named failure modes (incl. Steph Ango's own
  "separate vault" advice). This is the biggest gap the first pass left open.
- Added hard facts (stars, versions, activity) to `docs/capability-map.md` and
  real practitioner sources to `sources/source-ledger.md`.
- Added `docs/folder-conventions.md` - supports H1 (no folder restructure needed;
  the missing layer is governance, per H2).
- Recorded the agent's own knowledge limits in `capability-map.md`: `.base`
  syntax and Obsidian CLI must be verified against the skill/docs, never recalled.

Next improvement:

- Promote ADR-001 and ADR-002 from Proposed to Accepted (decision is Christophe's).
- Code-level inspection of obsidian-mind hooks and obsidian-second-brain safety
  command prompts (see research-queue).
- Confirm whether autonomous write is even wanted, or only better human-owned
  write-back. That single answer sets the phase-2 scope.

## 2026-06-06 (hungry exploration sweep)

Broad sweep beyond the three repos: four parallel research agents on Bases,
MCP/agent access, automation, and novel/2026 uses. See `docs/exploration-2026-06-06.md`.

What changed:

- **Bases is much stronger than assumed** - core plugin, real multi-Base "OS"
  builds, agent-writable. H3 upgraded from "active" to "strengthened".
- **A real MCP/access landscape exists** - the repo had this as "revisit later".
  Now we have concrete, security-graded options: built-in Local REST API MCP
  server, cyanheads scoped server (safest), official CLI as sanctioned surface.
  Added H5 (scoped access model).
- **Found the rollback substrate**: Obsidian Git. Added H6 (set up before writes) -
  this unblocks the precondition that ADR-002 / failure-modes.md require.
- **Direction confirmed**: Obsidian is positioning as an agent *substrate* (open
  files + CLI + Skills), validating this repo's premise.
- Real security warnings logged (MCP command-injection, git MCP RCE) - hard
  constraints on any MCP adoption.

Gap / honesty:

- X.com was NOT covered - Chrome extension not connected, so the skill's mandated
  X path is missing. Queued for re-run once paired.

Next improvement:

- Decide git strategy for MyCVHVault (H6) - the gate to any write experiment.
- Prototype a read-only `.base` (H3) and compare CLI vs scoped MCP (H5).

## 2026-06-06 (X.com sweep, intent-first)

Live logged-in X sweep — see `sources/x-sweep-2026-06-06.md`.

Method correction (from Christophe): a first keyword + shallow-scroll pass caught
almost nothing. Redone intent-first: queries derived from the decision + evidence
lenses, using X operators (`from:`, `min_faves:`, `f=top`) to surface high-utility
posts and cut hype. This is the standard for X going forward.

What changed:

- **QMD validated** by a serious independent practitioner (@nurijanian, 160K views) -
  strengthens the "evaluate QMD" line. Tobi Lütke's tool.
- **kepano (authority) reinforces our stance**: "writing is thinking", anti
  "second brain" - supports keeping synthesis human-owned (FM-1).
- Obsidian = independent, user-supported, principled - durable substrate.
- Self-hosted **scoped MCP on a homelab** is a real working pattern (H5).
- The popular shared vault template on X ≈ MyCVHVault (numbered-prefix hybrid).

Evidence-rule learning:

- **X is a capability-discovery sensor, not a risk sensor.** It is overwhelmingly
  promotional; even critique keywords surface marketing. Source failure modes from
  blogs/Reddit, never X. (Added as an explicit rule below.)

