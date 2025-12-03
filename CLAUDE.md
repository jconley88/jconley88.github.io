# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Jekyll-based static site blog called "bitfiddle" hosted on GitHub Pages (jconley88.github.io). The actual Jekyll site lives in the `bitfiddle.io/` subdirectory, with a simple redirect at the repository root.

- **Site Title**: bitfiddle
- **Theme**: jekyll-whiteglass
- **Base URL**: `/blog`
- **Production URL**: http://bitfiddle.io

## Development Commands

All Jekyll commands must be run from the `bitfiddle.io/` directory.

### Local Development
```bash
cd bitfiddle.io
bundle exec jekyll serve
```

The site will be available at http://localhost:4000/blog/

**Important**: The `_config.yml` file is NOT reloaded automatically. After editing configuration, restart the server.

### Build Site
```bash
cd bitfiddle.io
bundle exec jekyll build
```

Built site outputs to `bitfiddle.io/_site/`

### Install Dependencies
```bash
cd bitfiddle.io
bundle install
```

## Ruby Environment

- **Required Ruby Version**: 3.1.0 (specified in `.tool-versions`)
- Use `mise` or `asdf` to manage Ruby version

## Content Structure

### Blog Posts
- Location: `bitfiddle.io/_posts/`
- Naming convention: `YYYY-MM-DD-title.markdown`
- Front matter required:
  ```yaml
  ---
  layout: post
  title: "Your Title"
  date: YYYY-MM-DD HH:MM:SS -0600
  categories: category1 category2
  ---
  ```

### Static Pages
- `about.md` - About page
- `archives.md` - Archives listing (auto-generated from posts)
- Navigation links configured in `_data/navigation.yml`

### Jekyll Configuration
- **Permalink structure**: `/:year/:month/:day/:title/`
- **Pagination**: 5 posts per page
- **Enabled plugins**:
  - jekyll-archives (for category and tag pages)
  - jekyll-paginate
  - jekyll-sitemap
  - jekyll-feed

## Repository Structure

```
/
├── index.html              # Redirect to bitfiddle.io
├── README.md
├── .tool-versions          # Ruby version specification
└── bitfiddle.io/           # Main Jekyll site
    ├── _config.yml         # Jekyll configuration
    ├── _posts/             # Blog posts
    ├── _data/              # Data files (navigation, i18n)
    ├── _site/              # Generated site (git-ignored)
    ├── Gemfile             # Ruby dependencies
    └── [static pages]
```

## Architecture Notes

- The repository root contains only a redirect page
- All Jekyll site content and configuration is within `bitfiddle.io/`
- The site uses the jekyll-whiteglass theme which provides the layout and styling
- Categories and tags automatically generate archive pages via jekyll-archives plugin
