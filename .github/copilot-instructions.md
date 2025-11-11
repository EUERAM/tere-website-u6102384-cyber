<!-- .github/copilot-instructions.md - Guidance for AI coding agents -->

# Copilot instructions — Tere Web (static landing)

This is a small static website (HTML + CSS + images). The goal of these
instructions is to help AI coding agents be immediately productive editing
content, styles, and assets without changing project layout or breaking links.

Key facts

- Project type: Plain static site (no build tools, frameworks, or tests).
- Entry point: `index.html` at repository root.
- Styles: `css/styles.css` — CSS variables are defined in `:root` and used
  throughout. The fixed `.container` width is 1280px and many layout rules
  (grid/flex) live in this file.
- Assets: `img/` contains `Logo.png`, `works.png`, `step.png` and other images.

What you should know and follow

- Do not introduce a build step or transpilers unless the maintainer asks.
  This codebase is served as-is (open `index.html` or start a simple HTTP
  server).
- Keep asset paths relative (e.g., `css/styles.css`, `img/Logo.png`). Moving
  files requires updating those paths in `index.html` and `css/styles.css`.
- Fonts: The project uses Google Fonts (`Inter`) via external link in
  `index.html`. Keep that link if you modify typography unless instructed.

Patterns and examples (copy/paste safe edits)

- Add a nav item: edit the `<ul>` inside `<header>` in `index.html`. Example:
  - Find: the `header > .menu > ul` list and add another `<li><a href="#">New</a></li>`.
- Update hero content: the `.hero` section is currently empty — insert markup
  and a background image via CSS (update `css/styles.css` accordingly).
- Steps block: `.how-it-works` uses a 3-column CSS grid (`.row`). To change
  step numbers or text, edit the corresponding `.step` blocks in
  `index.html` — images use `img/step.png` as a background for `.number`.

Conventions observed in repository

- Naming: kebab/kebab-like class names (e.g., `how-it-works`, `text-right`).
- Color tokens: CSS variables in `:root` (use these instead of hardcoding
  colors to preserve visual consistency).
- Typography: `Inter` used across elements; headings are uppercase where
  defined (see `h2`, `h3` rules in `styles.css`).

Developer workflows (how to run/test changes locally)

- Quick preview in browser: open `index.html` directly in a browser.
- Local static server (recommended to test relative fetches and font loading):
  - From project root run: `python3 -m http.server 8000` and open
    `http://localhost:8000`.
- Recommended editor workflow: open the project in VS Code. Use the
  Live Server extension if available for instant reloads.

Integration points and external deps

- External fonts: Google Fonts link in `index.html`.
- External links: header nav links point to `http://eram.cat` (these are
  likely placeholders — confirm before changing the domain).

Safe changes and low-risk additions

- Add new images to `img/` and reference them with relative paths.
- Add small CSS tweaks to `css/styles.css`. Keep changes scoped using
  class selectors to avoid global regressions.

When to ask the human

- If you plan to add a build tool (webpack, rollup, SASS) — ask first.
- If you need to rename files or change public URLs (affects hosting), ask.
- If you need to add external packages or tests — ask for approval.

Files to inspect for context

- `index.html` — main structure, header, hero placeholder, how-it-works.
- `css/styles.css` — variables, layout rules, typography.
- `img/` — image assets used by CSS and HTML (`Logo.png`, `works.png`, `step.png`).

If anything in these notes is unclear or you want me to expand examples
for a particular edit (for example, adding a hero section or wiring a
contact form), tell me which change you want and I'll update the instruction
file and provide the exact patch.
