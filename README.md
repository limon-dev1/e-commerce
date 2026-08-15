# MD Limon Ali — Portfolio

## File structure

```
/
├── index.html          Structure & content
├── style.css            All styling (design tokens at the top)
├── script.js            Scroll reveals, stat counters, contact form
├── three-scene.js       The 3D hero scene (Three.js)
├── Md-Limon-Ali-Resume.pdf   Your resume (used by the "Resume" button)
└── assets/
    ├── profile.png      Your hero photo — MUST be a transparent PNG (see below)
    ├── logo.png          Small logo shown top-left in the navbar
    ├── favicon.png       Browser tab icon
    └── projects/
        ├── vira-skincare.jpg
        ├── fashion-trends.jpg
        ├── car-servicing.jpg
        ├── home-cleaning.jpg
        ├── woocommerce-store.jpg
        └── portfolio.jpg
```

## Your hero photo — `assets/profile.png`

**File name must be exactly `assets/profile.png`.** It needs to be a **PNG with a transparent background**, not a JPG — JPGs can't have transparency. This one file is used two ways automatically by the CSS:
- On mobile, it's cropped into a circle with a white border.
- On desktop, it floats free with no frame — the transparent background lets it blend into the 3D scene instead of sitting in a box.

If you don't have a background-removed photo, use an AI photo editor (e.g. Photoroom, remove.bg, or an image model like Nano Banana/GPT image edit) with a prompt like:

> Remove the background from this photo and make it fully transparent. Keep the subject's edges natural and sharp, especially around hair and shoulders. Do not add any new background. Keep it photorealistic — no illustration or cartoon style. Slight warm, soft color grade to the lighting. Output as a high-resolution transparent PNG, portrait crop from the shoulders up, subject centered.

If `assets/profile.png` is missing, the site simply hides that spot instead of showing a broken image — it won't look buggy.

## Your logo — `assets/logo.png`

This replaces the "ML/" text mark in the top-left of the navbar. **File name must be exactly `assets/logo.png`**, ideally a transparent PNG or SVG renamed to `.png`, roughly square, at least 100×100px (it displays at 28px tall).

AI logo prompt:

> Design a minimal monogram logo using the initials "ML" for a web developer. Clean geometric sans-serif or monospace letterforms, flat single-color line-art style in terracotta (#B0663F), on a transparent background. Must read clearly at small sizes like 28px tall. No gradients, no shadows, no 3D effects. Optionally incorporate a forward slash "/" to echo code syntax. Export as a transparent PNG or SVG, square canvas.

Until you add this file, the site automatically falls back to showing the "ML/" text mark — nothing breaks.

## Your favicon — `assets/favicon.png`

The small icon shown in the browser tab. **File name must be exactly `assets/favicon.png`**, 512×512px, PNG.

AI favicon prompt:

> Create a simple square icon, 512×512px, transparent or solid cream (#FCF8F0) background, using the letters "ML" or a single minimal geometric shape (e.g. an icosahedron outline) in terracotta (#B0663F). Bold and legible at tiny sizes like 16×16px — flat design, no gradients, no shadows, no fine detail that disappears when shrunk.

## Adding your project images

Drop screenshots into `assets/projects/` using the exact filenames listed above.
If an image is missing, the card gracefully shows an "Add project image" placeholder instead of breaking — so the site never looks buggy while you're still collecting screenshots. Recommended: 1200×750px, JPG, under 300KB each (compress at squoosh.app or tinypng.com so the site stays fast).

## Adding your resume

Export your resume as `Md-Limon-Ali-Resume.pdf` and place it in the root folder (same level as `index.html`). The "Resume" button in the hero downloads it directly.

## Hosting on GitHub Pages

1. Create a new repository (e.g. `portfolio` or `<your-username>.github.io` if you want it at the root domain).
2. Push all files in this folder to the repository root — `index.html` must be at the top level, not inside a subfolder.
3. In the repo: **Settings → Pages → Source → Deploy from a branch → main → / (root) → Save**.
4. Your site will be live at `https://<username>.github.io/<repo-name>/` within a minute or two.

```bash
git init
git add .
git commit -m "Portfolio site"
git branch -M main
git remote add origin https://github.com/<your-username>/<repo-name>.git
git push -u origin main
```

## Notes on the 3D hero

- Built with Three.js (loaded from a CDN — no build step, no npm required).
- On load, the shapes scale up from nothing and settle into place — a nod to code "compiling."
- On desktop, the shapes gently follow your mouse (parallax). On mobile, this is disabled and the canvas opacity is reduced for performance and battery life.
- If a visitor has "reduce motion" enabled in their OS, the scene renders statically — no spinning, no parallax.

## Customizing

- Colors, fonts, and spacing are all defined as CSS variables at the top of `style.css` under `:root` — change a value there and it updates everywhere.
- Skill bar percentages are set inline in `index.html` via `style="--w:90%"` on each `<li>` — adjust to taste.
- Stat numbers (projects shipped, platforms, etc.) are set via `data-target` attributes on `.stat-number` elements in `index.html`.
