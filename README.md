# Bhanishi Sharma – Portfolio

A single-page static portfolio. No build step, no dependencies, no framework.

## Folder contents

| File | Purpose |
|---|---|
| `index.html` | The whole site (HTML, CSS and a tiny bit of markup-only animation) |
| `netlify.toml` | Optional. Security headers and publish settings for Netlify |
| `.nojekyll` | Optional. Tells GitHub Pages to serve files as-is |
| `README.md` | This guide |

## Preview locally

Open `index.html` in a browser. Or, for a local server:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Deploy (pick one)

### Option A: Netlify Drop (fastest, about 1 minute)
1. Go to https://app.netlify.com/drop
2. Drag this whole folder onto the page.
3. You get a live URL immediately. Rename it under Site settings > Change site name.

### Option B: GitHub Pages (free, good for a permanent URL)
1. Create a new public repo, for example `portfolio`.
2. Upload the folder contents (or push with git):
   ```bash
   git init
   git add .
   git commit -m "Initial portfolio"
   git branch -M main
   git remote add origin https://github.com/<your-username>/portfolio.git
   git push -u origin main
   ```
3. In the repo go to Settings > Pages > Source: "Deploy from a branch" > `main` / `/ (root)` > Save.
4. Your site appears at `https://<your-username>.github.io/portfolio/` in a minute or two.

### Option C: Vercel
1. Push the folder to GitHub (as above).
2. At https://vercel.com/new import the repo.
3. Framework preset: **Other**. Leave build command and output directory empty. Deploy.

## Custom domain
Buy a domain, then add it in your host's dashboard (Netlify: Domain management; GitHub Pages: Settings > Pages > Custom domain; Vercel: Settings > Domains). Follow the DNS records the host shows. HTTPS is issued automatically.

## Editing the content

Everything is in `index.html`. Search for these markers:

- **Name, role, intro:** the `<div class="hero">` block
- **Experience:** `<ol class="tl">`, one `<li>` per job
- **Skills:** `<div class="skills">`, one `.card` per group, one `<li>` per chip
- **Projects:** `<div class="projects">`, one `<article class="card">` per project
- **Contact links:** `<section id="contact">`
- **Colors:** the CSS variables at the top of `<style>` (`--accent`, `--bg`, `--ink`). Dark-mode values are in the `prefers-color-scheme: dark` block.

## Before you go live (checklist)
- [ ] Remove any skill chip you cannot discuss in an interview (JWT, Docker, query optimization and Linux were added by inference).
- [ ] Add the real deployment stack you used (AWS, VPS, Docker, CI/CD) to the Certainty entry.
- [ ] Expand both projects with stack, scale and your role.
- [ ] Decide whether to keep the phone number public. Email and LinkedIn are usually enough.
- [ ] Replace `og:description` and the `<meta name="description">` in `<head>` if you change your pitch.
- [ ] Optional: add a profile photo and a link to a PDF resume (place `resume.pdf` next to `index.html` and link it with `<a href="resume.pdf" download>`).

## Notes
- Fonts load from Google Fonts. If offline, the site falls back to system fonts.
- The site follows the visitor's light or dark system setting automatically.
