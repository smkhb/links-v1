# links-v1

> A minimal, fast personal links page inspired by Linktree and Beacons, styled to match `portfolio-v3`.

A lightweight personal landing page with a dark background, iA Writer Mono typography, colorful link underlines, and locally hosted assets. No framework, dependencies, or build step required.

## ✨ Features

- Minimal, responsive single-page design
- Customizable links, colors, profile photo, and footer
- Locally hosted fonts and image assets
- Cloudflare Pages-ready, with cache rules in `_headers`
- Small footprint: approximately 93 KB total

## 🛠️ Customize

Most of the page content and styling lives in `index.html`:

| Item | Where to edit |
| --- | --- |
| Name and role | The `<h1>` and `<p class="cargo">` elements |
| Links | The `<li>` elements inside `<nav>` |
| Profile photo | Replace `profile.jpg` (currently 240 × 240 px) |
| Colors | CSS variables in the `<style>` block's `:root` |
| Footer | The `<footer>` element |

To add a link, duplicate an existing `<li>` and update its `href`, `.rotulo`, and `.destino` values. Link underline colors are distributed automatically.

## ☁️ Deploy to Cloudflare Pages

1. Push this project to a GitHub repository.
2. In Cloudflare, go to **Workers & Pages → Create → Pages → Connect to Git**.
3. Select the repository and configure the build settings:
   - **Framework preset:** `None`
   - **Build command:** leave blank
   - **Build output directory:** `/` (the repository root)
4. Click **Save and Deploy**. Cloudflare will provide a `*.pages.dev` URL.
5. To use a custom domain, open **Custom domains** in your Pages project and follow the setup instructions.

Every push to the configured Git branch will trigger a new deployment. The `_headers` file sets long-lived caching for the fonts and profile photo, and revalidation for the HTML page.

## 📁 Project structure

```text
.
├── index.html       # Single-page site with embedded CSS
├── profile.jpg      # Profile photo (240 × 240 px)
├── favicon.svg      # “sb” favicon
├── _headers         # Cloudflare Pages cache rules
└── fonts/
    ├── ia-writer-mono-400.woff2
    └── ia-writer-mono-700.woff2
```
**Suggested topics:** `personal-website`, `link-in-bio`, `static-site`, `cloudflare-pages`, `html`, `css`
