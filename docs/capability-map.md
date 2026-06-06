# Obsidian Agent Capability Map

Last updated: 2026-06-06

## Capability Classes

| Capability | What it enables | Evidence so far | Current stance |
|---|---|---|---|
| Obsidian Markdown skills | Agents write valid wikilinks, properties, embeds, callouts | `kepano/obsidian-skills` | Adopt |
| Obsidian Bases | Dashboard/query views over notes using properties and filters | `kepano/obsidian-skills`, Obsidian docs | Adapt |
| JSON Canvas | Agent-created system maps and visual flows | `kepano/obsidian-skills`, JSON Canvas spec | Adapt narrowly |
| Obsidian CLI | Vault-aware read/create/search/property operations when Obsidian is running | `kepano/obsidian-skills` | Evaluate |
| Defuddle | Web-to-markdown extraction for cleaner source ingest | `kepano/obsidian-skills` | Evaluate |
| QMD semantic search | Meaning-based retrieval over vault notes | `breferrari/obsidian-mind` | Evaluate after basic retrieval map |
| MCP / Local REST API | Tool-level read/write/search access to vault | X signals, Local REST API references, MCP repos | Revisit later |
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

