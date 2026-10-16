# 10kwebsite

Landing page for an AI brand. One self-contained file (`index.html`), no build step.

## Make it yours

Open `index.html`, scroll to the `SITE` block near the bottom and fill in:

- `brand`, `tagline`, `headline`, `category`, `cta`, `email`
- `formEndpoint`: a form service URL (Formspree, Tally, Google Apps Script) so the early-access form saves emails

Section copy (features, steps, use cases, FAQ) is plain HTML; edit it in place.

## Run locally

```sh
python3 -m http.server 8000
# open http://localhost:8000
```

## Deploy

Any static host works: GitHub Pages (Settings → Pages → deploy from this branch, root folder), Netlify or Vercel (drag and drop the folder).
