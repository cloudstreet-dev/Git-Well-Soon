# Chapter 4: Installing Medical Equipment - Git Installation

> "We need to set up your home care equipment before you leave the hospital."

## 🏥 Treatment Goals for This Chapter

By the end of this chapter, you'll:
- Have Git installed on your computer
- Configure Git with your identity
- Understand the terminal/command line basics
- Verify everything is working correctly

## 🔧 Preparing Your Operating Room (Terminal Introduction)

Before we install Git, we need to talk about the terminal (also called command line, console, or shell). Think of it as your surgical instruments - it might look scary, but it's actually quite simple!

### What is the Terminal?

- A text-based way to control your computer
- Where you'll run Git commands
- Like talking directly to your computer's brain
- No clicking required!

### Opening Your Terminal

**Windows Users:**
- Option 1: Press `Windows Key`, type "cmd", press Enter
- Option 2: Press `Windows Key`, type "PowerShell", press Enter
- Option 3: (Recommended) Install Git Bash (comes with Git!)

**Mac Users:**
- Option 1: Press `Cmd + Space`, type "Terminal", press Enter
- Option 2: Go to Applications → Utilities → Terminal
- Option 3: (Power user) Install iTerm2 for a better experience

**Linux Users:**
- You probably already know this! 
- Usually `Ctrl + Alt + T`
- Or search for "Terminal" in your applications

### Terminal First Aid Kit

Here are the only terminal commands you need to know for now:

| Command | What it does | Medical Analogy |
|---------|-------------|-----------------|
| `pwd` | Shows current location | "Where am I in the hospital?" |
| `ls` | Lists files in current folder | "What's in this room?" |
| `cd foldername` | Change directory | "Walk to another room" |
| `cd ..` | Go up one folder | "Go back to the hallway" |
| `clear` | Clear the screen | "Clean the workspace" |

## 💉 Installation Procedures by Operating System

### 🪟 Windows Installation

#### Option A: Git for Windows (Recommended)

1. **Download the installer:**
   - Go to: https://git-scm.com/download/win
   - The download should start automatically
   - If not, click "Click here to download manually"

2. **Run the installer:**
   - Double-click the downloaded `.exe` file
   - If Windows asks "Do you want to allow this app?", click "Yes"

3. **Installation wizard settings:**
   - **Select Components**: Keep defaults, ensure "Git Bash Here" is checked
   - **Default Editor**: Choose your preference (Notepad++ or VS Code if installed, otherwise Vim)
   - **PATH Environment**: Select "Git from the command line and also from 3rd-party software"
   - **HTTPS Transport**: Use the OpenSSL library
   - **Line Ending Conversions**: "Checkout Windows-style, commit Unix-style"
   - **Terminal Emulator**: Use MinTTY
   - **Extra Options**: Keep defaults

4. **Complete installation:**
   - Click "Install"
   - Wait for the progress bar
   - Click "Finish"

#### Option B: Windows Subsystem for Linux (Advanced)
- Only if you're comfortable with Linux
- Provides a full Linux environment
- More complex setup

### 🍎 Mac Installation

#### Option A: Homebrew Method (Recommended)

1. **Install Homebrew first** (if not already installed):
   ```bash
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```

2. **Install Git:**
   ```bash
   brew install git
   ```

#### Option B: Xcode Command Line Tools

1. **Open Terminal**
2. **Type:**
   ```bash
   git --version
   ```
3. **If Git isn't installed**, macOS will prompt you to install Xcode Command Line Tools
4. **Click "Install"** in the popup
5. **Wait** for installation (can take 10-15 minutes)

#### Option C: Direct Download

1. **Go to:** https://git-scm.com/download/mac
2. **Download** the installer
3. **Open** the `.dmg` file
4. **Run** the installer package
5. **Follow** the installation wizard

### 🐧 Linux Installation

#### Ubuntu/Debian:
```bash
sudo apt update
sudo apt install git
```

#### Fedora:
```bash
sudo dnf install git
```

#### Arch:
```bash
sudo pacman -S git
```

#### Other distributions:
- Check your package manager's documentation
- Or build from source (advanced)

