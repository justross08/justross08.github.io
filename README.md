# justross08.github.io
The Academic Webpage of Justin M. Ross

## About
This is an academic website built with R Markdown and deployed to GitHub Pages. The site showcases research, teaching, and professional information.

## Building the Site Locally

### Prerequisites
- R (version 4.0 or higher recommended)
- RStudio (optional but recommended)
- Required R packages: `rmarkdown`

### Installation
Install the required R package:
```r
install.packages("rmarkdown")
```

### Building
To rebuild the entire site, run in R:
```r
setwd("C:/Users/justross/Dropbox/gitpage/justross08.github.io")
rmarkdown::render_site()
```

This will generate HTML files in the `docs/` directory.

To render a single page (note: `render()` writes the HTML to the working
directory, **not** `docs/` — use `render_site()` to build into `docs/`):
```r
rmarkdown::render("index.Rmd")
```

### Updating the CV
Place the new `cv.pdf` in the **project root**:
```
C:\Users\justross\Dropbox\gitpage\justross08.github.io\cv.pdf
```
Then run `rmarkdown::render_site()` — it will automatically copy `cv.pdf` to `docs/` as part of the build. Do **not** place it directly in `docs/`.

## Repository Structure
```
/
├── _site.yml           # Site configuration and navbar
├── custom.css          # Custom styles (referenced in _site.yml)
├── index.Rmd           # Homepage
├── research.Rmd        # Research & publications
├── running.Rmd         # Running accomplishments
├── doc_students.Rmd    # Doctoral students
├── doc_exams.Rmd       # PhD exam resources
├── about.Rmd           # About page
├── cv.pdf              # Curriculum vitae (source; copied to docs/ on build)
├── images/             # Image assets (compressed)
├── docs/               # Output directory for HTML + PDFs
│   ├── *.html         # Generated HTML pages
│   ├── cv.pdf         # Curriculum vitae
│   └── *.doc          # PhD exam files (TODO: convert to PDF)
└── site_libs/          # Generated R Markdown dependencies

```

## Deployment
The site is deployed to GitHub Pages from the `docs/` directory.

### GitHub Pages Setup
1. Go to repository Settings > Pages
2. Set Source to "Deploy from a branch"
3. Select branch: `main` and folder: `/docs`
4. Save

After pushing changes to the main branch, GitHub will automatically serve the updated site.

## Maintenance Tasks

### Image Optimization
Images have been compressed using Python PIL. To re-compress images if needed:
```python
from PIL import Image
img = Image.open('large_image.jpg')
img.thumbnail((1200, 1200))
img.save('large_image.jpg', 'JPEG', quality=85, optimize=True)
```

### TODO
- [ ] Convert `.doc` exam files in `docs/` to PDF format for better accessibility
- [ ] Consider setting up GitHub Actions for automated building

## Links
- Live site: https://justross08.github.io/
- Substack: https://justinross.substack.com/
