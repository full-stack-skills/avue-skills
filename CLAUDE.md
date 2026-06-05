# CLAUDE.md

## Project Overview

**avue-skills** — Agent Skills for the [Avue](https://avuejs.com) enterprise framework (Vue 2.x). Part of the [Full Stack Skills](https://github.com/partme-ai/full-stack-skills) ecosystem by PartMe.AI. Each skill is a self-contained `SKILL.md` loaded on-demand by AI coding agents.

## Skills (3)

| Skill | Purpose |
|-------|---------|
| `avue` | Core framework — global config, installation, table/tree/upload components, CRUD patterns, i18n |
| `avue-crud` | CRUD component — column config, pagination, search, sorting, selection, export, validation |
| `avue-form` | Form component — dynamic forms, validation, events, methods, column-driven config |

## Directory Structure

```
skills/
  {skill-name}/              # kebab-case, matches SKILL.md `name` field
    SKILL.md                 # Required: YAML frontmatter + progressive disclosure body
    LICENSE.txt              # Apache 2.0
    api/                     # API reference docs (props, events, methods, options)
    examples/                # Usage examples organized by topic area
      getting-started/       # Installation, quick-start, basic usage
      components/            # Per-component examples
      advanced/              # Advanced features (i18n, column types, validation)
    templates/               # Complete Vue component templates (full copy-paste code)
```

## SKILL.md Frontmatter

```yaml
---
name: <kebab-case-name>
description: One sentence with trigger phrases. "Use when the user asks about..."
license: Complete terms in LICENSE.txt
---
```

Body follows progressive disclosure: `## When to use this skill` bullets, then `## How to use this skill` with a topic-to-file mapping table.

## Authoring Conventions

- **Kebab-case** for directory names, matching the `name` field in frontmatter.
- **SKILL.md under 500 lines** — detailed reference material stays in `api/`, `examples/`, `templates/`.
- **Progressive disclosure** — SKILL.md links to supporting files; agents read those only when relevant.
- **One skill per directory** — no shared files across skills; each is self-contained.
- **Bilingual content** — code examples in Vue 2.x Options API; docs use `# English | 中文标题` headings.
- **Example docs** follow consistent structure: `# Title`, `**Official docs**: <url>`, `## Instructions` → `### Key Concepts`, `### Example`, `### Key Points`.
- This is a **docs-only plugin** (no `scripts/` directory); all skills are pure reference material.

## Key Files

| File | Purpose |
|------|---------|
| `AGENTS.md` / `AGENTS_EN.md` | Full skill authoring guide (structure, naming, zip packaging) |
| `README.md` / `README.zh-CN.md` | User-facing install docs and ecosystem links |
| `.claude-plugin/plugin.json` | Plugin manifest — registers skills for Claude Code discovery |
| `skills/*/SKILL.md` | Skill definitions with YAML frontmatter |

## Plugin Registration

Claude Code discovers skills via `.claude-plugin/plugin.json`. Add new skills to the `skills` array there. Install with: `npx skills add full-statck-skills/avue-skills`
