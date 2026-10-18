# censor

Hides your name and avatar in Discord screenshots. Box your name once and it gets covered in every screenshot you add.

https://censor.works4you.dev

It all runs in the browser. Images aren't uploaded anywhere.

## How to use it

Drop in screenshots or paste them. Drag a box around your name, then your avatar, then the small name and avatar on reply lines. Click a box to turn it off. Save one, save all as a zip, or stitch them into one tall image.

Other stuff it does:

- hide more than one person, and give each one an alias that gets drawn where their name was
- type a name to find it instead of boxing it
- hide timestamps and dates
- crop, reorder, and stitch with the overlap cut out
- save as censored-01.png and so on, so the filename doesn't give away the date
- install as an app, and on Android you can share screenshots into it

Keys: space to peek at the original, ctrl+z to undo, arrows to switch screenshots, n and x to step through matches and turn them off, m b c for tools.

Matching is pixel based, so a screenshot taken at a different Discord zoom usually needs its own box. Blur and pixelate can sometimes be undone, so use erase or solid if it matters.

## Deploy

Static files in `public/`, served by Cloudflare Workers.

```bash
npx wrangler deploy
```
