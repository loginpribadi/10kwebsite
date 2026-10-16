# 10kwebsite

Landing page for an AI brand. One self-contained file (`index.html`), no build step.

## Make it yours

Open `index.html`, scroll to the `SITE` block near the bottom and fill in:

- `brand`, `tagline`, `headline`, `category`, `cta`, `email`
- `formEndpoint`: a form service URL (Formspree, Tally, Google Apps Script) so the early-access form saves emails
- `heroVideo` / `heroPoster`: your hero film, e.g. `assets/hero.mp4` and `assets/hero-poster.jpg`. Until set, the hero plays a generated animated background. Keep the video short (10 to 20 s loop), muted, and under about 8 MB; it plays darkened under the headline.

- `scrollVideo` or `scrollFrames`: the scrolling film in the pinned section after the hero. It advances as the visitor scrolls, and the four captions fade in along the way (edit their text and timing via `data-from` / `data-to` in the HTML). Until set, an animated placeholder plays.
  - Video: browsers only scrub smoothly when every frame is a keyframe. Re-encode with
    `ffmpeg -i in.mp4 -an -vf scale=1920:-2 -c:v libx264 -g 1 -crf 24 -movflags +faststart assets/scroll.mp4`
  - Image sequence (smoothest, best on phones): `ffmpeg -i in.mp4 -vf fps=30,scale=1600:-2 assets/frames/frame_%04d.webp`, then set `scrollFrames: { path: "assets/frames/frame_{i}.webp", count: <number of frames>, pad: 4 }`.

Section copy (features, steps, use cases, FAQ) is plain HTML; edit it in place.

## Run locally

```sh
python3 -m http.server 8000
# open http://localhost:8000
```

## Deploy

Any static host works: GitHub Pages (Settings → Pages → deploy from this branch, root folder), Netlify or Vercel (drag and drop the folder).
