# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is a Jekyll-based academic personal website for Kenichiro Ando, a postdoctoral researcher at RIKEN. The site is deployed to MIT Media Lab servers and features a multi-language setup (English/Japanese). The template is based on Martin Saveski's academic website template.

## Key Commands

### Development
- `jekyll serve` - Start local development server at http://localhost:4000
- `jekyll build` - Build the static site to _site directory

### Deployment
- `./__deploy.sh` - Deploy site to production (requires MIT server access)
  - Note: The current deployment script references msaveski's account and needs to be updated for the actual deployment target

## Architecture

### Data-Driven Content
All dynamic content is managed through YAML files in `_data/`:
- `main_info.yaml` - Personal information and social links
- `publications.yaml` - Academic publications (fields: title, authors, venue, paper_pdf, in_doc)
- `projects.yaml` - Research projects
- `news.yaml` / `news_ja.yaml` - News items (English/Japanese)
- `experience.yaml` - Work experience
- `students.yaml` - Student information
- `talks.yaml` - Conference talks
- `classes.yaml` - Teaching information
- `activities.yaml` / `activities_ja.yaml` - Academic activities (committees, etc.)
- `reviwer.yaml` - Reviewer roles (note: filename has typo)

### Site Structure
- `index.html` - Main English homepage
- `japanese.html` - Japanese version
- `_layouts/` - Page templates (default.html, jpn.html, project.html)
- `_includes/` - Reusable components
- `_projects/` - Individual project pages (Markdown with YAML front matter)
- `assets/` - Images and downloadable files
- `libs/` - External CSS/JS libraries
- `_site/` - Generated static site (not in version control)

### Project Pages
Project markdown files in `_projects/` use YAML front matter:
```yaml
---
layout: project
title: "Project Title"
subtitle: "Brief description"
---
```

### Styling & Libraries
- CSS Framework: Skeleton CSS
- Icons: Font Awesome 4.7.0 and 6.2.0
- JavaScript: jQuery 3.1.1
- Additional: Skeleton Tabs, Timeline CSS

## Common Development Tasks

### Adding Publications
Edit `_data/publications.yaml` with structure:
```yaml
papers:
  - title: "Paper Title"
    authors: "Author1, Author2, ..."
    venue: "Conference/Journal Name"
    paper_pdf: "URL or path to PDF"
    in_doc: y  # Include in documentation
```

### Adding News
Edit `_data/news.yaml` (English) or `_data/news_ja.yaml` (Japanese):
```yaml
- date: "YYYY.MM"
  description: "News description"
```

### Creating New Projects
1. Add markdown file to `_projects/` with naming: `YYYY_project-name.md`
2. Include proper YAML front matter
3. Use `{{"/assets/projects/..." | prepend: site.baseurl }}` for image paths

### Updating Personal Info
Modify `_data/main_info.yaml` for name, title, email, and social media links.

## Important Notes
- The deployment script assumes access to MIT Media Lab servers
- Site uses Jekyll collections for projects
- Multi-language support requires updating both English and Japanese data files
- No npm/bundler dependencies - uses system Jekyll installation
- The `_config.yml` may need baseurl updates for different deployment targets
- When referencing assets in markdown, use the `prepend: site.baseurl` filter