# Makerspace Guides — d-school Afrika

Static site for QR codes around the makerspace. Each machine gets its own page
with a quickstart, an idea-to-finished-product TL;DR, software/manual links,
and safety notes. Branded with the Hasso Plattner d-school Afrika colour
palette and dash motif.

## Folder structure

```
makerspace-site/
├── index.html              ← homepage, links to every machine
├── assets/
│   └── style.css            ← shared stylesheet (brand colours, layout)
├── h2d-printer/index.html
├── laser-cutter/index.html
├── cricut-maker/index.html
├── heat-press/index.html
├── hand-tools/index.html
├── 3d-scanner/index.html
├── spray-booth/index.html
└── sewing-embroidery/index.html
```

## Deploying to GitHub Pages

1. Drag this whole `makerspace-site` folder into VS Code (File → Open Folder).
2. Open the built-in terminal in VS Code and run:
   ```
   git init
   git add .
   git commit -m "Initial makerspace site"
   git branch -M main
   git remote add origin https://github.com/<your-username>/<your-repo>.git
   git push -u origin main
   ```
   (Create the empty repo on github.com first if you haven't already.)
3. On GitHub: go to your repo → **Settings → Pages** → under "Build and
   deployment", set **Source** to "Deploy from a branch", branch `main`,
   folder `/ (root)`. Save.
4. GitHub will give you a URL like:
   `https://<your-username>.github.io/<your-repo>/`
5. Each machine page will then live at a clean URL, e.g.:
   - `.../h2d-printer/`
   - `.../laser-cutter/`
   - `.../cricut-maker/`
   - `.../heat-press/`
   - `.../hand-tools/`
   - `.../3d-scanner/`
   - `.../spray-booth/`
   - `.../sewing-embroidery/`

## Generating your QR codes

Once the site is live, generate one **static** QR code per machine page
pointing straight at that machine's URL (not the homepage) — see the note on
static vs. dynamic QR codes below. Any free QR generator works
(e.g. the built-in one at qr-code-generator.com, or `qrencode` on the command
line). Print and stick one on/near each machine.

**Why static, not dynamic/programmable QR codes:** since this site lives on
GitHub Pages, you can update any page's content just by editing the file and
pushing — no need to route through a third-party redirect service to change
where a code points. Dynamic QR codes add an ongoing subscription and a
single point of failure (if their redirect service goes down, every code in
the space breaks, even though your site is fine). Keep the URLs above stable
forever and static codes give you everything you need.

## Editing content later

- To change wording, safety notes, or links for one machine: edit that
  machine's `index.html` directly.
- To change the shared look (colours, fonts, spacing): edit
  `assets/style.css` — it affects every page at once.
- To add a video for the heat press page (or any other page): see the
  commented-out embed snippet inside `heat-press/index.html`.
- To add a new machine: copy an existing machine folder, rename it, edit its
  content, and add a matching card to the grid in `index.html`.

## Brand reference

Colours (from the Hasso Plattner d-school Afrika Brand CI, 2021):
- Red `#d13327` — primary
- Teal `#00949c`
- Yellow `#f5ab33`
- Navy `#070b51`

Fonts: Avenir (primary), Helvetica (fallback) — both referenced in
`assets/style.css` with system-font fallbacks since Avenir isn't a free web
font.
