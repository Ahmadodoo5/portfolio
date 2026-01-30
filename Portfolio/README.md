# AM Odoo Solutions — Portfolio Website

A single-page portfolio site inspired by the [LanX Framer template](https://landerx.framer.website/), branded for **AM Odoo Solutions** and focused on **Odoo implementation and all services**.

## Contents

- **index.html** — Main page with hero, features, benefits, testimonials, pricing, integrations, comparison, FAQ, and contact/footer
- **styles.css** — Layout, typography, and component styles (dark theme)
- **script.js** — FAQ accordion, mobile nav toggle, footer year

## Contact (on site)

- **Phone:** 0305-6567570 · 0335-4160621  
- **Email:** m.ahmadodoo5@gmail.com  
- **LinkedIn:** [linkedin.com/in/ahmad-odoo5](https://www.linkedin.com/in/ahmad-odoo5)

## How to open

1. **Direct open:** Double-click `index.html` or open it in your browser (file://).
2. **Local server (recommended):** From this folder run:
   - Python 3: `python -m http.server 8080`
   - Node: `npx serve .`
   Then visit `http://localhost:8080` (or the port shown).

## Customization

- Edit **index.html** for copy, sections, and links.
- Edit **styles.css** and `:root` variables for colors and spacing.
- Add or change FAQ items in the `.faq-list` block and ensure each has `.faq-item`, `.faq-question`, and `.faq-answer`.

No build step required. Works in modern browsers.

## Deploy to Vercel (fixing NOT_FOUND / 404)

If this repo is **custom_addons** (or the repo root is not the `Portfolio` folder), Vercel will serve from the repo root. There is no `index.html` at that root, so you get **NOT_FOUND** (404).

**Fix:** Set the project **Root Directory** so Vercel uses the folder that contains `index.html`:

1. Vercel Dashboard → your project → **Settings** → **General**.
2. Under **Root Directory**, set it to the path to this folder:
   - If the connected repo is **custom_addons**: use `Portfolio`.
   - If the connected repo is **Odoo19_work** (parent): use `custom_addons/Portfolio`.
3. Save and **redeploy**.

After this, the site root URL will serve `Portfolio/index.html` and NOT_FOUND will go away.

The `vercel.json` in this folder tells Vercel this is a static site (no build). The optional rewrite sends path-based URLs (e.g. `/about`) to `index.html` so you can add more routes later without changing config.
