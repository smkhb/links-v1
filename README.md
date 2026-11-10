<div align="center">

# links-v1

A minimal, fast personal links page inspired by Linktree and Beacons, styled to match `portfolio-v3`.

[![Static Site](https://img.shields.io/badge/site-static-222222?style=for-the-badge)](#)
[![HTML](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)](#)
[![Cloudflare Pages Ready](https://img.shields.io/badge/Cloudflare%20Pages-ready-F38020?style=for-the-badge&logo=cloudflare&logoColor=white)](#)
[![No Build Required](https://img.shields.io/badge/build-none-5A5A5A?style=for-the-badge)](#)

</div>

A lightweight personal landing page with a dark background, iA Writer Mono typography, colorful link underlines, and locally hosted assets. No framework, dependencies, or build step required.

## ✨ Features

- Minimal, responsive single-page design
- Customizable links, colors, profile photo, and footer
- Locally hosted fonts and image assets
- Cloudflare Pages-ready, with cache rules in `_headers`
- Small footprint: approximately 93 KB total

## 🚀 Run locally

From the project directory, start a local web server:

```bash
python3 -m http.server 4174
```

Then open <http://localhost:4174>.

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

## 📌 GitHub About

Copy this description into the repository's **About** field:

> A minimal, responsive personal links page built with plain HTML and CSS. No dependencies or build step; ready to deploy on Cloudflare Pages.

**Suggested topics:** `personal-website`, `link-in-bio`, `static-site`, `cloudflare-pages`, `html`, `css`
