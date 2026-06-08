# BurnZone — marketing & documentation site

Top-of-funnel site for **BurnZone**, a white-label, multi-tenant gym platform.
Built with [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/).

**Live:** https://sreenivas-sadhu-prabhakara.github.io/burnzone-site/

It has two audience tracks:

- **For Gyms** (`/gyms/`) — the B2B platform: white-label, operator console, roles, plans.
- **For Members** (`/members/`) — the B2C app: Train, Eat, Book, Track.

Plus **How it works** (architecture) and a **What's available** status page.

## Develop

```bash
pip install --user mkdocs-material
python3 -m mkdocs serve        # live preview at http://localhost:8000
python3 -m mkdocs build --strict
```

## Deploy (GitHub Pages)

```bash
python3 -m mkdocs gh-deploy --force
```

This builds the site and pushes it to the `gh-pages` branch, which GitHub Pages serves.

## Structure

```
docs/
  index.md            # custom hero landing (uses overrides/home.html)
  gyms/               # For Gyms (B2B) track
  members/            # For Members (B2C) track
  how-it-works.md
  whats-available.md
  overrides/home.html # custom landing template
  stylesheets/extra.css
  assets/logo.svg
mkdocs.yml
```
