# Player Skill Improvement Uplift

Analysis of point-level college tennis tracking data to identify which skill areas (serve, return, serve-plus-one, rally control, pressure points) give each player the biggest potential gain in point-win probability. The workflow loads raw CSVs, engineers score/context features, trains an embedding-based neural net, runs LOFO tests on skill buckets, and computes per-player counterfactual uplift to recommend training priorities.

## Project layout
- `player_improvement.qmd` — Quarto notebook with the full analysis.
- `player_improvement.html` — Rendered HTML output (same as the GitHub Pages site).
- `Comstat Data/` — Raw CSV files consumed by the notebook.
- `docs/` — Copy of the rendered report that GitHub Pages serves (created from `player_improvement.html` and `player_improvement_files/`).

## View the results
- Local: open `player_improvement.html` in a browser.
- GitHub Pages: once Pages is enabled for this repo with the `docs/` folder selected as the source, the site will serve the same HTML (default URL: `https://<your-username>.github.io/<repo-name>/`).

## Reproduce or update the analysis
1) Install Quarto and the required R packages: `tidyverse`, `janitor`, `recipes`, `keras3`, and their dependencies.
2) Render: `quarto render player_improvement.qmd`.
3) To publish updates, copy the freshly rendered HTML and `_files` directory into `docs/`:
   - `mkdir -p docs`
   - `cp player_improvement.html docs/index.html`
   - `cp -R player_improvement_files docs/`

## GitHub Pages setup
- In GitHub → Settings → Pages, set Source to `Deploy from a branch`, branch `main`, folder `/docs`.
- After saving, GitHub will build and host the site using `docs/index.html` and its assets.
