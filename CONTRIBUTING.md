# Contributing to Agent Skills - Development Team

Thank you for your interest in contributing! This document provides guidelines for contributing to this project.

## How to Contribute

### Reporting Issues

1. Check if the issue already exists
2. Use a clear, descriptive title
3. Provide detailed information:
   - What you expected to happen
   - What actually happened
   - Steps to reproduce
   - Your environment (agent, OS, etc.)

### Suggesting Enhancements

1. Use a clear, descriptive title
2. Explain the enhancement and its benefits
3. Provide examples of how it would be used
4. Consider if it fits within the project's scope

### Creating New Skills

Want to add a new skill to the collection? Great! Follow these steps:

#### 1. Plan Your Skill

- **Domain**: What area does it cover?
- **Purpose**: What specific problem does it solve?
- **Activation**: When should the agent use this skill?
- **Hierarchy**: Where does it fit in the organizational structure?

#### 2. Create the Skill Structure

```bash
# Create skill directory
mkdir -p .agents/skills/your-skill-name

# Create SKILL.md
npx skills init your-skill-name
```

#### 3. Write the SKILL.md

Follow this template:

```markdown
---
name: your-skill-name
description: Brief description. Use when: (1) Scenario one, (2) Scenario two, (3) Scenario three.
---

# Your Skill Name

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

- **Related Skill 1**: Location: `.agents/skills/related-skill-1/SKILL.md`
- **Related Skill 2**: Location: `.agents/skills/related-skill-2/SKILL.md`
```

#### 4. Required Elements

**YAML Frontmatter** (REQUIRED):
- `name`: lowercase-with-hyphens
- `description`: What it does and when to use it

**Content Sections**:
- Role: Brief description
- Responsibilities: Clear list
- When to Use: Specific trigger scenarios
- Workflow: Step-by-step process
- Best Practices: Guidelines
- Related Skills: Links to related skills

#### 5. Test Your Skill

Before submitting:

1. **Validate YAML**: Ensure frontmatter is valid
2. **Test locally**: 
   ```bash
   npx skills add . --skill your-skill-name
   ```
3. **Test with agent**: Ask your agent to use the skill
4. **Verify context**: Ensure instructions are clear and concise

### Making Changes to Existing Skills

#### 1. Fork and Clone

```bash
git clone https://github.com/<your-username>/develop-skills.git
cd develop-skills
```

#### 2. Create a Branch

```bash
git checkout -b feature/improve-dev-skill
```

#### 3. Make Your Changes

- Keep changes focused and atomic
- Maintain the existing structure
- Update related documentation

#### 4. Test Your Changes

```bash
# Test installation
npx skills add . --skill <modified-skill>

# Test with your agent
```

#### 5. Commit Your Changes

```bash
git add .
git commit -m "improve: enhance dev skill with TypeScript patterns"
```

Use conventional commit messages:
- `feat:` - New feature or skill
- `improve:` - Enhancement to existing skill
- `fix:` - Bug fix
- `docs:` - Documentation changes
- `refactor:` - Code restructuring
- `test:` - Test additions or changes

#### 6. Submit a Pull Request

1. Push to your fork: `git push origin feature/improve-dev-skill`
2. Open a PR on GitHub
3. Describe your changes clearly
4. Link any related issues

## Code Style Guidelines

### SKILL.md Format

- Use **YAML frontmatter** with `name` and `description`
- Use **Markdown** for content
- Use **clear headers** (##, ###)
- Use **numbered lists** for workflows
- Use **bullet points** for lists
- Use **bold** for emphasis
- Use **code blocks** with language tags

### Naming Conventions

- **Skill directories**: `lowercase-with-hyphens`
- **Skill names**: Same as directory name
- **File names**: `SKILL.md` (uppercase, exact)
- **Sections**: Title Case for ## headers

### Content Guidelines

1. **Be Concise**: Keep instructions clear and brief
2. **Be Specific**: Provide concrete examples
3. **Be Actionable**: Use imperative mood ("Do this", not "You should do this")
4. **Be Consistent**: Follow existing patterns
5. **Be Focused**: Each skill should have a clear, narrow purpose

### Description Format

Write descriptions that clearly indicate when to use the skill:

```markdown
description: Brief role description. ReportsTo if applicable. Use when: (1) First scenario, (2) Second scenario, (3) Third scenario, ...
```

## Organizational Structure

When adding skills, respect the hierarchy:

```
CTO (Entry point)
├── PM (Product) → PO, UX
├── QAL (Quality) → QA, SecOps
├── TL (Technical) → Architect, Dev
├── InfraLead (Infrastructure) → DevOps, DBA
└── DataLead (Data/AI) → DataEng, AIEng
```

### Adding New Hierarchies

If proposing a new hierarchy:
1. Explain the need
2. Show how it integrates
3. Provide examples
4. Update all related docs

## Documentation

When changing skills, update:

- [ ] The skill's SKILL.md
- [ ] README.md (if adding/removing skills)
- [ ] AGENTS.md (if changing structure)
- [ ] package.json (add to skills list)

## Testing

### Manual Testing Checklist

- [ ] YAML frontmatter is valid
- [ ] Skill installs with `npx skills add`
- [ ] Skill loads in target agents
- [ ] Instructions are clear and actionable
- [ ] No typos or grammatical errors
- [ ] Links work correctly
- [ ] Examples are accurate

### Test Installation

```bash
# Test local installation
npx skills add . --skill your-skill

# Test specific agent
npx skills add . --skill your-skill --agent claude-code

# Verify
npx skills list
```

## Pull Request Process

1. **Create PR** with clear title and description
2. **Reference issues** if applicable
3. **Wait for review** - maintainers will provide feedback
4. **Address feedback** - make requested changes
5. **Merge** - once approved, your PR will be merged

### PR Checklist

- [ ] Follows contribution guidelines
- [ ] Tests pass locally
- [ ] Documentation updated
- [ ] Commit messages follow conventions
- [ ] No merge conflicts
- [ ] Links to related issues

## Community Guidelines

- Be respectful and inclusive
- Provide constructive feedback
- Help others learn and grow
- Focus on collaboration
- Celebrate contributions

## Questions?

- Open a GitHub issue for questions
- Tag issues with `question` label
- Check existing issues first
- Be patient and respectful

## Recognition

Contributors are recognized in:
- GitHub contributors page
- Release notes for significant contributions
- README acknowledgments (for major features)

## License

By contributing, you agree that your contributions will be licensed under the MIT License.

## Thank You!

Every contribution, no matter how small, helps make this project better. Thank you for being part of the community! 🎉
