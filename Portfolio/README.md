# AM Odoo Solutions — Portfolio Website

A single-page portfolio site inspired by the [LanX Framer template](https://landerx.framer.website/), branded for **AM Odoo Solutions** and focused on **Odoo implementation and all services**.

## Contents

- **index.html** — Main page with hero, features, benefits, testimonials, pricing, integrations, comparison, FAQ, and contact/footer
- **styles.css** — Layout, typography, and component styles (dark theme)
- **script.js** — FAQ accordion, mobile nav toggle, footer year
- **vercel.json** — Vercel project config (static site, no build, SPA-style rewrites)

## Contact (on site)

- **Phone:** 0305-6567570 · 0335-4160621  
- **Email:** m.ahmadodoo5@gmail.com  
- **LinkedIn:** [linkedin.com/in/ahmad-odoo5](https://www.linkedin.com/in/ahmad-odoo5)

## How to open locally

1. **Direct open:** Double-click `index.html` or open it in your browser (file://).
2. **Local server (recommended):** From this folder run:
   - Python 3: `python -m http.server 8080`
   - Node: `npx serve .`
   Then visit `http://localhost:8080` (or the port shown).

No build step required. Works in modern browsers.

---

## Vercel par deploy karein (Project setup)

Vercel docs ke hisaab se ye project **static site** hai — koi build step nahi, sirf HTML/CSS/JS aur images.

### Option A: Git se (monorepo / subfolder)

Agar repo **custom_addons** (ya koi parent) hai aur site **Portfolio** folder mein hai:

1. [Vercel](https://vercel.com) → **Add New** → **Project** → apna repo connect karein.
2. **Root Directory** set karein:
   - **Settings** → **General** → **Root Directory** → **Edit**
   - Path: `Portfolio` (agar repo root = custom_addons) ya `custom_addons/Portfolio` (agar repo = Odoo19_work).
3. **Framework Preset:** Other (auto-detect ho sakta hai; `vercel.json` override karega).
4. **Deploy** dabayein.

Iske baad site root URL par `index.html` serve hogi, NOT_FOUND nahi aayega.

### Option B: CLI se (sirf Portfolio folder)

Agar aap **sirf** `Portfolio` folder deploy karna chahte ho (alag repo ya drag-drop jaisa):

1. [Vercel CLI](https://vercel.com/docs/cli) install karein: `npm i -g vercel`
2. Terminal mein `Portfolio` folder mein jao:
   ```bash
   cd path/to/Portfolio
   vercel
   ```
3. Login/ signup ke baad prompts follow karein; default settings se deploy ho jayega.

CLI se deploy karoge to root directory already `Portfolio` hogi, isliye Root Directory change karne ki zaroorat nahi.

### vercel.json kya karta hai

- **framework: null** — Koi framework (Next, etc.) use nahi; static files as-is serve.
- **buildCommand: null** — Koi build nahi.
- **outputDirectory: "."** — Site ki files yahi folder se serve hon.
- **cleanUrls: true** — `.html` extension URLs se hata kar clean URLs (e.g. `/` for index).
- **rewrites** — Jo path pe koi file nahi milti (e.g. `/about`), unhe `index.html` par bhejna (SPA-style), taake baad mein aap path-based routes add kar sako.

---

## Customization

- Edit **index.html** for copy, sections, and links.
- Edit **styles.css** and `:root` variables for colors and spacing.
- Add or change FAQ items in the `.faq-list` block and ensure each has `.faq-item`, `.faq-question`, and `.faq-answer`.
