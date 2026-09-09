# Glasscoin Landing

The Glasscoins Protocol landing page: an interactive glass Bitcoin on a black
background, with pointer-driven liquid refraction, encrypted text, drag-to-spin
motion, and subtle reflections around the rim.

[Live site](https://glasscoins.github.io/)

## Run locally

Requires Node.js 22.13 or later and npm.

```sh
git clone https://github.com/glasscoins/glasscoins.github.io.git
cd glasscoins.github.io
npm ci
npm run dev
```

Open the local URL printed by the dev server. The landing page does not need
application secrets or a database.

## Build and deploy

```sh
npm run build:pages
```

The static site is generated in `dist/client`. `npm run build` creates the same
export, and `npm start` previews the built site locally.

Push to `main` to publish to https://glasscoins.github.io/ using GitHub Actions.
The workflow checks the code, builds the site, and deploys `dist/client` to
GitHub Pages. See [DEPLOYMENT.md](DEPLOYMENT.md) for setup and details.

## Code and checks

- `app/page.tsx`: pointer, touch, and keyboard interaction.
- `app/globals.css`: layout and visual fallbacks.
- `lib/glass-renderer.ts`: WebGL coin geometry, refraction, and reflections.
- `lib/coin-motion.ts`: rotation and release momentum.
- `public/images/glass-bitcoin.png`: glass coin artwork.

```sh
npx tsc --noEmit --incremental false
node --experimental-strip-types tests/coin-motion.test.mjs
```
