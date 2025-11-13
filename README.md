# Arc57_Proposal

Confidential partnership proposal website for **Arc57, LLC**, prepared and branded by **Stewardship.IS, Inc.**. This site mirrors the AMP version’s style and sections, with Arc57 branding and local HTML5 video embeds.

> CONFIDENTIAL — Proprietary materials. Do not copy or redistribute.

---

## Live Preview

If GitHub Pages is enabled:

- Settings → Pages → Deploy from branch → Branch: `main`, Folder: `/ (root)`.
- URL: `https://jcnewport.github.io/Arc57_Proposal/`

---

## Structure

```
Arc57_Proposal/
├─ index.html                 # AMP-style page, Arc57 branding
├─ assets/
│  ├─ branding/
│  │  ├─ arc57-logo.jpg       # Arc57 logo (case-sensitive); header uses ?v=2 cache-buster
│  │  └─ stewardshipis-logo.png
│  ├─ slides/                 # 25 JPG slide images (carousel)
│  └─ video/
│     └─ Stewardship.IS_iPad-Config.webm
└─ README.md
```

---

## Videos: correct “stand-still” frame

- The page auto-generates the poster from each video’s first frame (no manual thumbnails required).
- It seeks to 0.1s and captures to a data URL, then assigns it as the `poster`. This avoids black frames on some encoders and works on GitHub Pages (same-origin).

If you ever want static posters instead:

```bash
# Extract first frame as poster (requires ffmpeg)
ffmpeg -ss 00:00:00.100 -i assets/video/Stewardship.IS_iPad-Config.webm -vframes 1 -q:v 2 assets/video/portal-poster.jpg
```

Then set `<video poster="assets/video/portal-poster.jpg">`.

---

## Notes

- GitHub Pages is case-sensitive and cached. If an image looks “stuck,” append a small cache-buster (e.g., `?v=2`) and hard refresh (Ctrl+F5).
- Tailwind is loaded via CDN (no build step).

---

## Common Git

- Stage & commit: `git add -A && git commit -m "Update"`
- Push: `git push`
- Pull with rebase: `git pull --rebase origin main`
