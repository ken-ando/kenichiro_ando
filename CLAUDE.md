# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is a Jekyll-based academic personal website for Kenichiro Ando, a postdoctoral researcher at RIKEN. The site is deployed to MIT Media Lab servers and features a multi-language setup (English/Japanese).

## Key Commands

### Development
- `jekyll serve` - Start local development server to preview changes
- `jekyll build` - Build the static site to _site directory

### Deployment
- `./__deploy.sh` - Deploy site to production (requires MIT server access)

## Architecture

### Data-Driven Content
All dynamic content is managed through YAML files in `_data/`:
- `main_info.yaml` - Personal information and social links
- `publications.yaml` - Academic publications
- `projects.yaml` - Research projects
- `news.yaml` / `news_ja.yaml` - News items (English/Japanese)
- `experience.yaml` - Work experience
- `students.yaml` - Student information
- `talks.yaml` - Conference talks
- `classes.yaml` - Teaching information

### Site Structure
- `index.html` - Main English homepage
- `japanese.html` - Japanese version
- `_layouts/` - Page templates (default.html, jpn.html, project.html)
- `_includes/` - Reusable components
- `_projects/` - Individual project pages (Markdown)
- `assets/` - Images and downloadable files
- `libs/` - External CSS/JS libraries

### Styling & Libraries
- CSS Framework: Skeleton CSS
- Icons: Font Awesome
- JavaScript: jQuery 3.1.1
- Additional: Skeleton Tabs, Timeline CSS

## Common Development Tasks

### Adding Publications
Edit `_data/publications.yaml` and add entries with fields like title, authors, venue, paper_pdf, etc.

### Adding News
Edit `_data/news.yaml` (English) or `_data/news_ja.yaml` (Japanese) with date and description.

### Creating New Projects
Add markdown files to `_projects/` directory following existing naming convention (YYYY_project-name.md).

### Updating Personal Info
Modify `_data/main_info.yaml` for name, title, email, and social media links.

## Important Notes
- The deployment script assumes access to MIT Media Lab servers
- Site uses Jekyll collections for projects
- Multi-language support requires updating both English and Japanese data files
- No npm/bundler dependencies - uses system Jekyll installation