# baaskoebies.github.io

This is my personal portfolio site — Tlhologello Biyana, Data Scientist & Analytics Consultant.

Live at: https://baaskoebies.github.io/

---

## What's in here

```
.
├── index.html          the whole site — HTML, CSS and JS all in one file
├── favicon.svg         the browser tab icon
├── .nojekyll           tells GitHub Pages to serve the files as-is
├── README.md           this file
└── images/
    ├── portrait.jpg
    ├── personal-loans.jpg
    ├── recommender.jpg
    └── car-counter.jpg
```

No build step, no dependencies, no framework. I just open `index.html` in a browser and it works.

---

## Deploying

When I need to push a new version, I replace everything in the repo with these files and push to `main`:

```bash
# from inside my local clone of baaskoebies.github.io
git rm -r --cached .          # unstage the old template files
rm -rf assets                 # old HTML5UP template folder, not used anymore
# copy the new files in, then:
git add -A
git commit -m "Redesign portfolio"
git push origin main
```

GitHub Pages rebuilds on its own after that. I usually wait a minute, then hard-refresh (Ctrl/Cmd + Shift + R) so my browser isn't showing me a cached copy.

### Old files I don't need anymore
- `assets/` — the old HTML5UP "Dimension" template (CSS, JS, webfonts)
- `LICENSE.txt` and `README.txt` — HTML5UP's template licence

None of that HTML5UP code is in the site anymore, so I don't need to keep their attribution around. Fonts come from Google Fonts; everything else is self-contained.

---

## Editing the site

Everything lives in `index.html`. The bits I end up touching most:

- **Career chart milestones** — the `marks` array in the "career scatter chart" script
- **Boot screen text** — the `<pre id="bootText">` block
- **Scrolling ticker text** — the `items1` / `items2` arrays in the "marquee content" script
- **Colours** — the `:root` CSS variables at the top
- **Project write-ups** — the three `<details class="proj">` blocks

To add a project, I copy an existing `<details class="proj">` block, swap in the new text, thumbnail path and GitHub link, then bump the `--d` delay value (`.36s`) so it staggers in with the others instead of popping in at the same time.

---

## Design notes

I built the palette around matplotlib's default colour cycle — C0 `#1F77B4`, C1 `#FF7F0E`, C2 `#2CA02C`, C3 `#D62728`, C4 `#9467BD` — laid over a graph-paper grid, since that felt right for a data person's site.

The boot screen is an amber-phosphor CRT power-on effect, and it's skippable via the button, a click, or Enter/Space/Esc.

Fonts: Bricolage Grotesque for display text, Source Sans 3 for body copy, IBM Plex Mono for code and labels.

I made sure it respects `prefers-reduced-motion` (skips the boot screen and all the animation), keeps keyboard focus visible throughout, and turns off the 3D tilt/parallax on touch devices.

---

## Things to remember

- The site links to three GitHub repos under `BaasKoebies/DSProjects`. If I rename those folders, I need to update the `.repo-btn` links too.
- Google Fonts is the only external dependency. If it's ever blocked, the site falls back to system fonts and still looks fine.
