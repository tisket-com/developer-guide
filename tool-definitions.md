# Tool Definitions

This document defines all MCP tools available in Tisket. All tools support context resolution - tools that operate on files accept optional `workspace`, `project`, and `team` parameters to override the current context.

## Workspace Management

### context
View or set the current working context. Call with no arguments to see current state.

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| workspace | string | No | Workspace to select (slug or name) |
| project | string | No | Project to select |
| team | string | No | Team to select (alternative to project) |

### create_workspace
Create a new workspace to organize projects and teams.

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| name | string | Yes | Workspace name |
| slug | string | No | URL-friendly slug (auto-generated if omitted) |

### add_to_workspace
Add a project or team to the current workspace.

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| project | string | No | Project name to add |
| team | string | No | Team name to add |

### remove_from_workspace
Remove a project or team from the current workspace.

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| project | string | No | Project name to remove |
| team | string | No | Team name to remove |

### delete_workspace
Delete a workspace. Only the owner can delete. Projects and teams are unlinked but not deleted.

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| workspace | string | Yes | Workspace slug or name to delete |
| confirm | boolean | Yes | Must be true to confirm deletion |

## Projects and Teams

### create_project
Create a new project (documentation repository).

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| name | string | Yes | Project name |
| description | string | No | Project description |

### create_team
Create a new team (ticket repository). Automatically adds .tickets suffix.

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| name | string | Yes | Team name (e.g. engineering becomes engineering.tickets) |
| description | string | No | Team description |

## File Operations

### read_file
Read a file from the current project or team.

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| path | string | Yes | Path to the file |
| workspace | string | No | Workspace (uses current if omitted) |
| project | string | No | Project (uses current if omitted) |
| team | string | No | Team (alternative to project) |

### write
Write content to a file. Creates the file if it does not exist.

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| file_path | string | Yes | Path to the file |
| contents | string | Yes | Content to write |
| workspace | string | No | Workspace (uses current if omitted) |
| project | string | No | Project (uses current if omitted) |
| team | string | No | Team (alternative to project) |

### delete_file
Delete a file.

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| path | string | Yes | Path to the file to delete |
| workspace | string | No | Workspace (uses current if omitted) |
| project | string | No | Project (uses current if omitted) |
| team | string | No | Team (alternative to project) |

### list_dir
List directory contents.

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| path | string | No | Directory path (default: root) |
| glob | string | No | File pattern filter |
| workspace | string | No | Workspace (uses current if omitted) |
| project | string | No | Project (uses current if omitted) |
| team | string | No | Team (alternative to project) |

### tree
Get the complete file tree.

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| depth | number | No | Maximum depth to traverse |
| glob | string | No | File pattern filter |
| workspace | string | No | Workspace (uses current if omitted) |
| project | string | No | Project (uses current if omitted) |
| team | string | No | Team (alternative to project) |

### search
Search for a pattern across all files.

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| pattern | string | Yes | Text or regex pattern to search for |
| glob | string | No | File pattern filter |
| max_results | number | No | Maximum results to return (default: 50) |
| context | number | No | Lines to show before/after each match |
| workspace | string | No | Workspace (uses current if omitted) |
| project | string | No | Project (uses current if omitted) |
| team | string | No | Team (alternative to project) |

## Git Operations

### git_status
Show git status (uncommitted changes).

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| workspace | string | No | Workspace (uses current if omitted) |
| project | string | No | Project (uses current if omitted) |
| team | string | No | Team (alternative to project) |

### git_commit
Stage all changes and commit.

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| message | string | Yes | Commit message |
| workspace | string | No | Workspace (uses current if omitted) |
| project | string | No | Project (uses current if omitted) |
| team | string | No | Team (alternative to project) |

### git_push
Push commits to GitHub.

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| workspace | string | No | Workspace (uses current if omitted) |
| project | string | No | Project (uses current if omitted) |
| team | string | No | Team (alternative to project) |

### git_log
Show recent commit history.

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| depth | number | No | Number of commits to show (default: 10) |
| workspace | string | No | Workspace (uses current if omitted) |
| project | string | No | Project (uses current if omitted) |
| team | string | No | Team (alternative to project) |

## Timelines

### create_timeline
Create a new timeline file.

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| title | string | Yes | Timeline title |
| description | string | No | Description of what this timeline tracks |
| slug | string | No | URL-friendly slug (defaults to title) |
| workspace | string | No | Workspace (uses current if omitted) |
| project | string | No | Project (uses current if omitted) |
| team | string | No | Team (alternative to project) |

### add_timeline_entry
Add an entry to an existing timeline.

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| timeline | string | Yes | Timeline slug (filename without .timeline.yaml) |
| name | string | Yes | Name/title of the task or milestone |
| assignee | string | Yes | Who is responsible |
| code | string | No | Short unique code (auto-generated if omitted) |
| start | string | No | Start date YYYY-MM-DD (default: today) |
| end | string | No | End date YYYY-MM-DD (default: start date) |
| status | string | No | done, in_progress, upcoming, blocked, or cancelled |
| category | string | No | Category/tag for grouping |
| notes | string | No | Additional notes |
| link | string | No | Link to related resource |
| tickets | array | No | Array of ticket references |
| workspace | string | No | Workspace (uses current if omitted) |
| project | string | No | Project (uses current if omitted) |
| team | string | No | Team (alternative to project) |

## Tickets

### list_tickets
List tickets in the current team.

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| status | string | No | Filter by: open, in_progress, resolved, or closed |
| workspace | string | No | Workspace (uses current if omitted) |
| team | string | No | Team (required context) |

### create_ticket
Create a new ticket with validated frontmatter. Auto-generates ticket ID.

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| title | string | Yes | Ticket title |
| description | string | No | Ticket description/body |
| status | string | No | Initial status: open, in_progress, resolved, closed (default: open) |
| priority | string | No | Priority: urgent, high, medium, low (default: medium) |
| assignee | string | No | Who is assigned to this ticket |
| project | string | No | Project/category for grouping |
| workspace | string | No | Workspace (uses current if omitted) |
| team | string | No | Team (required context) |

### update_ticket
Update ticket metadata (status, priority, assignee).

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| ticket_id | string | Yes | Ticket ID (e.g. TKT-001) |
| status | string | No | New status: open, in_progress, resolved, closed |
| priority | string | No | New priority: urgent, high, medium, low |
| assignee | string | No | New assignee |
| resolved | boolean/string | No | Set resolved date (true for today, or YYYY-MM-DD) |
| workspace | string | No | Workspace (uses current if omitted) |
| team | string | No | Team (required context) |

### add_comment
Add a comment to a ticket.

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| ticket_id | string | Yes | Ticket ID (e.g. TKT-001) |
| author | string | Yes | Comment author name |
| content | string | Yes | Comment text (markdown supported) |
| workspace | string | No | Workspace (uses current if omitted) |
| team | string | No | Team (required context) |

## Reports

### validate_report
Validate a report YAML file without executing it. Checks schema, input definitions, and code syntax.

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| yaml | string | Yes | The full YAML content of the report file |

### test_report
Execute a report and return the structured output. Validates the YAML, runs the code in a sandbox, and returns results.

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| yaml | string | Yes | The full YAML content of the report file |
| inputs | object | No | Input values to pass to the report (uses defaults if omitted) |