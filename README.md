# Lars Martin Risdal — portfolio

A cyberpunk-inspired personal portfolio built with Astro and Bun. Static HTML, CSS circuit animations, system fonts, and no runtime API requests. Small scripts handle theme cycling, active navigation, scroll reveals, and the two browser-local project demos.

## Development

Requires Bun 1.3.11 and Node.js 22.12+.

```sh
bun install
bun run dev
```

Open the printed local URL (normally http://localhost:4321/).

```sh
bun run check
bun run build
bun run preview
```

## Content

Edit `src/data/portfolio.ts` for profile links, featured repositories, and work experience. Page copy lives in `src/pages/index.astro`; styling in `src/styles/global.css`.

Work experience is based on the supplied LinkedIn details. Project descriptions are based on the public chordio and lgctl READMEs. Repository data is deliberately stored locally so loading the site never depends on the GitHub API.

## GitHub Pages

The site is configured at the root, **https://lmrisdal.github.io/**. GitHub Pages serves this root URL from a repository named `lmrisdal.github.io`. To deploy from the `me` repository at a domain root instead, configure a custom domain.

1. In the GitHub repository, open **Settings → Pages** and select **GitHub Actions** as the source.
2. Push this project to `main` (or run the deployment workflow manually once it is on GitHub).
3. The workflow installs locked dependencies, checks types, builds, and deploys `dist/`.

For a custom domain, update `site` in `astro.config.mjs`, set `base` to `/`, add `public/CNAME`, and configure the domain in GitHub Pages and your DNS provider. For a `lmrisdal.github.io` repository, use `base: '/'`.

## Design and accessibility

Responsive layouts, keyboard-visible focus states, a skip link, semantic headings, and reduced-motion support. Content and navigation work without JavaScript; the theme then follows system preferences. Project previews require JavaScript. SVGs are decorative and hidden from screen readers.
