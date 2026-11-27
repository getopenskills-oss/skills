# OpenSkills — Agent Skills

[![Website](https://img.shields.io/badge/registry-getopenskills.xyz-black)](https://getopenskills.xyz)
[![License: MIT](https://img.shields.io/badge/license-MIT-black)](LICENSE)
[![Skills](https://img.shields.io/badge/skills-31-black)](#skills)

**31 open-source Agent Skills** (`SKILL.md`) for Claude Code, Cursor, Codex, GitHub Copilot and other AI agents — written and maintained by [OpenSkills](https://getopenskills.xyz), the open registry for Agent Skills.

> Browse 150+ more skills, read the automatic safety check for each one, and install in one command at **[getopenskills.xyz](https://getopenskills.xyz)**.

## Install

**Any agent that supports `npx skills`:**

```bash
npx skills add getopenskills-oss/skills
```

**One skill, by hand** (Claude Code example — use `.cursor/skills`, `.agents/skills` or `.github/skills` for Cursor, Codex or Copilot):

```bash
mkdir -p .claude/skills/code-reviewer && curl -fsSL https://getopenskills.xyz/api/skills/code-reviewer/raw -o .claude/skills/code-reviewer/SKILL.md
```

**Let your agent find skills on its own** with the OpenSkills MCP server (free, no API key):

```bash
claude mcp add --transport http openskills https://getopenskills.xyz/api/mcp
```

## Skills

### 💻 Coding

| Skill | What it does |
|---|---|
| [`api-designer`](skills/api-designer/SKILL.md) | Design clean, consistent HTTP/REST APIs: resources, endpoints, request and response shapes, errors, pagination, auth and versioning, delivered as an OpenAPI sketch. [↗](https://getopenskills.xyz/skill/api-designer) |
| [`code-explainer`](skills/code-explainer/SKILL.md) | Explain unfamiliar code clearly — what it does, how data flows through it, why it is written that way, and what to watch out for — at the reader's level. [↗](https://getopenskills.xyz/skill/code-explainer) |
| [`code-reviewer`](skills/code-reviewer/SKILL.md) | Review a code diff or file for bugs, security issues, performance problems, and readability, and return prioritized, actionable findings. [↗](https://getopenskills.xyz/skill/code-reviewer) |
| [`debugger`](skills/debugger/SKILL.md) | Find the root cause of a bug systematically: reproduce it, form hypotheses, test them with evidence, then fix and verify. [↗](https://getopenskills.xyz/skill/debugger) |
| [`dockerfile-writer`](skills/dockerfile-writer/SKILL.md) | Write small, secure, fast-building Dockerfiles and docker-compose files for an application, using multi-stage builds, layer caching and a non-root user. [↗](https://getopenskills.xyz/skill/dockerfile-writer) |
| [`git-commit-writer`](skills/git-commit-writer/SKILL.md) | Write clear git commit messages from a diff or a description of the change, following Conventional Commits. [↗](https://getopenskills.xyz/skill/git-commit-writer) |
| [`refactoring-guide`](skills/refactoring-guide/SKILL.md) | Plan and carry out safe refactorings in small, behavior-preserving steps backed by tests: find the real pain, choose the refactoring, change, verify. [↗](https://getopenskills.xyz/skill/refactoring-guide) |
| [`regex-builder`](skills/regex-builder/SKILL.md) | Build, explain and test regular expressions for matching, validating, extracting or replacing text, with clear breakdowns and test cases for each flavor (JavaScript, Python, PCRE, grep). [↗](https://getopenskills.xyz/skill/regex-builder) |
| [`test-writer`](skills/test-writer/SKILL.md) | Write focused unit and integration tests for existing code using the project's own test framework and conventions. [↗](https://getopenskills.xyz/skill/test-writer) |

### 📊 Data

| Skill | What it does |
|---|---|
| [`data-analyst`](skills/data-analyst/SKILL.md) | Analyze a CSV, spreadsheet or dataset: profile and clean it, answer the question with numbers, and present findings with honest caveats. [↗](https://getopenskills.xyz/skill/data-analyst) |
| [`spreadsheet-formulas`](skills/spreadsheet-formulas/SKILL.md) | Write and debug Excel and Google Sheets formulas — lookups, conditional sums, date math, text cleanup, dynamic arrays and pivot-style summaries — with explanations. [↗](https://getopenskills.xyz/skill/spreadsheet-formulas) |
| [`sql-writer`](skills/sql-writer/SKILL.md) | Write correct, readable and efficient SQL from a plain-language question, using the real schema. [↗](https://getopenskills.xyz/skill/sql-writer) |

### ✍️ Writing

| Skill | What it does |
|---|---|
| [`changelog-writer`](skills/changelog-writer/SKILL.md) | Write user-facing release notes and CHANGELOG entries from commits, merged pull requests, or a diff between versions, grouped by impact. [↗](https://getopenskills.xyz/skill/changelog-writer) |
| [`content-writer`](skills/content-writer/SKILL.md) | Write blog posts, articles, newsletters, and social posts from a brief, matched to a target audience and tone. [↗](https://getopenskills.xyz/skill/content-writer) |
| [`email-writer`](skills/email-writer/SKILL.md) | Draft clear, concise emails for any situation — requests, follow-ups, updates, apologies, cold outreach, saying no — with the right tone and a single clear ask. [↗](https://getopenskills.xyz/skill/email-writer) |
| [`job-description-writer`](skills/job-description-writer/SKILL.md) | Write clear, inclusive job descriptions that attract the right candidates: impact of the role, real responsibilities, must-have vs. [↗](https://getopenskills.xyz/skill/job-description-writer) |
| [`pitch-deck-writer`](skills/pitch-deck-writer/SKILL.md) | Outline and write a clear pitch deck — problem, solution, market, traction, business model, team and ask — slide by slide, with speaker notes. [↗](https://getopenskills.xyz/skill/pitch-deck-writer) |
| [`readme-writer`](skills/readme-writer/SKILL.md) | Write or improve a project README that gets a new user from zero to running in minutes: what it is, install, quick start, configuration, and how to contribute. [↗](https://getopenskills.xyz/skill/readme-writer) |
| [`seo-optimizer`](skills/seo-optimizer/SKILL.md) | Improve a web page or article for search: search intent, keywords, title and meta description, headings, internal links, structured data and content gaps — without keyword stuffing. [↗](https://getopenskills.xyz/skill/seo-optimizer) |

### 🔎 Research

| Skill | What it does |
|---|---|
| [`competitor-research`](skills/competitor-research/SKILL.md) | Research and compare competitors for a product: who they are, positioning, pricing, features, strengths and weaknesses, and where the gaps are. [↗](https://getopenskills.xyz/skill/competitor-research) |
| [`deep-research`](skills/deep-research/SKILL.md) | Research a question across many sources and deliver a structured, cited report. [↗](https://getopenskills.xyz/skill/deep-research) |
| [`fact-checker`](skills/fact-checker/SKILL.md) | Check claims in a text against reliable sources and report what is true, false, misleading or unverifiable, with citations. [↗](https://getopenskills.xyz/skill/fact-checker) |
| [`user-interview-synthesis`](skills/user-interview-synthesis/SKILL.md) | Turn user interview notes or transcripts into evidence-backed insights: themes, pains, jobs-to-be-done, quotes, and recommendations with how strongly the evidence supports each. [↗](https://getopenskills.xyz/skill/user-interview-synthesis) |

### ✅ Productivity

| Skill | What it does |
|---|---|
| [`decision-memo`](skills/decision-memo/SKILL.md) | Write a one-page decision memo that frames a decision, compares realistic options with their trade-offs, and makes a clear recommendation. [↗](https://getopenskills.xyz/skill/decision-memo) |
| [`document-summarizer`](skills/document-summarizer/SKILL.md) | Summarize long documents, reports, papers, contracts or threads into the format the reader needs — TL;DR, key points, decisions, numbers, and open questions — with references back to the source. [↗](https://getopenskills.xyz/skill/document-summarizer) |
| [`meeting-notes`](skills/meeting-notes/SKILL.md) | Turn a meeting transcript or rough notes into a concise summary with decisions, action items (owner and due date), and open questions. [↗](https://getopenskills.xyz/skill/meeting-notes) |
| [`task-planner`](skills/task-planner/SKILL.md) | Turn a goal or a messy project into a concrete plan: milestones, ordered tasks with owners and estimates, dependencies, risks, and the very next step. [↗](https://getopenskills.xyz/skill/task-planner) |

### 🎨 Design

| Skill | What it does |
|---|---|
| [`accessibility-checker`](skills/accessibility-checker/SKILL.md) | Audit a web page, component or design for accessibility against WCAG 2.2 AA — keyboard use, screen readers, contrast, forms, media and motion — and give concrete code fixes. [↗](https://getopenskills.xyz/skill/accessibility-checker) |
| [`diagram-maker`](skills/diagram-maker/SKILL.md) | Turn a description of a process, system, or data model into a clear Mermaid diagram (flowchart, sequence, ER, state, or timeline). [↗](https://getopenskills.xyz/skill/diagram-maker) |
| [`ux-reviewer`](skills/ux-reviewer/SKILL.md) | Review a screen, flow, or prototype for usability and accessibility problems and return prioritized, specific fixes. [↗](https://getopenskills.xyz/skill/ux-reviewer) |

### 🧩 Other

| Skill | What it does |
|---|---|
| [`prompt-improver`](skills/prompt-improver/SKILL.md) | Rewrite a prompt for an AI model so it is clear, specific and reliable: role, task, context, constraints, output format, and examples. [↗](https://getopenskills.xyz/skill/prompt-improver) |

## What is a skill?

A skill is a folder with a `SKILL.md` file: YAML frontmatter (`name`, `description`) plus clear, step-by-step instructions. Agents load a skill when a task calls for it. Learn more at [https://getopenskills.xyz/about](https://getopenskills.xyz/about).

## Contributing

Found a problem or have an idea for a skill? Open an issue, or publish your own skill at [https://getopenskills.xyz/publish](https://getopenskills.xyz/publish).

## License

[MIT](LICENSE) © 2026 OpenSkills
