# Chapter 9: Preventive Care - Git Hygiene

> "An ounce of prevention is worth a pound of cure... especially in Git!"

## 🏥 Treatment Goals for This Chapter

By the end of this chapter, you'll understand:
- Best practices for healthy repositories
- Common Git mistakes and how to avoid them
- The .gitignore file
- How to handle common error messages
- Daily Git hygiene habits

## 🧼 Git Hygiene Principles

Like personal hygiene, Git hygiene keeps your project healthy:

1. **Commit Often**: Small, frequent commits
2. **Clear Messages**: Descriptive commit messages
3. **Stay Synced**: Pull before push
4. **Ignore Wisely**: Use .gitignore properly
5. **Branch Carefully**: Keep main branch stable (advanced)

## 🚫 The .gitignore File: Your "Do Not Disturb" Sign

### What is .gitignore?

A special file that tells Git which files to ignore:
- Prevents accidental commits of sensitive data
- Keeps repository clean
- Avoids version controlling generated files
- Like a "Staff Only" sign on certain doors

### Common Files to Ignore

```gitignore
# Operating System Files
.DS_Store           # Mac
Thumbs.db          # Windows
*.swp              # Vim temporary files

# IDE/Editor Files
.vscode/           # VS Code settings
.idea/             # IntelliJ IDEA
*.sublime-*        # Sublime Text

# Dependencies
node_modules/      # Node.js packages
venv/             # Python virtual environment
vendor/           # PHP dependencies

# Sensitive Information
.env              # Environment variables
secrets.txt       # Any secrets file
*.key             # Private keys
config.json       # Configuration with passwords

# Build/Compiled Files
dist/             # Distribution folder
build/            # Build output
*.exe             # Executables
*.class           # Java compiled files

# Logs and Databases
*.log             # Log files
*.sqlite          # SQLite databases
```

### Creating Your .gitignore

1. In your repository root:
```bash
touch .gitignore
```

2. Edit it:
```bash
nano .gitignore
```

3. Add patterns for files to ignore

4. Commit the .gitignore:
```bash
git add .gitignore
git commit -m "Add .gitignore file"
```

### .gitignore Patterns

| Pattern | What it Ignores |
|---------|----------------|
| `file.txt` | Specific file |
| `*.log` | All .log files |
| `logs/` | Entire logs directory |
| `**/temp` | All temp directories |
| `!important.log` | Exception - don't ignore this |

## 💊 Common Git Ailments and Their Cures

### Ailment 1: "I Committed the Wrong File!"

**Symptoms**: Accidentally committed a file you shouldn't have

**Treatment** (if not pushed yet):
```bash
git reset HEAD~1
```
This undoes the last commit but keeps changes.

**Prevention**: Always check `git status` before committing

### Ailment 2: "I Wrote the Wrong Commit Message!"

**Symptoms**: Typo or wrong message in last commit

**Treatment** (if not pushed):
```bash
git commit --amend -m "Correct message"
```

**Prevention**: Review message before hitting enter

### Ailment 3: "I Want to Undo My Changes!"

**Symptoms**: Made changes you want to discard

**Treatment** (for unstaged changes):
```bash
git restore filename.txt
```
Or restore everything:
```bash
git restore .
```

**Warning**: This permanently deletes uncommitted changes!

### Ailment 4: "Git Says I Have Conflicts!"

**Symptoms**: Merge conflicts when pulling

**Treatment**:
1. Open conflicted files
2. Look for conflict markers:
```
<<<<<<< HEAD
Your changes
=======
Their changes
>>>>>>> branch-name
```
3. Edit to keep what you want
4. Remove conflict markers
5. Stage and commit

**Prevention**: Pull frequently, communicate with team

### Ailment 5: "I Committed Sensitive Data!"

**Symptoms**: Passwords, API keys in repository

**Treatment** (URGENT):
1. Change the compromised credentials immediately!
2. If not pushed: Use `git reset` to remove commit
3. If pushed: This is serious - the data is public forever
   - Still change credentials
   - Consider using git filter-branch (advanced)
   - Add to .gitignore to prevent repeat

