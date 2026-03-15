# takezawa-site

Masanori Takezawa's academic website — built with [Astro](https://astro.build) and deployed to GitHub Pages at [lalalarakko.github.io](https://lalalarakko.github.io).

---

## Quick Start

```bash
npm install
npm run dev       # localhost:4321
npm run build     # build to dist/
npm run preview   # preview build locally
```

After editing content, commit and push to `main` — GitHub Actions deploys automatically.

---

## Content Editing (Markdown)

All content lives in `src/content/`. Edit these files directly in any text editor.

```
src/content/
├── site.md              # Name, affiliation, links, hero text
├── updates.md           # Top page Recent Updates
├── contact.md           # Email, address, profile links
├── research/
│   ├── perspective.md   # Overarching Perspective (EN + JA)
│   └── themes.md        # 5 Research Themes (EN + JA)
├── publications/
│   ├── papers.md        # Peer-reviewed papers (newest first)
│   ├── preprints.md     # Preprints (remove when accepted → add to papers.md)
│   ├── books.md         # Books & chapters
│   └── misc.md          # Misc. & reviews
├── lab/
│   ├── members.md       # Current members
│   ├── alumni.md        # PhD + Master's alumni
│   ├── theses.md        # Dissertations & theses
│   └── news.md          # Lab news (Japanese)
└── cv/
    ├── positions.md     # Academic positions
    ├── education.md     # Education
    ├── grants.md        # Grants (PI + Co-I)
    ├── awards.md        # Awards
    ├── service.md       # Editorial & service roles
    ├── membership.md    # Professional memberships
    ├── reviewing.md     # Ad hoc reviewing
    └── teaching.md      # Teaching
```

### Adding a new paper

Open `src/content/publications/papers.md` and add an entry at the top of the `papers:` list:

```yaml
- year: 2026
  authors: "Surname, A., & Takezawa, M."
  title: "Title of the paper"
  journal: "Journal Name, vol(issue), pages, Month YYYY"
  doi: "10.xxxx/xxxxx"
  cat: cooperation          # cooperation / culture / crowd / misc_tag / (blank)
  role: last                # lead / last / corresponding / contributor
```

### Adding a Lab News item

Open `src/content/lab/news.md` and add at the top:

```yaml
- date: "2026年X月"
  tag: award                # award / jsps / grant
  text: "**名前**が〇〇賞を受賞。"
  url: "https://..."        # optional
```

### Adding an Update (top page)

Open `src/content/updates.md` and add at the top:

```yaml
- date: "Jan 2026"
  tag: "Paper"              # Paper / Award / Position / Service / Grant
  text: "New paper in *Journal* — ..."
```

---

## Design System

| Token | Value |
|-------|-------|
| `--black` | `#0a0a0a` |
| `--white` | `#f5f4f0` |
| `--accent` | `#c0392b` |
| `--gray-light` | `#e8e7e3` |
| `--gray-mid` | `#666` |
| `--gray-dark` | `#222` |
| `--serif` | DM Serif Display |
| `--sans` | DM Sans |
| `--jp` | Noto Sans JP |

**Layout principles:** 1px borders, no shadows, no cards (except research grid on index).

---

## Deployment

Push to `main` → GitHub Actions builds and deploys automatically.

### First-time GitHub Pages setup

1. Go to repo **Settings → Pages**
2. Set **Source** to `GitHub Actions`
3. Push to `main`

---

## For large design changes

Pass the relevant `.astro` or `.css` file to Claude (claude.ai) along with this README. Claude can reconstruct context from the README and make structural changes to components or CSS.
