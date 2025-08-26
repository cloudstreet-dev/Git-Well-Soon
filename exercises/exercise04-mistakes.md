# Exercise 4: Fixing Mistakes

> Everyone makes mistakes. The key is knowing how to fix them!

## 🎯 Learning Objectives

- Undo changes in working directory
- Fix commit messages
- Recover from common errors
- Handle merge conflicts

## 📝 Tasks

### Part 1: Undo Uncommitted Changes

1. Make some changes to README.md:
   ```bash
   echo "This is a mistake!" >> README.md
   echo "Delete all the things!" >> README.md
   ```

2. Check the damage:
   ```bash
   git diff
   ```

3. Restore the file:
   ```bash
   git restore README.md
   ```

4. Verify it's fixed:
   ```bash
   git diff
   # Should show no differences
   ```

### Part 2: Unstage Files

1. Create and stage a wrong file:
   ```bash
   echo "API_KEY=secret123" > .env
   git add .env
   ```

2. Check status:
   ```bash
   git status
   # Shows .env staged
   ```

3. Unstage it:
   ```bash
   git restore --staged .env
   ```

4. Add to .gitignore instead:
   ```bash
   echo ".env" >> .gitignore
   git add .gitignore
   git commit -m "Update .gitignore to exclude .env files"
   ```

### Part 3: Fix Wrong Commit (Before Push)

1. Make a commit with a typo:
   ```bash
   echo "# Documentation" > docs.md
   git add docs.md
   git commit -m "Add dcoumentation file"
   ```

2. Fix the message:
   ```bash
   git commit --amend -m "Add documentation file"
   ```

3. Verify the fix:
   ```bash
   git log --oneline -1
   ```

### Part 4: Simulate and Resolve a Conflict

1. First, push your current changes:
   ```bash
   git push
   ```

2. Edit README.md on GitHub (simulate teammate):
   - Go to your repo on GitHub
   - Click on README.md
   - Click the pencil icon to edit
   - Add at the top: `# EDITED ON GITHUB`
   - Commit directly to main branch

3. Edit README.md locally (without pulling):
   ```bash
   echo "# EDITED LOCALLY" | cat - README.md > temp && mv temp README.md
   git add README.md
   git commit -m "Update README locally"
   ```

4. Try to push (will fail):
   ```bash
   git push
   # Error: rejected
   ```

5. Pull and resolve:
   ```bash
   git pull origin main
   # Will show merge conflict
   ```

6. Open README.md and fix the conflict:
   - Look for conflict markers
   - Keep the version you want
   - Remove the markers

7. Complete the merge:
   ```bash
   git add README.md
   git commit -m "Resolve merge conflict in README"
   git push
   ```

### Part 5: Reset a Bad Commit (Advanced)

1. Make a commit to undo:
   ```bash
   echo "Bad content" > bad.txt
   git add bad.txt
   git commit -m "Add bad file"
   ```

2. Reset but keep changes:
   ```bash
   git reset HEAD~1
   ```

3. The file exists but isn't committed:
   ```bash
   git status
   # Shows bad.txt as untracked
   ```

4. Remove the file:
   ```bash
   rm bad.txt
   ```

## ✅ Success Criteria

You've completed this exercise when:
- [ ] Successfully restored a modified file
- [ ] Unstaged a file before committing
- [ ] Amended a commit message
- [ ] Resolved a merge conflict
- [ ] Reset a commit

## 🚑 Troubleshooting

**Can't resolve conflict**
- Look for `<<<<<<<`, `=======`, and `>>>>>>>`
- Delete these markers after choosing content
- If totally stuck: `git merge --abort`

**Reset went too far**
- Check `git reflog` to find lost commits
- Use `git reset <commit-hash>` to restore

**Pushed by accident**
- You can't easily undo pushed commits
- May need to push a new commit that reverts changes

## 💡 Recovery Principles

1. **Don't panic** - Git rarely loses data
2. **Check status first** - Understand the situation
3. **Google the exact error** - Others have been there
4. **Commit before experimenting** - Create a safety point
5. **Ask for help** - No shame in learning

## 🎉 Congratulations!

You can now:
- Fix common Git mistakes
- Resolve merge conflicts
- Recover from errors
- Work confidently knowing you can fix problems

**Next**: [Exercise 5: Final Project](exercise05-final-project.md)

---

[Back to Exercises](README.md) | [Main Book](../README.md)