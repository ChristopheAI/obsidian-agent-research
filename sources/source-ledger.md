# Source Ledger

This file tracks sources inspected for Obsidian agent setup decisions.

| Date | Source | Type | Evidence grade | Why it matters | Follow-up |
|---|---|---|---|---|---|
| 2026-06-06 | `kepano/obsidian-skills` | GitHub repo | A | Syntax layer, by Obsidian CEO. 34.6k stars, MIT, last push 2026-05-24. 5 skills, no autonomous rewriting | Adopted (ADR-001) |
| 2026-06-06 | `breferrari/obsidian-mind` | GitHub repo | A | Persistent-memory framework. 2.8k stars, TS, v6.2.1. ShardMind + QMD + 5 hooks. Engineering/perf-review oriented (use-case mismatch) | Borrow lifecycle ideas only |
| 2026-06-06 | `eugeniughelbur/obsidian-second-brain` | GitHub repo | A | Self-rewriting vault (Karpathy LLM-Wiki). 2.2k stars, v0.10.0 "The Architect", 44 commands. Safeguards: raw/, sentinels | Extract safety rules (ADR-002) |
| 2026-06-06 | `breferrari/shardmind` | GitHub repo | A | Package manager behind obsidian-mind: 3-way-merge template upgrades | Reference if we ever template the vault |
| 2026-06-06 | Proudfrog "LLM Wiki Skeptics Guide" | Analysis blog | B | Hallucination-becomes-canon, self-lint fails; quotes Steph Ango's "separate vault" advice | Cited in FM-2, FM-6 |
| 2026-06-06 | Simon Spati "Keep AI Out of Your Vault" (ssp.sh) | Practitioner essay | B | Authorship contamination / AI slop; AI-as-retrieval stance | Cited in FM-1 |
| 2026-06-06 | dev.to/notoriouslab "AI as Retrieval, Not Generation" | Practitioner essay | B | Permanent authorship contamination; 3-layer container + rewrite-step mitigation | Cited in FM-1 |
| 2026-06-06 | Theo James "What the Setup Everyone's Building Can't Do" | Practitioner essay | B | Meaning drift on rewrites; folder-in/out, diff-first, do-not-edit guardrails | Cited in FM-3 |
| 2026-06-06 | systemsculpt "Gate Consequences" | Practitioner essay | B | "Gate consequences, not effort" - the mitigation framing for write autonomy | Cited in mitigations |
| 2026-06-06 | bagrounds.org "Catastrophic Vault Data Loss RCA" | Incident report | B | Real multi-year vault wipe via bidirectional sync on partial cache | Cited in FM-4 |
| 2026-06-06 | iansinnott/vibesidian (security notes) | GitHub repo | B | Prompt injection + hallucination risk when agent has vault write access | Cited in FM-5 |
| 2026-06-06 | phelps-sg/claude-code-obsidian-skills | GitHub repo | B | Alternative pattern: vault-before-code, /pkm, vault auditor | Compare if we design governance |
| 2026-06-06 | benenewton.com "Obsidian Skills" | Practitioner blog | C+ | Official skills *compose* with custom skills, not replace | Background |
| 2026-06-06 | kurtis-redux (Medium) | Practitioner blog | C+ | Lock-in caveat: skills funnel toward Anthropic platform; OpenCode works | Background |
| 2026-06-06 | vibecoding / claudeskills.info / gentic.news / ngjoo / sourcepulse | Aggregator/SEO | C | README restatements; used for facts only, not judgment | Ignore for decisions |
| 2026-06-06 | theaioperator.io (obsidian-second-brain author) | Author promo | C | Creator's own framing; bias-marked, kept out of risk analysis | Background |

### Exploration block (2026-06-06 hungry sweep)

