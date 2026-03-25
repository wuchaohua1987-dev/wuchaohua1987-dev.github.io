# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is a personal website built with Jekyll using the Minimal Mistakes remote theme, deployed on GitHub Pages.

## Development Commands

```bash
# Install dependencies
bundle install

# Serve site locally with auto-regeneration
bundle exec jekyll serve

# Serve with drafts enabled
bundle exec jekyll serve --drafts

# Build site for production
bundle exec jekyll build

# Update GitHub Pages gems
bundle update github-pages
```

## Architecture

**Theme System**: Uses `remote_theme: mmistakes/minimal-mistakes` in `_config.yml`. The theme files are not local; they are pulled from the remote repository at build time. To override theme defaults, create local files with the same path structure.

**Key Directories**:
- `_posts/` - Blog posts in Markdown; naming convention `YYYY-MM-DD-title.md`
- `_pages/` - Static pages (About, 404, archive pages)
- `_data/navigation.yml` - Top navigation menu configuration
- `assets/` - Static assets (images, CSS, JS overrides)

**Post Front Matter**:
```yaml
---
title: "Post Title"
date: YYYY-MM-DD HH:MM:SS +/-TTTT
categories: [category1, category2]
tags: [tag1, tag2]
---
```

**Configuration** (`_config.yml`):
- `minimal_mistakes_skin` - Theme skin (default, air, aqua, contrast, dark, dirt, neon, mint, plum, sunrise)
- `author` - Sidebar author information
- `defaults` - Default front matter for posts and pages
- `paginate` - Number of posts per page

**Plugins** (GitHub Pages compatible):
- jekyll-paginate, jekyll-sitemap, jekyll-gist, jekyll-feed, jemoji, jekyll-include-cache, jekyll-algolia

**Important Notes**:
- Changes to `_config.yml` require restarting the Jekyll server
- The `include: [_pages]` setting is required for pages to be processed
- Site is designed for GitHub Pages deployment via the `github-pages` gem
