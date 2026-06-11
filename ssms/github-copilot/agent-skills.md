---
title: Agent Skills
titleSuffix: GitHub Copilot in SQL Server Management Studio
description: Learn how to create and use skills with GitHub Copilot in SQL Server Management Studio (SSMS) to provide reusable task-specific instructions for Agent mode.
author: rwestMSFT
ms.author: randolphwest
ms.reviewer: erinstellato
ms.date: 06/09/2026
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - ce-skilling-ai-copilot
ms.update-cycle: 180-days
# CustomerIntent: As a database administrator or database developer, I want to create and use Agent skills with GitHub Copilot in SQL Server Management Studio so that I can provide reusable task-specific instructions.
---

# Use Agent skills with GitHub Copilot in SQL Server Management Studio

Agent skills are reusable sets of instructions that instruct GitHub Copilot how to perform specific tasks. Each skill is a markdown file that you define one time, saving time and ensuring consistent behavior across your workflow. Think of skills as a runbook, not one giant prompt. When you use [Agent mode (preview)](agent-mode.md), Copilot automatically discovers and applies relevant skills based on what you're asking.

> [!NOTE]  
> GitHub Copilot Agent mode in SQL Server Management Studio (SSMS) is currently in preview.

Unlike [custom instructions](custom-instructions.md), which set general preferences for every response, skills provide focused task-specific guidance that any agent can discover and use. Define a skill once, and it applies consistently across sessions and across your team.

## Prerequisites

