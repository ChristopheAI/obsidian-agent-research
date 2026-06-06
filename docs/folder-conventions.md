# Folder Conventions: How Others Organize Obsidian Vaults

Last updated: 2026-06-06

Reference knowledge for deciding whether MyCVHVault's structure needs to change.
Short answer from `H1`: it probably does not. This documents the landscape so
that conclusion is evidence-based, not assumed.

## The five dominant families

1. **PARA** (Tiago Forte) - sort by *actionability*, not topic:
   `01 Projects` / `02 Areas` / `03 Resources` / `04 Archives`.
   Strength: tool-agnostic, simple. Weakness: Area/Resource boundary blurs;
   knowledge gets buried in Archive when a project ends.

2. **LYT / ACE** (Nick Milo) - three thinking spaces:
   `Atlas` (knowledge + MOCs), `Calendar` (time), `Efforts` (action).
   Older form was **ACCESS** (Atlas, Calendar, Cards, Extras, Sources, Spaces).
   Core idea: organize by *connection via MOCs*, not by category.

3. **Johnny.Decimal** - strict numeric taxonomy, max 10 areas x 10 categories,
   one bucket per item (`21.01`). Strong for shared/file management, rigid for
   loose thoughts.

4. **Numbered prefix hybrid** - what most experienced solo users actually run:
   numbers force sort order (Obsidian sorts alphabetically otherwise), PARA-ish
   logic, Zettelkasten/MOCs underneath. Examples: Rob Dunn (`01..99`,
   meta at the end); Tony Nguyen (`XX.YY-name`, tens digit as a slot so a new
   workspace is just `30` with no renumbering).

5. **Minimal / flat** - deliberately small (`Inbox, Daily, Projects, Reference,
   Archive`), let structure emerge. Philosophy: the folder tree is cosmetic;
   the links do the real work.

## Where MyCVHVault sits

MyCVHVault is a **numbered prefix hybrid** (family 4), and a considered one:

| Folder | Maps to |
|---|---|
| `00 Discoveries` | Inbox / insights staging |
| `01 Daily` | Calendar (LYT) |
| `02 Topics` | Atlas / Resources - knowledge + MOCs |
| `03 Projects` | Projects (PARA) / Efforts (LYT) |
| `04 Decisions` | Distinctive - almost no one has this top-level |
| `05 Templates` | Meta |
| `06 Sources` | Sources / Resources |

Two observations:

- **`04 Decisions` as a top-level folder is unusual and strong.** Most systems
  bury decisions inside projects or daily notes. Treating them as a first-class,
  reusable artifact fits the write-back rule directly.
- **The structure is already AI-native.** A recurring 2025-2026 theme: people
  pick plain markdown + numbered folders precisely because agents read the vault
  directly. One MOC per topic lets an agent grasp a topic's landscape fast -
  which is what `02 Topics` already does.

## Naming conventions practitioners share

- Number prefix for sort order (important on top, meta at `97/98/99`).
- Consistent casing (kebab-case is common); no exceptions - predictability pays.
- `YYYY-MM-DD` for anything time-stamped.
- Max two folder levels deep.
- `index.md` / `Overview - X.md` / MOC per domain as the hub, instead of deep nesting.
- Folders are not the organization; links are. Let structure follow content.

## Implication for this repo

This supports `H1` (no template replacement needed). The first build should add
the *governance and retrieval* layer (`H2`), not restructure folders.

## Sources

See `sources/source-ledger.md`.
