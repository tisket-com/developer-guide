# Features

Tisket provides a comprehensive suite of tools for managing documentation, tickets, and project timelines.

## Core Features

### 📁 Projects (Documentation Repositories)

Store and organize your technical documentation in Git-backed repositories.

- **Markdown-first** — Write docs in Markdown with full formatting support
- **Version controlled** — Track changes with Git history
- **Collaborative** — Multiple team members can contribute simultaneously
- **Structured** — Organize content with folders and cross-references

### 🎫 Teams (Ticket Repositories)

Manage work items with `.tickets` repositories designed for agile workflows.

- **YAML-based tickets** — Structured data with flexible schemas
- **Status tracking** — Track progress from backlog to completion
- **Assignees & labels** — Organize work by team member and category
- **Linked to timelines** — Connect tickets to project milestones

### 📅 Timelines

Visualize project progress and coordinate team efforts with timeline tracking.

- **Milestone planning** — Define key dates and deliverables
- **Status indicators** — Track what's done, in progress, blocked, or upcoming
- **Assignee tracking** — See who's responsible for each item
- **Category grouping** — Organize entries by team, phase, or theme

### 📊 Reports

Generate dynamic reports with embedded code execution.

- **YAML definitions** — Declarative report configuration
- **JavaScript/TypeScript** — Write custom logic for data processing
- **Parameterized inputs** — Create reusable report templates
- **Validated output** — Schema-checked results for consistency

### 🗂️ Workspaces

Organize related projects and teams into logical workspaces.

- **Group by product** — Combine docs and tickets for each product
- **Cross-project visibility** — See everything in one place
- **Easy switching** — Quickly move between contexts

## Git Integration

All content is stored in Git repositories with full version control:

- `git_status` — View pending changes
- `git_commit` — Stage and commit with a message
- `git_push` — Push to GitHub
- `git_log` — View commit history

## Search & Navigation

Find content quickly across your projects:

- **Full-text search** — Find patterns across all files
- **File tree** — Browse directory structures
- **Glob filtering** — Target specific file types

## Next Steps

- [Getting Started](./getting-started.md) — Set up your first project
- [API Reference](./api/overview.md) — Explore the full API
