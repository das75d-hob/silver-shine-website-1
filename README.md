# Silver Shine Products — Website

A single-page website for **Silver Shine Products**, a Mumbai-based manufacturer of Corian and acrylic solid surface sheets, in business for 25 years.

## Files

```
index.html   → the entire website (HTML, CSS, and JS all in one file)
README.md    → this file
```

There are no other dependencies to install — it's a static site. Two Google Fonts are loaded from a CDN (`Space Grotesk`, `Inter`, `IBM Plex Mono`); everything else is self-contained.

## Viewing it locally

Just double-click `index.html`, or open it in a browser directly. No build step, no server required.

## Sections included

- **Header** — sticky nav with call button
- **Hero** — headline + animated "swatch fan" graphic (CSS/SVG, no stock photos)
- **Trust strip** — 25 years / Mumbai / custom colours stats
- **Products** — Corian sheets, countertops, wash basins, wall cladding, reception counters, custom fabrication
- **Why Us** — non-porous, seamless joints, thermoformable, UV/stain resistant, renewable finish
- **Process** — 5-step order-to-installation timeline
- **Colour Library** — sample swatch grid
- **Contact** — call, WhatsApp, and a working enquiry form
- **Footer**

## The enquiry form

The contact form has no backend — it works by packaging the visitor's name, phone number, and requirement into a message and opening **WhatsApp** with that message pre-filled to:

```
+91 87799 42023 (Biswa Ranjan Das)
```

The visitor just taps **Send** in WhatsApp to complete the enquiry. This means every submission is validated in the browser, but no data is stored anywhere by the website itself.

**To change the enquiry number:** open `index.html`, search for `BUSINESS_WHATSAPP`, and update the digits (country code + number, no `+` or spaces).

**To switch to email instead of WhatsApp**, or to route submissions to a form service (e.g. Formspree) so they land silently in an inbox, that logic lives in the `<script>` block near the bottom of `index.html`, inside the `enquiryForm.addEventListener('submit', ...)` handler — let your developer (or Claude) know and it can be swapped in.

## Customizing content

Everything is plain HTML/CSS in one file, organized by `<section>`:

| Section | Find it by searching for |
|---|---|
| Hero headline/copy | `class="hero"` |
| Stats strip | `class="strip"` |
| Product cards | `id="products"` |
| Features | `id="why"` |
| Process steps | `id="process"` |
| Colour swatches | `id="gallery"` |
| Contact details | `id="contact"` |
| Colors/fonts | `:root { ... }` at the top of the `<style>` block |

To update the phone number sitewide, search for `8779942023` / `+918779942023` and replace all instances.

## Deploying

**GitHub Pages (free, recommended):**
1. Create a new GitHub repository.
2. Upload `index.html` to it.
3. Go to **Settings → Pages → Deploy from branch**, select `main` / root, save.
4. Your site goes live at `https://<username>.github.io/<repo-name>/`.

**Any other static host** (Netlify, Vercel, cPanel, etc.): just upload `index.html` — no build process needed.

## Notes for the business owner

- Stats like "Est. 2000" and generic figures on the page are placeholders to support the "25 years" claim — replace with your actual founding year, address, and any real certifications.
- No stock product photography is used (to avoid copyright issues); all visuals are CSS-generated swatches. Real photos of your factory/products can be added later.
- Add your exact business address if you'd like a Google Maps embed in the Contact section.
