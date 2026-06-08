# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a static personal portfolio website for Marco Muccinelli (Senior iOS & Flutter Developer) hosted on GitHub Pages at www.muccy.it. The site uses the "Dimension" template from HTML5 UP, featuring a single-page design with modal-based content sections.

## Architecture

### Static Site Structure
- **index.html**: Main landing page with header, navigation, and footer
- **index.orig.html**: Original unmodified HTML5 UP template (preserved as reference only - DO NOT modify or deploy, blocked from search engines via robots.txt)
- **assets/**: All static assets organized by type
  - **css/**: Compiled CSS files (main.css, noscript.css, fontawesome-all.min.css)
  - **sass/**: SCSS source files organized into base/, components/, layout/, and libs/
  - **js/**: JavaScript files including jQuery and custom modal/navigation logic
  - **webfonts/**: Font Awesome icon fonts
- **images/**: Image assets for the site

### SEO and Discoverability
- **robots.txt**: Configures search engine crawlers (blocks index.orig.html from indexing)
- **sitemap.xml**: XML sitemap for search engines
- **humans.txt**: Human-readable info about the site creator and tech stack
- **ai.txt**: Instructions for LLM crawlers (OpenAI, Anthropic, Google, Meta)
- **Meta tags**: Comprehensive SEO tags including Open Graph and Twitter Card
- **JSON-LD**: Structured data for Person schema

### Key Behavioral Components

**Modal Navigation System** (assets/js/main.js):
- Uses hash-based routing to show/hide modal "pages"
- `$main._show(id)` and `$main._hide()` handle article visibility with 325ms transition delays
- Locking mechanism prevents concurrent animations
- Supports browser back/forward navigation via hashchange events
- ESC key closes active modals

**Responsive Design**:
- Breakpoints defined in main.js: xxsmall (≤360px), xsmall (361-480px), small (481-736px), medium (737-980px), large (981-1280px), xlarge (1281-1680px)
- IE-specific flexbox height fix implemented

**Styling System**:
- SCSS organized modularly in assets/sass/
- Main entry points: main.scss and noscript.scss
- Font Awesome icons used throughout for visual elements

## Development Workflow

### Making Content Changes
Edit index.html directly to update:
- Personal information in the header section
- Navigation links to external profiles (LinkedIn, Medium, GitHub)
- Contact information

### Making Style Changes
1. Edit SCSS files in assets/sass/
2. Compile SCSS to CSS (place output in assets/css/)
3. The compiled CSS is what the browser loads

### Deployment
This is a GitHub Pages site. Changes pushed to the master branch are automatically deployed to www.muccy.it (configured via CNAME file).

## Branch Strategy
- **master**: Production branch (deployed to GitHub Pages)
- **develop**: Development branch for staging changes

Current branch: develop

## Agent skills

### Issue tracker

Issues and PRDs are tracked as GitHub issues (`gh` CLI). See `docs/agents/issue-tracker.md`.

### Triage labels

Default vocabulary (needs-triage, needs-info, ready-for-agent, ready-for-human, wontfix). See `docs/agents/triage-labels.md`.

### Domain docs

Single-context (one CONTEXT.md + docs/adr/ at root). See `docs/agents/domain.md`.
