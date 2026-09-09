# Glasscoins deployment

The primary public site is https://glasscoins.github.io/.

The repository must be named `glasscoins/glasscoins.github.io`. In its
**Settings → Pages → Build and deployment**, set **Source** to **GitHub Actions**.
No custom domain or DNS records are needed for this address.

Every push to `main` runs `.github/workflows/pages.yml`, which installs the
locked dependencies, checks TypeScript, runs the motion tests, builds the static
export, and publishes `dist/client` to GitHub Pages. You can also run the workflow
manually from the repository's Actions tab.

Build locally with `npm ci` followed by `npm run build`. The site needs no server
runtime, application secrets, or database. `npm start` previews the static output
locally using Wrangler.

The legacy `npm run deploy:pages` command targets the separate Cloudflare Pages
project `glasscoins-protocol`; it does not update the GitHub Pages site.
