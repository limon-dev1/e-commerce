# MD Limon Ali — Portfolio

## File structure

```
/
├── index.html          Structure & content
├── style.css            All styling (design tokens at the top)
├── script.js            Scroll reveals, stat counters, contact form
├── three-scene.js       The 3D hero scene (Three.js)
├── Md-Limon-Ali-Resume.pdf   Your resume (add this file — used by the "Resume" button)
└── assets/
    ├── profile.jpg      Not currently used in the design, but keep here if you add a photo later
    └── projects/
        ├── vira-skincare.jpg
        ├── fashion-trends.jpg
        ├── car-servicing.jpg
        ├── home-cleaning.jpg
        ├── woocommerce-store.jpg
        └── portfolio.jpg
```

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
