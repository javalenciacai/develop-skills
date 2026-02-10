# AGENTS.md

This file provides guidance to AI coding agents (Claude Code, Cursor, GitHub Copilot, etc.) when working with code in this repository.

## Repository Overview

A comprehensive collection of AI agent skills organized as a virtual development team. These skills provide structured knowledge and workflows for software development tasks across all domains: product management, quality assurance, technical development, infrastructure, and data/AI.

### Key Features

- **Hierarchical Organization**: Skills are organized in a clear organizational structure
- **Entry Point Pattern**: All tasks flow through the CTO orchestrator
- **Specialized Domains**: Each skill has clear domain boundaries
- **Cross-Agent Compatibility**: Works with 35+ AI coding agents

## Skill Architecture

### Organizational Structure

```
CTO (Entry point)
├── PM (Product)
│   ├── PO (Requirements)
│   └── UX (Design)
├── QAL (Quality)
│   ├── QA (Testing)
│   └── SecOps (Security)
├── TL (Technical)
│   ├── Architect (Architecture)
│   └── Dev (Development)
├── InfraLead (Infrastructure)
│   ├── DevOps (CI/CD)
│   └── DBA (Databases)
└── DataLead (Data/AI)
    ├── DataEng (Pipelines)
    └── AIEng (AI/ML Models)
```

### Directory Structure

```
.agents/
└── skills/
    ├── cto/
    │   └── SKILL.md
    ├── pm/
    │   └── SKILL.md
    ├── po/
    │   └── SKILL.md
    ├── ux/
    │   └── SKILL.md
    ├── qal/
    │   └── SKILL.md
    ├── qa/
    │   └── SKILL.md
    ├── secops/
    │   └── SKILL.md
    ├── tl/
    │   └── SKILL.md
    ├── architect/
    │   └── SKILL.md
    ├── dev/
    │   └── SKILL.md
    ├── infralead/
    │   └── SKILL.md
    ├── devops/
    │   └── SKILL.md
    ├── dba/
    │   └── SKILL.md
    ├── datalead/
    │   └── SKILL.md
    ├── dataeng/
    │   └── SKILL.md
    ├── aieng/
    │   └── SKILL.md
    ├── find-skills/
    │   └── SKILL.md
    └── skill-creator/
        └── SKILL.md
```

## Skill Format

