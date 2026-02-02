# Harshit's Portfolio

A modern, interactive personal portfolio built with Next.js (app directory) and TypeScript. The site showcases projects, client logos, a custom grid-based about section, animated hero, and a number of small UI/UX flourishes (Lottie animations, Framer Motion effects, an interactive 3D globe, and theme switching). It was styled with utility-first classes and integrates the Aceternity UI library for some UI primitives.

Live demo: https://myportfoloo.netlify.app/

---

## Table of contents

- About
- Highlights / Features
- Tech stack
- Project structure (overview)
- Important files & components
- Run locally
- Build & deploy
- Customize (what to edit)
- Notes & tips
- Contributing
- License

---

## About

This repo contains a single-page portfolio built on Next.js using the app router. The layout is responsive and crafted to highlight projects, skillset, and contact information. The UI includes animated sections, gradient backgrounds, Lottie confetti, and a small 3D globe component.

Primary intent: A personal portfolio to present projects and contact information with a polished, animated UI.

---

## Highlights / Features

- Next.js (app directory) + TypeScript project structure.
- Dark / light theme toggle via a ThemeProvider.
- Animated hero section with a text generation effect and multiple “spotlight” gradient layers.
- Custom responsive grid (BentoGrid) for the About section that supports mixed-size items and images.
- Recent projects listing (data-driven).
- Clients / testimonials / experience sections with motion effects.
- Lottie animations integrated for micro-interactions.
- Small interactive 3D globe and animated pin effects.
- Smooth UI motion via Framer Motion.
- Icons via react-icons.
- Easy content editing via data files.

---

## Tech stack

- Next.js (app router)
- TypeScript
- Aceternity UI library (used for UI primitives)
- Framer Motion
- react-lottie / Lottie animations
- Three.js (used by the globe; or other 3D helper code referenced)
- Tailwind-style utility classes (project uses utility classes — check tailwind config)
- React Icons

(Exact dependencies and versions are in package.json — review it before installing.)

---

## Project structure (high level)

Root
- app/                — Next.js app directory (layout.tsx, page.tsx, globals.css)
  - layout.tsx        — root HTML layout and ThemeProvider
  - page.tsx          — home page assembly (Hero, Grid, Projects, etc.)
- components/         — presentational and composite UI components
  - Hero.tsx
  - Grid.tsx
  - Footer.tsx
  - Approach.tsx
  - Experience.tsx
  - RecentProjects.tsx
  - Clients.tsx
  - MagicButton.tsx
  - ui/               — smaller UI building blocks
    - BentoGrid.tsx
    - GridGlobe.tsx
    - Pin.tsx
    - Spotlight.tsx
    - TextGenerateEffect.tsx
    - CanvasRevealEffect.tsx
    - FloatingNavbar.tsx
- data/               — site data and content used by components
  - index.ts          — navItems, gridItems, projects, socialMedia, etc.
  - confetti.json     — Lottie animation data (referenced)
- public/             — static assets (svgs, images, icons)
- styles/ or globals.css — global styles (imported from app/layout)
- next.config.js
- package.json
- README.md
- LICENSE

---

## Important files and where to look

- app/layout.tsx
  - Site metadata, imports global CSS, wraps site in ThemeProvider.
  - Edit title/description here (metadata object).

- app/page.tsx
  - Main home page: imports and composes Hero, Grid, RecentProjects, Clients, Experience, Approach, Footer.

- components/Hero.tsx
  - Main top-of-page hero with animated text and CTA.

- components/Grid.tsx + components/ui/BentoGrid.tsx
  - The “about” grid layout and individual grid item implementation.

- components/ui/GridGlobe.tsx
  - Interactive 3D globe / visual centerpiece for one of the grid items.

- data/index.ts
  - All primary static content (navItems, gridItems, projects, icon lists, social links).
  - Update this file to change nav labels, project entries, or the grid content.

- components/Footer.tsx
  - Contact CTA and link to contact anchor.

---

## Run locally

1. Clone
   ```bash
   git clone https://github.com/harshitsharmaaaa/portFolio.git
   cd portFolio
   ```

2. Install dependencies
   ```bash
   npm install
   # or
   yarn install
   ```

3. Development server
   ```bash
   npm run dev
   # or
   yarn dev
   ```
   Open http://localhost:3000

Notes:
- This project uses the Next.js app directory; use Node.js 18+ for best compatibility.
- If you use TypeScript, ensure your editor has the TypeScript toolchain enabled.

---

## Build & deploy

1. Build for production
   ```bash
   npm run build
   # or
   yarn build
   ```

2. Start production server (after build)
   ```bash
   npm run start
   # or
   yarn start
   ```

Deploy:
- Recommended platforms: Vercel (seamless with Next.js), Netlify, or any container hosting.
- For Vercel:
  - Install the Vercel CLI (optional) and run `vercel` or connect the GitHub repo on vercel.com and deploy.
  - Set any required environment variables in the Vercel dashboard (if you add APIs later).

Note: This project is already deployed at https://myportfoloo.netlify.app/ — use that URL as the Live demo.

---

## Customize — quick guide

- Edit site content
  - Open data/index.ts to change nav items, grid cards, projects, and social links.

- Change the site title/description
  - app/layout.tsx -> metadata object.

- Replace images & static assets
  - Add/replace files in public/ (svg, png, jpg, etc.) and update paths in data/index.ts or components.

- Theme and CSS
  - globals.css / styles/ contains global styles and utility overrides. ThemeProvider in layout.tsx toggles dark/light.

- Add or change animations
  - Lottie files live in data/ (e.g., confetti.json). Components using Lottie are in components/ui/*.

- Add new components or pages
  - Create new files under app/ (for full pages) or components/ (for reusable parts).

---

## Notes & Tips

- Lottie: If you see usage of react-lottie, you may need the types package for development: `npm i --save-dev @types/react-lottie` if TypeScript complains.
- The project references a 3D globe — ensure three.js or your chosen 3D library is installed if you modify the globe.
- Accessibility: review color contrast and semantic tags if you plan to expand accessibility features.
- Performance: large Lottie / three.js assets impact load speed. Consider lazy-loading heavy assets or using dynamic imports.

---

## Contributing

- If you want me to update this README in the repo, or commit code changes (readme improvements or fixes), I can prepare a PR or push a branch — tell me if you'd like that.
- For code contributions: open an issue or PR describing the change and I'll review.

---

## License

This project is licensed under the MIT License. See the LICENSE file for details.

---
Made with ❤️ using Next.js
