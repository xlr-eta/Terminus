# Terminus

> The convergence point — all frameworks, Obsidian configurations, and collaborative systems built with Claude.

## What This Is

Terminus is the persistent memory layer across all Claude Code sessions. It holds every framework, Obsidian vault setting, template, and system design developed in collaboration, so nothing has to be rebuilt from scratch and every new session starts with full context.

When starting any session in this repo, read this file first and load relevant files from the directories below before touching anything.

---

## Repository Structure

```
terminus/
├── CLAUDE.md                        # Primary context — read this first
├── obsidian/
│   ├── settings/                    # Vault-level .json configs
│   ├── templates/                   # Note templates (Templater / core)
│   ├── snippets/                    # CSS snippets
│   ├── plugins/                     # Community plugin configs & notes
│   └── vault-structure.md           # Folder map, PARA or equivalent
├── frameworks/
│   ├── README.md                    # Index of all frameworks
│   └── ...                          # One file per framework
├── workflows/
│   └── ...                          # Repeatable, named workflows
├── prompts/
│   └── ...                          # Reusable Claude prompt templates
└── archive/
    └── ...                          # Deprecated versions, old iterations
```

---

## Working Conventions

### Claude Code Behaviour in This Repo

- Always read CLAUDE.md at session start.
- Before proposing a new framework, check `frameworks/README.md` for overlap.
- Prefer evolving existing systems over replacing them — patch, don't nuke.
- When a decision is made, document the *why*, not just the *what*.
- All Obsidian-destined content uses Obsidian Markdown: wikilinks `[[Note]]`, frontmatter, callouts.
- Commit after every meaningful unit of work; don't let sessions end without pushing.

### File Naming

| Context | Convention | Example |
|---|---|---|
| Code / config | kebab-case | `daily-note-template.md` |
| Obsidian notes | Title Case | `My Framework.md` |
| Framework docs | kebab-case | `para-method.md` |
| Constants | SCREAMING_SNAKE | `MAX_DEPTH` |

### Obsidian Frontmatter Standard

```yaml
---
created: YYYY-MM-DD
updated: YYYY-MM-DD
tags: []
status: draft | active | archived
type: note | framework | reference | template
---
```

### Git Workflow

- **Branches:** `feature/<name>` or `framework/<name>` in kebab-case
- **Commits:** imperative present tense — `add PARA vault structure`, `update daily note template`
- **Push** to origin after every session; this repo is the source of truth

---

## Obsidian Vault Configuration

> Detail lives in `obsidian/` — this section is the high-level map.

### Core Plugins Enabled

- [ ] To be documented — run `obsidian/settings/app.json` snapshot here

### Community Plugins

- [ ] To be documented — list name, purpose, key settings

### Vault Structure

- [ ] To be documented — see `obsidian/vault-structure.md`

### Themes & Snippets

- [ ] To be documented — see `obsidian/snippets/`

---

## Active Frameworks

> Full docs live in `frameworks/` — this section is the master index.

### Knowledge Management

- [ ] To be populated — e.g. PARA, Zettelkasten, MOC structure

### AI & Automation

- [ ] To be populated — e.g. prompt chains, Claude workflows, automation hooks

### Project & Task Management

- [ ] To be populated — e.g. GTD adaptation, project templates, review cadences

### Personal Operating System

- [ ] To be populated — e.g. weekly review, daily driver, goal tracking

---

## Active Workflows

> Full docs live in `workflows/` — named, repeatable processes.

- [ ] To be populated

---

## Session Startup Checklist

1. Read `CLAUDE.md`
2. `git log --oneline -10` — what changed recently?
3. Load relevant framework file(s) for today's work
4. Work, commit incrementally
5. End of session: push, update any relevant index files

---

## Notes on This Repo's History

This repository was initialised on **2026-05-30** as the canonical home for all frameworks and systems developed over the preceding year. Framework files will be populated iteratively — each session adds to the record rather than starting from zero.

> "Terminus" — the Roman god of boundaries and landmarks. Every journey ends here; every next one begins here.
