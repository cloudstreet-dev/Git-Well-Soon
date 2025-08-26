# Exercise 2: Daily Workflow

> Practice the edit-add-commit-push cycle until it's second nature!

## 🎯 Learning Objectives

- Edit files locally
- Stage changes
- Commit with good messages
- Push to GitHub

## 📝 Tasks

### Part 1: Make Your First Edit

1. Open README.md in your editor:
   ```bash
   nano README.md
   # OR
   code README.md
   ```

2. Replace the content with:
   ```markdown
   # My Git Practice Repository
   
   This is where I'm learning Git!
   
   ## What I've Learned
   - How to create a repository
   - How to clone locally
   - How to make commits
   
   ## My Favorite Git Command
   `git status` - because it tells me everything!
   ```

3. Save the file

### Part 2: Stage and Commit

1. Check what changed:
   ```bash
   git status
   git diff
   ```

2. Stage the changes:
   ```bash
   git add README.md
   ```

3. Verify staging:
   ```bash
   git status
   ```

4. Commit with a message:
   ```bash
   git commit -m "Update README with learning progress"
   ```

### Part 3: Push to GitHub

1. Push your changes:
   ```bash
   git push origin main
   ```

2. Go to GitHub and verify your changes appear

### Part 4: Make Another Change

Practice the whole cycle again:

1. Create a new file:
   ```bash
   touch notes.md
   ```

2. Add content:
   ```bash
   echo "# Git Notes" > notes.md
   echo "" >> notes.md
   echo "- Always use clear commit messages" >> notes.md
   echo "- Commit often" >> notes.md
   echo "- Pull before push" >> notes.md
   ```

3. Add, commit, and push:
   ```bash
   git add notes.md
   git commit -m "Add Git best practices notes"
   git push
   ```

## ✅ Success Criteria

You've completed this exercise when:
- [ ] README.md is updated on GitHub
- [ ] notes.md exists on GitHub
- [ ] You have at least 3 commits in history
- [ ] All changes are pushed

## 🚑 Troubleshooting

**"Nothing to commit"**
- Make sure you saved your changes
- Check `git status` to see what's happening

**"Everything up-to-date" when pushing**
- You already pushed or haven't committed
- Check `git log` to see recent commits

**Authentication errors**
- Use personal access token, not password
- Check GitHub settings for token creation

## 💡 Pro Tips

- Use `git status` before and after each step
- Make commits small and focused
- Write messages that explain "why" not just "what"

## 🎉 Congratulations!

You've mastered the basic workflow:
1. Edit
2. Add
3. Commit
4. Push

This is 80% of daily Git usage!

**Next**: [Exercise 3: Git Hygiene](exercise03-hygiene.md)

---

[Back to Exercises](README.md) | [Main Book](../README.md)