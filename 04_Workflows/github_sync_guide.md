# GitHub Sync Guide

## Overview
Keep your Obsidian vault synchronized with GitHub for backup and collaboration.

## Initial Setup

### 1. Install Git
```bash
# macOS
brew install git

# Verify installation
git --version
```

### 2. Configure Git
```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

### 3. Initialize Repository
```bash
cd /path/to/your/vault
git init
git add .
git commit -m "Initial commit"
```

### 4. Connect to GitHub
```bash
git remote add origin https://github.com/username/repo-name.git
git branch -M main
git push -u origin main
```

## Daily Workflow

### Commit Changes
```bash
git add .
git commit -m "Update notes"
git push
```

### Pull Updates
```bash
git pull origin main
```

## Automated Sync Options

### Option 1: Git Plugin
- Install Obsidian Git plugin
- Configure auto-commit settings
- Set sync interval

### Option 2: Shell Script
Create a sync script:
```bash
#!/bin/bash
cd /path/to/vault
git add .
git commit -m "Auto-sync $(date)"
git push
```

### Option 3: Cron Job
```bash
# Edit crontab
crontab -e

# Add sync every hour
0 * * * * /path/to/sync-script.sh
```

## Best Practices
- Commit frequently with descriptive messages
- Use .gitignore for sensitive files
- Create branches for experimental work
- Regular backups beyond Git

## Files to Ignore
Create `.gitignore`:
```
.obsidian/workspace*
.obsidian/cache
.DS_Store
*.tmp
```

## Troubleshooting

### Merge Conflicts
```bash
git status
# Edit conflicting files
git add .
git commit -m "Resolve conflicts"
git push
```

### Reset to Last Commit
```bash
git reset --hard HEAD
```

## Related
- [[productivity_tips]]
- [[obsidian_publish_workflow]]
