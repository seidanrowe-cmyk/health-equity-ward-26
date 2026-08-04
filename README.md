# Chicago Ward Health — Health Equity Project

Two connected public-health data products for Chicago's City Council wards, built for the office of Ald. Jessie Fuentes (26th Ward) and generalized to all 50 wards.

## 🔗 Live site (GitHub Pages)

- **Dashboard (landing page):** https://seidanrowe-cmyk.github.io/health-equity-ward-26/
- **Ward 26 deep-dive infographic:** https://seidanrowe-cmyk.github.io/health-equity-ward-26/ward26.html

The plain site URL opens the search screen — type any ward number (1–50) to load that ward's profile.

## 📁 Files

| File | What it is |
|------|-----------|
| `index.html` | **The 50-ward dashboard.** Opens to a search bar; enter a ward number to see its profile. Adapts everything (cards, maps, causal read, policy plans) to the ward you pick. Self-contained HTML/CSS/JS. |
| `warddash.js` | **The dashboard's data** (`window.DASH`). All 50 wards + 77 community areas: 7 health indicators, 6 social-determinant indicators, and boundary geometry, embedded so the dashboard works offline. `index.html` loads this file. |
| `ward26.html` | **The Ward 26 infographic** — the original single-ward deep-dive (life-expectancy gap, "one ward, two realities" community map, drivers, policy levers). Self-contained. |
| `README.md` | This file. |

> `index.html` needs `warddash.js` in the same folder to work. `ward26.html` is fully standalone.

## 📊 What the dashboard shows (per ward)

- **Section A — Four biggest problems:** the four community-health measures where the ward ranks worst among all 50 (chosen from hypertension, diabetes, obesity, hyperlipidemia, depression, asthma, food insecurity), each vs. the citywide rate.
- **Section B — Maps:** a 50-ward city choropleth beside a zoom of the selected ward split into its community areas.
- **Section C — Why it clusters:** the social determinant most strongly tracking the ward's worst condition across its communities.
- **Section D — What's driving it:** social-determinant profile vs. the city + a community × determinant heat grid.
- **Section E — Three/four levers:** one tailored, evidence-cited policy plan for each of the ward's biggest problems.
- **Section F — Sources.**

## 🗃️ Data sources

- **Chicago Health Map** (chicagohealthmap.com, a project of CAPriCORN) — ward- and community-area-level condition prevalence, 2024. These are rates among *patients seen in Chicago health systems* (a clinical population, not a general-population survey), so they run higher and are best read as comparisons between geographies.
- **Chicago Health Atlas** (chicagohealthatlas.org) — food insecurity, income, poverty, food access, uninsurance, unemployment, life expectancy (community-area level).
- **Chicago Data Portal** — ward and community-area boundaries.
- **Peer-reviewed literature** — cited inline in the policy sections (see Section F / the infographic's Sources).

## ✏️ Editing / re-running

- It's plain static HTML — open the files directly in a browser, or edit and refresh. No build step.
- **Refreshing the data:** `warddash.js` is a snapshot. It was generated from the Chicago Health Map GraphQL API (`https://chicagohealthmap.com/api/graphql`) and the Atlas API. Search the dashboard source for `// TODO: EJScreen` — that marks where an environmental-burden (freight/pollution) layer would be wired in.

## 🚀 Deploying

The site is served by **GitHub Pages** from the `main` branch, root folder. Any push to `main` republishes automatically within a minute or two:

```bash
git add -A
git commit -m "your message"
git push origin main
```

## 💬 Resuming the Claude Code session

From this folder, run `claude --resume` (or `claude -c` to continue the latest) to pick the conversation back up with full history.
