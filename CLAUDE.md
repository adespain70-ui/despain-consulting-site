# CLAUDE.md - AI Assistant Guide for DeSpain Consulting Website

## Project Overview

This is a Jekyll-based static website for DeSpain Consulting, a professional consulting firm specializing in AI-powered business solutions and operational efficiency. The site is hosted on GitHub Pages at despain-consulting.com.

## Tech Stack

| Component | Technology |
|-----------|------------|
| Static Site Generator | Jekyll 4.3 |
| Templating | Liquid |
| Markup | Markdown (Kramdown) |
| Styling | CSS (custom properties, no preprocessor) |
| Fonts | Google Fonts (Inter, Playfair Display) |
| SEO | jekyll-seo-tag plugin |
| Analytics | Google Analytics 4 + LinkedIn Insight Tag |
| Hosting | GitHub Pages |

## Directory Structure

```
despain-consulting-site/
├── _config.yml          # Jekyll configuration (site settings, collections, defaults)
├── _includes/           # Reusable HTML components
│   ├── header.html      # Navigation with mobile hamburger menu
│   └── footer.html      # Footer with mobile nav JS
├── _layouts/            # Page templates
│   ├── default.html     # Base layout (includes head, analytics, header, footer)
│   ├── home.html        # Home page with hero section
│   ├── page.html        # Standard page layout
│   └── venture.html     # Individual venture detail pages
├── assets/
│   ├── css/
│   │   └── style.css    # Single stylesheet (~560 lines)
│   └── images/          # Logo and certification images
├── index.md             # Home page content
├── about.md             # About page (founder story, services)
├── problems.md          # Business problems we solve
├── ventures.md          # Business ventures showcase
├── contact.md           # Contact information
├── CNAME                # Custom domain configuration
├── Gemfile              # Ruby dependencies
└── .gitignore           # Build artifacts exclusions
```

## Development Commands

```bash
# Install dependencies (first time setup)
bundle install

# Start local development server (auto-reload)
jekyll serve
# Server runs at http://localhost:4000

# Build for production
jekyll build
# Output goes to _site/ directory
```

## Content Editing

### Front Matter Pattern
All content pages use YAML front matter:

```yaml
---
layout: page        # Options: home, page, venture
title: Page Title
subtitle: Optional subtitle text
---

Markdown content here...
```

### Layout Hierarchy
- `default.html` - Base template (all pages extend this)
  - Includes: head, analytics, header, footer
- `home.html` - Extends default, adds hero section
- `page.html` - Extends default, standard page wrapper
- `venture.html` - Extends default, venture detail formatting

### Adding New Pages
1. Create a new `.md` file in the root directory
2. Add front matter with `layout: page` and `title`
3. Add navigation link in `_includes/header.html`

## CSS Conventions

### Color Variables (defined in :root)
```css
--color-primary: #877167      /* Warm brown - primary brand color */
--color-primary-dark: #6d5a52 /* Darker brown - hover states */
--color-bg-alt: #FCF7F1       /* Warm off-white - section backgrounds */
--color-accent: #A59E97       /* Muted taupe - secondary elements */
--color-border: #e5e7eb       /* Light gray - borders */
```

### Typography
- **Headings (h1-h6)**: Playfair Display (serif)
- **Body text**: Inter (sans-serif)
- **Spacing base**: `--spacing-unit: 1rem`

### Component Classes
- `.container` - Max-width content wrapper (1200px)
- `.btn`, `.btn-primary`, `.btn-secondary` - Button styles
- `.problem-card`, `.venture-card` - Grid card components
- `.testimonial` - Quote block with left border
- `.hero`, `.home-section`, `.page-header` - Section containers

### Responsive Design
- Mobile-first approach
- Single breakpoint at 768px
- Mobile hamburger menu with JS toggle

## Key Conventions

### Writing Style
- Professional, confident tone
- Focus on AI and operational efficiency expertise
- Use "we/our" (company voice), not "I/my"

### Commit Messages
- Use present tense, descriptive messages
- Examples: "Add feature", "Update content", "Fix styling issue"

### File Naming
- Use kebab-case for all files (e.g., `about.md`, `style.css`)
- Images should be descriptive (e.g., `cert-ai-foundations.jpg`)

## Deployment

The site auto-deploys to GitHub Pages when changes are pushed to the main branch.

- **Domain**: despain-consulting.com (configured in CNAME file)
- **Build**: Jekyll generates static files to `_site/`
- **Excluded from build**: Gemfile, Gemfile.lock, README.md

## Analytics Configuration

Located in `_layouts/default.html`:
- **Google Analytics 4**: Property ID `GA-BRM5GJDPWV`
- **LinkedIn Insight Tag**: Partner ID `8584260`

## Common Tasks

### Update Homepage Hero
Edit `index.md` - the hero content is in the front matter and first content section.

### Add New Venture
Create a file in `_ventures/` directory (collection) or add to `ventures.md` page content.

### Modify Navigation
Edit `_includes/header.html` - navigation links are in the `<nav>` element.

### Change Colors/Styling
Edit `assets/css/style.css` - CSS variables are at the top in `:root`.

### Update SEO Metadata
Edit `_config.yml` for site-wide settings, or individual page front matter for page-specific metadata.

## Troubleshooting

### Local server not starting
```bash
bundle install  # Ensure dependencies are installed
```

### Changes not appearing
- Jekyll requires restart for `_config.yml` changes
- Check for YAML syntax errors in front matter
- Clear browser cache

### Build errors
- Validate Liquid syntax in layouts/includes
- Check for unclosed tags in markdown
