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

## Evidence Grades

- A: primary source, code/docs/repo, directly inspectable
- B: practitioner walkthrough with concrete workflow or artifacts
- C: hype, marketing, or weakly evidenced post

