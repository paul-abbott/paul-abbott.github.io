<!-- Copilot instructions for contributors and AI coding agents -->
# Repo overview

- **Type:** Small Jekyll/GitHub Pages site (static). Key config: `_config.yml` (kramdown settings). A custom domain is present (`CNAME`).
- **Content layout:** Markdown pages live at the repository root (e.g. `index.md`) and under folders like `beta/`. Assets (CSS, images) are under `assets/`.

# How the site builds (quick)

- Jekyll builds this repo on GitHub Pages. Local preview (standard):

  - If the repo has a `Gemfile`: `bundle install && bundle exec jekyll serve`.
  - Otherwise you can install Jekyll and run: `jekyll serve`.

- Note: `assets/css/style.scss` contains SASS front-matter (`---`) and `@import "{{ site.theme }}";`. The site may rely on a theme set in `_config.yml`.

# Where to make changes (concrete examples)

- Text pages: edit Markdown files in the repository root or `beta/` (e.g. `beta/index.md`).
- Styling: edit `assets/css/style.scss`. This file contains project-specific overrides and a hard `max-width: 600px` for images/containers — preserve that unless intentionally changing layout.
- Images: put stable images under `assets/images/` and reference them with relative paths in Markdown.

# Project conventions and patterns

- Pages use YAML front-matter (standard Jekyll). If you add SASS/CSS files that should be processed by Jekyll, include the three-dash front-matter block at the top (see `assets/css/style.scss`).
- Content in `beta/` is experimental: keep feature experiments isolated there and do not auto-promote to live pages without review.
- Small, focused PRs are preferred: this repo is a static site — avoid large structural refactors unless asked.

# Helpful code examples from this repo

- SASS file header (processed by Jekyll):

  ```scss
  ---
  ---
  @import "{{ site.theme }}";
  ```

- CSS constraint to respect when changing images/layout: `.container-lg` and `img { max-width: 600px; }` (see `assets/css/style.scss`).

# Typical tasks and where to edit

- Update homepage copy: `index.md` (root).
- Add a new page: create `newpage.md` with YAML front-matter and commit to master.
- Add an image: `assets/images/` and reference in Markdown using relative path.

# Build & debugging notes

- If local Jekyll build fails, check for missing front-matter blocks in SASS files and malformed YAML in `_config.yml` or page front-matter.
- For CSS changes, Jekyll processes `assets/css/*.scss` — ensure front-matter is present so the file is compiled.

# Integration points & external dependencies

- GitHub Pages: site is published automatically from `master` (default branch). `CNAME` indicates a custom domain; do not remove it unless you intend to change DNS.
- There are no other obvious external services configured in repo files (no API keys or server code present).

# Guidance for AI code agents

- Make minimal, localizable edits. Prefer changing single files (Markdown or one CSS file) and include a short PR description explaining the intent.
- When editing styles, reference `assets/css/style.scss` and maintain image container rules (max-width 600px) unless explicitly asked to change layout.
- Keep experimental work in `beta/` and call this out in the PR title/body.
- If you need to run the site locally, mention whether a `Gemfile` exists; use `bundle exec jekyll serve` when present.

# If anything is unclear

- Ask what the intended page/section is (root vs `beta/`), whether CSS layout constraints should change, and whether changes should be published to the live site.

---
Please review and tell me any missing specifics you want included (build commands you use, CI hooks, or preferred PR/branch rules).
