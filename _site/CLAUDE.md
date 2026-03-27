# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Jekyll-based static website for Gutz Analytics, a pharmaceutical companion diagnostics company. The site is built using Jekyll 4.2 and is designed for GitHub Pages deployment. The content focuses on multi-omics AI platforms for companion diagnostic development in oncology, autoimmune, and neurological diseases.

## Development Commands

### Setup
```bash
bundle install
```

### Local Development Server
```bash
bundle exec jekyll serve --watch --verbose
```

The `--watch` flag enables auto-regeneration when files change. The `--verbose` flag provides detailed output for debugging.

### Build
```bash
bundle exec jekyll build
```

## Architecture

### Content Structure

**Jekyll Collections:**
- `_services/` - Service pages are stored as markdown files in this collection
  - Collection configured in `_config.yml` with `output: true` and `sort_by: weight`
  - Each service has frontmatter including `title`, `date`, and `weight` (for ordering)
  - Services automatically get the `service` layout via defaults in `_config.yml`

**Pages:**
- Top-level markdown files (`index.md`, `about.md`, `contact.md`, `services.md`, `team.md`) define main pages
- Each page specifies its layout via frontmatter

**Layouts:**
- `_layouts/default.html` - Base layout
- `_layouts/home.html` - Homepage layout (displays service previews, limited by `site.home.limit_services`)
- `_layouts/service.html` - Individual service page layout
- `_layouts/services.html` - Services listing page layout
- `_layouts/page.html` - Generic page layout
- `_layouts/contact.html` - Contact page layout

**Includes:**
- `_includes/` contains reusable HTML components (header, footer, navigation, etc.)

**Data Files:**
- `_data/menus.yml` - Navigation menu configuration (main and footer menus with weights)
- `_data/contact.yml` - Contact information
- `_data/seo.yml` - SEO metadata
- `_data/social.json` - Social media links
- `_data/features.json` - Homepage features (currently empty)

### Styling

- SASS files in `_sass/` directory
- Bootstrap framework included via `_sass/bootstrap/`
- Custom component styles in `_sass/components/`
- Page-specific styles in `_sass/pages/`
- SASS compilation configured with `style: compressed` in `_config.yml`
- Compiled CSS output in `assets/css/`

### Configuration

**_config.yml key settings:**
- `permalink: pretty` - Clean URLs without `.html` extensions
- `baseurl` is commented out for root domain deployment (uncomment and set for subdirectory deployment)
- Logo configuration with separate mobile/desktop settings
- Collections configuration for services
- Jekyll plugins: `jekyll-environment-variables`

## Content Guidelines

**Business Focus:**
- The site is positioned for pharmaceutical companion diagnostics, specifically Phase 3 trial de-risking and failed asset rescue
- Primary therapeutic areas: oncology immunotherapies, autoimmune biologics, CNS therapeutics
- The "Dynomics" platform is the proprietary technology

**Service Pages:**
- Currently consolidated into one comprehensive service (`service1.md`)
- Service content covers both prospective (Phase 3 de-risking) and retrospective (failed asset rescue) applications
- Weight parameter controls ordering when multiple services exist

**Homepage Content:**
- `index.md` contains the main value proposition
- Layout pulls in service previews automatically via the `home` layout
- Services are limited to 6 on homepage (`limit_services: 6` in config)

## Navigation

Navigation is controlled via `_data/menus.yml`:
- `main` section defines header navigation
- `footer` section defines footer navigation
- `weight` parameter controls ordering (lower numbers appear first)
- URLs use trailing slashes for pretty permalinks

## Deployment

The site is configured for GitHub Pages deployment. When deploying to a subdirectory, update the `baseurl` in `_config.yml` to match the repository name (e.g., `baseurl: "/repo-name/"`).

## Important Notes

- The `_site/` directory contains the generated static site and should not be edited directly
- Images are stored in `images/` directory
- Custom domain configured via `CNAME` file (gutzanalytics.com)
- Jekyll excludes Gemfile, vendor directories, and documentation files from the build (see `exclude` in config)
