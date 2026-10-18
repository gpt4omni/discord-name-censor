# Screenshot Name Censor

Hide your name and avatar in Discord screenshots before you share them. Mark something once, and every copy of it in every screenshot gets covered.

Live at **https://censor.works4you.dev**. Everything runs in your browser. No images are uploaded anywhere.

## Use it

Go to https://censor.works4you.dev, or open `public/index.html` in any modern browser.

1. Add screenshots: drop them on the page, paste with Ctrl+V, or click **add screenshots**. You can add as many as you like.
2. Drag a box around your name on one message. Every identical copy in every screenshot is covered.
3. Do the same for your avatar, and for the smaller name and avatar shown in reply lines.
4. Click a box to switch a single match off or back on. If a copy was missed, lower that item's **similarity** slider.
5. Click **save all** to get a zip of the censored screenshots, **save** / **copy** for the one you are viewing, or **stitch** to join them into one tall image.

Tick **remember people and things to hide on this device** and new screenshots are censored as soon as you add them.

## Features

- **Several people.** Add a person for each name you want hidden. New boxes go to the highlighted person.
- **Aliases.** Give a person an alias and it is drawn where their name was, in the same colour and size. Their avatar becomes a coloured circle with the alias's first letter. When an alias is longer than the real name, the rest of the line slides over to make room.
- **Find by typing.** Type a name and click **find**. Text recognition (tesseract.js) finds it in the screenshot and adds it.
- **Times and dates.** Click **hide times and dates** to cover message timestamps and date dividers in every screenshot. Click a box to bring one back.
- **No metadata.** Saved images are re-encoded PNGs with no EXIF or text chunks. By default they are named `censored-01.png` and so on, so a filename like `Screenshot 2026-10-18 235012.png` doesn't give the date away.
- **Crop.** Use the crop tool to trim a screenshot. Saving and stitching use the cropped area.
- **Stitch.** Joins every screenshot, top to bottom, into one image and removes rows that overlap between consecutive screenshots. Drag the thumbnails to change the order.
- **Other zoom levels.** Tick **also find other zoom levels** to match avatars and longer names in screenshots taken at a different Discord zoom.
- **Install.** The site works as an installable app. On Android, the installed app shows up in the share menu, so you can send screenshots straight to it.

## Shortcuts

| Key | Action |
| --- | --- |
| Hold Space | Show the original screenshot |
| Ctrl+Z | Undo |
| ← / → | Previous / next screenshot |
| N / Shift+N | Next / previous match |
| X | Switch the current match off or on |
| M / B / C | "hide every copy" / "single box" / "crop" tool |
| Ctrl+scroll | Zoom |

## Notes

- Matching compares pixels. Without **also find other zoom levels**, screenshots must be taken at the same Discord zoom as the one you marked.
- JPEG screenshots and hover-highlighted messages still match.
- **Solid block** is the safest style. Blurred or pixelated text can sometimes be recovered.
- The zip download loads JSZip from cdnjs, and find by typing loads tesseract.js from jsDelivr the first time you use it.

## Deploy

The site is static files in `public/`, served by Cloudflare Workers static assets. `wrangler.jsonc` binds it to the custom domain.

```bash
npx wrangler deploy
```
