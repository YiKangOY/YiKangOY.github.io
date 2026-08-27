# Repository Guidelines

## Project Structure & Module Organization

This repository is a Jekyll academic website based on Academic Pages. Site-wide metadata and collection settings live in `_config.yml`; navigation and author data live in `_data/`. Write content in the matching collection: `_pages/` for standalone pages, `_publications/`, `_talks/`, `_teaching/`, and `_portfolio/` for academic material, and `_posts/` for dated blog posts. Liquid templates are split between `_layouts/` and reusable `_includes/`. Edit styles in `_sass/` or `assets/css/`, JavaScript sources in `assets/js/`, images in `images/`, and downloadable PDFs in `files/` or `assets/`.

## Build, Test, and Development Commands

- `bundle install` installs the Ruby and GitHub Pages dependencies.
- `bundle exec jekyll serve -l -H localhost` builds the site, serves it at `http://localhost:4000`, and reloads changed pages.
- `bundle exec jekyll build` performs a production-style build into `_site/`; run this before submitting changes.
- `npm install` installs the JavaScript build dependencies.
- `npm run build:js` regenerates `assets/js/main.min.js` from jQuery, plugins, and `assets/js/_main.js`.
- From `markdown_generator/`, run `python publications.py` or `python talks.py` after editing the corresponding TSV source.

## Coding Style & Naming Conventions

Use two-space indentation in YAML, SCSS, HTML/Liquid, and JavaScript. Preserve valid YAML front matter and quote values containing punctuation or HTML. Name blog posts `YYYY-MM-DD-short-title.md`; use lowercase, descriptive slugs and stable collection permalinks. Keep reusable presentation logic in `_includes/` rather than duplicating markup. Modify source SCSS and JavaScript files, not generated or minified output, except when rebuilding `main.min.js`.

## Testing Guidelines

There is no automated test suite or coverage requirement. Treat a clean `bundle exec jekyll build` as the minimum check. Preview affected pages locally and verify navigation, links, publication metadata, responsive layout, and downloadable assets. For JavaScript changes, rebuild the bundle and exercise the changed interaction in a browser.

## Commit & Pull Request Guidelines

Recent history uses short, imperative summaries such as `Update about.md` and `Add paper URLs to all publications`. Keep each commit focused and describe the visible change. Pull requests should explain the purpose, list validation performed, link relevant issues, and include before/after screenshots for layout or styling changes. Do not commit `_site/`, dependency directories, caches, or local editor files.