| Date | Source | Type | Evidence grade | Why it matters | Follow-up |
|---|---|---|---|---|---|
| 2026-06-06 | Obsidian Bases syntax docs + changelog 1.12.4 | Official docs | A | Views/filters/formulas/summaries; drag-drop import, search, plugin API | Confirm exact .base syntax before writing |
| 2026-06-06 | Obsidian roadmap | Official | A | Kanban (~May 2026), Bases search, Bases API NOT yet shipped; multiplayer late 2026 | Watch for Bases API |
| 2026-06-06 | practicalpkm "Moving to Bases from Dataview" | Practitioner | B | Bases beats Dataview perf at 50k notes; migration path | Reference for H3 |
| 2026-06-06 | dev.to/rlschlesinger "Everything lives in Obsidian" | Practitioner | B | Real 8-Base solo "OS" (projects/tasks/CRM/revenue/content) | Pattern source |
| 2026-06-06 | wanderloots Bases project management | Practitioner | B | Per-note dashboards via `project contains this.file` | Pattern source |
| 2026-06-06 | Local REST API plugin (built-in MCP server) | Official plugin | A | In-app MCP server, bearer auth, surgical vault_patch; 3rd-party now optional | Evaluate as in-app access |
| 2026-06-06 | cyanheads/obsidian-mcp-server | GitHub repo | A | Folder scoping (READ/WRITE_PATHS) + READ_ONLY kill switch = safest write model | Candidate for safe write zone |
| 2026-06-06 | Official Obsidian CLI (obsidian.md/cli) | Official | A | 100+ cmds, native binary, "vault access without full-computer access" + headless sync | Sanctioned automation surface |
| 2026-06-06 | sokojh/obsidian-vault (`ov`) | GitHub repo | B | Agent-first CLI: JSON I/O, --dry-run, schema introspection | Compare to official CLI |
| 2026-06-06 | RAIT-09/obsidian-agent-client | GitHub repo | A | ACP brings Claude Code/Codex/Gemini inside Obsidian (~1937 stars) | Inspect access/security model |
| 2026-06-06 | OX Security MCP supply-chain; THN mcp-server-git RCE | Security report | A | Systemic MCP command-injection + prompt-injection RCE | Hard constraint on any MCP adoption |
| 2026-06-06 | Vinzent03/obsidian-git | GitHub repo | A | Auto commit-and-sync = atomic revertible rollback for agent edits | Set up before any write (H6) |
| 2026-06-06 | obsidian.md/clipper + kepano/defuddle | Official | A | Web Clipper uses Defuddle; `status: inbox` triage flow | Capture pipeline pattern |
| 2026-06-06 | st3v3nmw/spaced-repetition; whisper-obsidian-plugin | GitHub repos | A | FSRS spaced repetition; voice→transcribe→LLM cleanup | Optional capture add-ons |
| 2026-06-06 | obsidian.md/blog/json-canvas + spec | Official | A | MIT open format, multi-language libs = durable agent artifacts | Durability bet |
| 2026-06-06 | notes-automate.com Bases "review" 2026 | SEO | C | Claims SQLite/relations/rollups already ship — contradicts roadmap | Distrust; do not cite |

### X.com block (2026-06-06 intent-first sweep — see `x-sweep-2026-06-06.md`)

| Date | Source | Type | Evidence grade | Why it matters | Follow-up |
|---|---|---|---|---|---|
| 2026-06-06 | @kepano (from: search) | X / authority | A | "writing is thinking", anti-"second brain"; Obsidian user-supported, no VC | Watch for direction signals |
| 2026-06-06 | @nurijanian (160K views) | X / practitioner | B | Claude Code + Obsidian PM stack; context 15min→<1min; validates tobi/qmd | QMD is real retrieval tool |
| 2026-06-06 | @Artifexx / Ilya Shabanov (34K) | X / practitioner | B | Bases > Notion; video of academic Papers-by-Year base | Bases-for-research pattern |
| 2026-06-06 | @kpmdev Kyle McDonald | X / practitioner | B | Self-hosted scoped MCP on homelab, "talk to vault from Claude on the go" | Supports H5 |
| 2026-06-06 | @cyrilXBT, @Atenov_D | X / influencer | C | "Obsidian = JARVIS in 1h"; "manual vault dies in a week" — dominant hype | Discount; capability signal only |
| 2026-06-06 | X contrarian lens (slop/regret/abandoned) | X / meta | C | Barren of real critique; keywords surface pro-AI marketing | Do NOT source failure modes from X |
| 2026-06-06 | @cyrilXBT "Second Brain that connects every idea" (X Article) | X / build guide | B | Concrete guide; `05-INTELLIGENCE` AI-output quarantine = clean FM-1 fix | Drove ADR-003; see source note |
| 2026-06-03 | @cyrilXBT "Set Up Obsidian From Scratch" (X Article, 111K views) | X / build guide | B | Radical minimalism: "not to capture everything; think better." Same author's simple post out-reaches his maximalist one 3:1 | Counterweight to over-building; see source note |
| 2026-05-30 | @cyrilXBT "Replaced my $500/month stack" (X Article, 306K views) | X / build guide | B | His most-viewed; keystone = the weekly review ("covers everything" = a ritual, not a machine). View gradient 306K/111K/39K as AI/complexity rises | See source note; converges w/ our research |

## Evidence Grades

- A: primary source, code/docs/repo, directly inspectable
- B: practitioner walkthrough with concrete workflow or artifacts
- C: hype, marketing, or weakly evidenced post

