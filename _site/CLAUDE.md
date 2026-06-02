# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Jekyll-based static website for Gutz Technologies, a multi-omics AI company focused on drug repositioning and experimental design (trial/biomarker design) for pharmaceutical and research partners. The site is built using Jekyll 4.2 and is designed for GitHub Pages deployment. The platform models patient biology across multiple molecular layers to resolve disease subtypes, match existing compounds to the subtypes they work in, and design the experiments that prove it. Companion diagnostics is a related, secondary capability rather than the core positioning. Autism spectrum disorder is the initial focus area; the platform also applies to oncology, autoimmune, and neurological diseases.

**Positioning note:** The company is platform/services-led and pharma-led in audience. It is currently undecided whether it will ever own and develop a repositioned asset itself — so site copy should NOT imply Gutz takes drugs through the clinic. Frame repositioning as surfacing prioritized candidates and evidence *for partners*, who take them forward. Avoid "lead indication" (implies an owned pipeline); use "initial focus" instead.

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
- The site is positioned around drug repositioning and experimental design (trial cohort stratification + biomarker panel design); companion diagnostics is a related, secondary capability
- Audience is pharma-led/both: pharmaceutical BD/portfolio/clinical teams and research consortia (e.g. Wellcome LEAP). Not direct-to-patient/B2C
- Initial focus area: autism spectrum disorder (validated via Nature Neuroscience subtype work). Platform also applies to oncology immunotherapies, autoimmune biologics, CNS therapeutics
- The multi-omics AI platform is the proprietary technology
- Do not overclaim asset ownership: it is undecided whether Gutz will develop a repositioned asset itself — frame outputs as candidates/evidence delivered to partners

**Service Pages:**
- Currently consolidated into one comprehensive service (`service1.md`)
- Service content covers drug repositioning and experimental design as the primary offerings, with companion diagnostics as a related capability
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
- Custom domain configured via `CNAME` file (gutztechnologies.com)
- Jekyll excludes Gemfile, vendor directories, and documentation files from the build (see `exclude` in config)
