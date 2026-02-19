# Installation Guide

This guide explains how to install and use the Agent Skills - Development Team collection.

## Quick Start

### Install All Skills

The easiest way to get started is to install all skills at once:

```bash
npx skills add javalenciacai/develop-skills
```

This will:
1. Detect which AI agents you have installed (Claude Code, Cursor, GitHub Copilot, etc.)
2. Prompt you to select where to install (project or global)
3. Install all 18 skills to your selected agents
4. Make them immediately available for use

### Install Specific Skills

If you only need certain skills, you can install them individually:

```bash
# Install just the CTO orchestrator (entry point)
npx skills add javalenciacai/develop-skills --skill cto

# Install multiple specific skills
npx skills add javalenciacai/develop-skills --skill tl --skill dev --skill architect
```

## Installation Scope

### Project-Level (Default)

Installs skills to your current project directory:

```bash
npx skills add javalenciacai/develop-skills
```

Skills will be available in:
- `.agents/skills/` (GitHub Copilot, Codex, etc.)
- `.claude/skills/` (Claude Code)
- `.cursor/skills/` (Cursor)
- `.windsurf/skills/` (Windsurf)

**Best for**: Project-specific workflows, team collaboration (committed to git)

### Global Installation

Installs skills for all your projects:

```bash
npx skills add javalenciacai/develop-skills --global
# or
npx skills add javalenciacai/develop-skills -g
```

Skills will be available in:
- `~/.agents/skills/` (GitHub Copilot, Codex, etc.)
- `~/.claude/skills/` (Claude Code)
- `~/.cursor/skills/` (Cursor)
- `~/.windsurf/skills/` (Windsurf)

**Best for**: Personal productivity, consistent workflows across all projects

## Installation Methods

When installing interactively, you'll be prompted to choose:

### Symlink (Recommended)

Creates symbolic links from your agent directories to a canonical copy. Benefits:
- Single source of truth
- Easy updates (`npx skills update`)
- Saves disk space

```bash
npx skills add javalenciacai/develop-skills
# Select: Symlink
```

### Copy

Creates independent copies for each agent. Use when:
- Your filesystem doesn't support symlinks
- You want isolated versions per agent

```bash
npx skills add javalenciacai/develop-skills
# Select: Copy
```

## Target Specific Agents

Install to specific agents only:

```bash
# Install to Claude Code only
npx skills add javalenciacai/develop-skills --agent claude-code

# Install to multiple specific agents
npx skills add javalenciacai/develop-skills --agent cursor --agent github-copilot

# Non-interactive installation (CI/CD friendly)
npx skills add javalenciacai/develop-skills --all -y
```

## Skill Categories

### Complete Installation by Category

```bash
# Product Management (PM + PO + UX)
npx skills add javalenciacai/develop-skills --skill pm --skill po --skill ux

# Quality Assurance (QAL + QA + SecOps)
npx skills add javalenciacai/develop-skills --skill qal --skill qa --skill secops

# Development (TL + Architect + Dev)
npx skills add javalenciacai/develop-skills --skill tl --skill architect --skill dev

# Infrastructure (InfraLead + DevOps + DBA)
npx skills add javalenciacai/develop-skills --skill infralead --skill devops --skill dba

# Data & AI (DataLead + DataEng + AIEng)
npx skills add javalenciacai/develop-skills --skill datalead --skill dataeng --skill aieng

# Meta Skills (find-skills + skill-creator)
npx skills add javalenciacai/develop-skills --skill find-skills --skill skill-creator
```

## Managing Skills

### List Installed Skills

See what skills you have:

```bash
# List all installed skills
npx skills list

# List only global skills
npx skills list --global

# List skills for specific agents
npx skills list --agent claude-code --agent cursor
```

### Update Skills

Keep your skills up to date:

```bash
# Check for updates
npx skills check

# Update all skills
npx skills update
```

### Remove Skills

Uninstall skills you no longer need:

```bash
# Remove specific skill
npx skills remove cto

# Remove multiple skills
npx skills remove dev architect tl

# Remove from global scope
npx skills remove --global qa

# Remove from specific agents
npx skills remove --agent cursor devops
```

## Supported Agents

