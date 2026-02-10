# Publishing to skills.sh

This guide explains how to publish your skills repository to make it available on [skills.sh](https://skills.sh/) and installable via npx.

## Prerequisites

1. ✅ GitHub account
2. ✅ Git installed
3. ✅ Skills repository ready (you're here!)

## Step-by-Step Publishing

### 1. Update Repository Information

Replace placeholder text with your actual information:

**In `README.md`:**
- Replace `<your-github-username>` with your GitHub username

**In `package.json`:**
- Replace `<your-github-username>` with your GitHub username
- Update `author` field with your name
- Verify `homepage`, `repository`, and `bugs` URLs

**In `INSTALLATION.md`:**
- Replace `<your-github-username>` with your GitHub username

### 2. Create GitHub Repository

```bash
# Initialize git (if not already done)
git init

# Add all files
git add .

# Commit
git commit -m "feat: initial release of agent skills development team"

# Create repository on GitHub (via web or CLI)
# Then add remote
git remote add origin https://github.com/<your-username>/develop-skills.git

# Push to GitHub
git branch -M main
git push -u origin main
```

### 3. Make Repository Public

Ensure your repository is **public**:

1. Go to repository Settings on GitHub
2. Scroll to "Danger Zone"
3. Click "Change visibility"
4. Select "Make public"

### 4. Add Repository Topics

Add relevant topics to help users discover your skills:

1. Go to your repository on GitHub
2. Click the ⚙️ gear icon next to "About"
3. Add topics:
   - `agent-skills`
   - `ai-agents`
   - `claude-code`
   - `github-copilot`
   - `cursor`
   - `development`
   - `orchestration`

### 5. Test Installation

Test that your skills can be installed:

```bash
# Test with your actual username
npx skills add <your-github-username>/develop-skills --list

# Test full installation
npx skills add <your-github-username>/develop-skills
```

### 6. Automatic Indexing

Your skills will automatically appear on [skills.sh](https://skills.sh/) when:

1. ✅ Repository is public on GitHub
2. ✅ Skills have valid SKILL.md files with YAML frontmatter
3. ✅ Users start installing your skills with `npx skills add`

The ranking system is based on anonymous telemetry of installation counts.

## What Gets Indexed

The `npx skills` CLI automatically discovers skills in these locations:

- ✅ `.agents/skills/` (your structure)
- ✅ `skills/`
- ✅ `.claude/skills/`
- ✅ Root directory (if SKILL.md exists)

Each SKILL.md must have:

```yaml
---
name: skill-name
description: Clear description with use cases
---
```

## Verification

After publishing, verify everything works:

### ✅ Checklist

- [ ] Repository is public on GitHub
- [ ] All `<your-github-username>` placeholders are replaced
- [ ] `package.json` has correct URLs and author
- [ ] Skills install with: `npx skills add <username>/develop-skills`
- [ ] Individual skills work: `npx skills add <username>/develop-skills --skill cto`
- [ ] Skills list correctly: `npx skills add <username>/develop-skills --list`

### Test Commands

```bash
# List available skills
npx skills add <your-github-username>/develop-skills --list

# Install specific skill
npx skills add <your-github-username>/develop-skills --skill cto

# Install all skills
npx skills add <your-github-username>/develop-skills

# Verify installation
npx skills list
```

## Promoting Your Skills

### README Badge

Add a badge to your README:

```markdown
[![Install with npx](https://img.shields.io/badge/install-npx_skills-blue)](https://skills.sh/<your-username>/develop-skills)
```

### Share on Social Media

Share your skills:

```
🚀 Just published a comprehensive agent skills collection!

18 specialized skills for AI coding agents:
✅ Product Management (PM, PO, UX)
✅ Development (Architect, Dev, TL)
✅ Quality (QA, SecOps, QAL)
✅ Infrastructure (DevOps, DBA, InfraLead)
✅ Data/AI (DataEng, AIEng, DataLead)

Install: npx skills add <username>/develop-skills

Works with Claude Code, GitHub Copilot, Cursor, and 30+ agents!

#AI #Agents #Development
```

### Add to Skills Ecosystem

Your skills will appear on:
- [skills.sh](https://skills.sh/) leaderboard (based on installs)
- GitHub search results
- Skills CLI search: `npx skills find`

## Updating Published Skills

### Making Updates

```bash
# Make your changes
git add .
git commit -m "improve: enhance architect skill with new patterns"
git push

# Users can update with:
npx skills update
```

### Versioning

Follow semantic versioning in `package.json`:

- **MAJOR** (1.0.0 → 2.0.0): Breaking changes
- **MINOR** (1.0.0 → 1.1.0): New features, backward compatible
- **PATCH** (1.0.0 → 1.0.1): Bug fixes

Update `CHANGELOG.md` with each release.

## Monitoring

### Track Installations

While the CLI collects anonymous telemetry, you can monitor:

1. **GitHub Stars**: Indicator of interest
2. **GitHub Forks**: Community engagement
3. **GitHub Issues**: User feedback
4. **skills.sh Ranking**: Installation-based ranking

### Getting Feedback

Encourage users to:
- Star the repository
- Open issues for bugs/improvements
- Submit PRs for contributions
- Share use cases and examples

## Troubleshooting Publishing

### Skills Not Installing

**Issue**: `npx skills add` doesn't find skills

**Solution**:
- Verify repository is public
- Check SKILL.md files have valid YAML
- Ensure skills are in `.agents/skills/` directory
- Test with full GitHub URL: `npx skills add https://github.com/<user>/<repo>`

### Skills Not Appearing on skills.sh

**Issue**: Skills not showing on leaderboard

**Why**: Skills appear after users install them (telemetry-based ranking)

**Timeline**: Can take time to appear based on installation volume

### Invalid YAML Error

**Issue**: YAML frontmatter validation fails

**Solution**:
- Verify `---` on lines 1 and 4 (or after description)
- Ensure `name:` and `description:` are present
- Check for proper YAML syntax
- Test locally: `npx skills add .`

## Support

Questions or issues?

- GitHub Issues: Open an issue on your repository
- Skills.sh Docs: [https://skills.sh/docs](https://skills.sh/docs)
- Skills CLI: [https://github.com/vercel-labs/skills](https://github.com/vercel-labs/skills)

## Next Steps

After publishing:

1. 🎉 Celebrate! Your skills are now public
2. 📢 Share with the community
3. 📊 Monitor usage and feedback
4. 🔄 Iterate based on user input
5. 🤝 Welcome contributions

## Learn More

- [Agent Skills Specification](https://agentskills.io/)
- [Skills Directory](https://skills.sh/)
- [Skills CLI Documentation](https://github.com/vercel-labs/skills)
- [Agent Skills Best Practices](https://skills.sh/docs)
