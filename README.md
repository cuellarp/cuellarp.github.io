# Patricia Cuellar — Portfolio Site

A single-page portfolio site built with plain HTML/CSS/JS (no build tools, no dependencies).

## File structure

```
portfolio-site/
├── index.html
├── css/style.css
├── js/script.js
├── assets/docs/Patricia-Cuellar-Resume.pdf   ← downloadable resume
└── serve.ps1                                  ← local preview server (optional)
```

## Preview it locally

Just double-click `index.html` — it opens fine directly in any browser (Chrome, Edge, etc.).

If you want it served over `http://localhost` instead (e.g. to test the contact form), run:

```powershell
powershell -ExecutionPolicy Bypass -File serve.ps1
```

Then visit `http://localhost:8080/`. Press Ctrl+C in that terminal to stop it.

## Before you launch it — 2 things to finish

### 1. Add your photo
Right now the header shows a "PC" placeholder circle instead of a photo. To swap it in:
1. Save your headshot as `assets/img/headshot.jpg` (create the `img` folder).
2. In `index.html`, find `<div class="avatar" aria-hidden="true">PC</div>` and replace it with:
   ```html
   <img class="avatar" src="assets/img/headshot.jpg" alt="Patricia Cuellar">
   ```
3. In `css/style.css`, under `.avatar`, add `object-fit: cover;` so the photo crops nicely into the circle.

### 2. Connect the contact form
The form currently points to a placeholder (`https://formspree.io/f/YOUR_FORM_ID`) and will show an error if someone submits it. To make it live, for free:
1. Go to [formspree.io](https://formspree.io) and sign up (free tier = 50 submissions/month).
2. Create a new form, copy the endpoint it gives you (looks like `https://formspree.io/f/abc123xy`).
3. In `index.html`, replace `YOUR_FORM_ID` in the `<form action="...">` line with your real endpoint.

Until you do this, recruiters can still always reach you via the email/phone/LinkedIn links, which work immediately with no setup.

## Deploying for free (recommended: GitHub Pages)

1. Create a free GitHub account if you don't have one, and create a new repository (e.g. `portfolio`).
2. Upload the entire contents of this `portfolio-site` folder to that repository (drag-and-drop works fine on github.com, or use Git).
3. In the repo, go to **Settings → Pages**, set Source to the `main` branch / root folder, and save.
4. GitHub gives you a live URL like `https://yourusername.github.io/portfolio/` within a minute or two.

**Alternative — Netlify (drag-and-drop, no GitHub needed):**
1. Go to [app.netlify.com/drop](https://app.netlify.com/drop).
2. Drag the `portfolio-site` folder onto the page.
3. Netlify gives you a live URL immediately (e.g. `https://random-name.netlify.app`), which you can rename in site settings.

Both are free and give you a link you can put directly on your resume or LinkedIn.

## Updating content later

All the text lives in `index.html` — experience bullets, highlight cards, skills, and education are plain HTML you can edit directly. No rebuild step needed; just save and refresh (or re-upload if already deployed).
