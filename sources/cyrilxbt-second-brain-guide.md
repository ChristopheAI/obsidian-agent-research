# Source Note — CyrilXBT "Obsidian Second Brain That Connects Every Idea"

- URL: https://x.com/cyrilXBT/status/2063073652925505632
- Date: 2026-06-06 (39.5K views)
- Source grade: **B for this artifact** (concrete, actionable build guide) despite
  the account being promotional (graded C elsewhere). Judge the artifact, not the avatar.

A full build guide for an AI-augmented Obsidian "second brain": a 4-layer model
(Capture → Permanent → Connection → Intelligence), a vault structure, a capture
convention, permanent-note + Map-of-Content templates, a `CLAUDE.md`, and six
Claude prompts + three manual linking habits.

## The three genuinely valuable ideas

1. **The `05-INTELLIGENCE/` quarantine (the standout).** All AI-generated output
   (`connection-reports/`, `syntheses/`, `patterns/`) lives in a dedicated folder,
   never mixed into the human-written `01-PERMANENT` notes. This is exactly Steph
   Ango's "let AI make a mess in its own space" and **structurally solves FM-1
   (authorship contamination)** — you can always tell what is yours vs the agent's,
   and you can delete/regenerate the whole folder as a cache. Best public
   implementation of this principle seen so far. → candidate **ADR-003**.

2. **The capture convention `IDEA / CONNECTS TO / MIGHT USE FOR`.** Thirty seconds
   at capture time records the connections while the brain is still on the topic.
   The `CONNECTS TO` line becomes a permanent retrieval path. Cheap, high-leverage,
   no automation required.

3. **Read-only intelligence prompts + the "Key Tension" note field.** Several of
   his six integrations are read-only or write only to `05-INTELLIGENCE`: weekly
   connection finder, topic synthesis, pattern detector, question answerer, and a
   **contradiction detector** (flags inconsistent positions across notes). These
   are safe and align with our governance interest. The permanent-note "Key
   Tension" section is a nice generativity device.

## What conflicts with our risk findings — handle with guardrails

- **Integration 1 (Capture Processor) and the "Two Link Rule" automation WRITE into
  permanent notes** (add links to both notes, create new permanent notes). That is
  the agent editing the human knowledge layer — touches FM-2/FM-3 and our ADR-002
  stance. Allowed only behind: git (H6), diff review, and a do-not-edit list for
  `02 Topics` / `04 Decisions`.
- The whole guide assumes Claude reading the **entire vault** every run — fine for
  retrieval, but token-heavy and (for Christophe) a privacy surface for sensitive
  notes. Prefer scoped access (H5) + tiered loading.
- Tone is "build it this weekend, your vault will think" — discount the hype; the
  compounding claims are plausible but unproven at month 6.

## Mapping to MyCVHVault (gap analysis)

| CyrilXBT | MyCVHVault equivalent | Gap |
|---|---|---|
| 00-CAPTURE | 00 Discoveries | ~same |
| 01-PERMANENT | 02 Topics | ~same |
| 02-MAPS (MoCs) | (inside 02 Topics) | **No explicit MoC/map layer** |
| 03-PROJECTS | 03 Projects | same |
| 04-RESOURCES | 06 Sources | ~same |
| **05-INTELLIGENCE** | — | **Missing: AI-output quarantine folder** |
| 06-DAILY | 01 Daily | same |
| 07-ARCHIVE | (none explicit) | minor |
| 08-SYSTEM (CLAUDE.md) | .claude / global CLAUDE.md | same |
| — | **04 Decisions** | Christophe has this; Cyril lacks it (our advantage) |

Two takeaways: MyCVHVault would benefit from (a) an **AI-output quarantine folder**
and (b) an explicit **MoC/map layer** — without giving up its distinctive
`04 Decisions`.

## Candidate ADR-003

"Quarantine all agent-generated synthesis in a dedicated, regeneratable folder;
keep `02 Topics` and `04 Decisions` human-owned." This would convert FM-1's
mitigation into an accepted decision and unblock safe read-only intelligence
workflows. Proposed, pending Christophe.
