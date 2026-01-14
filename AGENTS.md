# AGENTS.md

This file contains guidelines and commands for agentic coding agents working in this Hugo static site repository.

## Project Overview

Hugo static site generator focused on philosophy content. Deployed to GitHub Pages with Flexoki color palette and custom design system.

## Build/Development Commands

### Hugo Commands
- `hugo server` - Start dev server (http://localhost:1313)
- `hugo server --buildDrafts` - Include draft content
- `hugo server --watch` - Auto-reload on file changes
- `hugo build` - Build for production
- `hugo build --minify` - Build with minification (CI uses this)
- `hugo new content/posts/article-title.md` - Create new post

### Testing
- No automated test framework (static site)
- Manual testing: dev server, mobile responsiveness, theme switching, links
- Build verification: `hugo build` before commits

## Code Style Guidelines

### File Structure
```
content/          # Markdown content (_index.md, posts/)
assets/           # styles.css, images/
static/           # favicon, static files
archetypes/       # Content templates
hugo.toml         # Hugo config
```

### Frontmatter (TOML)
- Delimiters: `+++`
- Required: `title`, `date`, `draft`
- Optional: `description`, `images` (array)
- Date format: `YYYY-MM-DDTHH:MM:SS-07:00`
```toml
+++
title = 'Article Title'
date = 2024-01-15T12:00:00-07:00
draft = false
description = "SEO description"
images = ["/images/social/article-image.jpeg"]
+++
```

### CSS Architecture
- Single-file: `assets/styles.css`
- CSS custom properties for theming
- Flexoki color palette (light/dark themes)
- Mobile-first responsive design

### CSS Naming Conventions
- Kebab-case class names
- Semantic: `.site-footer`, `.social-links`
- Utility: `.pa` (padding), `.st` (margin-top), `.bg` (background)
- Theme: `.theme-light`, `.theme-dark`
- Components: `.theme-toggle`, `.font-toggle`

### Typography
- Primary: Lora (serif)
- Secondary: System sans-serif
- Monospace: Berkeley Mono
- Font loading: `font-display: swap`
- Sizes: 18px mobile, 20px desktop

### Images
- Location: `assets/images/`
- Format: WebP (optimized)
- Social: `assets/images/social/`
- Markdown: `![alt](/images/file.webp "title")`
- Responsive: `max-width: 100%`

### Color System
- CSS custom properties for all colors
- Semantic names: `--color-bg-primary`, `--color-tx-normal`
- Light/dark theme variables

### JavaScript
- Minimal approach (theme/font toggles)
- No external dependencies or frameworks

### Git/Version Control
- Commits: lowercase, descriptive (e.g., "performance improvements", "add rss feature")
- Main branch: `main`
- Feature branches: `feature/description`

### Content Style
- Philosophy/ethics focus
- Internal linking between posts
- External links open in new window (CSS handled)
- Proper markdown formatting

### Security
- Static site security model
- No user input processing
- HTTPS enforced via GitHub Pages

### Performance
- Image optimization (WebP)
- CSS minification in production
- Font loading optimization

## Common Tasks

### New Blog Post
1. Create: `content/posts/article-title.md`
2. Add TOML frontmatter
3. Write markdown content
4. Add images to `assets/images/`
5. Test: `hugo server --buildDrafts`
6. Publish: set `draft = false`

### Update Styles
1. Edit `assets/styles.css`
2. Test in dev server
3. Verify light/dark themes and mobile
4. Build: `hugo build`

### Add Images
1. Optimize to WebP
2. Place in `assets/images/`
3. Create social version in `assets/images/social/`
4. Reference with relative paths

### Deployment
- Auto-deploy on main branch push
- CI/CD: GitHub Actions → Hugo → GitHub Pages
- Site: https://fivetwentythree.github.io/exp/

## Tools
- Hugo static site generator
- No npm/Node.js dependencies
- Custom CSS (no preprocessors)