- SSMS 22.7 or a later version with the [AI Assistance workload](installation-state.md#install-github-copilot-in-ssms-using-the-visual-studio-installer).
- A GitHub account with [Copilot access](https://docs.github.com/copilot/get-started/what-is-github-copilot#getting-access-to-copilot). Alternatively, [use GitHub Copilot for free in SQL Server Management Studio](free-plan.md).

## How Agent skills work

When you use Agent mode, Copilot scans the known skill locations for your repository and user profile. If a skill's description matches the intent of your request, Copilot activates the skill and applies its instructions as extra context. When a skill is active, its name appears in the chat so you know it's being applied.

Copilot decides which skills to activate based on the `description` field in each skill's frontmatter. A clear, keyword-rich description helps Copilot identify when a skill is relevant.

## Skill locations

Copilot discovers skills from the following locations:

| Scope | Paths | Details |
| --- | --- | --- |
| **Workspace** (shared with your team) | `.github/skills/`, `.claude/skills/`, `.agents/skills/` | Stored in your repository root. Committed to source control so all team members get the same skills. |
| **Personal** (your profile only) | `~/.copilot/skills/`, `~/.claude/skills/`, `~/.agents/skills/` | Applies across all your projects. Not committed to any repository. |

Workspace skills take precedence for project-specific conventions. Personal skills are useful for workflows and preferences that travel with you across projects.

## Create a skill

You can create a skill from the **Skills** panel in SSMS or manually in your file system.

### Create a skill from the Skills panel

1. In the Copilot Chat window, select the **Tools** icon.
1. Select the **Skills** panel.
1. In the Skills panel, select the **+** button.
1. Choose the scope: a workspace skill (stored in the repository) or a personal skill (stored in your user profile).
1. Enter a name for the skill. The name becomes the directory name and must use lowercase letters, numbers, and hyphens only.
1. SSMS generates a `SKILL.md` template in the new skill directory. Edit the template and add your instructions to the file.

### Create a skill manually

1. Create a skills directory in the appropriate location. For a workspace skill, create `.github/skills/` at the root of your repository.
1. Create a subdirectory for your skill. Each skill must have its own directory. For example: `.github/skills/tsql-style-guide/`.
1. Create a `SKILL.md` file inside the skill directory.
1. Optionally, add supporting files such as scripts, reference documents, or example output.

#### Skill directory structure

```output
your-repo/
└── .github/
    └── skills/
        └── index-verification/
        │   ├── SKILL.md          # Required: metadata and instructions
        │   └── references/       # Optional: supplementary documentation
        └── agent-job-failure-triage/
            ├── SKILL.md
            └── examples/         # Optional: example scripts
```

## SKILL.md format

Each `SKILL.md` file must contain YAML frontmatter followed by Markdown instructions. The frontmatter provides the metadata Copilot uses to discover and activate the skill.

### Frontmatter properties

| Property | Required | Description |
| --- | --- | --- |
| `name` | Yes | Lowercase letters, numbers, and hyphens only. Must match the parent directory name. Maximum 64 characters. |
| `description` | Yes | Describes what the skill does and when to use it. Maximum 1,024 characters. Include specific keywords that signal when the skill is relevant. |
| `license` | No | License name or a reference to a license file bundled with the skill. |
| `compatibility` | No | Environment requirements, such as the intended product or required system capabilities. |
| `metadata` | No | Arbitrary key-value pairs for other metadata. |
| `allowed-tools` | No | Space-separated list of tool names the skill is pre-approved to use. |

## Manage skills from the Skills panel

Select the **Tools** icon in the Copilot Chat window to open the **Skills** panel. The panel shows every skill Copilot discovers for your current session.

From the panel, you can:

- **Edit**: Open any skill's `SKILL.md` file directly in the editor from the `...` menu.
- **Open file location**: Jump to the skill directory on disk.
- **Search**: Filter skills by name or keyword.

The panel also surfaces diagnostics for any skill configuration errors, so you can quickly identify and fix problems.

## Tips for writing effective skills

- **Keep `SKILL.md` concise**: Aim for under 300 lines. Move detailed reference material to separate files in relevant subdirectories.
- **Write a keyword-rich description**: Copilot uses the `description` to decide when to activate the skill. Include the specific tasks, objects, and scenarios where the skill applies.
- **Use numbered steps for procedures**: Step-by-step instructions are easier for the model to follow than prose.
- **Include examples of expected output**: Show sample code, table formats, or comment blocks so the model knows what "done" looks like.
- **Set explicit limits**: Tell the skill what *not* to do. For example, "Don't recommend dropping indexes on tables with more than 10 million rows without first reporting write volume."
- **Reference supporting material**: Store related content and scripts in files within `references\`, `scripts\`, or `examples\` and point to specific content from the skill.

## Example SQL skills

The following examples demonstrate how to write skills for common SQL Server tasks. Use them as starting points and adapt them to your team's conventions.

### Index verification

Review existing indexes before recommending new ones to avoid duplication.

```markdown
---
name: index-verification
description: Use when an index recommendation has been generated and must be validated before implementation. Verifies workload benefit, redundancy, write overhead, storage impact, and existing index coverage.
---

# Index Verification

## Use this skill when

- A missing index recommendation exists
- An agent generated an index recommendation
- Query tuning suggests adding an index
- A user asks whether an index should be created

## Never assume

- Missing index DMVs are recommendations, not requirements.
- Do not recommend index creation until validation is complete.

## Verification Checklist

### 1. Check Existing Indexes

Determine whether:

- An equivalent index already exists
- A wider index already covers the workload
- Included columns already satisfy the query
- The recommendation duplicates another recommendation

### 2. Estimate Read Benefit

Evaluate:

- Query execution frequency
- Current execution cost
- Expected seek/selectivity improvement
- Number of affected queries

### 3. Evaluate Write Cost

Determine:

- Insert impact
- Update impact
- Delete impact
- Additional maintenance cost

### 4. Evaluate Storage Impact

Estimate:

- Index size on disk
- Memory pressure
- Replication impact

### 5. Make Recommendation

Return one of:

- Create index
- Modify existing index
- Consolidate with existing recommendation
- Reject recommendation

## Avoid

- Blindly trusting missing-index DMVs
- Creating overlapping indexes
- Recommending indexes for one-off queries
- Ignoring write-heavy workloads

## Output Format

Format output as a table: index name, columns, type, and recommendation (create / modify / consolidate / reject).
```

### Agent job failure triage

Analyze history of failed SQL Agent jobs and make recommendations to address the root issue.

```markdown
---
name: agent-job-failure-triage
description: Use when an automated job, workflow, maintenance task, or agent execution fails. Determines root cause and appropriate remediation while avoiding unsafe recovery actions.
---
# Agent Job Failure Triage

## Objective

Identify root cause before attempting remediation.

## First Rule

Never retry repeatedly without understanding why the job failed.

## Investigation Order

### 1. Collect Failure Details

Gather:

- Job name
- Error message
- Start time
- End time
- Retry history

### 2. Classify Failure

Determine whether failure is:

- Resource-related
- Permission-related
- Configuration-related
- Data-related
- Dependency-related
- Other or unknown

### 3. Check Recent Changes

Investigate:

- Deployments
- Configuration changes
- Schema changes
- Security changes
- Infrastructure changes

### 4. Determine Blast Radius

Identify:

- Data modified by job
- Schema modified by job
- Affected users or departments
- Downstream jobs
- SLA impact
- Data correctness risk

## Safe Actions

- Collect logs
- Validate dependencies
- Escalate when root cause is unknown

## Unsafe Actions

- Retry job
- Disable job
- Force-completing jobs
- Disabling validation checks
- Modifying production data to "make it pass"
- Restarting the SQL Agent service
```

## Related content

- [Use GitHub Copilot Agent mode (preview) in SQL Server Management Studio](agent-mode.md)
- [Use MCP servers with GitHub Copilot in SQL Server Management Studio](mcp-servers.md)
- [Use custom instructions with GitHub Copilot in SQL Server Management Studio](custom-instructions.md)
- [Troubleshoot GitHub Copilot in SQL Server Management Studio](troubleshoot.md)
