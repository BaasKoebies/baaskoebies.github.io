# baaskoebies.github.io

Personal portfolio site for **Tlhologello Biyana** — Data Scientist & Analytics Consultant.

Live at: https://baaskoebies.github.io/

---

## What's in here

```
.
├── index.html          the entire site (HTML + CSS + JS in one file)
├── favicon.svg         browser tab icon
├── .nojekyll           tells GitHub Pages to serve files as-is
├── README.md           this file
└── images/
    ├── portrait.jpg
    ├── personal-loans.jpg
    ├── recommender.jpg
    └── car-counter.jpg
```

No build step, no dependencies, no framework. Open `index.html` in a browser and it works.

---

## How to deploy

Replace everything currently in the repo with these files, then push to the `main` branch:

```bash
# from inside your local clone of baaskoebies.github.io
git rm -r --cached .          # unstage the old template files
rm -rf assets                 # old HTML5UP template folder, no longer used
# copy these new files in, then:
git add -A
git commit -m "Redesign portfolio"
git push origin main
```

GitHub Pages rebuilds automatically. Give it a minute, then hard-refresh (Ctrl/Cmd + Shift + R) to bypass your browser cache.

### Files you can safely delete from the old repo
- `assets/` — the entire HTML5UP "Dimension" template (CSS, JS, webfonts)
- `LICENSE.txt` and `README.txt` — HTML5UP's template licence

The new site uses **no HTML5UP code**, so their attribution is no longer required. Fonts load from Google Fonts; everything else is self-contained.

---

## Editing the site

Everything lives in `index.html`. The parts you're most likely to change:

| What | Where to look |
|---|---|
| Career chart milestones | the `marks` array in the `career scatter chart` script |
| Boot screen text | the `<pre id="bootText">` block |
| Scrolling ticker text | the `items1` / `items2` arrays in the `marquee content` script |
| Colours | the `:root` CSS variables at the top |
| Project write-ups | the three `<details class="proj">` blocks |

### Adding a project
Copy an existing `<details class="proj">` block, change the text, thumbnail path, and GitHub link, then give it the next `--d` delay value (`.36s`) so it staggers into view with the others.

---

## Design notes

- **Palette** is matplotlib's default colour cycle (C0 `#1F77B4`, C1 `#FF7F0E`, C2 `#2CA02C`, C3 `#D62728`, C4 `#9467BD`) on graph-paper grid.
- **Boot screen** is an amber-phosphor CRT power-on. Skippable via the button, a click, or Enter/Space/Esc.
- **Typography**: Bricolage Grotesque (display), Source Sans 3 (body), IBM Plex Mono (code/labels).
- **Accessibility**: honours `prefers-reduced-motion` (skips the boot screen and all animation), keyboard focus is visible throughout, and 3D tilt/parallax disable on touch devices.

---

## Known things to keep an eye on

- The site links to three GitHub repos under `BaasKoebies/DSProjects`. If those folder names change, update the `.repo-btn` links.
- Google Fonts is the only external dependency. If it's ever blocked, the site falls back to system fonts and still reads fine.