## 🔬 Verification: Testing Your Equipment

After installation, let's verify Git is working:

1. **Open a NEW terminal window** (important: must be new after installation)

2. **Check Git version:**
   ```bash
   git --version
   ```
   
   You should see something like:
   ```
   git version 2.40.0
   ```
   
   (Your version number may be different - that's OK!)

3. **If you get an error:**
   - Windows: Restart your computer and try again
   - Mac: Make sure you opened a new terminal
   - Linux: Check your PATH variable

## 🏥 Configuration: Setting Up Your Doctor's Credentials

Now we need to tell Git who you are. This information will be attached to every commit you make.

### Setting Your Name and Email

Open your terminal and run these commands (replace with YOUR information):

```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

**Important Notes:**
- Use the SAME email you used for GitHub
- Use quotes around your name if it has spaces
- The `--global` flag sets this for all projects

### Verify Your Configuration

Check that your settings were saved:

```bash
git config --global user.name
git config --global user.email
```

You should see your name and email printed back.

### View All Settings

To see all your Git configuration:

```bash
git config --list
```

## 🎨 Optional: Customizing Your Equipment

### Setting Your Default Branch Name

GitHub uses "main" as the default branch. Let's match that:

```bash
git config --global init.defaultBranch main
```

### Enabling Colors (Pretty Output)

Make Git output easier to read:

```bash
git config --global color.ui auto
```

### Setting Your Default Editor

Choose your preferred text editor for commit messages:

```bash
# For VS Code:
git config --global core.editor "code --wait"

# For Sublime Text:
git config --global core.editor "subl -n -w"

# For Notepad (Windows):
git config --global core.editor notepad

# For nano (simple):
git config --global core.editor nano
```

## 🧪 Clinical Trial #4: Installation Verification

Complete ALL these checks:

### Basic Checks:
1. ✅ Run `git --version` and get a version number
2. ✅ Run `git config user.name` and see your name
3. ✅ Run `git config user.email` and see your email

### Terminal Navigation:
1. ✅ Run `pwd` to see your current location
2. ✅ Run `ls` to list files
3. ✅ Run `cd Desktop` (or another folder) to change directories
4. ✅ Run `cd ..` to go back

### Git Help System:
1. ✅ Run `git help` to see available commands
2. ✅ Run `git help commit` to see commit documentation
3. ✅ Press `q` to exit the help viewer

## 🏥 Emergency Card: Installation Troubleshooting

| Problem | Solution |
|---------|----------|
| "git: command not found" | Restart terminal, reinstall Git |
| "Permission denied" | On Mac/Linux, use `sudo` for installation |
| Can't open terminal | Windows: Try PowerShell instead of CMD |
| Installation hangs | Cancel and download installer directly from git-scm.com |
| Wrong Git version | Uninstall old version first, then reinstall |

## 🩺 Doctor's Notes

**Windows Users**: Git Bash (installed with Git) gives you a Linux-like terminal. This makes following tutorials easier since most use Linux/Mac commands.

**Mac Users**: If you're on an older Mac, you might need to update macOS first. Git requires relatively recent OS versions.

**Everyone**: Don't worry if the terminal feels weird at first. You'll only use about 6 Git commands regularly. It becomes second nature quickly!

## 📋 Discharge Summary

You've successfully:
- ✅ Installed Git on your computer
- ✅ Configured your identity (name and email)
- ✅ Learned basic terminal navigation
- ✅ Verified everything is working

Your medical equipment is ready for use!

## 🎯 Chapter Checkpoint

Before proceeding, ensure you can:
- ✅ Open a terminal/command prompt
- ✅ See Git version with `git --version`
- ✅ Navigate folders with `cd` commands
- ✅ Your name/email are configured in Git

## 🚀 What's Next?

Now you have:
- ✅ A GitHub account (Chapter 3)
- ✅ Git installed locally (Chapter 4)

Time to create your first repository and start your Git journey!

---

**Next**: [Chapter 5: Creating Your First Patient File - New Repository](chapter05-new-repository.md)

*Terminal Tip: Scared of the command line? Think of it as texting with your computer. Short messages, instant responses!*