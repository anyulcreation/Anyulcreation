# Anyul Creation Website
Static, responsive storefront (no build step). Open `index.html` directly, or upload the whole folder to GitHub Pages / Netlify / any static host.
- Product data is embedded in `index.html` (a copy lives in `data.json` for reference) — edit prices/products there.
- Bag is saved in the visitor's browser; "Order on WhatsApp" sends the full order to +91 74900 97263.

## Clean URLs (no `#`)
Pages now use normal paths: `/shop/Men`, `/p/horse`, `/about` (also works inside a GitHub Pages `/your-repo/` folder).
- `404.html` is an exact copy of `index.html` — GitHub Pages serves it for any deep link so reloads and shared links keep working. **If you edit `index.html`, copy it over `404.html` again.**
- `_redirects` does the same job on Netlify / Cloudflare Pages.
- Old links like `#/p/horse` automatically turn into `/p/horse`.
- Opening `index.html` straight from your computer (file://) cannot use clean paths, so it falls back to `#` there only. On any real host the address bar stays clean.

## Header & mobile notes
- Header: floating rounded bar at the top of the page; after a small scroll it slides into a full-width bar attached to the top (same menu, same text). Styles are in the "HEADER" block at the end of the `<style>` in `index.html`.
- Mobile (<= 900px): slider shows the whole banner with the text underneath; each banner's focus point is set in the `--mpos` value of the slide image. Tested for sideways overflow from 320px to 1024px wide.
- After editing `index.html`, copy it over `404.html` again (GitHub Pages deep-link fallback).
