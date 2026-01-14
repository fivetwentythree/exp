# AGENTS.md

This file contains guidelines and commands for agentic coding agents working in this Hugo static site repository.

## Project Overview

This is a Hugo static site generator project focused on philosophy and ethics content. The site is deployed to GitHub Pages and uses a custom design system with the Flexoki color palette.

## Build and Development Commands

### Core Hugo Commands
- `hugo server` - Start development server (default: http://localhost:1313)
- `hugo server --buildDrafts` - Include draft content in development
- `hugo server --watch` - Auto-reload on file changes
- `hugo server --port 1314` - Use different port if 1313 is occupied
- `hugo build` - Build the site for production
- `hugo build --minify` - Build with minification (used in CI/CD)

### Content Management
- `hugo new content/posts/article-title.md` - Create new blog post
- Content files use TOML frontmatter with `+++` delimiters
- Draft posts should have `draft = true` in frontmatter

### Deployment
- Site is automatically deployed via GitHub Actions on push to main branch
- CI/CD workflow: `.github/workflows/deploy.yml`
- Build command in CI: `hugo --minify`

## Code Style Guidelines

### File Structure and Organization
```
/
├── content/           # All markdown content
│   ├── _index.md     # Homepage content
│   └── posts/        # Blog posts
├── assets/           # Static assets
│   ├── styles.css    # Main stylesheet
│   └── images/       # Image files
├── static/           # Static files (favicon, etc.)
├── archetypes/       # Content templates
└── hugo.toml        # Hugo configuration
```

### Content Frontmatter Style
- Use TOML format with `+++` delimiters
- Required fields: `title`, `date`, `draft`
- Optional fields: `description`, `images` (array)
- Date format: `YYYY-MM-DDTHH:MM:SS-07:00`
- Example:
```toml
+++
title = 'Article Title'
date = 2024-01-15T12:00:00-07:00
draft = false
description = "Brief description for SEO"
images = ["/images/social/article-image.jpeg"]
+++
```

### CSS Architecture
- Single-file CSS approach: `assets/styles.css`
- CSS custom properties (CSS variables) for theming
- Flexoki color palette for light/dark themes
- Mobile-first responsive design
- Utility-first classes for spacing, layout, typography

### CSS Naming Conventions
- Kebab-case for class names
- Semantic class names: `.site-footer`, `.social-links`
- Utility classes: `.pa` (padding), `.st` (margin-top), `.bg` (background)
- Theme-specific: `.theme-light`, `.theme-dark`
- Component-specific: `.theme-toggle`, `.font-toggle`

### Typography and Fonts
- Primary font: Lora (serif)
- Secondary font: System sans-serif
- Monospace font: Berkeley Mono
- Font loading: `font-display: swap`
- Variable font sizes: 18px mobile, 20px desktop

### Image Guidelines
- Store in `assets/images/`
- Use WebP format for optimization
- Social images in `assets/images/social/`
- Image syntax in markdown: `![alt text](/images/filename.webp "optional title")`
- Responsive images with `max-width: 100%`

### Color System
- CSS custom properties for all colors
- Light/dark theme support
- Semantic color names: `--color-bg-primary`, `--color-tx-normal`
- Flexoki palette base colors

### JavaScript and Interactivity
- Minimal JavaScript approach
- Theme toggle functionality
- Font switching capability
- No external dependencies or frameworks

### Git and Version Control
- Conventional commit messages (see recent commits for examples)
- Main branch: `main`
- Feature branches: `feature/description`
- Commit style: lowercase, descriptive (e.g., "performance improvements", "add rss feature")

### Content Writing Style
- Philosophy and ethics focus
- Thoughtful, exploratory tone
- Internal linking between related posts
- External links open in new window (handled by CSS)
- Use proper markdown formatting

### Testing and Quality Assurance
- No automated test framework (static site)
- Manual testing required:
  - Development server functionality
  - Mobile responsiveness
  - Theme switching
  - Image loading
  - Link validation
- Build verification: `hugo build` before commits

### Security Considerations
- No user input processing
- Static site security model
- No server-side components
- HTTPS enforced via GitHub Pages

### Performance Optimization
- Image optimization (WebP format)
- CSS minification in production builds
- Font loading optimization
- Minimal external dependencies

## Common Tasks

### Adding a New Blog Post
1. Create file: `content/posts/article-title.md`
2. Add TOML frontmatter with required fields
3. Write content in markdown
4. Add images to `assets/images/`
5. Test locally: `hugo server --buildDrafts`
6. Set `draft = false` when ready to publish

### Updating Styles
1. Edit `assets/styles.css`
2. Test changes in development server
3. Check both light and dark themes
4. Verify mobile responsiveness
5. Build and test production version

### Adding New Images
1. Optimize for web (WebP format)
2. Place in `assets/images/`
3. Create social preview version in `assets/images/social/`
4. Reference in content with relative paths

### Theme Modifications
- Edit CSS custom properties in `assets/styles.css`
- Test both `.theme-light` and `.theme-dark` classes
- Ensure proper contrast ratios
- Check mobile compatibility

## Deployment Notes
- Automatic deployment on main branch push
- Build process: GitHub Actions → Hugo → GitHub Pages
- No manual deployment required
- Site URL: https://fivetwentythree.github.io/exp/

## Tools and Dependencies
- Hugo static site generator
- No package.json or npm dependencies
- No build tools beyond Hugo
- Custom CSS only (no preprocessors)