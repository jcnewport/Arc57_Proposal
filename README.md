# Arc57_Proposal

Confidential partnership proposal website for **Arc57, LLC**, prepared and branded by **Stewardship.IS, Inc.**. This site mirrors the AMP version’s style and sections with Arc57 branding, local HTML5 videos, and dynamic posters that use the first frame.

> CONFIDENTIAL — Proprietary materials. Do not copy or redistribute.

---

## Live Preview

- Enable Pages: Settings → Pages → Deploy from branch → Branch: `main`, Folder: `/ (root)`.
- URL: `https://jcnewport.github.io/Arc57_Proposal/`

---

## Structure

```
Arc57_Proposal/
├─ index.html                 # AMP-style page, Arc57 branding
├─ assets/
│  ├─ branding/
│  │  ├─ arc57-logo.jpg       # Arc57 logo (case-sensitive; header uses ?v=2 cache-buster)
│  │  └─ stewardshipis-logo.png
│  ├─ slides/                 # 25 JPG slide images (carousel)
│  └─ video/
│     └─ Stewardship.IS_iPad-Config.webm
└─ README.md
```

---

## Sections (restored)

1. Confidential banner
2. Logos & Header (Stewardship.IS + Arc57)
3. Intro + Quick Navigation
4. Portal Demo (Video 1, local `<video>`, poster from first frame)
5. Pain Points
6. Our Partnership Solution (cards)
7. The S.IS Difference
8. Example 1: Core Financial Analytics & Reporting (gauge + AFE table + well-level returns table)
9. Example 2: Deduct Defender™ Revenue Recoupment Case Study (Problem + Recoupment boxes)
10. Example 3: S.IS Product Modules & Interfaces Evolution (25‑slide carousel)
11. Example 4: VS Code Statements Management Tool (Video 2, local `<video>`, poster from first frame)
12. Example 5: Quick Customized Applications & Extensions
13. Moving Forward
14. Footer

---

## Video posters (first frame)

No manual thumbnails required. The page seeks to 0.1s, captures a frame into a data URL, and sets it as the `poster` for each video tagged with `data-poster-from-first-frame`.

If you want static posters instead:

```bash
# Requires ffmpeg; extract first frame
ffmpeg -ss 00:00:00.100 -i assets/video/Stewardship.IS_iPad-Config.webm -vframes 1 -q:v 2 assets/video/portal-poster.jpg
```

Then set: `<video poster="assets/video/portal-poster.jpg">`.

---

## Notes

- GitHub Pages is case-sensitive and caches aggressively. If an image appears stuck, append `?v=2` and hard refresh (Ctrl+F5).
- Tailwind is loaded via CDN (no build step).

---

## Common Git

- Stage & commit: `git add -A && git commit -m "Update"`
- Push: `git push`
- Pull (rebase): `git pull --rebase origin main`
