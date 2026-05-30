# Terminus

> The convergence point — all frameworks, Obsidian configurations, and collaborative systems built between Chris and Claude.

---

## User Profile — Chris

| Field | Detail |
|---|---|
| **Full context** | 41-year-old B.Eng. student, Wirtschaftsingenieurwesen Maschinenbau |
| **Institution** | Hochschule Hannover, Fakultät 2 |
| **Personality** | INTJ-T, neurodivergent, multilingual (DE / EN / AR) |
| **Communication style** | Casual warmth ("Bro", "Habibi") + demands for academically rigorous, deeply structured output |
| **Interests** | Berlin techno (Tresor), Kojima Productions / gaming, fitness & body transformation, cooking, ceramics & craft, Obsidian PKM, biohacking, engineering |
| **Working style** | Systematic, interdisciplinary, visual — prefers comprehensive notes with diagrams over summaries |

---

## Pre-Generation Protocol — ALWAYS FOLLOW THIS

**Before generating any substantial output, ask Chris which format he needs.**

Prompt to use:

> "What's the destination for this output? Options:
> - Obsidian note (full visual treatment — callouts, Mermaid, tables, citations)
> - Copy-paste message (plain, no markdown syntax)
> - Email (appropriate tone + structure)
> - Text / analytical summary (structured but lean)
> - Code output (documented, with README)
> - Something else?"

Do NOT skip this step and assume a format. The format determines everything downstream.

---

## Output Generation Standards

These rules apply to **all output** unless the chosen format explicitly overrides them.

### Language & Units

- **SI units only** — never Imperial. No inches, feet, pounds, Fahrenheit, miles. Convert if source material uses Imperial.
- Default prose language: **English** unless Chris requests otherwise.
- Technical terms may stay in German when no clean English equivalent exists (e.g. *Wirtschaftsingenieurwesen*).

### Citations

- **Harvard referencing style** throughout.
- In Obsidian Markdown: use footnotes `[^1]` anchored inline, with full references collected at the bottom under `## Resources`.
- Always include **date of access** for web sources.
- Format:
  ```
  Author, A. (Year) *Title*. Publisher. Available at: URL [Accessed DD Month YYYY].
  ```

### Authorship

Every generated note includes an authorship block in the frontmatter or a visible header section:

```yaml
authors:
  - Chris (xlr-eta)
  - Claude (Anthropic)
```

Or as a callout if frontmatter is not appropriate:

```
> [!info] Authors
> Chris (xlr-eta) · Claude (Anthropic, claude-sonnet-4-6)
```

### Structure Requirements

Every substantive note must include:

1. **YAML frontmatter** (see schema below)
2. **tl;dr callout** directly after each `##` main heading
3. **Overall Summary** section before Resources
4. **Resources** section at the very end

### Keyword Linking

High-impact keywords must be wrapped as wikilinks `[[Keyword]]` so Chris can later create dedicated notes. Apply this to:
- Named frameworks or methodologies
- Scientific / technical concepts
- Named people central to the topic
- Tools, substances, or systems with standalone note potential

Flag new links with a callout if there are more than five in one note:

```
> [!tip] Linked Keywords
> The following terms are linked for future note creation: [[X]], [[Y]], [[Z]]
```

---

## Obsidian Output Specification

When format = Obsidian note, apply the full visual treatment.

### Frontmatter Schema

```yaml
---
title: ""
created: YYYY-MM-DD
updated: YYYY-MM-DD
tags: []
status: draft | active | archived
type: note | framework | reference | template | guide
authors:
  - Chris (xlr-eta)
  - Claude (Anthropic)
---
```

### Visual Elements Checklist

- [ ] **Callouts** — use at minimum: `[!info]`, `[!tip]`, `[!warning]`, `[!summary]` (tl;dr)
- [ ] **Tables** — for comparisons, specifications, structured data
- [ ] **Mermaid diagrams** — vary types contextually:
  - `flowchart` — processes, decision trees
  - `sequenceDiagram` — interactions over time
  - `gantt` — timelines, project phases
  - `mindmap` — concept maps
  - `quadrantChart` — 2×2 prioritisation matrices
  - `xychart-beta` — quantitative data
  - `classDiagram` — taxonomies, relationships
- [ ] **Section tl;dr** — `[!summary] tl;dr` callout after every `##` heading
- [ ] **Overall Summary** — before Resources
- [ ] **Resources** — Harvard-cited footnotes at the end

### Callout Types Reference

```
> [!abstract] Abstract / Overview
> [!info] Neutral information
> [!tip] Recommendation / actionable insight
> [!warning] Caution / risk
> [!danger] Critical warning
> [!success] Confirmed / works
> [!question] Open question
> [!quote] Direct quotation
> [!summary] tl;dr — keep these tight, 2–4 sentences max
> [!note] Supplementary detail
```

