# Exercise 3: Git Hygiene

> Learn to keep your repository clean and healthy!

## 🎯 Learning Objectives

- Create and use .gitignore
- Practice good commit messages
- Handle unwanted files

## 📝 Tasks

### Part 1: Create Files to Ignore

1. Create some files that shouldn't be tracked:
   ```bash
   # Create a "secrets" file
   echo "password=12345" > secrets.txt
   
   # Create a log file
   echo "Error log entry" > debug.log
   
   # Create a temporary file
   echo "Temporary data" > temp.txt
   ```

2. Check Git status:
   ```bash
   git status
   ```
   You should see these as "Untracked files"

### Part 2: Create .gitignore

1. Create .gitignore file:
   ```bash
   touch .gitignore
   ```

2. Add patterns to ignore:
   ```bash
   echo "# Sensitive files" >> .gitignore
   echo "secrets.txt" >> .gitignore
   echo "" >> .gitignore
   echo "# Log files" >> .gitignore
   echo "*.log" >> .gitignore
   echo "" >> .gitignore
   echo "# Temporary files" >> .gitignore
   echo "temp.txt" >> .gitignore
   echo "*.tmp" >> .gitignore
   ```

3. Check status again:
   ```bash
   git status
   ```
   The ignored files should disappear!

4. Commit .gitignore:
   ```bash
   git add .gitignore
   git commit -m "Add .gitignore for sensitive and temporary files"
   git push
   ```

### Part 3: Practice Good Commit Messages

1. Create a new feature file:
   ```bash
   echo "# Features" > features.md
   echo "- User login" >> features.md
   ```

2. Make a BAD commit (to see what not to do):
   ```bash
   git add features.md
   git commit -m "stuff"
   ```

3. Amend with a GOOD message:
   ```bash
   git commit --amend -m "Add features documentation with initial user stories"
   ```

4. Push the changes:
   ```bash
   git push
   ```

### Part 4: Clean Working Directory

1. Create some test files:
   ```bash
   touch test1.txt test2.txt
   ```

2. Check status:
   ```bash
   git status
   ```

3. Clean up (remove untracked files):
   ```bash
   rm test1.txt test2.txt
   ```

4. Verify clean status:
   ```bash
   git status
   ```
   Should show "nothing to commit, working tree clean"

## ✅ Success Criteria

You've completed this exercise when:
- [ ] .gitignore exists and is committed
- [ ] Sensitive files are NOT in the repository
- [ ] You've amended at least one commit message
- [ ] Working directory is clean
- [ ] All changes are pushed

## 🚑 Troubleshooting

**Accidentally committed a file to ignore**
```bash
# Remove from repository but keep locally
git rm --cached filename
git commit -m "Remove accidentally committed file"
```

**Can't amend - already pushed**
- Only amend commits that haven't been pushed
- Once pushed, commits are permanent

**.gitignore not working**
- Make sure file names match exactly
- Check for typos in patterns
- Already tracked files won't be ignored

## 💡 Best Practices Learned

1. **Always have a .gitignore**
2. **Never commit sensitive data**
3. **Write meaningful commit messages**
4. **Keep working directory clean**
5. **Check status before committing**

## 🎉 Congratulations!

You've learned essential Git hygiene:
- Protecting sensitive data
- Writing good commit messages
- Keeping repositories clean

**Next**: [Exercise 4: Fixing Mistakes](exercise04-mistakes.md)

---

[Back to Exercises](README.md) | [Main Book](../README.md)