# Chat Summary — Portfolio Web Design Sessions v1 + v2
### Last updated: April 2026

---

## What Was Built

A single-page academic/researcher portfolio website in plain HTML + CSS + JS (no framework).
Hosted on GitHub Pages at `arm0126.github.io`.
**Current live file:** `index.html` (formerly `index_v9.html`, renamed and pushed live)

---

## Session 1 Summary (v1)

### Starting Point
- Old `index.html` used a multi-page structure (6 subpages: Home, Gallery, Publications, Experience, Documents, Contact)
- Design problems: heavy serif font, dark gradient header, too many full-reload pages, placeholder text everywhere
- Gallery had missing/broken items: AFM empty, TEM files were `.tif`, MPI phantom and Hyperthermia folders missing

### Design Requirements
- Minimalistic — no heavy/cluttered layouts
- No scrolling between sections — single landing page with collapsible sections
- Dark theme default with light professional toggle (persists via localStorage)
- All personal info in a single JS config block
- Gallery: no previews on main page, click title → full-screen two-panel viewer
- Experience: one-line summaries per role
- Skills: grouped, dot-separated plain text (no bubble tags)

### Content Collected
**7 publications (2015–2025):** MPI partial volume, MPI forward model, NK cell MPI, sentinel lymph node MPI, 2D MNP arrays, magnetic field self-assembly, MNP arrays on recording media.

**7 experience roles:** Postdoctoral Scholar (Jan 2026–), Senior Applications Engineer (Mar 2024–), AI Trainer Freelance (Jan–Jun 2025), Applications Support Engineer (Nov 2022–Feb 2024), Graduate Research Assistant (Dec 2016–Nov 2022), Research Assistant (May 2017–Dec 2018), Assistant Professor of Physics (Mar 2010–Jan 2016).

**9 skill groups:** Microscopy & Characterization · Medical Imaging · Nanoparticle Science · Systems Engineering · Electronics · Programming & Analysis · Fabrication · Regulatory & Quality · Communication

**Gallery categories (order):** Medical Imaging & 3D Slicer · SEM · TEM · AFM · Hyperthermia

### Version History

| File | What Changed |
|------|-------------|
| `index_new.html` | First single-page tab-based redesign |
| `index_v2.html` | Full redesign: Spectral+Inter fonts, light default, foldable sections, one-line experience |
| `index_v3.html` | Bug fix attempt: `min-height: 0` for collapse — did not fully work |
| `index_v4.html` | Fixed collapse with `display: none` — reliable, no animation |
| `index_v5.html` | Gallery redesign: two-panel full-screen overlay viewer, reordered categories |
| `index_v6.html` | Gallery image zoom-out padding, section titles bigger, skills → dot-separated text |
| `index_v7.html` | Section title font bumped to 1rem |
| `index_v8.html` | Profile photo circle enlarged to 130px |
| `index_v9.html` | All sections start collapsed on page load |

---

## Session 2 Summary (v2)

### Memory Updated
- Full project context, design decisions, content status, and TODOs saved to Claude memory for future sessions.

### Git & GitHub Pages Setup
- User committed `index_v9.html`, renamed it to `index.html`, and pushed — site is now live at `arm0126.github.io`
- Learned: `git log --oneline` shows commit hashes; `git checkout <hash> -- index.html` restores old versions
- Going forward: commit after each meaningful change with a clear message — git history replaces manual versioning

### Copyright Protection Added
- Footer added to `index.html`: `© [year] [ME.name]. All rights reserved.` — pulls name dynamically from ME config
- `LICENSE` file created in repo root: all rights reserved, note about journal figures
- Committed and pushed: `git add index.html LICENSE && git commit -m "add copyright footer and LICENSE"`

### GIF Not Loading
- `MAGimageCapture2.gif` in `gallery/images/ct_mpi/` not displaying in the live gallery
- Likely cause: file uploaded via GitHub web UI after local push, or case sensitivity mismatch
- Fix: `git pull origin main` then re-add and push the file from local

---

## Current File Structure (live on GitHub)

```
arm0126.github.io/
├── index.html             ← LIVE — single-page portfolio (was index_v9)
├── LICENSE                ← copyright notice
├── assets/
│   ├── img/rec.png        ← profile photo placeholder
│   └── css/site.css       ← old CSS (not used by index.html)
├── gallery/
│   └── images/
│       ├── sem/           ← 400nm7a.jpg, justcheck.jpg, G6videocalc.mov
│       ├── tem/           ← 11.tif, 15.tif (need conversion to jpg/png)
│       ├── afm/           ← EMPTY
│       ├── ct_mpi/        ← MAGimageCapture2.gif (GIF load issue — see above)
│       └── hyperthermia/  ← EMPTY
├── publications/
├── experience/
├── contact/
├── documents/
└── figures/
```

---

## What Still Needs To Be Done

- [ ] Fill in real name, email, GitHub, LinkedIn in `ME` config in `index.html`
- [ ] Add real profile photo to `assets/img/`
- [ ] Fix GIF loading: pull from GitHub, re-commit `gallery/images/ct_mpi/MAGimageCapture2.gif`
- [ ] Convert TEM `.tif` files → `.jpg`/`.png` (use ImageJ/Fiji)
- [ ] Add published AFM images to `gallery/images/afm/`
- [ ] Add published hyperthermia images to `gallery/images/hyperthermia/`
- [ ] Add published MPI phantom images to `gallery/images/mpi/`
- [ ] Replace `[placeholder]` org names in EXPERIENCE config in `index.html`
- [ ] Consider adding Mathematica code / analysis plots section
- [ ] Update LICENSE file with full real name (currently uses initials A.R.M.)
