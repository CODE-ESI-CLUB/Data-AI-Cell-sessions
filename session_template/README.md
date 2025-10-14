# Session Template

Template for creating new Data & AI Cell sessions.

## 📁 Structure

```
session_XX/
├── README.md          # Session details (fill this out)
├── slides/            # Presentation slides (PDF only)
└── src/               # Code, notebooks, and data
    └── README.md      # How to run the code (create this)
```

## 🚀 Quick Start

```bash
# Copy template
cp -r session_template/ session_XX/
cd session_XX/
```

## 📝 What to Add

### 1. Main README.md
Fill in with:
- Session title & objectives
- Prerequisites
- Topics covered

### 2. Slides (PDF format)
- Use our [Canva Template](https://www.canva.com/design/DAG1tl9NsUc/7xSuFY1o9OycR4yhanqDwQ/edit?utm_content=DAG1tl9NsUc&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton)
- Export as PDF
- Save in `slides/` folder

### 3. Code & Notebooks
Add to `src/`:
- Jupyter notebooks (`.ipynb`)
- Python scripts (`.py`)
- Data files

**Important:** Create `src/README.md` explaining:
- How to run the code
- What each file does
- Installation requirements

### 4. Before Committing
```bash
# Strip notebook outputs
jupyter nbconvert --clear-output --inplace src/*.ipynb
```

## ✅ Checklist

- [ ] Main README filled out
- [ ] Slides in PDF format (using Canva template)
- [ ] `src/README.md` created with run instructions
- [ ] Notebook outputs stripped
- [ ] Code tested

---

See [CONTRIBUTING.md](../CONTRIBUTING.md) for full contribution guide.
