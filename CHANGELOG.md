# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.0.0] - 2026-02-10

### Added

- Initial release of Agent Skills - Development Team
- 18 comprehensive agent skills organized in hierarchical structure
- Skills.sh compatibility with npx installation support
- Complete documentation (README, AGENTS.md, INSTALLATION.md, CONTRIBUTING.md)
- MIT License
- Package.json with metadata and skill declarations

### Skills Included

**Orchestrators:**
- `cto` - Main entry point and task analyzer
- `pm` - Product management orchestrator
- `qal` - Quality assurance orchestrator  
- `tl` - Technical lead orchestrator
- `infralead` - Infrastructure orchestrator
- `datalead` - Data/AI orchestrator

**Product Management:**
- `po` - Product Owner (requirements, user stories)
- `ux` - UX Designer (interfaces, wireframes)

**Quality Assurance:**
- `qa` - Quality Assurance (testing, validation)
- `secops` - Security Operations (audits, DevSecOps)

**Development:**
- `architect` - Software Architect (architecture, patterns)
- `dev` - Developer (implementation, coding)

**Infrastructure:**
- `devops` - DevOps Engineer (CI/CD, Docker)
- `dba` - Database Administrator (databases, optimization)

**Data & AI:**
- `dataeng` - Data Engineer (pipelines, ETL)
- `aieng` - AI Engineer (ML models, LLM integration)

**Meta Skills:**
- `find-skills` - Skill discovery helper
- `skill-creator` - Skill creation guide

### Documentation

- README.md with complete overview and quick start
- AGENTS.md for AI agent compatibility
- INSTALLATION.md with detailed installation guide
- CONTRIBUTING.md with contribution guidelines
- CHANGELOG.md for version tracking
- LICENSE (MIT)

### Structure

- Organized in `.agents/skills/` for universal compatibility
- Each skill has proper YAML frontmatter (name + description)
- Clear hierarchical organization
- Support for 35+ AI coding agents

## [Unreleased]

### Planned

- Additional specialized skills (frontend, backend, testing frameworks)
- Integration examples and templates
- Video tutorials and guides
- Community skill contributions
- Tool integrations (Linear, Notion, Jira, etc.)
