# CLAUDE.md — Justin Ross's Academic Webpage

## Project Overview

This is the academic website of Justin M. Ross, Professor of Public Finance at Indiana University. It is built with **R Markdown** and deployed to **GitHub Pages** from the `docs/` directory.

Live site: https://justross08.github.io/

## Source Files

All editable content lives in `.Rmd` files in the project root:

| File | Page |
|------|------|
| `index.Rmd` | Homepage |
| `research.Rmd` | Research & publications |
| `running.Rmd` | Running accomplishments |
| `doc_students.Rmd` | Doctoral students |
| `doc_exams.Rmd` | PhD exam resources |
| `about.Rmd` | About page |
| `_site.yml` | Site config: navbar, output directory, theme |

The `docs/` directory contains the generated HTML files — **do not edit these directly**. Always edit the `.Rmd` source files.

## Building the Site

After editing `.Rmd` files, the HTML must be regenerated. Run in R (or RStudio):

```r
# Rebuild the entire site from R
setwd("C:/Users/justross/Dropbox/gitpage/justross08.github.io/.claude/worktrees/elegant-kalam")
rmarkdown::render_site()

# Rebuild a single page (faster for small edits)
rmarkdown::render("research.Rmd")
```

This outputs HTML to `docs/`. Both the `.Rmd` source and the regenerated `docs/*.html` must be committed together.

## Deploying to GitHub

After building, commit and push to `main`:

```bash
git add -A
git commit -m "Your message here"
git push origin main
```

GitHub Pages serves automatically from `docs/` on `main`. Changes are live within ~30 seconds of pushing.

## Design & Styling

The site currently uses the default R Markdown Bootstrap theme (no custom CSS file). To change the theme or add custom styles:

- **Theme**: Edit the `output` section in `_site.yml` (e.g., `theme: flatly`)
- **Custom CSS**: Create a `custom.css` file and reference it in `_site.yml`:
  ```yaml
  output:
    html_document:
      css: custom.css
  ```

Available Bootstrap themes: `default`, `cerulean`, `cosmo`, `flatly`, `journal`, `lumen`, `paper`, `readable`, `sandstone`, `simplex`, `spacelab`, `united`, `yeti`.

## Content Conventions

- **Research page** (`research.Rmd`): 
  - Sections: Published Peer Review, Working Papers, Works in Progress, Book & Symposium Contributions, Policy Statements/Op-Eds, Book Reviews.
  - **Published Peer Review**: List in reverse chronological order (most recent first). Treat "Forthcoming" papers as the most recent — they appear at the top before dated publications.
  - Example order: Forthcoming (no year) → 2025 → 2024 → 2023 → etc.
- **Links**: Use standard Markdown `[text](url)` format. Publication titles are bolded and linked.
- **Images**: Stored in `images/`. Referenced inline in `.Rmd` with `<img src="images/filename.jpg" style="width:50%">`.

## Common Tasks

**Add a new publication**: Edit `research.Rmd`, add an entry in the appropriate section following the existing format, then rebuild and push.

**Update homepage info**: Edit `index.Rmd`, rebuild, push.

**Change navbar items**: Edit `_site.yml`, rebuild entire site (`render_site()`), push.

**Add/change a photo**: Add image to `images/`, reference it in the relevant `.Rmd`, rebuild, push.
