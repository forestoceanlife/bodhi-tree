# Bodhi Tree — public website

Public-facing pages required by the App Store: **Privacy Policy** and **Support**, plus a small landing page. Designed to be hosted via GitHub Pages.

## Structure

```
.
├── index.html          # Landing page
├── privacy/
│   └── index.html      # Privacy Policy
├── support/
│   └── index.html      # Support / FAQ
├── styles.css          # Shared stylesheet (warm, calm palette)
├── .nojekyll           # Tell GitHub Pages to skip Jekyll processing
└── README.md           # This file
```

## Local preview

```bash
cd bodhitree-website
python3 -m http.server 8080
# open http://localhost:8080
```

Or just double-click `index.html`.

## Deploy on GitHub Pages

The recommended setup is a project repo (`forestoceanlife/bodhi-tree`) deployed from the `main` branch:

```bash
cd bodhitree-website

# Initialize a fresh repo (if not already done)
git init
git add .
git commit -m "Initial public site: privacy + support"
git branch -M main

# Create the repo on github.com/forestoceanlife/bodhi-tree first, then:
git remote add origin git@github.com:forestoceanlife/bodhi-tree.git
git push -u origin main
```

Then on github.com:

1. Open **Settings → Pages**
2. Under **Build and deployment**, set **Source: Deploy from a branch**
3. Select **Branch: main** and **Folder: / (root)**
4. Save. The site appears at `https://forestoceanlife.github.io/bodhi-tree/` within a minute.

## URLs to paste into App Store Connect

Once GitHub Pages is enabled:

- **Privacy Policy URL**: `https://forestoceanlife.github.io/bodhi-tree/privacy/`
- **Support URL**: `https://forestoceanlife.github.io/bodhi-tree/support/`

## Editing later

The pages are plain HTML; edit either `privacy/index.html` or `support/index.html` and push. GitHub Pages redeploys within a minute. The styling is shared in `styles.css`.

If you want to add a Traditional Chinese version later, copy the two pages to `zh-Hant/privacy/index.html` and `zh-Hant/support/index.html`, translate the content, and link them from the header.
