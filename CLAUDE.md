# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is an academic personal website built using Jekyll and the Academic Pages theme. It's a GitHub Pages site for displaying academic publications, CV, talks, teaching experience, and blog posts. The site is deployed at https://YiKangOY.github.io.

## Development Commands

### Local Development
```bash
# Install dependencies
sudo apt install ruby-dev ruby-bundler nodejs  # Linux/WSL
# or: brew install ruby node && gem install bundler  # macOS

# Install Ruby dependencies
bundle install

# Serve locally with live reload
jekyll serve -l -H localhost

# Alternative with bundle exec
bundle exec jekyll serve -l -H localhost
```

The site will be available at `localhost:4000` with automatic rebuilding on file changes.

### JavaScript Building
```bash
# Minify and concatenate JavaScript files
npm run build:js

# Watch for JavaScript changes and auto-build
npm run watch:js
```

## Architecture

### Jekyll Collections
The site uses Jekyll collections to organize different content types:
- `_publications/` - Research papers and publications
- `_talks/` - Conference talks and presentations
- `_teaching/` - Teaching experience and courses
- `_posts/` - Blog posts
- `_portfolio/` - Portfolio items
- `_pages/` - Static pages (About, CV, etc.)

### Key Configuration
- `_config.yml` - Main Jekyll configuration and site metadata
- `_data/navigation.yml` - Site navigation structure
- `_data/authors.yml` - Author information for multi-author support

### Theme Structure
- `_layouts/` - Page layout templates
- `_includes/` - Reusable template components
- `_sass/` - Sass stylesheets
- `assets/` - CSS, JS, and other static assets

### Content Generation Tools
The `markdown_generator/` directory contains Python scripts and Jupyter notebooks for generating markdown files from structured data:
- `publications.py` / `publications.ipynb` - Generate publication pages from TSV
- `talks.py` / `talks.ipynb` - Generate talk pages from TSV
- `pubsFromBib.py` / `PubsFromBib.ipynb` - Generate publications from BibTeX

### Talk Map Generation
- `talkmap.py` - Generates an interactive map of talk locations
- Requires: `glob`, `getorg`, `geopy` packages
- Run from `_talks/` directory to create map in `talkmap/`

## Content Management

### Adding Publications
1. Edit `markdown_generator/publications.tsv` with new publication data
2. Run `python markdown_generator/publications.py` to generate markdown files
3. Files are created in `_publications/` directory

### Adding Talks
1. Edit `markdown_generator/talks.tsv` with new talk data
2. Run `python markdown_generator/talks.py` to generate markdown files
3. Files are created in `_talks/` directory

### Manual Content
- Blog posts: Add to `_posts/` with YYYY-MM-DD-title.md format
- Pages: Add to `_pages/` directory
- Files: Upload to `files/` directory for public access

## Site Deployment

This is a GitHub Pages site that auto-deploys from the master branch. No manual deployment commands needed - just push to master and GitHub Pages will build and deploy the site.