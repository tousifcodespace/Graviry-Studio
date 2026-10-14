# GRAVITY — Digital Studio

A one-page site with a full-screen real-time WebGL "gravity field" of
physically simulated spheres (Three.js), driven by scroll progress through
four sections, plus a palette-switching "Studio Controls" drawer.

## Files

- `index.html` — page structure (header, 4 sections, footer, loader, drawer)
- `style.css` — all styling (glassmorphism, type, layout, reveal animations)
- `script.js` — smooth scroll, scroll-driven physics, loader, reveals, and
  the Three.js scene (ES module, imports Three.js from a CDN via importmap)
- `assets/` — empty on purpose; the scene is 100% procedural, no textures/images

## Running it

Because `script.js` is loaded as an ES module (`<script type="module">`),
most browsers will block it from `file://` due to CORS. Serve the folder
over `http://` instead, e.g. from inside `gravity-studio/`:

```bash
# Python
python3 -m http.server 8080

# or Node
npx serve .
```

Then open `http://localhost:8080`.

## What's wired up (every button works)

- **Sliders icon** (header) → opens the Studio Controls drawer
- **Close (×)** / **clicking the scrim** / **Esc** → closes the drawer
- **Contact us** pill & nav links (`Works / Services / Team / Story / Contact`)
  → smooth-scroll to the matching section
- **4 palette cards** in the drawer → tears down and rebuilds the WebGL
  scene with the new sphere color (Royal Blue, Rose Blush, Volt Lime, Arctic Sky)
- **Reset Defaults** → rebuilds back to Royal Blue
- **Email pill** (footer) → opens a `mailto:hello@gravity.studio`
- **Footer link columns & social icons** → real anchors/links (internal
  sections scroll smoothly; external social icons open in a new tab)
- Cursor repels the spheres everywhere; click-and-hold strengthens the repel
