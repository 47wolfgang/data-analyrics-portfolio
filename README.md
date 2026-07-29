# Your Name — Data Visualization Portfolio

A personal, résumé-style portfolio site for showcasing interactive dashboard
projects. Fully static — no build step, no framework, no backend. New
dashboards can be added over time as more projects are built.

## Structure

```
.
├── index.html                          # Main landing page (hero, about, projects, contact)
├── projects/
│   ├── valorant-meta.html              # Project detail page — embeds the dashboard live
│   └── vct-2026.html                   # Project detail page — embeds the dashboard live
├── dashboards/
│   ├── valorant-meta-overview.html     # The actual dashboard (self-contained)
│   └── vct-2026-overview.html          # The actual dashboard (self-contained)
├── netlify.toml                        # Redirects + headers
└── README.md
```

## Before you deploy — personalize it

Search each file for these placeholders and replace them with your info:

| Placeholder | Where | Replace with |
|---|---|---|
| `Your Name` / `YOUR NAME` | `index.html`, footers | Your actual name |
| `[email protected]` | `index.html` (hero + contact) | stiven14cq@gmail.com |
| `LinkedIn` / `GitHub` `href="#"` | `index.html` hero + contact | https://www.linkedin.com/in/john-stiven-correa-quiroz |
| `Download résumé (PDF)` `href="#"` | `index.html` | https://drive.google.com/file/d/11r7YJa61w5inNHylwNxntuwjqEog29QS/view?usp=drive_link |
| About paragraph | `index.html` → `#about` | I'm Stiven Correa Quiroz, from Bello, Antioquia, Colombia. I currently work as a Commission Analyst Sr. (developer) at Siigo, focused on Python development, data analysis, People Analytics, and process automation (RPA). Previously, I worked at Grupo Éxito and Magneto in similar roles involving analytics, Power BI dashboards, and HR automation. |
| Skill tags | `index.html` → `#about` | Python, SQL, Power BI, Power Automate, Power Apps, Knime, Excel/VBA, HTML, CSS, JavaScript, Java, React, RPA Development, Data Analysis, ETL, Row Level Security (RLS), Web Scraping, API Integration |

The two project pages already describe the dashboards accurately — no edits
needed there unless you want to adjust the "Role" or add real project dates.

## Adding a new dashboard to the portfolio

1. Drop the new self-contained dashboard HTML file into `dashboards/`.
2. Duplicate `projects/valorant-meta.html`, rename it, and update: title,
   description, meta row, tags, iframe `src`, and the "what this dashboard
   does" list.
3. Add a new `.project-card` block in `index.html` under `#projects`,
   pointing the `<iframe class="preview-frame">` and the card link at the
   new files.
4. Optional: add a redirect for it in `netlify.toml`.

## Deploy to Netlify

**Option A — Drag & drop (fastest)**
1. Go to https://app.netlify.com/drop
2. Drag this whole folder (or a zip of it) onto the page
3. Netlify assigns a live URL immediately

**Option B — Netlify CLI**
```bash
npm install -g netlify-cli
cd portfolio
netlify deploy --prod
```

**Option C — Git-based deploy**
1. Push this folder to a GitHub/GitLab/Bitbucket repo
2. In Netlify: "Add new site" → "Import an existing project"
3. Build command: (leave empty) · Publish directory: `.`

## Notes

- Each dashboard is 100% self-contained (data, styles, and logic all embedded
  in one HTML file), so the `iframe` embeds work with zero configuration —
  no shared assets, no cross-file dependencies.
- The homepage project cards use a *live, scaled-down iframe* of the real
  dashboard as the preview — not a screenshot — so it's always in sync with
  the actual project.
- The portfolio shell (nav, hero, about, contact) uses its own neutral visual
  identity, independent from each dashboard's own styling, so future
  dashboards on different topics will fit in visually without a redesign.
