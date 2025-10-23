# Contributing to BaseProject Template

This document outlines the development workflow for maintaining and improving the BaseProject template repository.

## Branch Strategy

BaseProject uses a two-branch strategy to separate template development from user-facing distribution:

### `dev` Branch (Development)
**Purpose:** Template development, testing, and maintenance

**Contains:**
- All files from main branch
- `TemplateDocs/` - Internal template documentation
  - `NEW_PROJECT_SETUP.md` - Manual setup guide
  - `QUICK_REFERENCE.md` - Quick reference card
  - Other development/maintenance docs
- `CONTRIBUTING.md` (this file)
- Work-in-progress features
- Experimental guides and workflows

**Workflow:**
- All development work happens here first
- Test changes thoroughly before merging to main
- Can have multiple feature branches off of dev
- Safe space for iteration and experimentation

### `main` Branch (Production)
**Purpose:** Clean, minimal template for users to clone

**Contains:**
- `README.md` - Streamlined user-facing documentation
- `TEMPLATE_CLAUDE.md` - Template for project-specific instructions
- `ClaudeUsage/` - Complete workflow guide collection
- `.gitignore` - Comprehensive gitignore
- Only production-ready, user-facing files

**Workflow:**
- Only receives merges from dev when changes are stable
- Should always be in a "ready to clone" state
- Users clone from this branch by default

## Development Workflow

### 1. Making Changes

```bash
# Start on dev branch
git checkout dev
git pull origin dev

# Create feature branch (optional, for larger changes)
git checkout -b feature/your-feature-name

# Make your changes
# Test thoroughly
# Commit using conventional commits
git add .
git commit -m "feat: add new workflow guide for X"
```

### 2. Testing Changes

Before merging to main, test that the template works:

```bash
# Test the magic prompt by asking Claude Code to:
# "Clone BaseProject from dev branch to /tmp/test-project and set it up"

# Verify:
# - All files are present
# - No broken links in documentation
# - CLAUDE.md template is clear
# - Magic prompt works correctly
```

### 3. Merging to Main

Only merge to main when changes are:
- ✅ Tested and working
- ✅ Documentation is complete
- ✅ No broken links or references
- ✅ Ready for users to use immediately

```bash
# Switch to main branch
git checkout main
git pull origin main

# Merge from dev (or feature branch)
git merge dev

# Review merged changes
git diff HEAD~1

# Push to remote
git push origin main
```

### 4. Keeping Branches in Sync

After merging dev to main, make sure to:

```bash
# Remove files from main that should only be in dev
git checkout main
git rm -r TemplateDocs/
git rm CONTRIBUTING.md
git commit -m "chore: remove dev-only files from main"
git push origin main

# Switch back to dev
git checkout dev
```

## What Goes Where?

### Dev Branch Only
- `TemplateDocs/` - Template development docs
- `CONTRIBUTING.md` - This file
- Experimental features
- Draft documentation
- Testing scripts for template validation

### Main Branch Only
- Streamlined `README.md` focused on user experience

### Both Branches
- `TEMPLATE_CLAUDE.md` - Users need this
- `ClaudeUsage/` - Core workflow guides users need
- `.gitignore` - Essential for all projects
- Pre-commit hooks and templates

## Commit Message Standards

Follow conventional commits:

```
feat: add new workflow guide
fix: correct typo in git_workflow.md
docs: update README with clearer instructions
chore: update .gitignore
refactor: reorganize ClaudeUsage directory
```

## Adding New Workflow Guides

When adding a new guide to `ClaudeUsage/`:

1. Create the guide in dev branch
2. Follow the standard format (see `ClaudeUsage/documentation_standards.md`)
3. Update `ClaudeUsage/README.md` index
4. Test that examples work
5. Add cross-references to related guides
6. Merge to main when complete

## Updating Existing Guides

1. Make changes in dev branch
2. Check for any dependent guides that need updates
3. Update cross-references if guide structure changes
4. Test any code examples
5. Merge to main

## Documentation Standards

All guides should follow the format in `ClaudeUsage/documentation_standards.md`:

- Clear "When to Use" section
- Practical examples
- Common pitfalls section
- Cross-references to related guides
- Scannable headers and structure

## Testing the Template

Before merging major changes to main:

### Manual Testing
```bash
# In a test directory
cd /tmp
# Ask Claude Code:
# "Clone BaseProject from main branch, set up a new Python project called TestProject"

# Verify:
# - Setup completes without errors
# - All referenced files exist
# - Magic prompt works as expected
# - Documentation is clear
```

### Checklist
- [ ] README.md is accurate and up-to-date
- [ ] Magic prompt works from main branch
- [ ] All ClaudeUsage guides are present
- [ ] No broken internal links
- [ ] TEMPLATE_CLAUDE.md has clear instructions
- [ ] .gitignore covers common cases
- [ ] Pre-commit hooks work (if used)

## Questions or Issues?

When working on template improvements:

1. **For major changes**: Create an issue first to discuss approach
2. **For bug fixes**: Create PR directly from dev to main
3. **For documentation**: Can update directly in dev, merge when ready
4. **For new features**: Test thoroughly in dev before main merge

## Project-Specific vs Template Development

**This workflow is for BaseProject template development only.**

When users create new projects from this template, they should follow the workflow patterns described in `ClaudeUsage/git_workflow.md` and other guides. Future projects created from BaseProject can adopt their own dev/main strategy based on their needs.

## Philosophy

The goal is to keep main branch as a **clean, minimal, ready-to-use template** while allowing dev branch to be a **comprehensive development workspace**.

Users should be able to:
1. Clone from main
2. Run the magic prompt
3. Start building immediately

Without any:
- Cleanup required
- Confusion about which files to delete
- Extra documentation to wade through

Development complexity stays in dev. User simplicity lives in main.

---

**Happy template developing!** 🚀
