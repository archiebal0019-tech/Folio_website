# Archie Ballinger — Portfolio

Personal portfolio site. Static HTML, CSS and vanilla JavaScript. No build step, no dependencies.

## Files

| Path | What it is |
| --- | --- |
| `index.html` | Landing page and all seven project pages, in one self-contained file |
| `resume.html` | CV page, matching the same design system |
| `resume-data.js` | Base64 CV PDF, read by the Download PDF button on `resume.html` |
| `images/` | 48 project images |
| `.nojekyll` | Tells GitHub Pages to serve the files as-is |

The only external requests are Google Fonts. Everything else is local.

## Publishing to GitHub Pages

From this folder:

```bash
git init
git add .
git commit -m "Portfolio site"
git branch -M main
git remote add origin https://github.com/<your-username>/<repo-name>.git
git push -u origin main
```

Then in the repository on github.com: **Settings → Pages → Source: Deploy from a branch → Branch: `main` / `/ (root)` → Save.**

The site appears at `https://<your-username>.github.io/<repo-name>/` within a minute or two.

To publish at `https://<your-username>.github.io/` instead, name the repository `<your-username>.github.io`.

### Custom domain

Add a file named `CNAME` containing only your domain (for example `archieballinger.com`), then point the domain's DNS at GitHub Pages and set the domain under Settings → Pages.

## Running it locally

Open `index.html` in a browser. Everything works from the file system.

## Editing

- **Colour** is defined once as CSS custom properties at the top of `index.html`, and again for dark mode. Change a token there and it propagates everywhere.
- **The backdrop** is `images/studio-backdrop.jpg`, drawn by `.bg-photo`. Its framing is the `center 58%` value in that rule. Blur and veil are driven by `--bg-progress`, written by the scroll handler and tuned per breakpoint.
- **Image sizing rule:** never display an image wider than its source. Every image slot carries `--natw` (the file's true pixel width) and `--ar` (its aspect ratio) inline; the CSS caps display width at `--natw / 1.3`. When adding an image, set both to the real dimensions.
- **Breakpoints** are 1000px and 640px, plus a landscape rule at 560px tall.
