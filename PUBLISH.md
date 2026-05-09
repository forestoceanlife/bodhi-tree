# Publishing the site to GitHub Pages

The App Store URLs should be:

- Privacy Policy URL: `https://forestoceanlife.github.io/bodhi-tree/privacy/`
- Support URL: `https://forestoceanlife.github.io/bodhi-tree/support/`

As of the last local verification, both live URLs returned GitHub's 404 page. That means the pages are built locally but the GitHub Pages repo is not published yet, or Pages is not enabled for the repo.

## Step 1 — Confirm the GitHub repo exists

Open `https://github.com/forestoceanlife/bodhi-tree`.

If it does not exist, create it at `https://github.com/new`:

- Owner: `forestoceanlife`
- Repository name: `bodhi-tree`
- Visibility: Public
- Leave "Add a README", ".gitignore", and "license" unchecked

## Step 2 — Push this local website repo

The `bodhitree-website` folder already has its own local git repository and an initial commit. Do not delete its `.git` folder.

```bash
cd ~/Desktop/"Buddha Chat"/bodhitree-website

# If no remote is configured yet:
git remote add origin https://github.com/forestoceanlife/bodhi-tree.git

git add .
git commit -m "Update privacy and support pages"
git push -u origin main
```

If `git remote add origin` says the remote already exists, run this instead:

```bash
git remote set-url origin https://github.com/forestoceanlife/bodhi-tree.git
git push -u origin main
```

## Step 3 — Enable GitHub Pages

In the `forestoceanlife/bodhi-tree` repo:

1. Open Settings.
2. Open Pages.
3. Set Source to `Deploy from a branch`.
4. Set Branch to `main` and Folder to `/ (root)`.
5. Save.

GitHub Pages usually publishes within a few minutes.

## Step 4 — Verify before App Store submission

Run:

```bash
curl -I https://forestoceanlife.github.io/bodhi-tree/privacy/
curl -I https://forestoceanlife.github.io/bodhi-tree/support/
```

Both should return `HTTP/2 200` before the URLs are pasted into App Store Connect.

## Optional custom domain

The GitHub Pages URL is acceptable for v1.0. If you later point a custom domain such as `bodhitree.app` at GitHub Pages, update the canonical links in the HTML and update the App Store URLs.
