# Exercise 5: Final Project

> Put all your Git skills together in one comprehensive project!

## 🎯 Learning Objectives

- Apply all learned Git skills
- Build a complete project workflow
- Practice real-world Git usage
- Graduate from Git patient to Git practitioner!

## 📝 Project: Build a Personal Portfolio

You'll create a simple portfolio website and manage it with Git.

### Part 1: Setup

1. Create a new repository on GitHub called `my-portfolio`
   - Initialize with README
   - Make it public

2. Clone it locally:
   ```bash
   cd ~/Code
   git clone https://github.com/YOUR-USERNAME/my-portfolio.git
   cd my-portfolio
   ```

### Part 2: Create Project Structure

1. Create the files:
   ```bash
   # Create HTML file
   cat > index.html << 'EOF'
   <!DOCTYPE html>
   <html lang="en">
   <head>
       <meta charset="UTF-8">
       <meta name="viewport" content="width=device-width, initial-scale=1.0">
       <title>My Portfolio</title>
       <link rel="stylesheet" href="style.css">
   </head>
   <body>
       <h1>Welcome to My Portfolio</h1>
       <p>I'm learning Git and web development!</p>
       <h2>Skills</h2>
       <ul>
           <li>Git & GitHub</li>
           <li>HTML & CSS</li>
           <li>Problem Solving</li>
       </ul>
   </body>
   </html>
   EOF
   
   # Create CSS file
   cat > style.css << 'EOF'
   body {
       font-family: Arial, sans-serif;
       max-width: 800px;
       margin: 0 auto;
       padding: 20px;
       background-color: #f0f0f0;
   }
   
   h1 {
       color: #333;
       border-bottom: 2px solid #4CAF50;
       padding-bottom: 10px;
   }
   
   ul {
       background-color: white;
       padding: 20px;
       border-radius: 5px;
   }
   EOF
   ```

2. Commit initial structure:
   ```bash
   git add .
   git commit -m "Add initial portfolio structure with HTML and CSS"
   git push
   ```

### Part 3: Add .gitignore

1. Create .gitignore:
   ```bash
   cat > .gitignore << 'EOF'
   # OS Files
   .DS_Store
   Thumbs.db
   
   # Editor Files
   .vscode/
   *.swp
   
   # Temporary Files
   *.tmp
   *.log
   
   # Sensitive Data
   .env
   secrets.txt
   EOF
   ```

2. Commit it:
   ```bash
   git add .gitignore
   git commit -m "Add .gitignore for common unnecessary files"
   git push
   ```

### Part 4: Update README

1. Create a proper README:
   ```bash
   cat > README.md << 'EOF'
   # My Portfolio Website
   
   A simple portfolio website to showcase my journey learning web development and Git.
   
   ## Technologies Used
   - HTML5
   - CSS3
   - Git for version control
   
   ## What I Learned
   - Creating and structuring HTML documents
   - Styling with CSS
   - Managing code with Git and GitHub
   - Writing good documentation
   
   ## Setup Instructions
   1. Clone this repository
   2. Open `index.html` in your browser
   
   ## Future Improvements
   - [ ] Add JavaScript interactivity
   - [ ] Include project showcases
   - [ ] Add contact form
   - [ ] Implement responsive design
   
   ## Author
   Created while learning Git through the "Git Well Soon" book!
   
   ---
   
   *This project is part of my Git learning journey.*
   EOF
   ```

2. Commit the update:
   ```bash
   git add README.md
   git commit -m "Update README with project information and setup instructions"
   git push
   ```

### Part 5: Add a Feature

1. Add a projects section to index.html:
   ```bash
   # Create a backup first (good practice!)
   cp index.html index.html.backup
   
   # Add projects section before </body>
   cat >> index.html << 'EOF'
       <h2>Projects</h2>
       <div class="projects">
           <div class="project">
               <h3>Git Well Soon Exercises</h3>
               <p>Completed all exercises in the Git learning book!</p>
           </div>
           <div class="project">
               <h3>My Portfolio Site</h3>
               <p>This website - built with HTML and CSS.</p>
           </div>
       </div>
   EOF
   ```

2. Add styling for projects:
   ```bash
   cat >> style.css << 'EOF'
   
   .projects {
       display: grid;
       gap: 20px;
       margin-top: 20px;
   }
   
   .project {
       background-color: white;
       padding: 15px;
       border-radius: 5px;
       border-left: 4px solid #4CAF50;
   }
   
   .project h3 {
       margin-top: 0;
       color: #333;
   }
   EOF
   ```

3. Commit the feature:
   ```bash
   git add index.html style.css
   git commit -m "Add projects section to portfolio"
   git push
   ```

### Part 6: Fix a "Mistake"

1. Simulate an error and fix it:
   ```bash
   # Make a "mistake"
   echo "/* BROKEN CSS */" >> style.css
   git add style.css
   git commit -m "Update styles"
   
   # Realize the mistake and amend
   git restore style.css
   git add style.css
   git commit --amend -m "Add projects section styling"
   git push
   ```

### Part 7: Final Touches

1. Check your work:
   ```bash
   # Ensure clean working directory
   git status
   
   # Review commit history
   git log --oneline
   
   # Check all files are tracked properly
   ls -la
   ```

2. Open index.html in your browser to see your portfolio!

### Part 8: Deploy to GitHub Pages (Bonus!)

1. Go to your repository on GitHub
2. Click Settings → Pages
3. Under "Source", select "Deploy from a branch"
4. Choose "main" branch and "/ (root)"
5. Click Save
6. Wait a few minutes
7. Your site will be live at: `https://YOUR-USERNAME.github.io/my-portfolio`

## ✅ Success Criteria

You've completed the final project when:
- [ ] Repository created and cloned
- [ ] Multiple files added and committed
- [ ] .gitignore properly configured
- [ ] README is comprehensive
- [ ] At least 5 meaningful commits
- [ ] All changes pushed to GitHub
- [ ] Working directory is clean
- [ ] (Bonus) Site deployed to GitHub Pages

## 🎓 Final Assessment

Can you answer these questions?
1. What command shows your commit history?
2. How do you see what changes are staged?
3. What file prevents sensitive data from being committed?
4. How do you undo changes to a file?
5. What's the difference between `git add .` and `git add filename`?

## 🏆 Congratulations!

You've completed all exercises and built a real project using Git!

You are now officially recovered from your Git ailments and ready to:
- Start your own projects
- Contribute to open source
- Collaborate with others
- Help others learn Git

## 🎉 You Did It!

**You've graduated from the Git Well Soon program!**

Don't forget to:
- Star the Git Well Soon repository
- Share your portfolio link
- Help someone else learn Git
- Keep practicing daily

---

[Back to Exercises](README.md) | [Main Book](../README.md) | [What's Next?](../chapter10-next-steps.md)

*Remember: The best way to solidify your Git knowledge is to use it every day. Version control everything - even your grocery lists!*