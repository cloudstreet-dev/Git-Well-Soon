# Exercise 1: First Repository

> Time to create your first patient file from scratch!

## 🎯 Learning Objectives

- Create a GitHub repository
- Clone it locally
- Verify the connection

## 📝 Tasks

### Part 1: Create Repository on GitHub

1. Log into GitHub
2. Create a new repository called `my-git-practice`
3. Initialize with a README
4. Make it public

### Part 2: Clone Locally

1. Copy the HTTPS clone URL
2. Open your terminal
3. Navigate to your Code folder:
   ```bash
   cd ~/Code
   ```
4. Clone the repository:
   ```bash
   git clone https://github.com/YOUR-USERNAME/my-git-practice.git
   ```
5. Enter the repository:
   ```bash
   cd my-git-practice
   ```

### Part 3: Verify Setup

Run these commands and verify the output:

```bash
# Check you're in the right place
pwd
# Should show: .../Code/my-git-practice

# Check Git status
git status
# Should show: "On branch main" and "nothing to commit"

# Check remote connection
git remote -v
# Should show: origin URLs pointing to your GitHub repo

# List files
ls -la
# Should show: .git folder and README.md
```

## ✅ Success Criteria

You've completed this exercise when:
- [ ] Repository exists on GitHub
- [ ] Repository is cloned locally
- [ ] `git status` works without errors
- [ ] You can see the .git folder
- [ ] Remote is properly connected

## 🚑 Troubleshooting

**"Repository not found"**
- Check the URL is correct
- Make sure you're logged into GitHub

**"fatal: not a git repository"**
- Make sure you're inside the cloned folder
- Use `cd my-git-practice`

**Can't see .git folder**
- It's hidden! Use `ls -la` (note the -a flag)

## 🎉 Congratulations!

You've successfully:
- Created a repository
- Cloned it locally
- Verified everything works

**Next**: [Exercise 2: Daily Workflow](exercise02-daily-workflow.md)

---

[Back to Exercises](README.md) | [Main Book](../README.md)