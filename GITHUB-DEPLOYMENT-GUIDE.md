# GitHub Deployment Guide - Custom Playing Card Generator

This guide explains how to upload your project to GitHub for the first time.

---

## 📦 Files to Upload

### ✅ Must Include (Public)
```
custom-playing-card-generator/
├── index.html              # Main application (145KB)
├── gamecrafter-api.js      # Game Crafter API wrapper
├── README.md              # Project documentation
├── LICENSE                # CC BY-SA 4.0 license
├── CONTRIBUTING.md        # Contribution guidelines
├── CHANGELOG.md           # Version history
├── .gitignore            # Ignore personal files
└── docs/
    └── showcase.png       # Banner image for README (optional)
```

### ❌ Never Include (Keep Local)
```
DO NOT COMMIT THESE FILES:
├── dan.html              # Contains your password!
├── dan-*.html            # Any personal versions
└── *-backup.html         # Backup files
```

**Why?** These files contain hardcoded credentials (password, API key). Once committed to GitHub, they become **public forever** even if you delete them later!

---

## 🚀 Step-by-Step Upload Process

### Step 1: Create GitHub Repository

1. Go to [github.com/new](https://github.com/new)
2. Repository name: `playing-card-generator`
3. Description: `Free, open-source web app for creating custom playing cards`
4. Visibility: **Public** (required for GitHub Pages)
5. **Do NOT initialize with README** (you already have one)
6. Click "Create repository"

### Step 2: Prepare Local Files

```bash
# Create project folder
mkdir custom-playing-card-generator
cd custom-playing-card-generator

# Copy files from /mnt/user-data/outputs/
# Copy ONLY these files:
cp /mnt/user-data/outputs/index.html .
cp /mnt/user-data/outputs/README.md .
cp /mnt/user-data/outputs/LICENSE .
cp /mnt/user-data/outputs/CONTRIBUTING.md .
cp /mnt/user-data/outputs/CHANGELOG.md .
cp /mnt/user-data/outputs/.gitignore .

# DO NOT copy dan.html!
```

### Step 3: Initialize Git

```bash
git init
git add .
git status  # Verify dan.html is NOT in the list!

# If you see dan.html in git status:
git rm --cached dan.html  # Remove it!
```

### Step 4: First Commit

```bash
git commit -m "Initial commit: Custom Playing Card Generator v5.2

Features:
- 4-suit or 5-suit deck generation
- Custom suit icons (upload or library)
- Face cards (blank, upload, or library)
- Jokers (none, 2, or 7 for game decks)
- Game Crafter integration
- High-res output (MPC and GC formats)
- Click-to-enlarge card showcase
- Professional footer with links

License: CC BY-SA 4.0"
```

### Step 5: Push to GitHub

```bash
# Add remote (replace SanityVacuum with your GitHub username)
git remote add origin https://github.com/SanityVacuum/custom-playing-card-generator.git

# Push
git branch -M main
git push -u origin main
```

---

## 🌐 Enable GitHub Pages (Optional)

Make your app accessible at `sanityvacuum.github.io/custom-playing-card-generator`:

1. Go to repository → Settings → Pages
2. Source: **Deploy from a branch**
3. Branch: **main** / root
4. Click Save

Wait 1-2 minutes, then visit:
**https://sanityvacuum.github.io/custom-playing-card-generator**

**Note:** You'll need to copy `gamecrafter-api.js` to the repo or host it elsewhere, as it's currently an external dependency.

---

## 📝 Update Repository Details

On GitHub repository page:

### About Section (Top Right)
- **Website:** https://www.capsaicin.com
- **Topics:** `playing-cards` `card-generator` `game-design` `html5-canvas` `creative-commons` `print-on-demand`
- **Description:** Free, open-source web app for creating custom playing cards

### Repository Settings
- **Social Preview Image:** Upload `/docs/showcase.png` if you have one
- **Features:**
  - ✅ Wikis (disable - not needed)
  - ✅ Issues (enable)
  - ✅ Projects (enable if you want)
  - ❌ Preserve this repository (not needed yet)

---

## 🔒 Security Checklist

Before pushing, **double-check:**

- [ ] `dan.html` is NOT in git staging area
- [ ] `dan.html` is listed in `.gitignore`
- [ ] No passwords visible in `index.html`
- [ ] No API keys visible in `index.html`
- [ ] `gamecrafter-api.js` doesn't contain credentials

**Verify:**
```bash
git status           # Should NOT show dan.html
cat .gitignore       # Should include dan.html
grep -r "gHN9Zgy" .  # Should NOT find your password
```

If you find your password anywhere:
```bash
git reset --hard  # Undo all changes
# Remove the file with password
# Try again
```

---

## 📤 Uploading gamecrafter-api.js

**Option 1: Include in repo (Recommended)**
```bash
# Copy from wherever you have it
cp /path/to/gamecrafter-api.js .
git add gamecrafter-api.js
git commit -m "Add Game Crafter API wrapper"
git push
```

**Option 2: Host separately**
```bash
# Upload to capsaicin.com
scp gamecrafter-api.js user@capsaicin.com:/path/to/public/

# Update index.html:
<script src="https://www.capsaicin.com/gamecrafter-api.js"></script>
```

---

## 🎨 Optional: Add Showcase Image

Create a banner image showing your cards:

1. Take screenshot of card showcase
2. Crop to just the cards
3. Save as `docs/showcase.png`
4. Add to repo:

```bash
mkdir docs
mv showcase.png docs/
git add docs/showcase.png
git commit -m "Add showcase image for README"
git push
```

Then update README.md:
```markdown
![Card Showcase](docs/showcase.png)
```

---

## 🔄 Future Updates

After initial upload, update with:

```bash
# Make your changes to index.html
git add index.html
git commit -m "Fix: Card back resize appearing on courts"
git push
```

**Update version in:**
1. `index.html` (header comment)
2. `README.md` (version badge, version history)
3. `CHANGELOG.md` (new version section)

---

## 📊 Repository Stats

After upload, you'll see:

- **Language:** HTML (99.5%), JavaScript (0.5%)
- **Size:** ~150 KB
- **Files:** 6 main files
- **License:** CC BY-SA 4.0 (shows badge automatically)

---

## 🎯 First Issue (Optional)

Create a "Welcome" issue to help others:

**Title:** Welcome Contributors!

**Body:**
```markdown
👋 Welcome to the Custom Playing Card Generator!

This project is open for contributions. Here are some ways to help:

- ⭐ Star this repo if you find it useful
- 🐛 Report bugs in Issues
- 💡 Suggest features in Issues
- 🤝 Submit Pull Requests
- 📢 Share with others

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

Thank you! - Dan
```

Label: `good first issue`, `help wanted`

---

## ✅ Checklist Before Going Public

- [ ] Verified no passwords in any committed files
- [ ] .gitignore includes dan.html and personal files
- [ ] README.md is complete and accurate
- [ ] LICENSE file is present
- [ ] CONTRIBUTING.md explains how to contribute
- [ ] CHANGELOG.md documents all versions
- [ ] Repository description and topics are set
- [ ] GitHub Pages is enabled (if desired)
- [ ] All links in README work correctly

---

## 🚨 If You Accidentally Commit Credentials

**Immediate action:**

1. **Change your password/API key** on Game Crafter
2. **Delete the repository** (Settings → Danger Zone → Delete)
3. **Create new repository** following this guide
4. **Never mention the password** in any commit, issue, or PR

**Why?** Git history is permanent. Even if you delete a file, the password remains in history forever.

---

## 📞 Need Help?

- GitHub Docs: [Creating a new repository](https://docs.github.com/en/get-started/quickstart/create-a-repo)
- GitHub Docs: [GitHub Pages](https://docs.github.com/en/pages)
- Git Basics: [Git - The Simple Guide](https://rogerdudler.github.io/git-guide/)

---

**You're ready to upload!** 🎉

Follow the steps above and your project will be live on GitHub in ~5 minutes.
