# Organization Profile & PC Paper Map (`.github`)

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-green?logo=creativecommons&logoColor=white)](https://creativecommons.org/licenses/by/4.0/)
[![GitHub Pages](https://img.shields.io/badge/Pages-PC%20Paper%20Map-181717?logo=github)](https://probabilistic-computing.github.io/.github/)
[![PC Learn](https://img.shields.io/badge/Learn-PC%20Learning%20Portal-3949AB?logo=readthedocs&logoColor=white)](https://probabilistic-computing.github.io/public/)
[![Corpus: 105+ Papers](https://img.shields.io/badge/Corpus-105%2B%20Papers-blue)](https://probabilistic-computing.github.io/.github/)

[![Stars](https://img.shields.io/github/stars/Probabilistic-Computing/.github?style=flat&logo=github)](https://github.com/Probabilistic-Computing/.github/stargazers)
[![Last Commit](https://img.shields.io/github/last-commit/Probabilistic-Computing/.github)](https://github.com/Probabilistic-Computing/.github/commits/main)
[![Org Followers](https://img.shields.io/github/followers/Probabilistic-Computing?label=followers&logo=github)](https://github.com/Probabilistic-Computing)

Special GitHub organization repository for **[Probabilistic-Computing](https://github.com/Probabilistic-Computing)**: [`profile/README.md`](profile/README.md) renders as the organization's public homepage, and [`docs/`](docs/) deploys to **GitHub Pages** as an interactive, client-side searchable and sortable **PC Paper Map** covering curated research on stochastic computing, bitstream arithmetic, invertible / p-bit logic, and related VLSI work.

- **Repository**: https://github.com/Probabilistic-Computing/.github
- **Organization homepage**: https://github.com/Probabilistic-Computing
- **Interactive paper map**: https://probabilistic-computing.github.io/.github/
- **Learning portal**: https://probabilistic-computing.github.io/public/ ([`Probabilistic-Computing/public`](https://github.com/Probabilistic-Computing/public))
- **License**: CC BY 4.0 (see [`LICENSE`](LICENSE))

## TL;DR

- **Topic**: Stochastic computing (SC), probabilistic bits, invertible logic, and related IEEE circuits / CAD literature
- **Total papers**: curated catalog with titles, authors, venues, DOIs, and publisher abstracts
- **Modality**: Structured bibliographic database (`papers.json`), static org homepage (`profile/README.md`), and client-side web application (`docs/index.html`)
- **Learning**: Separate public MkDocs curriculum at [`Probabilistic-Computing/public`](https://github.com/Probabilistic-Computing/public) (DOI citations only; no PDFs)
- **Research domains**: Neural Networks & Learning, Coding & Communications, DSP & Imaging, Number Generators, Invertible & p-bit Logic, Fault Tolerance, Foundations & Surveys, Stochastic Arithmetic & Circuits
- **Deployment**: Zero-dependency static site on GitHub Pages (Actions or `/docs` branch deploy)

## Features

| Path | Role |
| :--- | :--- |
| [`profile/README.md`](profile/README.md) | Organization landing page |
| [`docs/index.html`](docs/index.html) | Interactive Paper Map (search, domain filters, sort, abstracts, theme switcher) |
| [`docs/papers.json`](docs/papers.json) | Structured JSON catalog (DOIs, venues, abstracts) |
| [`docs/.nojekyll`](docs/.nojekyll) | Disables Jekyll on GitHub Pages |
| [`.github/workflows/deploy-pages.yml`](.github/workflows/deploy-pages.yml) | GitHub Actions → Pages |
| [`LICENSE`](LICENSE) | CC BY 4.0 |

> [!NOTE]
> Do **not** manually edit `profile/README.md` or `docs/papers.json`. Refresh them with `python3 scripts/export_papers_catalog.py` from the catalog source tree.

## Project layout

```text
.github/
├── .github/workflows/deploy-pages.yml
├── docs/
│   ├── .nojekyll
│   ├── index.html
│   └── papers.json
├── profile/README.md
├── LICENSE
└── README.md
```

## Catalog schema

Each item in [`docs/papers.json`](docs/papers.json) includes:

- `slug`, `title`, `authors`, `year`, `venue`, `category`, `categories`
- `abstract` (publisher abstract when available)
- `innovation` (short key-idea blurb when analysis notes exist)
- `url` / `doi`, `has_analysis`

## Quick start

### Standalone clone

```bash
git clone git@github.com:Probabilistic-Computing/.github.git
cd .github
```

### GitHub Pages

- **Branch deploy**: Settings → Pages → Deploy from a branch → `main` / `/docs`
- **Actions**: Settings → Pages → Source → GitHub Actions (uses `deploy-pages.yml`)

### Local preview

```bash
python3 -m http.server 8000 --directory docs
# http://localhost:8000
```

### Refresh catalog

```bash
python3 scripts/export_papers_catalog.py
cd share/github
git add -A && git commit -m "chore: sync papers catalog" && git push origin main
```

## License

Documentation and catalog metadata: [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Publisher titles, DOIs, and abstracts remain under their respective copyright holders. PDFs are not hosted in this repository.

## Citation

```bibtex
@misc{pclab2026catalog,
  title        = {Probabilistic Computing Research Literature Map and Catalog},
  author       = {{Probabilistic Computing Lab Contributors}},
  year         = {2026},
  howpublished = {\url{https://probabilistic-computing.github.io/.github/}},
  note         = {GitHub Organization Profile and Curated Research Map}
}
```

## Contact

- **Organization**: https://github.com/Probabilistic-Computing
- **Issues**: https://github.com/Probabilistic-Computing/.github/issues
