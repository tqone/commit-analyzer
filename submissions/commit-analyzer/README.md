# Commit Analyzer

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Platform: Windows | macOS | Linux](https://img.shields.io/badge/Platform-Windows%20%7C%20macOS%20%7C%20Linux-blue.svg)](#)
[![Git Requirement: 2.0+](https://img.shields.io/badge/Git-2.0%2B-red.svg)](https://git-scm.com)

Developer-focused Git commit analysis tool for generating work reports with intelligent categorization and multi-project support.

**🎯 When to Use This Skill:**
- User requests to summarize development work for a specific day (e.g., "what did I do today?")
- User wants a weekly or monthly report (e.g., "generate my weekly report for March 3-9")
- User asks to summarize work in a specific date range (e.g., "summarize my February development")
- User requests multi-project analysis of their work (e.g., "analyze all my projects")

## 🎯 Quick Start

```bash
# View today's commits
gca --summary

# Generate weekly report
gca --summary --after "2026-03-03" --before "2026-03-09"

# Analyze all projects
gca --summary --config projects.config.json

# Get help
gca --help
```

## ✨ Key Features

- 📊 **Instant Reports**: Generate daily, weekly, and monthly work summaries
- 🎯 **Smart Categorization**: Automatically classify commits (feat, fix, docs, test, refactor, etc.)
- 👥 **Multi-Project Support**: Analyze multiple projects with individual and summary reports
- 🌍 **Multi-Language**: Output in English or Chinese
- ⚙️ **Flexible Filtering**: Date ranges, merge commits, project selection
- 🧠 **Intelligent Inference**: Non-standard commits auto-classified by file patterns

## 📖 Documentation

For complete documentation, see [SKILL.md](./SKILL.md):

- Installation guide
- 6 detailed use case scenarios
- Parameters reference
- Configuration file format
- Best practices and common pitfalls
- FAQ section

## 💡 Common Usage Examples

### Daily Stand-Up
```bash
gca --summary
```

### Weekly Report for Team
```bash
gca --summary --after "2026-03-03" --before "2026-03-09"
```

### Multi-Project Summary
```bash
gca --summary --config projects.config.json
```

### Specific Date Analysis
```bash
gca --summary --after "2026-03-06" --before "2026-03-06"
```

### Exclude Merge Commits
```bash
gca --summary --exclude-merge
```

### Generate in Chinese
```bash
gca --summary --lang zh
```

## 🔧 Requirements

- **Node.js**: 14.0+
- **Git CLI**: 2.0+
- **Platform**: Windows, macOS, or Linux

## 📋 Configuration

Create `projects.config.json` for multi-project analysis:

```json
{
  "description": "My project repositories",
  "projects": [
    "F:/projects/project1",
    "F:/projects/project2",
    "F:/projects/project3"
  ]
}
```

## 🎯 Use Cases

| Scenario | Command |
|----------|---------|
| Today's work | `gca --summary` |
| Weekly report | `gca --summary --after "2026-03-03" --before "2026-03-09"` |
| Monthly summary | `gca --summary --all` |
| All projects | `gca --summary --config projects.config.json` |
| Specific date | `gca --summary --after "2026-03-06" --before "2026-03-06"` |
| English output | `gca --summary --lang en` |

## ⚙️ Parameters

| Parameter | Type | Purpose |
|-----------|------|---------|
| `--summary` | flag | Enable statistics mode (required) |
| `--all` | flag | Analyze all commits from current user |
| `--after` | date | Analysis start date (YYYY-MM-DD) |
| `--before` | date | Analysis end date (YYYY-MM-DD) |
| `--config` | path | Multi-project configuration file |
| `--lang` | string | Output language (en/zh) |
| `--exclude-merge` | flag | Exclude merge commits |
| `--include-files` | flag | Include file list per commit |

## 📊 Output Example

```
============================================================
📊 Git Commit Statistics Report
👤 User: John Developer
📈 Total: 9 commits
============================================================

🐛 Bug Fixes (3)
  📅 2026-03-06
    1. fix: Resolve code diff calculation
    2. fix: Fix marketing campaign lottery issue

✨ Features (1)
  📅 2026-03-06
    1. feat: Add toggle for lottery prize slot

🔀 Merge Commits (5)
  📅 2026-03-06
    1. Merge branch 'feature-xxx' into main
```

## ❓ FAQ

**Q: What commits are analyzed by default?**
A: Today's commits from the current Git user.

**Q: How do I change the user being analyzed?**
A: Use `git config user.name "Name"` for current project or `--global` for all projects.

**Q: What's the maximum date range?**
A: 30 days per query. For larger ranges, use `--all` or multiple queries.

**Q: How do I analyze a specific branch?**
A: Switch branch first: `git checkout branch-name`, then run the command.

**Q: Can I export the report?**
A: Output can be redirected: `gca --summary > report.txt`

For more FAQ, see [SKILL.md](./SKILL.md#-faq).

## 🏆 Best Practices

✅ **Do:**
- Use Conventional Commits format for better categorization
- Generate daily summaries to track work progress
- Create `projects.config.json` for multi-project teams
- Check commit messages for accuracy

❌ **Don't:**
- Use `--all` by default (today's commits are sufficient)
- Query beyond 30-day spans without `--all`
- Forget to switch Git user when needed
- Rely on non-standard commit messages

## 🔗 Resources

- [Full Documentation](./SKILL.md)
- [Conventional Commits](https://www.conventionalcommits.org/)

## 📧 Support

- Report issues on GitHub
- Check FAQ above or in [SKILL.md](./SKILL.md)

---

**Version**: 1.0.0
**Release Date**: 2026-03-12
**License**: MIT
