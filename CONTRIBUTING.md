# Contributing to Data & AI Cell Sessions

Thank you for contributing to the Data & AI Cell Sessions! 🎉

Follow this guide to add your session materials to the repository.

## 🤝 How to Contribute

### Step 1: Fork & Clone (First Time Only)
```bash
# Fork the repository on GitHub first, then:

# Clone your fork
git clone https://github.com/YOUR-USERNAME/Data-AI-Cell-sessions.git
cd Data-AI-Cell-sessions

# Add upstream remote
git remote add upstream https://github.com/CODE-ESI-CLUB/Data-AI-Cell-sessions.git

# Verify remotes
git remote -v
```

### Step 2: Create a Feature Branch
```bash
# Make sure you're on main
git checkout main

# Pull latest changes from upstream
git pull upstream main

# Create and switch to your feature branch
git checkout -b feat/session05-neural-networks

# Verify you're on the new branch
git branch
```

**Branch naming format:** `feat/sessionXX-topic`

**Examples:**
- `feat/session01-python-basics`
- `feat/session05-neural-networks`
- `feat/session12-nlp-transformers`

### Step 3: Add Your Session Content
```bash
# Copy the template to create your session folder
cp -r session_template/ session_05/

# Navigate to your session folder
cd session_05/

# Edit the README.md with your session details
nano README.md  # or use: code README.md

# Add your slides to the slides/ folder
cp /path/to/your/slides.pdf slides/

# Add your notebooks and code to src/
cp /path/to/your/notebook.ipynb src/

# Go back to repo root
cd ..
```

**Session folder structure:**
```
session_05/
├── README.md          # Session documentation
├── slides/            # Your presentation files
└── src/              # Notebooks and code
```

### Step 4: Strip Notebook Outputs (REQUIRED!)
```bash
# Install nbstripout (first time only)
pip install nbstripout

# Strip outputs from ALL notebooks in your session
jupyter nbconvert --clear-output --inplace session_05/src/*.ipynb

# Alternative: using nbstripout
nbstripout session_05/src/*.ipynb

# Verify outputs are cleared
git diff session_05/src/your_notebook.ipynb
```

**Why strip outputs?**
- Keeps the repository clean and small
- Avoids merge conflicts
- Removes sensitive data from outputs
- Makes diffs readable

### Step 5: Stage and Commit Your Changes
```bash
# Check what files you've changed
git status

# Stage all your session files
git add session_05/

# Or stage specific files
git add session_05/README.md session_05/src/*.ipynb session_05/slides/*

# Commit with a conventional message
git commit -m "feat(session05): add neural networks tutorial"

# View your commit
git log -1
```

**Commit message format:** `<type>(sessionXX): <description>`

**Commit types:**
- `feat` - New session or feature
- `docs` - Documentation updates
- `fix` - Bug fixes or corrections
- `refactor` - Code improvements
- `chore` - Maintenance tasks

**Examples:**
```bash
git commit -m "feat(session05): add neural networks tutorial"
git commit -m "docs(session05): update learning objectives"
git commit -m "fix(session03): correct preprocessing function"
git commit -m "chore: update requirements.txt"
```

### Step 6: Push to Your Fork
```bash
# Push your branch to YOUR fork
git push origin feat/session05-neural-networks

# Git will show you the PR link - copy it!
```

### Step 7: Create a Pull Request
```bash
# Go to GitHub in your browser:
# https://github.com/YOUR-USERNAME/Data-AI-Cell-sessions

# You'll see a banner "Compare & pull request" - click it!
```

**Manual PR creation:**
1. Go to: https://github.com/CODE-ESI-CLUB/Data-AI-Cell-sessions
2. Click "Pull requests" tab
3. Click "New pull request"
4. Click "compare across forks"
5. Select your fork and branch
6. Fill in title and description
7. Request at least 1 reviewer
8. Click "Create pull request"

**PR Title Format:** `feat(sessionXX): Brief description`

**PR Description Template:**
```markdown
## Session Details
- **Session Number:** 05
- **Topic:** Neural Networks
- **Duration:** 2 hours

## Changes
- Added session materials
- Included slides and notebooks
- Updated documentation

## Checklist
- [ ] Followed branch naming convention
- [ ] Stripped notebook outputs
- [ ] Updated session README
- [ ] Tested all code/notebooks
- [ ] Requested reviewer(s)
```

### Step 8: Address Review Comments
```bash
# If reviewers request changes, make them locally
code session_05/src/notebook.ipynb

# Strip outputs again if you edited notebooks
jupyter nbconvert --clear-output --inplace session_05/src/*.ipynb

# Stage and commit the changes
git add session_05/
git commit -m "fix(session05): address review comments"

# Push to update the PR
git push origin feat/session05-neural-networks
```

### Step 9: After PR Approval & Merge
```bash
# Once merged, sync your local main
git checkout main
git pull upstream main

# Delete your feature branch (cleanup)
git branch -d feat/session05-neural-networks
git push origin --delete feat/session05-neural-networks
```

## 🚫 Important Rules

- ⛔ **Never push directly to `main`**
- ⛔ **Never merge without review approval**
- ⛔ **Never commit notebooks with outputs**
- ⛔ **Never commit large datasets** (use `.gitignore` or provide download links)

## 📋 Quick Reference

### Common Git Commands
```bash
# Check status
git status

# View branches
git branch -a

# Switch branches
git checkout branch-name

# Pull latest changes
git pull upstream main

# View commit history
git log --oneline -10

# Undo last commit (keep changes)
git reset --soft HEAD~1

# Discard uncommitted changes
git checkout -- filename
```

### Notebook Output Stripping
```bash
# Single notebook
jupyter nbconvert --clear-output --inplace notebook.ipynb

# All notebooks in folder
jupyter nbconvert --clear-output --inplace src/*.ipynb

# Using nbstripout
nbstripout src/*.ipynb

# Setup auto-strip (one-time)
nbstripout --install --attributes .gitattributes
```

## 💡 Best Practices

1. **Keep commits focused** - One logical change per commit
2. **Write clear messages** - Describe what and why, not how
3. **Test before pushing** - Run all notebooks to ensure they work
4. **Document well** - Update READMEs with clear instructions
5. **Review your own PR** - Check the diff before requesting reviews
6. **Respond promptly** - Address review comments quickly
7. **Keep it clean** - Remove unnecessary files and outputs

## ❓ Need Help?

- 📖 Read the [main README](README.md)
- 💬 Ask in [Discord](https://discord.gg/UbyuzfKK)
- 📧 Email: code@esi.ac.ma
- 🐛 [Open an issue](https://github.com/CODE-ESI-CLUB/Data-AI-Cell-sessions/issues)

---

**Thank you for contributing! 🙏**

*CODE ESI CLUB - Data & AI Cell*
