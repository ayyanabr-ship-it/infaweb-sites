# InfaWeb — Website

Immersive underwater-themed marketing site for InfaWeb. Two pages:

- `index.html` — Homepage (animated WebGL hero, scroll-driven "worlds", contact form)
- `about.html` — About page (animated ocean, concept work, pricing, CTA)

## Tech

Plain static HTML. Each page mounts a small self-contained runtime (`support.js`) that
loads React 18 from a CDN (unpkg) and renders the page. No build step, no npm install.

- Fonts: Google Fonts (loaded via CDN)
- React/ReactDOM: unpkg CDN (also preloaded in each page's `<head>`)
- Images: repo root, alongside the HTML files
- Contact form: posts to Formspree (`https://formspree.io/f/xgojlkpn`)

## Run locally

Any static file server works, e.g.:

```bash
npx serve .
# or
python3 -m http.server 8000
```

Then open http://localhost:8000 . (Opening the file directly with file:// also works,
but a server is recommended so relative asset paths resolve cleanly.)

## Deploy to Vercel

This is a zero-config static site.

1. Push this folder to a GitHub repo.
2. In Vercel: **New Project → Import** the repo.
3. Framework preset: **Other**. Build command: *(leave empty)*. Output directory: **/** (root).
4. Deploy. `index.html` is served at `/`, `about.html` at `/about.html`.

(Or from this folder: `npm i -g vercel && vercel`.)

## Notes

- **Internet required at runtime** for the React CDN and Google Fonts (standard for most sites).
- **Contact form:** submissions go to the Formspree form `xgojlkpn`. Before it delivers email,
  submit once and confirm the activation email Formspree sends to the form owner's address.
- Keep `support.js` and the image `.png` files alongside the HTML files — they're required.
