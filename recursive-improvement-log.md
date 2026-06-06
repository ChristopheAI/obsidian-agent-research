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