**Prevention**: Always use .gitignore for sensitive files

## 📋 Daily Git Health Checklist

### Morning Routine
```bash
# Start your day
git pull origin main        # Get latest changes
git status                  # Check working directory
```

### Before Each Commit
```bash
git status                  # What's changed?
git diff                    # Review changes
git add .                   # Stage changes
git status                  # Verify staging
git commit -m "Clear message"
```

### End of Day
```bash
git status                  # Any uncommitted work?
git push origin main        # Push your changes
```

## 🏥 Error Message Emergency Room

### Common Error Messages and Solutions

| Error | Meaning | Solution |
|-------|---------|----------|
| "fatal: not a git repository" | Not in a git folder | Navigate to repo or `git init` |
| "Your branch is behind" | Remote has newer commits | `git pull origin main` |
| "Permission denied (publickey)" | SSH key issues | Use HTTPS or fix SSH |
| "Changes not staged for commit" | Need to add files | `git add` your files |
| "Untracked files" | New files Git doesn't know | `git add` to track them |
| "Nothing to commit" | No changes detected | Make changes first |
| "Rejected - non-fast-forward" | Remote has changes you don't | Pull first, then push |

## 🎯 Best Practices Summary

### The Golden Rules

1. **Commit Logical Units**
   - One feature/fix per commit
   - Don't mix unrelated changes

2. **Write Good Messages**
   - Present tense: "Add feature" not "Added feature"
   - Be specific but concise
   - Include "why" when not obvious

3. **Never Commit**
   - Passwords or API keys
   - Large binary files (use Git LFS)
   - Generated files (build output)
   - Personal IDE settings

4. **Always Commit**
   - Source code
   - Documentation
   - Configuration templates
   - .gitignore file

5. **Pull Before Push**
   - Avoid conflicts
   - Stay synchronized
   - Respect others' work

## 🧪 Clinical Trial #9: Health Check

Perform a complete repository health check:

### Repository Hygiene:
1. ✅ Create a .gitignore file
2. ✅ Add at least 3 ignore patterns
3. ✅ Commit the .gitignore
4. ✅ Verify ignored files don't show in `git status`

### Practice Recovery:
1. ✅ Make a change, then restore it
2. ✅ Create a commit, then amend the message
3. ✅ Successfully pull and push

### Status Check:
1. ✅ Working directory is clean
2. ✅ All changes are pushed
3. ✅ No sensitive data in repository

## 🏥 The Healthy Git Lifestyle

### Signs of a Healthy Repository

- ✅ Clean `git status` when work is done
- ✅ Meaningful commit history
- ✅ No sensitive data exposed
- ✅ Regular commits (not huge chunks)
- ✅ Synchronized with remote
- ✅ .gitignore properly configured

### Signs You Need Treatment

- ❌ Commits like "asdfgh" or "stuff"
- ❌ One massive commit per week
- ❌ Passwords in repository
- ❌ Conflicted merges everywhere
- ❌ Out of sync with team
- ❌ Fear of using Git

## 🩺 Doctor's Notes

**Remember**: Everyone makes Git mistakes. The key is learning from them and preventing recurrence.

**Pro Tip**: Use GitHub's .gitignore templates. When creating a repo, GitHub offers language-specific templates!

**Warning**: Once something is pushed to a public repository, consider it public forever, even if deleted later.

## 📋 Discharge Summary

You now know:
- ✅ How to maintain Git hygiene
- ✅ Using .gitignore effectively
- ✅ Handling common problems
- ✅ Best practices for commits
- ✅ Daily Git routines

Your preventive care training is complete!

## 🎯 Chapter Checkpoint

Before proceeding:
- ✅ You have a .gitignore file
- ✅ You understand common error messages
- ✅ You know how to undo changes
- ✅ You follow commit best practices

---

**Next**: [Chapter 10: Follow-up Appointments - Where to Go From Here](chapter10-next-steps.md)

*Hygiene Wisdom: "A clean repository is a happy repository. Commit often, push regularly, and always use .gitignore!"*