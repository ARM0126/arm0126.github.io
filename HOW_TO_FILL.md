# HOW_TO_FILL.md — Portfolio Update SOP

---

## Adding a New Gallery Image or Video

**Step 1 — Copy the file into the correct folder**

| Category | Folder |
|---|---|
| 3D Slicer | `gallery/images/slicer3d/` |
| Microscopy | `gallery/images/microscopy/` |
| HDD Write and Read Optimization | `gallery/images/hdd/` |
| Fabrication | `gallery/images/fabrication/` |

> **File name rule:** No spaces. Use underscores or hyphens. Bad: `SlicerCapture brain.mp4` → Good: `SlicerCapture_brain.mp4`
> If a file already has spaces, encode them as `%20` in the HTML src path.

**Step 2 — Add the entry to the gallery array in `index.html`**

Open `index.html` and find the relevant category block (search for the folder name).
Add a line inside the `images: [...]` array:

```js
{ src: "gallery/images/ct_mpi/your_file.mp4", alt: "Short description" },
```

Supported formats: `.png`, `.jpg`, `.gif`, `.mp4`

**Step 3 — Create a new version file**

```bash
cp index.html index_vN.html   # increment N
```

Make your edits in `index.html`, keep `index_vN.html` as the backup.

**Step 4 — Commit and push**

```bash
git add index.html gallery/images/<folder>/your_file.ext
git commit -m "add <description> to gallery"
git push origin main
```

---

## Checklist Before Pushing

- [ ] File is in the right `gallery/images/` subfolder
- [ ] No spaces in the filename (or `%20` used in src)
- [ ] Entry added to the `images: [...]` array in `index.html`
- [ ] New version backup created (`index_vN.html`)
- [ ] Only published or PI-approved images — no raw unpublished data

---

## Other Common Updates

### Update personal info (name, email, links)
Find the `const ME = {` block near the top of `index.html` and edit inline.

### Add a publication
Find `const PUBS = [` and add an object:
```js
{
  title:   "Full paper title",
  venue:   "Journal Name · Year",
  url:     "https://doi.org/...",
  abstract: "Paste abstract here.",
},
```

### Add an experience entry
Find `const EXP = [` and add:
```js
{ role: "Job Title", org: "Org Name", period: "Mon YYYY–Mon YYYY", note: "One-line summary." },
```

---

## TEM Image Conversion (.tif → .jpg)

Open in **ImageJ/Fiji**:
`File → Open` → `File → Save As → JPEG...`

Then add to `gallery/images/tem/` and follow the steps above.
