# 🚀 GitHub + Netlify Deployment Guide

This guide will help you put your DHB website on GitHub and connect it to Netlify for automatic deployments.

---

## 📋 What You'll Need

- ✅ A GitHub account (free - we'll create this)
- ✅ Git installed on your computer
- ✅ Your DHB website files (you have these!)

**Time:** ~15 minutes
**Cost:** $0 (completely free!)

---

## 🎯 STEP 1: Install Git (If Not Already Installed)

### Check if Git is Already Installed

Open Command Prompt (Windows) or Terminal (Mac) and run:

```bash
git --version
```

If you see a version number like `git version 2.x.x`, **skip to Step 2**.

### Install Git (Windows)

1. Download Git from: **https://git-scm.com/download/win**
2. Run the installer
3. Use default settings (just click Next through everything)
4. Restart Command Prompt after installation

### Install Git (Mac)

1. Open Terminal
2. Run: `xcode-select --install`
3. Click Install when prompted

---

## 🌐 STEP 2: Create a GitHub Account

1. Go to: **https://github.com/signup**
2. Enter your email address
3. Create a password
4. Choose a username (example: `yourname` or `dhb-project`)
5. Verify your account (check email)
6. Complete the setup

**✅ Done!** You now have a GitHub account.

---

## 📦 STEP 3: Create a New Repository on GitHub

### 3.1 Create the Repository

1. Log into GitHub: **https://github.com**
2. Click the **+** icon in the top right
3. Click **New repository**

### 3.2 Configure Your Repository

Fill in these details:

- **Repository name:** `dhb-historical-analysis` (or any name you like)
- **Description:** `DHB Historical Policy Analysis Website`
- **Visibility:**
  - Choose **Public** (free, visible to everyone)
  - Or **Private** (if you want it hidden - also free)
- **DO NOT** check "Initialize this repository with a README"
- **DO NOT** add .gitignore or license yet

### 3.3 Create Repository

Click **Create repository**

**Important:** Keep this page open! You'll need the commands shown.

---

## 💻 STEP 4: Push Your Code to GitHub

Now we'll upload your DHB files to GitHub using Command Prompt (Windows) or Terminal (Mac).

### 4.1 Open Command Prompt/Terminal

**Windows:**
1. Press `Windows + R`
2. Type `cmd` and press Enter
3. Navigate to your DHB folder:
   ```bash
   cd C:\Users\mackb\DHB
   ```

**Mac:**
1. Open Terminal (Cmd + Space, type "Terminal")
2. Navigate to your DHB folder:
   ```bash
   cd /path/to/your/DHB
   ```

### 4.2 Initialize Git Repository

Run these commands one at a time:

```bash
git init
```

This creates a new Git repository in your folder.

### 4.3 Configure Git (First Time Only)

If this is your first time using Git, configure your identity:

```bash
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```

Replace with your actual name and the email you used for GitHub.

### 4.4 Add Your Files

```bash
git add .
```

This stages all your files for commit.

### 4.5 Create Your First Commit

```bash
git commit -m "Initial commit - DHB Historical Analysis website"
```

This creates a snapshot of your code.

### 4.6 Connect to GitHub

Replace `YOUR-USERNAME` with your GitHub username and `dhb-historical-analysis` with your repository name:

```bash
git remote add origin https://github.com/YOUR-USERNAME/dhb-historical-analysis.git
```

**Example:**
```bash
git remote add origin https://github.com/johnsmith/dhb-historical-analysis.git
```

### 4.7 Push to GitHub

For the first push, run:

```bash
git branch -M main
git push -u origin main
```

**You may be prompted to login to GitHub:**
- Enter your GitHub username
- For password, use a **Personal Access Token** (not your account password)

#### Creating a Personal Access Token:

1. Go to: **https://github.com/settings/tokens**
2. Click **Generate new token** → **Generate new token (classic)**
3. Name it: `DHB Netlify Deployment`
4. Select scopes: Check **repo** (all sub-items)
5. Click **Generate token**
6. **COPY THE TOKEN** (you won't see it again!)
7. Use this token as your password when pushing

### 4.8 Verify Upload

Go to your GitHub repository page and refresh. You should see all your files!

**✅ Success!** Your code is now on GitHub.

---

## 🌍 STEP 5: Deploy to Netlify from GitHub

Now let's connect GitHub to Netlify for automatic deployments.

### 5.1 Go to Netlify

1. Log into Netlify: **https://app.netlify.com**
2. Click **Add new site**
3. Click **Import an existing project**

### 5.2 Connect to GitHub

1. Click **Deploy with GitHub**
2. **Authorize Netlify** to access your GitHub (click Authorize)
3. You may be asked to install Netlify on GitHub - click **Install**

### 5.3 Select Your Repository

1. Find your repository: `dhb-historical-analysis`
2. Click on it to select it

### 5.4 Configure Build Settings

Netlify will show build settings. **Leave everything as default:**

- Branch to deploy: `main`
- Build command: (leave empty)
- Publish directory: (leave empty)

Click **Deploy site**

### 5.5 Wait for Deployment

Netlify will now deploy your site. This takes 30-60 seconds.

You'll see:
- "Site deploy in progress"
- Then: "Site is live" ✅

**✅ Your site is LIVE!**

---

## 🌐 STEP 6: Connect Your Custom Domain

### 6.1 Add Your Domain

1. In your Netlify site dashboard, click **Domain settings**
2. Click **Add custom domain**
3. Enter: `democratshateblacks.com`
4. Click **Verify**
5. Click **Yes, add domain**

### 6.2 Configure DNS

Follow the same DNS steps from the Netlify Deployment Guide:
- Use Netlify DNS (recommended), or
- Add A records and CNAME to your registrar

**Wait 24-48 hours for DNS propagation.**

### 6.3 Enable HTTPS

Once DNS is configured:
1. Go to **Domain settings** → **HTTPS**
2. Click **Verify DNS configuration**
3. Click **Provision certificate**
4. Toggle **Force HTTPS** to ON

**✅ Your site is now live at https://democratshateblacks.com**

---

## 🔄 UPDATING YOUR SITE (Automatic Deployments!)

The beauty of GitHub + Netlify: **Automatic deployments!**

### How to Update Your Site:

1. **Edit your files locally** (in your DHB folder)
2. **Save your changes**
3. **Open Command Prompt/Terminal** and navigate to DHB folder
4. **Run these commands:**

```bash
git add .
git commit -m "Updated content"
git push
```

5. **Netlify automatically deploys!** Your site updates in 30 seconds.

**That's it!** No manual uploads needed.

---

## 📝 COMMON GIT COMMANDS

Here are commands you'll use regularly:

### Check Status
```bash
git status
```
Shows what files have changed.

### See Changes
```bash
git diff
```
Shows exactly what changed in your files.

### Add All Changes
```bash
git add .
```
Stages all changes for commit.

### Add Specific File
```bash
git add index.html
```
Stages only one file.

### Commit Changes
```bash
git commit -m "Your commit message here"
```
Creates a snapshot with a description.

### Push to GitHub
```bash
git push
```
Uploads your commits to GitHub (and triggers Netlify deploy).

### Pull from GitHub
```bash
git pull
```
Downloads latest changes from GitHub (if you edit online).

### View Commit History
```bash
git log --oneline
```
Shows your commit history.

---

## 🐛 TROUBLESHOOTING

### Problem: "Git is not recognized"

**Solution:**
- Make sure Git is installed
- Restart Command Prompt/Terminal after installing
- Windows: Add Git to PATH (search "Environment Variables")

### Problem: Authentication Failed

**Solution:**
- Use a Personal Access Token, not your password
- Create token at: https://github.com/settings/tokens
- Give it `repo` permissions

### Problem: "Remote origin already exists"

**Solution:**
```bash
git remote remove origin
git remote add origin https://github.com/YOUR-USERNAME/dhb-historical-analysis.git
```

### Problem: Push rejected / behind remote

**Solution:**
```bash
git pull origin main --rebase
git push
```

### Problem: Netlify build fails

**Solution:**
- Check the Netlify deploy log for errors
- Make sure `index.html` is in the root of your repository
- Try deploying again: Deploys → Trigger deploy → Deploy site

### Problem: Site shows old version

**Solution:**
- Wait a few seconds for Netlify to build
- Clear your browser cache (Ctrl+F5)
- Check Netlify deploys page to see if build succeeded

---

## 💡 PRO TIPS

### Tip 1: .gitignore File

Create a `.gitignore` file to exclude certain files:

```bash
# Create .gitignore in your DHB folder
echo node_modules/ > .gitignore
echo .env >> .gitignore
echo .DS_Store >> .gitignore
```

This prevents sensitive or unnecessary files from being uploaded.

### Tip 2: Commit Often

Make small, frequent commits with descriptive messages:
- ✅ "Add hero section images"
- ✅ "Update immigration section data"
- ✅ "Fix mobile responsive layout"
- ❌ "Updates" (too vague)

### Tip 3: Branch for Big Changes

For major changes, create a branch:
```bash
git checkout -b new-feature
# Make your changes
git add .
git commit -m "Add new feature"
git push -u origin new-feature
```

Then merge via GitHub pull request.

### Tip 4: Netlify Deploy Previews

When you push to a branch (not main), Netlify creates a preview:
- You can test changes before merging to main
- Share preview URL with others for feedback

### Tip 5: Backup Your Token

Save your GitHub Personal Access Token somewhere safe:
- Password manager
- Encrypted note
- You'll need it every time you push from a new computer

---

## ✅ SUCCESS CHECKLIST

After following this guide, you should have:

- ✅ Git installed on your computer
- ✅ GitHub account created
- ✅ Repository created on GitHub
- ✅ Code pushed to GitHub
- ✅ Netlify connected to GitHub
- ✅ Site automatically deployed
- ✅ Custom domain connected
- ✅ HTTPS enabled
- ✅ Automatic deployments working

---

## 🎉 YOU'RE DONE!

Your workflow is now:

1. **Edit files** on your computer
2. **Run 3 commands:**
   ```bash
   git add .
   git commit -m "Description of changes"
   git push
   ```
3. **Netlify auto-deploys** in 30 seconds
4. **Site is updated** at your domain!

---

## 📚 LEARNING RESOURCES

Want to learn more about Git and GitHub?

- **Git Basics:** https://git-scm.com/book/en/v2/Getting-Started-Git-Basics
- **GitHub Guides:** https://guides.github.com
- **Netlify Docs:** https://docs.netlify.com
- **Git Cheat Sheet:** https://education.github.com/git-cheat-sheet-education.pdf

---

## 🆘 NEED HELP?

### GitHub Support
- GitHub Docs: https://docs.github.com
- GitHub Community: https://github.community

### Netlify Support
- Netlify Docs: https://docs.netlify.com
- Community Forum: https://answers.netlify.com

### Git Help
- Official Git Documentation: https://git-scm.com/doc
- Stack Overflow: https://stackoverflow.com/questions/tagged/git

---

## 🎊 CONGRATULATIONS!

You now have a professional development workflow:
- ✅ Version control with Git
- ✅ Code hosting on GitHub
- ✅ Automatic deployments with Netlify
- ✅ Live site on your custom domain
- ✅ Free forever!

This is the same workflow used by professional developers worldwide!

---

**Next Steps:**
1. Add your Gemini API key to enable AI features
2. Replace placeholder images with your own
3. Test your site on mobile devices
4. Share your site with the world! 🚀

Good luck! 🎉
