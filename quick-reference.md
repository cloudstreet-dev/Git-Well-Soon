# Git Quick Reference - Your Prescription Card

> Keep this handy for quick Git relief!

## 🏥 Essential Commands

### Setup & Configuration

```bash
# Check Git version
git --version

# Set your identity
git config --global user.name "Your Name"
git config --global user.email "you@example.com"

# Check settings
git config --list
```

### Starting a Repository

```bash
# Create new local repository
git init

# Clone existing repository
git clone https://github.com/user/repo.git

# Clone into specific folder
git clone https://github.com/user/repo.git folder-name
```

### Basic Workflow

```bash
# Check status
git status

# Add files to staging
git add filename.txt        # Specific file
git add .                   # All files
git add *.js               # All JS files

# Commit changes
git commit -m "Your message here"

# Push to remote
git push origin main
git push                    # If tracking is set

# Pull from remote
git pull origin main
git pull                    # If tracking is set
```

### Viewing Changes

```bash
# See unstaged changes
git diff

# See staged changes
git diff --staged

# View commit history
git log                     # Full history
git log --oneline          # Condensed view
git log -n 5               # Last 5 commits
git log --graph            # Visual branch structure
```

### Undoing Changes

```bash
# Discard changes in working directory
git restore filename.txt
git restore .              # All files

# Unstage files
git restore --staged filename.txt

# Amend last commit (before push)
git commit --amend -m "New message"

# Undo last commit (keep changes)
git reset HEAD~1

# Undo last commit (discard changes) - DANGEROUS
git reset --hard HEAD~1
```

### Remote Repositories

```bash
# Show remotes
git remote -v

# Add remote
git remote add origin https://github.com/user/repo.git

# Remove remote
git remote remove origin

# Change remote URL
git remote set-url origin https://github.com/user/newrepo.git
```

### Branching (Next Level)

```bash
# List branches
git branch                  # Local branches
git branch -a              # All branches

# Create branch
git branch feature-name

# Switch branch
git checkout feature-name
git switch feature-name     # Newer syntax

# Create and switch
git checkout -b feature-name

# Merge branch
git merge feature-name

# Delete branch
git branch -d feature-name  # Safe delete
git branch -D feature-name  # Force delete
```

## 💊 Common Workflows

### Start New Project

```bash
# On GitHub: Create new repository
# Locally:
mkdir project-name
cd project-name
git init
# Create files...
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/you/project.git
git push -u origin main
```

### Clone and Contribute

```bash
git clone https://github.com/user/project.git
cd project
# Make changes...
git add .
git commit -m "Add feature"
git push
```

### Daily Workflow

```bash
# Morning
git pull                    # Get latest changes

# Work...
git status                  # Check what changed
git diff                    # Review changes
git add .                   # Stage changes
git commit -m "Description" # Commit
git push                    # Share changes
```

### Fix Mistake Before Push

```bash
# Oops, wrong file committed
git reset HEAD~1           # Undo commit, keep changes
# Fix the issue...
git add .
git commit -m "Correct commit"
```

## 🚨 Emergency Commands

### "Help! I'm Lost!"

```bash
pwd                        # Where am I?
git status                 # What's happening?
git log --oneline -5       # Recent history
```

### "I Broke Everything!"

```bash
git stash                  # Save current mess
git checkout main          # Go to safe place
git stash pop             # Retrieve mess (optional)
```

### "Wrong Branch!"

```bash
git checkout main          # Go back to main
git branch                 # See where you are
```

### "Merge Conflicts!"

```bash
# Open conflicted files
# Look for <<<<<<< HEAD
# Fix conflicts manually
git add .
git commit -m "Resolve conflicts"
```

## 📊 Status Symbols

### git status meanings

- **Untracked**: New file Git doesn't know
- **Modified**: Changed but not staged
- **Staged**: Ready to commit (green)
- **Committed**: Saved in history

### File States

```
?? = Untracked
 M = Modified
A  = Added
D  = Deleted
R  = Renamed
C  = Copied
U  = Updated but unmerged
```

## 🎯 .gitignore Patterns

```gitignore
# Ignore specific file
secret.txt

# Ignore file type
*.log
*.tmp

# Ignore folder
node_modules/
build/

# Ignore everywhere
**/debug.log

# Exception (don't ignore)
!important.log
```

## 💡 Pro Tips Cheatsheet

### Aliases (Shortcuts)

```bash
# Create aliases
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.ci commit
git config --global alias.st status

# Use aliases
git st                     # Same as git status
git co main               # Same as git checkout main
```

### Useful Combinations

```bash
# Add and commit
git commit -am "Message"   # Only modified files

# Pull before push
git pull && git push

# See what changed in last commit
git show

# See who changed what
git blame filename.txt
```

## 🏥 Terminal Navigation

```bash
# Where am I?
pwd

# List files
ls                         # Basic list
ls -la                     # All files with details

# Change directory
cd folder-name             # Enter folder
cd ..                      # Go up one level
cd ~                       # Go home
cd -                       # Go to previous location

# Clear screen
clear                      # or Ctrl+L
```

## 📋 Commit Message Templates

### Good Examples

```
Add: User authentication feature
Fix: Navigation menu on mobile devices
Update: README with installation steps
Remove: Deprecated API endpoints
Refactor: Database connection logic
Test: Add unit tests for user service
Docs: Update API documentation
Style: Format code according to standards
```

### Format

```
<type>: <subject>

<body (optional)>

<footer (optional)>
```

## 🔗 Essential URLs

- **Git Documentation**: https://git-scm.com/docs
- **GitHub Docs**: https://docs.github.com
- **Interactive Tutorial**: https://learngitbranching.js.org
- **Git Cheat Sheet**: https://training.github.com/downloads/github-git-cheat-sheet/

## 🆘 Getting Help

```bash
# Git help
git help                   # General help
git help commit           # Specific command help
git commit --help         # Same thing

# Online
# Google: "git [exact error message]"
# Stack Overflow: Search first, ask if needed
```

---

**Remember**: This card covers 95% of daily Git usage. Keep it handy until these become second nature!

**Print Tip**: This page is designed to be printed and kept in your wallet or posted near your desk!

[Back to Table of Contents](README.md)