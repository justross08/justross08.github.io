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
rmarkdown::render_site()
```

This will generate HTML files in the `docs/` directory.

To render a single page:
```r
rmarkdown::render("index.Rmd")
```

## Repository Structure
```
/
├── _site.yml           # Site configuration and navbar
├── index.Rmd           # Homepage
├── research.Rmd        # Research & publications
├── running.Rmd         # Running accomplishments
├── doc_students.Rmd    # Doctoral students
├── doc_exams.Rmd       # PhD exam resources
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