These skills work with all agents supporting the [Agent Skills](https://agentskills.io/) format:

| Agent | Project Path | Global Path |
|-------|-------------|-------------|
| **Claude Code** | `.claude/skills/` | `~/.claude/skills/` |
| **GitHub Copilot** | `.agents/skills/` | `~/.copilot/skills/` |
| **Cursor** | `.cursor/skills/` | `~/.cursor/skills/` |
| **Windsurf** | `.windsurf/skills/` | `~/.codeium/windsurf/skills/` |
| **Cline** | `.cline/skills/` | `~/.cline/skills/` |
| **Goose** | `.goose/skills/` | `~/.config/goose/skills/` |
| **Roo Code** | `.roo/skills/` | `~/.roo/skills/` |
| **Codex** | `.agents/skills/` | `~/.codex/skills/` |

And [30+ more agents](https://skills.sh/)

## Verification

After installation, verify the skills are available:

### Method 1: Check Filesystem

```bash
# For project installation
ls .agents/skills/     # or .claude/skills/, .cursor/skills/, etc.

# For global installation
ls ~/.agents/skills/   # or ~/.claude/skills/, ~/.cursor/skills/, etc.
```

You should see directories for each installed skill.

### Method 2: Use npx skills list

```bash
npx skills list
```

### Method 3: Test with Agent

Start your AI agent and try:

```
"What skills do you have available?"
```

Your agent should list the installed skills.

## Usage Examples

Once installed, skills activate automatically based on context:

### Product Feature

```
"Design a new authentication feature"
```

Flow: CTO → PM → PO (requirements) + UX (design) → TL → Architect + Dev

### Code Review

```
"Review this component for performance issues"
```

Flow: CTO → TL → Dev (code review)

### Security Audit

```
"Audit this code for security vulnerabilities"
```

Flow: CTO → QAL → SecOps (security audit) + QA (testing)

### Infrastructure Setup

```
"Set up a CI/CD pipeline with Docker"
```

Flow: CTO → InfraLead → DevOps

### Data Pipeline

```
"Build an ETL pipeline for customer data"
```

Flow: CTO → DataLead → DataEng

### ML Model

```
"Create a recommendation model"
```

Flow: CTO → DataLead → AIEng (model) + DataEng (data)

## Troubleshooting

### Skills Not Loading

**Problem**: Agent doesn't recognize installed skills

**Solutions**:
1. Verify installation path matches your agent's expected location
2. Check SKILL.md files have valid YAML frontmatter
3. Restart your agent/IDE
4. Try re-installing with `npx skills add <owner>/develop-skills`

### Permission Errors

**Problem**: Cannot write to installation directory

**Solutions**:
1. Use global installation: `npx skills add <owner>/develop-skills -g`
2. Check directory permissions
3. Run with appropriate permissions (avoid sudo when possible)

### Symlink Failed

**Problem**: Symlink creation failed

**Solutions**:
1. Choose "Copy" method instead of "Symlink"
2. Enable symlink support on Windows (run as administrator)
3. Use a filesystem that supports symlinks

### Skills Not Updating

**Problem**: `npx skills update` doesn't update skills

**Solutions**:
1. Check if skills were installed as copies (not symlinks)
2. Remove and reinstall: `npx skills remove <skill> && npx skills add <owner>/develop-skills --skill <skill>`
3. For symlinked skills: `cd` to the source directory and `git pull`

### Agent-Specific Issues

**Claude Code**: Skills not appearing
- Check `~/.claude/skills/` or `.claude/skills/`
- Restart Claude Code
- Verify in Settings > Skills

**Cursor**: Skills not loading
- Check `.cursor/skills/` directory
- Restart Cursor
- Look for errors in Output panel

**GitHub Copilot**: Skills not available
- Ensure agent skills feature is enabled
- Check `.agents/skills/` directory
- Update GitHub Copilot extension

## Environment Variables

### Disable Telemetry

The skills CLI collects anonymous usage data to rank skills. To opt out:

```bash
# Set environment variable
export DISABLE_TELEMETRY=1

# or
export DO_NOT_TRACK=1

# Then install
npx skills add javalenciacai/develop-skills
```

Telemetry is automatically disabled in CI environments.

### Install Internal Skills

Some skills are marked as internal (work-in-progress). To install them:

```bash
INSTALL_INTERNAL_SKILLS=1 npx skills add javalenciacai/develop-skills --list
```

## CI/CD Integration

For automated installations in CI/CD pipelines:

```bash
# Non-interactive installation
npx skills add javalenciacai/develop-skills --all -y

# Install specific skills to specific agent
npx skills add javalenciacai/develop-skills \
  --skill cto --skill dev \
  --agent github-copilot \
  --yes
```

## Upgrading from Manual Installation

If you previously installed skills manually:

1. Remove old skill directories:
   ```bash
   rm -rf .agents/skills/*
   ```

2. Install with npx:
   ```bash
   npx skills add javalenciacai/develop-skills
   ```

3. Commit the new structure to git (if project-level)

## Getting Help

- **Documentation**: [README.md](README.md)
- **Agent Guide**: [AGENTS.md](AGENTS.md)
- **Issues**: Open an issue on GitHub
- **Community**: [skills.sh](https://skills.sh/)

## Next Steps

After installation:

1. ✅ Verify skills are installed: `npx skills list`
2. ✅ Test with your agent: Ask it what skills are available
3. ✅ Try an example workflow: "Design a new feature"
4. ✅ Explore individual skills: Read `.agents/skills/*/SKILL.md`
5. ✅ Create custom skills: `npx skills init my-skill`

## Learn More

- [Agent Skills Specification](https://agentskills.io/)
- [Skills Directory](https://skills.sh/)
- [Skills CLI](https://github.com/vercel-labs/skills)
