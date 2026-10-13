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

The site is configured for **https://risdal.me/** at the domain root.

GitHub Pages uses the GitHub Actions workflow in `.github/workflows/deploy.yml`. Pushes to `main` install locked dependencies, check types, build, and deploy `dist/`.

In GitHub Pages settings, set the custom domain to `risdal.me`. Custom Actions deployments use the Pages setting, not a CNAME file.

At Cloudflare, add these DNS-only A records for `@`:

- `185.199.108.153`
- `185.199.109.153`
- `185.199.110.153`
- `185.199.111.153`

Optionally add a DNS-only CNAME for `www` pointing to `lmrisdal.github.io`. Enable Enforce HTTPS in GitHub Pages once GitHub provisions the certificate.

## Design and accessibility

Responsive layouts, keyboard-visible focus states, a skip link, semantic headings, and reduced-motion support. Content and navigation work without JavaScript; the theme then follows system preferences. Project previews require JavaScript. SVGs are decorative and hidden from screen readers.
