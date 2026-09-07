# Appau Gideon Kofi Amo — academic website

Source for [amo-gideon.github.io](https://amo-gideon.github.io), built with the
[Academic Pages](https://github.com/academicpages/academicpages.github.io)
Jekyll template (Minimal Mistakes fork) and served by GitHub Pages.

## Layout

- `_config.yml` — site-wide settings and author profile/sidebar
- `_pages/` — About (front page), CV, Publications/Talks/Teaching/Portfolio index pages
- `_publications/` — one Markdown file per publication (front matter = citation metadata)
- `_talks/`, `_teaching/`, `_portfolio/` — same idea, one file per item
- `files/` — downloadable files (CV PDF lives here)
- `images/` — profile photo and site images

## Editing

1. Edit the relevant Markdown file (front matter + body).
2. Commit and push — GitHub Pages rebuilds the site automatically in about a minute.

Local preview (optional, needs Ruby + bundler):

```bash
bundle install
bundle exec jekyll serve -l -H localhost
# then open http://localhost:4000
```
