## 🚀 Quick Start - Use This Template

[![Use this template](https://img.shields.io/badge/Use%20this%20template-2ea44f?style=for-the-badge)](https://github.com/AutumnsGrove/BaseProject/generate)

**One-click setup:**

1. Click the green **"Use this template"** button above (or [click here](https://github.com/AutumnsGrove/BaseProject/generate))
2. Name your repository
3. GitHub Actions will automatically:
   - Rename `TEMPLATE_CLAUDE.md` → `CLAUDE.md`
   - Create a customized `TODOS.md`
   - Update `README.md` with your project name
   - Clean up template-specific files
   - Create a welcome issue with next steps

**Manual setup (if you prefer):**

```bash
# Clone and setup
git clone https://github.com/AutumnsGrove/BaseProject.git MyProject
cd MyProject
bash setup_new_project.sh
```

### What You Get

✅ **Instant project structure** - Ready-to-use layout
✅ **Claude Code optimized** - CLAUDE.md auto-loads context
✅ **16 workflow guides** - Git, testing, secrets, CI/CD, and more
✅ **Best practices built-in** - Security, code quality, documentation standards
✅ **Task management** - Integrated TODOS.md workflow

---

## To Enable Template Mode (Repository Owner)

1. Go to **Settings** → **General**
2. Scroll to **Template repository**
3. Check ✅ **Template repository**
4. Save changes

The "Use this template" button will now appear on your repository page!

---

# BaseProject - Claude Code Template

A comprehensive project template with built-in Claude Code workflows, best practices, and extensive documentation for rapid development setup.

## 🚀 Quick Start

### Option 1: New Project Setup

**One-liner in Claude Code:**
```
Clone https://github.com/AutumnsGrove/BaseProject (master branch) to /tmp, copy to ~/Projects/[ASK ME PROJECT NAME] excluding (.git/), rename TEMPLATE_CLAUDE.md to CLAUDE.md, customize CLAUDE.md sections (Project Purpose, Tech Stack, API Keys List, Architecture Notes) and README.md (title, description, features) with my project details [ASK ME: name, description, tech stack, API keys needed], init language-specific dependencies (uv for Python, npm for JS, go mod for Go), create proper directory structure (src/ with __init__.py or index.js, tests/ with __init__.py), generate secrets_template.json with my API key placeholders, write TODOS.md with 3-5 initial tasks derived from project description, git init with user.name and user.email from global git config, optionally copy pre-commit hooks from ClaudeUsage/pre_commit_hooks/ [ASK ME], make initial commit "feat: initialize [PROJECT] from BaseProject template", display project summary and next steps
```

Claude will interactively:
- Ask for project name, tech stack, and requirements
- Copy BaseProject template to your chosen location
- Customize CLAUDE.md with your project details
- Set up language-specific dependencies (pyproject.toml, package.json, etc.)
- Create proper project structure (src/, tests/)
- Generate secrets_template.json with your needed API keys
- Initialize git with proper configuration
- Create initial commit following our standards

---

### Option 2: Add to Existing Project

**For projects already in progress with existing code, documentation, and git history:**

```
Clone https://github.com/AutumnsGrove/BaseProject (master branch) to /tmp/bp, analyze my project: read existing README.md/CLAUDE.md, scan git history for commit patterns, detect tech stack and package managers, identify project architecture (monorepo/single package/etc), read TODOS.md if exists, copy ClaudeUsage/ to my project (preserve any existing ClaudeUsage/ files, only add new guides), intelligently merge CLAUDE.md: if exists parse sections and merge BaseProject sections using markers like "<!-- BaseProject: Git Workflow -->", if new create from template with detected project details, enhance .gitignore by merging entries (preserve existing, add missing), analyze commit messages and suggest adopting BaseProject style if inconsistent, check if using branches like dev/main and suggest workflow if not, optionally setup pre-commit hooks [ASK ME], generate/update TODOS.md with project-aware tasks, create integration-summary.md report showing what was added/merged/skipped, backup modified files to ./.baseproject-backup-[TIMESTAMP]/, cleanup temp directory, display next steps
```

Claude will intelligently:
- Analyze your existing project structure and conventions
- Detect tech stack from package files (package.json, pyproject.toml, etc.)
- Copy ClaudeUsage/ guides without overwriting existing files
- Merge CLAUDE.md sections with clear markers (preserves your content)
- Append missing .gitignore entries without removing existing ones
- Compare your commit style to BaseProject standards and offer suggestions
- Create backup of all modified files before making changes
- Generate integration-summary.md showing exactly what was changed
- Respect your existing README.md (won't overwrite)
- Adapt to your project's existing structure

### Manual Setup

For full control over the setup process, see [NEW_PROJECT_SETUP.md](https://github.com/AutumnsGrove/BaseProject/blob/dev/TemplateDocs/NEW_PROJECT_SETUP.md) in the dev branch for detailed step-by-step instructions.

---

## 📁 What's Included

```
BaseProject/
├── TEMPLATE_CLAUDE.md          # Main project instructions (rename to CLAUDE.md)
├── ClaudeUsage/                # Comprehensive workflow guides
│   ├── README.md               # Guide index
│   ├── git_workflow.md         # Git operations and commits
│   ├── secrets_management.md  # API key handling
│   ├── code_style_guide.md    # Code style principles
│   ├── project_setup.md       # Project initialization patterns
│   ├── uv_usage.md            # Python UV package manager
│   ├── testing_strategies.md  # Test patterns
│   ├── docker_guide.md        # Containerization
│   ├── ci_cd_patterns.md      # GitHub Actions
│   ├── house_agents.md        # Claude subagent usage
│   ├── pre_commit_hooks/      # Git hooks for code quality
│   ├── templates/             # Template files for common configs
│   └── ... (18 total guides)
└── .gitignore                  # Comprehensive gitignore
```

---

## 🏠 House Agents Integration

This template works seamlessly with [house-agents](https://github.com/houseworthe/house-agents) - specialized Claude Code sub-agents that keep your context clean.

### What Are House Agents?

Specialized sub-agents that run heavy operations in separate context windows:
- **house-research** - Search 70k+ tokens across files, return 3k summary (95% savings)
- **house-git** - Analyze 43k token diffs, return 500 token summary (98% savings)
- **house-bash** - Process 21k+ command output, return 700 token summary (97% savings)

### Quick Install

**Project-Level (this project only):**
```bash
git clone https://github.com/houseworthe/house-agents.git /tmp/house-agents
cp -r /tmp/house-agents/.claude .
```

**User-Wide (all projects):**
```bash
git clone https://github.com/houseworthe/house-agents.git /tmp/house-agents
mkdir -p ~/.claude/agents
cp /tmp/house-agents/.claude/agents/*.md ~/.claude/agents/
```

**Test Installation:**
```
Use house-research to find all TODO comments in the codebase
```

See [ClaudeUsage/house_agents.md](ClaudeUsage/house_agents.md) for usage patterns and examples.

**Credit:** House Agents by [@houseworthe](https://github.com/houseworthe/house-agents) (v0.2.0-beta)

---

## 🎯 What You Get

### Instant Best Practices
- **Git workflow patterns** - Conventional commits, proper branching
- **Security by default** - API key management, secrets handling
- **Code quality** - Pre-commit hooks, linting patterns
- **Testing strategies** - Unit, integration, and E2E test patterns
- **CI/CD templates** - GitHub Actions workflows
- **Documentation standards** - Consistent, scannable docs

### Claude-Optimized Workflows
- **House agents** - Specialized agents for research, coding, git analysis
- **Context7 integration** - Automatic library documentation fetching
- **TODO management** - Task tracking integrated into workflow
- **Subagent patterns** - Breaking down complex tasks

### Multi-Language Support
Guides and patterns for:
- Python (with UV package manager)
- JavaScript/TypeScript
- Go
- Rust
- Docker containerization

---

## 📚 Documentation Structure

All guides follow a consistent, scannable format:

1. **Overview** - What the guide covers
2. **When to Use** - Specific triggers and scenarios
3. **Core Concepts** - Key principles
4. **Practical Examples** - Real-world code
5. **Common Pitfalls** - What to avoid
6. **Related Guides** - Cross-references

See [ClaudeUsage/README.md](ClaudeUsage/README.md) for the complete index.

---

## 🛠️ Customization Workflow

After running setup:

1. **Edit CLAUDE.md** - Fill in your project specifics
   - Project purpose
   - Tech stack
   - Architecture notes

2. **Create secrets files** (if needed)
   ```bash
   # For Python projects
   cp ClaudeUsage/templates/secrets_template.json secrets_template.json
   cp secrets_template.json secrets.json
   # Edit secrets.json with real API keys
   ```

3. **Set up dependencies**
   ```bash
   # Python with UV
   uv init

   # JavaScript/Node
   npm init -y

   # Go
   go mod init yourproject
   ```

4. **Configure pre-commit hooks** (optional)
   ```bash
   cd ClaudeUsage/pre_commit_hooks/
   chmod +x pre-commit commit-msg
   cp pre-commit commit-msg ../../.git/hooks/
   ```

5. **Update TODOS.md** - Add your specific tasks

---

## 💡 Key Workflows

### Starting a New Feature
1. Check `TODOS.md` for pending tasks
2. Use Context7 to fetch relevant library docs
3. Follow git workflow for commits
4. Update TODOS.md as you progress

### Managing Secrets
1. Read `ClaudeUsage/secrets_management.md`
2. Create `secrets.json` (gitignored)
3. Provide `secrets_template.json` for team
4. Use environment variable fallbacks

### Large Codebase Search
1. Use house-research agent for 20+ file searches
2. Check `ClaudeUsage/house_agents.md` for patterns
3. Use subagents for complex multi-step tasks

### Writing Tests
1. Review `ClaudeUsage/testing_strategies.md`
2. Follow framework-specific patterns
3. Use test-strategist agent for planning

---

## 🔐 Security Defaults

This template includes security best practices by default:

- ✅ `secrets.json` in `.gitignore`
- ✅ Pre-commit hooks to prevent secret commits
- ✅ Environment variable fallback patterns
- ✅ Security audit guides in `secrets_advanced.md`

---

## 🤝 Working with Claude Code

This template is optimized for Claude Code CLI. Key features:

- **CLAUDE.md** triggers automatic context loading
- **Structured guides** for quick reference without token bloat
- **Subagent workflows** for complex tasks
- **Git commit standards** with auto-formatting

### Example Session
```bash
cd ~/Projects/MyNewProject/

# Claude automatically reads CLAUDE.md and knows your project context
claude "Add user authentication with JWT tokens"

# Claude will:
# 1. Check TODOS.md
# 2. Use Context7 to fetch JWT library docs
# 3. Implement following your git commit standards
# 4. Update TODOS.md
# 5. Commit with proper message format
```

---

## 📖 Learning Path

Recommended reading order for new projects:

1. [project_structure.md](ClaudeUsage/project_structure.md) - Directory layouts
2. [git_workflow.md](ClaudeUsage/git_workflow.md) - Version control
3. [secrets_management.md](ClaudeUsage/secrets_management.md) - API keys
4. [uv_usage.md](ClaudeUsage/uv_usage.md) - Python dependencies (if applicable)
5. [testing_strategies.md](ClaudeUsage/testing_strategies.md) - Test setup
6. [house_agents.md](ClaudeUsage/house_agents.md) - Advanced workflows

---

## 🆘 Troubleshooting

### "Git not initialized"
```bash
git init
git add .
git commit -m "Initial commit"
```

### "CLAUDE.md not found"
```bash
# Rename the template
mv TEMPLATE_CLAUDE.md CLAUDE.md

# Customize it
nano CLAUDE.md
```

### "Pre-commit hooks not working"
```bash
chmod +x ClaudeUsage/pre_commit_hooks/*
cp ClaudeUsage/pre_commit_hooks/* .git/hooks/
```

---

## 🔄 Keeping BaseProject Updated

To get updates from BaseProject while preserving your customizations:

```bash
# In your project directory
# Option 1: Manual merge of specific guides
cp /path/to/BaseProject/ClaudeUsage/new_guide.md ClaudeUsage/

# Option 2: Update all guides (careful - review diffs first)
rsync -av --exclude='CLAUDE.md' /path/to/BaseProject/ClaudeUsage/ ClaudeUsage/

# Review changes
git diff

# Commit updates
git add ClaudeUsage/
git commit -m "Update ClaudeUsage guides from BaseProject"
```

---

## 🎉 What's Next?

After setup:

1. **Customize** - Edit CLAUDE.md with your project details
2. **Explore** - Read guides in ClaudeUsage/ directory
3. **Build** - Start coding with Claude Code
4. **Iterate** - Update TODOS.md and guides as needed

---

## 📝 Contributing

Found a better pattern? Want to add a guide?

This template uses a **two-branch strategy**:
- **`master` branch** - Clean, user-facing template (you're here)
- **`dev` branch** - Template development and maintenance

### For Template Development:
1. Check out the [dev branch](https://github.com/AutumnsGrove/BaseProject/tree/dev)
2. Read [CONTRIBUTING.md](https://github.com/AutumnsGrove/BaseProject/blob/dev/CONTRIBUTING.md) for full workflow
3. Make changes in dev branch
4. Test thoroughly before merging to master

### For Quick Improvements:
1. Add your guide to `ClaudeUsage/`
2. Update `ClaudeUsage/README.md` index
3. Follow the documentation standards in `ClaudeUsage/documentation_standards.md`
4. Commit with proper message format

---

## 📄 License

This template is provided as-is for use with Claude Code. Customize freely for your projects.

---

**Last updated:** 2025-10-19
**Maintained for:** Claude Code CLI
**Guides:** 16 comprehensive workflow documents
