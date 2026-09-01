[![Netlify Status](https://api.netlify.com/api/v1/badges/8b93220a-4ec3-4914-917e-d0d51bacee39/deploy-status)](https://app.netlify.com/projects/fis-website/deploys)

# FIS — Foundations of Information Science

Static website for [FIS (Foundations of Information Science)](https://fis.sciforum.net/), migrated from WordPress to plain HTML and CSS for deployment on [Netlify](https://fis-website.netlify.app/).

## About

This site hosts information about the FIS initiative — a long-running scholarly community exploring information as a fundamental scientific concept across the Physical, Biological, Social, and Informational domains of science.

The site includes:

- **Home** — introduction to FIS and the information science perspective
- **About FIS** — history, conferences, and mission
- **Joining FIS Mailing List** — how to subscribe and posting rules
- **Discussion Sessions** — archive of FIS sessions and New Year lectures (2014–present)
- **Mail Archives** — links to mailing list archives (1997–present)
- **Resources** — papers and presentations from FIS contributors
- **Contact** — moderator and secretariat details

## Project structure

```
.
├── index.html                    # Home page
├── about-fis/index.html
├── fis-board/index.html
├── fis-discussion-sessions/index.html
├── fis-mailing-list/index.html
├── resources/index.html
├── contact/index.html
├── 404.html
├── assets/
│   ├── css/style.css             # Shared stylesheet
│   ├── img/                      # Logo, Escher image, favicon
│   └── docs/                     # Self-hosted PDFs and documents
├── scripts/
│   ├── build_site.py             # Regenerate HTML from WP API JSON
│   └── download_assets.py        # Download assets from WordPress
├── netlify.toml                  # Netlify deploy configuration
├── _redirects                    # Legacy URL redirects
├── robots.txt
├── sitemap.xml
└── README.md
```

## Editing content

Pages are plain HTML files. To edit:

1. Open the relevant `index.html` (e.g. `contact/index.html`).
2. Edit the content inside `<main class="site-main">`.
3. Shared styles live in `assets/css/style.css`.

To add a document:

1. Place the file in `assets/docs/`.
2. Link to it from the appropriate page using a relative path (e.g. `../assets/docs/my-paper.pdf` from a subpage).

Note: some legacy external documents may no longer be available at their original URLs; those links are preserved as external references.

## Local preview

No build step is required to serve the site. From the project root:

```bash
# Python 3
python3 -m http.server 8080

# or Node.js (if npx is available)
npx serve .
```

Then open [http://localhost:8080](http://localhost:8080).

## SEO

Each page includes:

- Unique `<title>` and meta description
- Canonical URL (`https://fis.sciforum.net/...`)
- Open Graph and Twitter Card tags
- `sitemap.xml` and `robots.txt`
- JSON-LD structured data on the home page (`WebSite` + `Organization`)

## License

Content © FIS contributors. Site structure and styling created for the FIS static migration.
