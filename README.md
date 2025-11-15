# fx-directory (static for GitHub Pages)

This repository contains a small personal portfolio/site originally using PHP includes. GitHub Pages only serves static sites, so I converted the main pages to static HTML so you can host them on GitHub Pages.

What I added/changed:
- Converted `about.php`, `project.php`, `library.php` into `about.html`, `project.html`, `library.html`.
- Updated `index.html` menu links to point to `.html` pages.
- Added `tools.html` placeholder and `.nojekyll` to avoid Jekyll processing.

How to publish on GitHub Pages:

1. Create a new repository on GitHub (or use an existing one). Name doesn't have to match the site.
2. Commit and push this project to the repository's `main` branch.
   Example (PowerShell):

```powershell
git init
git add .
git commit -m "Prepare static site for GitHub Pages"
git branch -M main
git remote add origin https://github.com/<your-username>/<your-repo>.git
git push -u origin main
```

3. In the GitHub repository settings -> Pages, set Source to `main` branch and folder `/ (root)`.
4. Wait a minute, then your site will be available at `https://<your-username>.github.io/<your-repo>/`.

Notes and follow-ups:
- The site assets (images, icons, `asset/style.css`) are referenced relatively — they will work as long as the `asset/` folder is present in the repository root.
- If you prefer the repo to be published as a user/organization page (no repo name in URL), name the repo `<your-username>.github.io` and push to its `main` branch.
- If you want to keep using PHP (server-side), GitHub Pages can't run PHP. Consider a host that supports PHP (DigitalOcean, Render, or a VPS), or use a GitHub Action to build static HTML from PHP if you can run PHP in CI and capture the output.

If you want, I can:
- Update the rest of the links and create nicer metadata (OG tags, page titles) for SEO.
- Generate a small GitHub Actions workflow that uses PHP to render pages and produce static files automatically.
