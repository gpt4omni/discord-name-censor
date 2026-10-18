# Screenshot Name Censor

Hide your name and avatar in Discord screenshots before you share them. Mark something once, and every copy of it in every screenshot gets covered.

Live at **https://censor.works4you.dev**. Everything runs in your browser. No images are uploaded anywhere.

## Use it

Go to https://censor.works4you.dev, or open `public/index.html` in any modern browser.

1. Add screenshots: drop them on the page, paste with Ctrl+V, or click **Add images**. You can add as many as you like.
2. Drag a box around your name on one message. Every identical copy in every screenshot is covered.
3. Do the same for your avatar, and for the smaller name and avatar shown in reply lines.
4. Click a box to switch a single match off or back on. If a copy was missed, lower that item's **Similarity** slider.
5. Click **Download all** to get a zip of the censored screenshots, or **Download** / **Copy** for the one you are viewing.

Tick **Remember my things to hide on this device** and new screenshots are censored as soon as you add them.

## Shortcuts

| Key | Action |
| --- | --- |
| Hold Space | Show the original screenshot |
| Ctrl+Z | Undo |
| ← / → | Previous / next screenshot |
| M / B | "Hide all copies" / "Single box" tool |
| Ctrl+scroll | Zoom |

## Notes

- Matching compares pixels, so screenshots must be taken at the same Discord zoom level as the one you marked. A screenshot at a different zoom needs its own boxes.
- JPEG screenshots and hover-highlighted messages still match.
- **Solid block** is the safest style. Blurred or pixelated text can sometimes be recovered.
- The zip download loads JSZip from cdnjs. Without it, each screenshot downloads as a separate file.

## Deploy

The site is static files in `public/`, served by Cloudflare Workers static assets. `wrangler.jsonc` binds it to the custom domain.

```bash
npx wrangler deploy
```
