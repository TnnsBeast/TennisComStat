# group_f_tennis

## Project overview
Point-by-point modeling for Pomona-Pitzer men’s tennis using Comstat data. We build neural models to predict point winners, run skill-bucket LOFO (leave-one-feature-out) analysis, and simulate counterfactual skill improvements per player.

## How to run the player improvement analysis
1. Knit `player_improvement.qmd` to HTML (code is folded by default for easy reading):
   ```bash
   quarto render player_improvement.qmd
   ```
2. The rendered HTML includes:
   - LOFO by skill bucket (which skill areas matter most globally).
   - Uplift tables showing, for each player, which skill bucket yields the biggest point-win lift.
   - Author highlights table (Neil Chulani, Charlie Coleman, Drew Goldman) with their top recommended skill focus.

If you rerun the analysis after adding new matches, re-render to refresh recommendations.

## Notebooks
- `analysis.qmd`: full-feature modeling, embeddings, LOFO.
- `fair_model.qmd`: pre-point “fair” model without rally-outcome leakage.
- `player_improvement.qmd`: player-specific uplift recommendations, LOFO by skill bucket, author highlights.
