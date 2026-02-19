# GitHub Configuration Checklist

After pushing your repository to GitHub, complete these steps to ensure it's properly indexed on skills.sh:

## ✅ Step 1: Add Repository Description

1. Go to your repository: https://github.com/javalenciacai/develop-skills
2. Click the ⚙️ gear icon next to "About"
3. Add description:
   ```
   Comprehensive collection of AI agent skills organized as a virtual development team. 18 specialized skills for product, quality, development, infrastructure, and data/AI.
   ```
4. Add website (optional):
   ```
   https://skills.sh/javalenciacai/develop-skills
   ```

## ✅ Step 2: Add Topics

In the same "About" section, add these topics:

**Required Topics:**
- `agent-skills`
- `ai-agents`

**Recommended Topics:**
- `development`
- `orchestration`
- `devops`
- `architecture`
- `product-management`
- `qa-testing`
- `security`
- `data-engineering`
- `machine-learning`
- `claude-code`
- `github-copilot`
- `cursor`

**Add topics by:**
1. Click "⚙️" next to "About"
2. In "Topics" field, type each topic
3. Press Enter after each one
4. Click "Save changes"

## ✅ Step 3: Create Initial Release

1. Go to "Releases" section
2. Click "Create a new release"
3. Click "Choose a tag" → type `v1.0.0` → "Create new tag: v1.0.0 on publish"
4. Release title: `Agent Skills - Development Team v1.0.0`
5. Description:
   ```markdown
   ## 🎉 Initial Release
   
   Comprehensive collection of 18 AI agent skills organized as a virtual development team.
   
   ### 📦 What's Included
   
   **Orchestrators (6):**
   - CTO, PM, QAL, TL, InfraLead, DataLead
   
   **Specialists (12):**
   - Product: PO, UX
   - Quality: QA, SecOps
   - Development: Architect, Dev
   - Infrastructure: DevOps, DBA
   - Data/AI: DataEng, AIEng
   - Meta: find-skills, skill-creator
   
   ### 🚀 Installation
   
   ```bash
   npx skills add javalenciacai/develop-skills
   ```
   
   ### 🤖 Compatible With
   
   Claude Code, GitHub Copilot, Cursor, Windsurf, Cline, and 30+ more agents.
   
   ### 📚 Documentation
   
   - [README](https://github.com/javalenciacai/develop-skills#readme)
   - [Installation Guide](INSTALLATION.md)
   - [Contributing](CONTRIBUTING.md)
   - [Publishing Guide](PUBLISHING.md)
   
   See [CHANGELOG.md](CHANGELOG.md) for detailed changes.
   ```
6. Click "Publish release"

## ✅ Step 4: Verify Installation

Test that your skills can be installed:

```bash
# List available skills
npx skills add javalenciacai/develop-skills --list

# Install all skills
npx skills add javalenciacai/develop-skills

# Verify
npx skills list
```

## ✅ Step 5: Monitor Indexing

Your repository will appear on skills.sh after:

1. ✅ Repository is public
2. ✅ Skills have valid YAML frontmatter
3. ✅ Users start installing via `npx skills add`

**Check status:**
- Visit: https://skills.sh/javalenciacai/develop-skills
- Search: https://skills.sh/ (search for "develop-skills")

## ✅ Step 6: Share Your Skills

Once indexed, share on social media:

```
🚀 Just published "Agent Skills - Development Team"!

18 specialized AI agent skills for:
✅ Product Management (PM, PO, UX)
✅ Quality Assurance (QAL, QA, SecOps)
✅ Development (TL, Architect, Dev)
✅ Infrastructure (InfraLead, DevOps, DBA)
✅ Data & AI (DataLead, DataEng, AIEng)

Install with one command:
npx skills add javalenciacai/develop-skills

Works with Claude Code, GitHub Copilot, Cursor & 30+ agents!

#AIAgents #Development #Automation
```

## 📋 Final Verification Checklist

Before announcing your release:

- [ ] Repository is public
- [ ] Description added
- [ ] Topics configured (minimum: agent-skills, ai-agents)
- [ ] Release v1.0.0 created
- [ ] Installation tested: `npx skills add javalenciacai/develop-skills`
- [ ] Skills list correctly: `npx skills add javalenciacai/develop-skills --list`
- [ ] All SKILL.md files have valid YAML
- [ ] README links work
- [ ] LICENSE is present

## 🎯 Expected Timeline

- **Immediate**: Installation via npx works
- **1-2 hours**: GitHub indexes new release
- **1-7 days**: Appears on skills.sh (based on installation count)

## 🆘 Troubleshooting

### Not Installing
**Issue**: `npx skills add` fails

**Fix**:
- Verify repository is public
- Check SKILL.md YAML frontmatter
- Try full URL: `npx skills add https://github.com/javalenciacai/develop-skills`

### Not on skills.sh
**Issue**: Doesn't appear on leaderboard

**Why**: skills.sh ranks by installation count (anonymous telemetry)

**Solution**: Share your skills to increase installations

### Topics Not Showing
**Issue**: Topics don't appear on repo

**Fix**:
- Must be added through GitHub UI (About section)
- Cannot be added via git commits

## 📚 Resources

- [Skills.sh Documentation](https://skills.sh/docs)
- [Agent Skills Specification](https://agentskills.io/)
- [Skills CLI](https://github.com/vercel-labs/skills)
