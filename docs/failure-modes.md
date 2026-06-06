# Failure Modes: AI Writing Into a Personal Vault

Last updated: 2026-06-06
Evidence pass: deep (Claude Opus 4.8 session)

This is the evidence base for `ADR-002` and hypothesis `H4`. It catalogs how
agent-driven vault writing fails in practice, with named sources. Every mode
here is a reason to keep final Topics and Decisions human-owned and to gate
autonomous rewriting behind rollback.

The throughline: the danger is not bad output you can see. It is plausible
output you cannot later distinguish from your own thinking.

## The modes

### FM-1 - Authorship contamination
After months, you can no longer tell which notes are your thinking and which are
AI summaries. The contamination is described as effectively permanent: you
cannot cleanly subtract AI prose back out of a vault once it is mixed in.
- Evidence: Simon Späti "Keep AI Out of Your Vault" (B); dev.to/notoriouslab
  "AI as Retrieval, Not Generation" (B)
- Why it matters here: MyCVHVault is Christophe's actual thinking, not a cache.
  This is the single most relevant risk.

### FM-2 - Hallucination becomes canon, and self-lint cannot catch it
A fabricated cross-reference does not get labeled "hallucination" once written.
It becomes a line in your notes. The lint/reconcile pass meant to catch it runs
on the *same class of model* that produced it, so it certifies its own errors.
Citation precision is unsolved: an LLM-compiled wiki has no reliable
"page 47, paragraph 3" traceback.
- Evidence: Proudfrog "LLM Wiki Skeptics Guide" (B)

### FM-3 - Meaning drift on rewrites
Rewrites quietly change semantics: a "maybe" becomes a "decision"; two distinct
projects with similar names ("Website Refresh" vs "Website Redesign") get merged
into one coherent narrative that never existed. The output reads clean and is
wrong.
- Evidence: Theo James "What the Setup Everyone's Building Can't Do" (B)

### FM-4 - Catastrophic data loss via automated sync
A scheduled automation wiped a multi-year vault: bidirectional sync on a partial
local cache interpreted missing files as deletions and propagated them. Sync is
not backup. No file-count circuit breaker existed.
- Evidence: bagrounds.org "Catastrophic Vault Data Loss RCA" (B)
- Mitigation requirement: git versioning + real backup before any autonomous
  write; a "too many deletions, abort" guard for any scripted vault operation.

### FM-5 - Prompt injection through note content
An agent with write access treats note bodies as part of its prompt. Malicious
text inside a note ("ignore all previous instructions...") can hijack it.
- Evidence: iansinnott/vibesidian security notes (B)
- Why it matters here: Christophe ingests adversarial documents (counterparty
  invoices, legal letters) into the vault. Their text can reach the agent.

### FM-6 - The tool author's own warning
Steph Ango (Obsidian co-creator / CEO, author of `kepano/obsidian-skills`)
advises keeping AI-generated content in a *separate vault* so the AI can "make a
mess in their own space." The person who designed Obsidian's markdown is saying
the output is not yet trustworthy enough to mix with real notes.
- Evidence: quoted in Proudfrog (B); consistent with the "files over apps" stance

## Mitigations that practitioners actually use

- **Gate consequences, not effort** (systemsculpt): let the agent run free on
  reversible local work (search, draft edits); hard-stop before irreversible or
  outward actions.
- **Additive over rewrite + diff-first + do-not-edit list** (Theo James):
  never rewrite daily/meeting notes; append only; review every diff.
- **Separate container + mandatory rewrite step** before anything enters the
  core vault (dev.to/notoriouslab). The friction of rewriting in your own words
  is where the value is.
- **Git versioning + periodic backup** (Time Machine / Syncthing). Non-negotiable
  once any write autonomy exists.
- **AI as retrieval, not generation** (Späti, notoriouslab): use semantic search
  to find what *you* wrote; keep synthesis human.
- **Treat any AI wiki as a regeneratable cache** over immutable sources
  (Proudfrog): if you stop trusting it, delete and rebuild. Small blast radius.

## How this maps to our ADRs

- FM-1, FM-2, FM-3, FM-6 → justify `ADR-002` (postpone autonomous self-rewriting).
- FM-4, FM-5 → become hard guardrails for any future write-enabled ADR:
  backup/rollback proven, deletion circuit breaker, untrusted-content handling.
- The mitigations are the acceptance criteria a future "safe write zone" ADR
  must satisfy before it can move from Proposed to Accepted.

## Sources

See `sources/source-ledger.md` for full URLs and grades.