---

## Dataview Code Standards

When writing Dataview queries for Chris:

1. **Comment everything** — every block of logic gets an English inline comment explaining what it does and why.
2. **README required** — every Dataview snippet ships with a companion `README.md` (or a README callout in the same note) that covers:
   - Purpose of the query
   - Required frontmatter fields / metadata dependencies
   - Expected output description
   - How to modify it for common variations
3. Use `TABLE` over `LIST` wherever columns add clarity.
4. Always define `FROM` scope explicitly — never leave it open-ended.
5. Sort order must be explicit and commented.

Example comment style:
```dataview
TABLE
  file.ctime AS "Created",          // Creation date for chronological sorting
  status AS "Status"                 // Workflow status from frontmatter
FROM "Projects"                       // Scoped to Projects folder only
WHERE status != "archived"            // Exclude archived items from view
SORT file.ctime DESC                  // Newest first
```

---

## Active Projects & Knowledge Areas

### 1. Advanced Influence & Persuasion Curriculum

12-module educational curriculum covering psychological influence mechanisms, ethical persuasion, and defence strategies. Sources include Chase Hughes' frameworks, academic psychology, and intelligence methodologies.

**Structure:** Foundation → Application → Integration → Specialisation
**Location:** `frameworks/influence-persuasion-curriculum.md`
**Status:** Framework established, modules in development

### 2. Obsidian PKM System

Comprehensive personal knowledge management system with sophisticated formatting, Mermaid diagrams, Harvard citations, and Templater scripts. Includes CSS theme customisation.

**Location:** `obsidian/`

### 3. Biohacking & Personal Transformation

Systematic knowledge base on biohacking research, body transformation, pharmaceutical documentation (quetiapine, venlafaxine), and practical implementation guides.

**Location:** `frameworks/biohacking/`

### 4. Technical Engineering Projects

Biomechanics analysis, Fourier transformations, and engineering documentation aligned with B.Eng. coursework.

**Location:** `frameworks/engineering/`

### 5. Cultural & Creative Research

Berlin techno history (Tresor), Kojima Productions / Death Stranding creative projects, ceramics, cyberpunk aesthetic research.

**Location:** `frameworks/culture/`

---

## Repository Structure

```
terminus/
├── CLAUDE.md                          # Primary context — read first every session
├── obsidian/
│   ├── settings/                      # Vault .json config snapshots
│   ├── templates/                     # Templater & core templates
│   ├── snippets/                      # CSS snippets
│   ├── plugins/                       # Community plugin configs & notes
│   └── vault-structure.md             # Folder map and taxonomy
├── frameworks/
│   ├── README.md                      # Master index of all frameworks
│   ├── influence-persuasion-curriculum.md
│   ├── biohacking/
│   ├── engineering/
│   └── culture/
├── workflows/
│   └── ...                            # Named repeatable processes
├── prompts/
│   └── ...                            # Reusable Claude prompt templates
└── archive/
    └── ...                            # Deprecated versions, old iterations
```

---

## Working Conventions

### Claude Behaviour in This Repo

- Read `CLAUDE.md` at the start of every session — no exceptions.
- Before generating output: **ask format first** (see Pre-Generation Protocol above).
- Before proposing a new framework: check `frameworks/README.md` for overlap.
- Evolve existing systems over replacing them.
- Document the *why* behind decisions, not just the *what*.
- Commit after every meaningful unit of work; never end a session without pushing.

### Git Workflow

- **Branches:** `feature/<name>` or `framework/<name>` in kebab-case
- **Commits:** imperative present tense — `add PARA vault structure`, `update daily note template`
- **Push** after every session; this repo is the source of truth

### File Naming

| Context | Convention | Example |
|---|---|---|
| Code / config | kebab-case | `daily-note-template.md` |
| Obsidian notes | Title Case | `Influence Frameworks.md` |
| Framework docs | kebab-case | `para-method.md` |

---

## Session Startup Checklist

1. Read `CLAUDE.md`
2. `git log --oneline -10` — what changed recently?
3. Load relevant framework file(s) for today's work
4. **Ask format before generating any output**
5. Work, commit incrementally
6. End of session: push, update index files if new frameworks added

---

## Notes on Repository History

Terminus was initialised on **2026-05-30** as the canonical home for all systems and frameworks developed over the preceding year of collaboration between Chris and Claude. Framework files will be populated iteratively — each session adds to the record rather than starting from zero.

> *"Terminus"* — the Roman god of boundaries and landmarks. Every journey ends here; every next one begins here.