Each skill follows the standardized [Agent Skills](https://agentskills.io/) format:

### SKILL.md Structure

```markdown
---
name: skill-name
description: Brief description including when to use this skill
---

# Skill Title

Detailed instructions for the agent...

## When to Use

Specific scenarios where this skill should be activated.

## Responsibilities

What this skill handles.

## Workflow

Step-by-step process.
```

### Required Fields

- **name**: Unique identifier (lowercase, hyphens allowed)
- **description**: Brief explanation including trigger conditions

### Optional Metadata

```yaml
---
name: skill-name
description: Description text
metadata:
  internal: true  # Hide from normal discovery
---
```

## Working with These Skills

### For AI Agents

When working with this repository:

1. **Entry Point**: Always start with the `cto` skill
2. **Task Analysis**: CTO analyzes the task and delegates to appropriate orchestrators
3. **Specialization**: Orchestrators delegate to specialized skills
4. **Coordination**: Skills can reference each other for complex workflows

### Delegation Pattern

```
User Request
    ↓
CTO analyzes domain
    ↓
Delegates to orchestrator (PM/QAL/TL/InfraLead/DataLead)
    ↓
Orchestrator delegates to specialist (PO/UX/QA/SecOps/etc.)
    ↓
Specialist executes with domain expertise
```

### Example Workflows

#### Product Feature Development

```
"Design and implement a new authentication feature"
    ↓
CTO → PM (product strategy)
    ↓
PM → PO (requirements) + UX (design)
    ↓
CTO → TL (technical implementation)
    ↓
TL → Architect (architecture) + Dev (code)
    ↓
CTO → QAL (quality validation)
    ↓
QAL → QA (testing) + SecOps (security audit)
```

#### Infrastructure Setup

```
"Set up CI/CD with Docker"
    ↓
CTO → InfraLead (infrastructure)
    ↓
InfraLead → DevOps (CI/CD setup)
```

#### AI/ML Project

```
"Build a recommendation engine"
    ↓
CTO → DataLead (data/AI)
    ↓
DataLead → AIEng (model) + DataEng (pipeline)
```

## Installation

### For End Users

```bash
# Install all skills
npx skills add <owner>/develop-skills

# Install specific skill
npx skills add <owner>/develop-skills --skill cto

# Install specific domain
npx skills add <owner>/develop-skills --skill tl --skill architect --skill dev
```

### For Agent Configuration

Most agents automatically discover skills in:
- `.agents/skills/` (project-level)
- `~/.agents/skills/` (global)

Some agents use different paths:
- Claude Code: `.claude/skills/`
- Cursor: `.cursor/skills/`
- GitHub Copilot: `.agents/skills/`

The `npx skills add` command handles this automatically.

## Creating New Skills

### Quick Start

```bash
# Create new skill template
npx skills init my-new-skill
```

### Naming Conventions

- **Skill directory**: `kebab-case` (e.g., `data-pipeline`, `api-design`)
- **SKILL.md**: Always uppercase, always this exact filename
- **Skill name**: lowercase with hyphens in YAML frontmatter

### Best Practices

1. **Clear Domain**: Each skill should have a clear, specific purpose
2. **Trigger Phrases**: Include specific trigger phrases in description
3. **Workflow Steps**: Provide structured, numbered workflows
4. **Cross-References**: Link to related skills when appropriate
5. **Context Efficiency**: Keep SKILL.md focused, reference external docs when needed

### Example Skill Template

```markdown
---
name: my-skill
description: Brief description. Use when: (1) Scenario one, (2) Scenario two, (3) Scenario three.
---

# My Skill Name

## Role

What this skill does.

## Responsibilities

- Responsibility 1
- Responsibility 2
- Responsibility 3

## When to Use

Detailed scenarios where this skill should activate.

## Workflow

1. Step one
2. Step two
3. Step three

## Best Practices

- Practice 1
- Practice 2

## Related Skills

- **Related Skill 1**: When to use
- **Related Skill 2**: When to use
```

## Compatibility

These skills are compatible with all agents supporting the [Agent Skills](https://agentskills.io/) specification:

- Claude Code
- GitHub Copilot
- Cursor
- Windsurf
- Cline
- Goose
- Roo Code
- And 30+ more

See [skills.sh](https://skills.sh/) for the complete list.

## Skill Discovery

The `npx skills add` CLI automatically discovers skills in these locations:

- `.agents/skills/`
- `skills/`
- `.claude/skills/`
- `.cursor/skills/`
- Root directory (if SKILL.md exists)

## Contributing

### Adding a New Skill

1. Create a new directory in `.agents/skills/`
2. Add `SKILL.md` with proper YAML frontmatter
3. Define clear use cases and workflows
4. Update this AGENTS.md if needed
5. Test the skill with your agent

### Updating Existing Skills

1. Maintain backward compatibility
2. Update version info if significant changes
3. Test with multiple agents
4. Document breaking changes

## Troubleshooting

### Skill Not Loading

- Verify YAML frontmatter is valid
- Ensure `name` and `description` fields are present
- Check file is named exactly `SKILL.md` (uppercase)
- Confirm directory structure matches expected paths

### Skills Conflict

- Skills should have unique, non-overlapping domains
- Orchestrator skills handle delegation
- Specialist skills focus on execution

### Agent-Specific Issues

- **Claude Code**: Ensure skills are in `~/.claude/skills/` or `.claude/skills/`
- **Cursor**: Check `.cursor/skills/` directory
- **GitHub Copilot**: Verify `.agents/skills/` path

## Meta Skills

### find-skills

Helps discover and install additional agent skills from the ecosystem.

**Use when**: "Find a skill for...", "Is there a skill that...", "Install skills for..."

### skill-creator

Guide for creating new skills with proper structure and format.

**Use when**: "Create a new skill", "How do I make a skill", "Design a skill for..."

## License

MIT

## Learn More

- [Agent Skills Specification](https://agentskills.io/)
- [Skills Directory](https://skills.sh/)
- [Skills CLI Documentation](https://github.com/vercel-labs/skills)
