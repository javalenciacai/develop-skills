# Agent Skills - Development Team

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Skills](https://img.shields.io/badge/skills.sh-install-blue)](https://skills.sh/javalenciacai/develop-skills)
[![GitHub release](https://img.shields.io/github/v/release/javalenciacai/develop-skills)](https://github.com/javalenciacai/develop-skills/releases)

A comprehensive collection of AI agent skills organized as a virtual development team. These skills provide structured knowledge and workflows for software development tasks across all domains: product management, quality assurance, technical development, infrastructure, and data/AI.

## Installation

Install all skills with a single command:

```bash
npx skills add javalenciacai/develop-skills
```

Or install specific skills:

```bash
# Install the CTO orchestrator (entry point)
npx skills add javalenciacai/develop-skills --skill cto

# Install product management skills
npx skills add javalenciacai/develop-skills --skill pm --skill po --skill ux

# Install development skills
npx skills add javalenciacai/develop-skills --skill tl --skill architect --skill dev

# Install quality assurance skills
npx skills add javalenciacai/develop-skills --skill qal --skill qa --skill secops

# Install infrastructure skills
npx skills add javalenciacai/develop-skills --skill infralead --skill devops --skill dba

# Install data/AI skills
npx skills add javalenciacai/develop-skills --skill datalead --skill dataeng --skill aieng
```

## Available Skills

### 🎯 Orchestrators

| Skill | Description |
|-------|-------------|
| **cto** | Main entry point. Analyzes tasks and delegates to appropriate teams |
| **pm** | Product management orchestrator. Coordinates requirements and design |
| **qal** | Quality assurance orchestrator. Coordinates testing and security |
| **tl** | Technical lead orchestrator. Coordinates architecture and development |
| **infralead** | Infrastructure orchestrator. Coordinates DevOps and database management |
| **datalead** | Data/AI orchestrator. Coordinates data engineering and AI/ML models |

### 📋 Product Management

| Skill | Description |
|-------|-------------|
| **po** | Product Owner. Defines requirements, user stories, and acceptance criteria |
| **ux** | UX Designer. Creates interfaces, wireframes, and defines user experience |

### ✅ Quality Assurance

| Skill | Description |
|-------|-------------|
| **qa** | Quality Assurance. Designs tests, validates acceptance criteria, reports bugs |
| **secops** | Security Operations. Performs security audits and vulnerability assessments |

### 💻 Development

| Skill | Description |
|-------|-------------|
| **architect** | Software Architect. Designs architecture and makes technical decisions |
| **dev** | Developer. Implements features, writes tests, and fixes bugs |

### 🚀 Infrastructure

| Skill | Description |
|-------|-------------|
| **devops** | DevOps Engineer. Manages Docker, CI/CD, and deployments |
| **dba** | Database Administrator. Manages databases, optimization, and backups |

### 📊 Data & AI

| Skill | Description |
|-------|-------------|
| **dataeng** | Data Engineer. Builds data pipelines, ETL, and data warehousing |
| **aieng** | AI Engineer. Develops AI/ML models, MLOps, and LLM integration |

### 🔧 Meta Skills

| Skill | Description |
|-------|-------------|
| **find-skills** | Helps discover and install additional agent skills |
| **skill-creator** | Guide for creating new skills |

## Usage

Once installed, the skills are automatically available to your AI agent. The **cto** skill acts as the main entry point and will delegate tasks to the appropriate specialized skills.

### Examples

```bash
"Design a new authentication feature"
# → CTO delegates to PM (requirements) → UX (design) → TL (architecture) → Dev (implementation)

"Review this code for security issues"
# → CTO delegates to QAL → SecOps (security audit) → QA (testing)

"Set up a CI/CD pipeline"
# → CTO delegates to InfraLead → DevOps (pipeline setup)

"Build a recommendation engine"
# → CTO delegates to DataLead → AIEng (ML model) → DataEng (data pipeline)
```

## How It Works

This skill collection follows an organizational hierarchy:

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

Each skill:
- Has clear domain boundaries
- Knows when to activate
- Can coordinate with related skills
- Provides structured workflows and best practices

## Skill Structure

Each skill is organized as:

```
.agents/skills/
└── {skill-name}/
    └── SKILL.md      # Skill definition with YAML frontmatter
```

Every `SKILL.md` contains:
- **name**: Unique identifier
- **description**: When and how to use the skill
- Instructions and workflows specific to that role

## Supported Agents

These skills work with all agents that support the [Agent Skills](https://agentskills.io/) format, including:

- Claude Code
- GitHub Copilot
- Cursor
- Windsurf
- Cline
- And [35+ more agents](https://skills.sh)

## Contributing

Want to add or improve a skill? Follow these guidelines:

1. Each skill must have a `SKILL.md` with proper YAML frontmatter
2. Use clear, descriptive names (lowercase, hyphens)
3. Define specific use cases in the description
4. Include structured workflows and best practices

## License

MIT

## Learn More

- [Agent Skills Specification](https://agentskills.io/)
- [Skills Directory](https://skills.sh/)
- [Creating Skills Guide](https://skills.sh/docs)

---

## 🏷️ Repository Topics

When configuring on GitHub, add these topics for better discoverability:

**Required:** `agent-skills`, `ai-agents`

**Recommended:** `development`, `orchestration`, `devops`, `architecture`, `product-management`, `qa-testing`, `security`, `data-engineering`, `machine-learning`, `claude-code`, `github-copilot`, `cursor`

See [GITHUB-SETUP.md](GITHUB-SETUP.md) for complete setup instructions.
