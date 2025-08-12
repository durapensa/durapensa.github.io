# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Jekyll-based blog site using the Chirpy theme, focused on AI alignment and AI welfare topics. It's a GitHub Pages site hosted at `durapensa.github.io` that serves as a personal blog for AI safety research and discussions.

## Key Architecture

- **Jekyll Site**: Static site generator using the Chirpy theme (`jekyll-theme-chirpy` v7.2+)
- **Content Structure**: 
  - Blog posts in `_posts/` with date-prefixed filenames (YYYY-MM-DD-title.md)
  - Static pages in `_tabs/` (about, archives, categories, tags)
  - Custom styling in `_sass/`
- **Git Integration**: Custom Jekyll plugin (`_plugins/posts-lastmod-hook.rb`) automatically tracks last modification dates for posts using git history
- **Configuration**: Main site config in `_config.yml` with Chirpy theme customizations

## Development Commands

### Local Development
```bash
# Start local development server
bash tools/run.sh

# Start with custom host
bash tools/run.sh -H 0.0.0.0

# Run in production mode
bash tools/run.sh -p
```

### Testing and Building
```bash
# Build and test the site (includes link checking)
bash tools/test.sh

# Build with custom config
bash tools/test.sh -c "_config.yml,_config.local.yml"
```

### Dependencies
```bash
# Install Ruby dependencies
bundle install

# Update theme and dependencies
bundle update
```

## Content Management

- **Posts**: Create new posts in `_posts/` following the naming convention `YYYY-MM-DD-title.md`
- **Front Matter**: Posts should include title, date, categories, tags, and optional last_modified_at
- **Images**: Store in `assets/` directory and reference with proper paths
- **Drafts**: Place in `_drafts/` directory (excluded from production builds)

## Theme Customization

- **Styling**: Custom SCSS in `_sass/` directory (main.scss, _custom.scss)
- **Configuration**: Site metadata, social links, and theme options in `_config.yml`
- **PWA**: Progressive Web App features enabled with offline caching

## Important Files

- `_config.yml`: Main Jekyll configuration
- `Gemfile`: Ruby dependency management
- `tools/run.sh`: Development server launcher
- `tools/test.sh`: Build and test automation
- `_plugins/posts-lastmod-hook.rb`: Automatic git-based last-modified tracking