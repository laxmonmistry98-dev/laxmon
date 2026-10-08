# Laxmon Mistry — WordPress & PHP Developer Portfolio

Premium 5-page portfolio: `index.html`, `about.html`, `services.html`, `projects.html`, `contact.html`.
Plain HTML5 / CSS3 / vanilla JS (no frameworks) + a small secure PHP contact backend.

## 1. Add your photo (important)
Save your photo as **`images/laxmon.jpg`** (portrait, ~800x1000, JPG/WebP-renamed-to-jpg).
Until then the site shows `images/profile-placeholder.svg`, so nothing is ever broken.
For the dark "developer studio" look, edit the photo (background removal + dark/blue-purple backdrop)
in Photoshop, Photopea, remove.bg + Canva, or an AI photo editor, then export as `laxmon.jpg`.
(I cannot see or edit uploaded photos in this chat, so no photo was embedded.)

## 2. Replace dummy project images
Files `images/project-*.svg` are generated device mockups. Drop in real screenshots
(e.g. `project-restaurant.jpg`) and update the filename in `tools/build.py` (PROJECTS list), then run:
    python3 tools/build.py
Edit all page copy in `tools/build.py` and re-run it — or edit the generated HTML directly.
To regenerate placeholder art: `python3 tools/gen_assets.py`.

## 3. Contact form (PHP)
Edit `includes/config.php` → `CONTACT_RECIPIENT` and `CONTACT_FROM` (use an address on your own domain).
Features: CSRF token (session), honeypot, time-trap, math human-check, allow-listed selects, server-side
validation + sanitisation, header-injection protection, rate limiting, optional log in `/storage`.
Requires PHP 8.1+ hosting (cPanel, shared hosting, VPS). Make `/storage` writable if you keep LOG_MESSAGES.

**Netlify note:** Netlify does not run PHP. On Netlify the form shows a friendly error with your email link.
Options: host on PHP hosting, or switch the form to Netlify Forms / Formspree.

## 4. Replace placeholders
- Email: `contact@laxmonmistry.com` (in `tools/build.py` + `includes/config.php`)
- Social links: `SOCIAL` dict in `tools/build.py` (currently generic profile roots)
- Live Demo links: `DEMO` in `tools/build.py`
- Journey dates, project descriptions and skill percentages are sample content — make them yours.

## Structure
/index.html /about.html /services.html /projects.html /contact.html
/css/style.css  /js/main.js  /images/  /includes/ (config.php, token.php, contact-handler.php)
/storage/ (message log, web-blocked)  /tools/ (build.py, gen_assets.py)
