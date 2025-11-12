# Arc57_Proposal

Confidential partnership proposal website for **Arc57, LLC**, prepared and branded by **Stewardship.IS, Inc.**. This static site presents illustrative analytics, automation workflows, and operational tooling examples.

> CONFIDENTIAL — Proprietary materials. Do not copy or redistribute without written consent.

---

## 1. Live Preview

If GitHub Pages is enabled:

- Enable: Settings → Pages → Deploy from branch → Branch: `main`, Folder: `/ (root)`.
- URL will be: `https://jcnewport.github.io/Arc57_Proposal/`

---

## 2. Repository Structure

```
Arc57_Proposal/
├─ index.html                # Main proposal page (Arc57 branding + confidential banner)
├─ assets/
│  ├─ branding/
│  │  ├─ arc57-logo.png      # Arc57 logo (add/replace)
│  │  └─ stewardshipis-logo.png
│  ├─ slides/                # 25 JPG slide images (carousel)
│  └─ video/
│     └─ Stewardship.IS_iPad-Config.webm  # Local demo video (replace as needed)
├─ .github/
│  └─ workflows/             # (Optional) automation workflows if added later
└─ README.md                 # This file
```

---

## 3. Branding

| Element          | Value                |
|------------------|----------------------|
| Company Name     | Arc57, LLC           |
| Abbreviation     | Arc57                |
| Primary Color    | `#1B3776` (arc57-navy) |
| Secondary Color  | `#02A64F` (arc57-green) |
| Co-Brand         | Stewardship.IS logo retained |
| Confidential Banner | Sticky top bar |

To adjust colors, edit Tailwind config override inside `index.html` (`tailwind.config`).

---

## 4. Content Sections

1. Confidential banner
2. Logos & Header
3. Intro & Quick Navigation
4. Portal Demo (HTML5 `<video>`)
5. Pain Points
6. Solution Grid
7. Stewardship.IS Difference
8. Example 1: Financial Analytics (AFE Budget Tracker + Well-Level Returns tables)
9. Example 2: Deduct Defender™ Case Study
10. Example 3: Modules & Interfaces Carousel (25 slides)
11. Example 4: Statements Management Tool (benefits + video)
12. Example 5: Custom Apps & Extensions
13. Moving Forward
14. Footer

---

## 5. Replacing / Adding Videos

Place new demo files in `assets/video/`:

```
assets/video/arc57-portal-demo.webm
assets/video/arc57-portal-demo.mp4
```

Update both `<source>` tags inside the relevant `<video>` wrapper. Keep total file < 100 MB or use Git LFS:

```bash
git lfs install
git lfs track "*.webm" "*.mp4"
git add .gitattributes
git commit -m "Track video with LFS"
git push
```

---

## 6. Optimizing Images

### Slides
Convert to WebP (optional performance boost):

```bash
# Requires ImageMagick (magick) installed
mkdir -p assets/slides/webp
for %i in (assets\slides\Slide-*.JPG) do magick "%i" -quality 82 "assets\slides\webp\%~ni.webp"
```

Then modify carousel script to prefer WebP (optional):

```js
const slideImages = Array.from({length:25},(_,i)=>`assets/slides/webp/Slide-${String(i+1).padStart(2,'0')}.webp`);
```

Keep original JPGs as fallback or create `<picture>` elements.

### Logos
Run `oxipng` or `pngquant`:

```bash
pngquant --quality=65-80 --force --output assets/branding/arc57-logo.png assets/branding/arc57-logo.png
```

---

## 7. Adding an Optimization Workflow (Optional)

Ask for “image optimization workflow” and a GitHub Actions file will be provided to batch convert on push.

---

## 8. Development Notes

- The site uses Tailwind CDN for rapid iteration (no build pipeline).
- For further modularization, you can split sections into partial HTML fragments and assemble with a tiny Node script or static site generator.
- Dark mode, password gate, or analytics can be added later.

---

## 9. Common Tasks

| Task | Command |
|------|---------|
| Stage & commit changes | `git add -A && git commit -m "Update"` |
| Push to remote | `git push` |
| Pull remote updates | `git pull --rebase origin main` |
| Force overwrite (use caution) | `git push --force-with-lease` |

---

## 10. Future Enhancements (Backlog)

- Dark mode toggle
- Slide thumbnails / faster navigation
- CSV/Excel download buttons for tables
- Automated nightly sync from source data repo
- Accessibility pass (aria labels on interactive elements)
- Analytics (lightweight, privacy friendly)

---

## 11. Confidentiality & Usage

This repository is a read‑only proposal deliverable. Do not distribute outside authorized Arc57, LLC decision makers. All code, text, and media remain property of Stewardship.IS, Inc. unless otherwise contracted.

---

## 12. Support

For refinements or deployment questions, open an issue (if issues are enabled) or reach out directly.

---

## 13. Quick Verification Checklist After Changes

| Item | Verify |
|------|--------|
| Logo displays | Header shows Arc57 & Stewardship.IS |
| Carousel works | Arrows & dots navigate all 25 slides |
| Tables visible | AFE and Well-Level Returns render with data |
| Videos play | Portal & Statements tool videos start & controls visible |
| Colors correct | Primaries (#1B3776) and accents (#02A64F) |
| Confidential banner | Sticky, top, legible |
| No residual AMP/FEP text | Search page source for "AMP" / "FEP" |

---

## 14. License

Not open source. Proprietary & confidential.
