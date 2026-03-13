## Submit to Claude Skills Hub

### Skill Name
Commit Analyzer

### Short Description
Analyzes Git commits to generate developer work reports with intelligent categorization, multi-project support, and flexible filtering.

### Long Description
Git Commit Analyzer is a developer-focused tool designed to automatically analyze Git commit history and generate comprehensive work reports. It intelligently categorizes commits (feat, fix, docs, test, refactor, perf, style, ci, chore), supports single and multi-project analysis, provides flexible date range queries, and offers multi-language output (English/Chinese). Perfect for daily standups, weekly team reports, and personal work tracking.

### Use Cases

- **Daily Stand-up**: Generate a quick summary of today's work with `gca --summary`
- **Weekly Team Report**: Analyze work from a specific date range and share categorized commits with team
- **Multi-Project Management**: Track work across multiple projects simultaneously with a config file and get consolidated reports
- **Personal Work Tracking**: Monitor productivity patterns with detailed categorization of commit types

### Installation

The skill is automatically available through Claude Code. Simply use:
```bash
gca --help
```

Or run directly with Node.js:
```bash
node gca.js --summary
```

### Examples

**Example 1: Today's Work Summary**
```bash
gca --summary
```
Output: Categorized commits from today grouped by type and date

**Example 2: Weekly Report**
```bash
gca --summary --after "2026-03-03" --before "2026-03-09"
```
Output: All commits from Monday to Sunday, organized by category

**Example 3: Multi-Project Analysis**
Create `projects.config.json`:
```json
{
  "projects": [
    "F:/projects/project1",
    "F:/projects/project2",
    "F:/projects/project3"
  ]
}
```
Then run:
```bash
gca --summary --config projects.config.json
```
Output: Individual reports per project plus consolidated summary

### Category
Development

### Tags
git, development, productivity, reporting, automation, multi-project, developer-tools, commit-analysis

### Repository URL
https://github.com/tqone/commit-analyzer

### Your Contact
GitHub: @tqone
