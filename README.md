# FIFA World Cup 2026 — Group Stage Predictions

This repository contains a Jupyter notebook that predicts group-stage standings for the FIFA World Cup 2026 using historical FIFA rankings and past match results. The notebook performs data loading, exploratory data analysis (EDA), feature engineering, and applies machine learning models to forecast group standings.

**Project Overview**
- **Notebook:** [group-stage-world-cup-2026-predictions.ipynb](group-stage-world-cup-2026-predictions.ipynb) — end-to-end analysis and predictions.
- **Purpose:** Use ranking and historical results to predict group-stage finishing positions and points.

**Input data**
- **Data folder:** `data/`
- **Files included:**
  - [data/fifa_ranking-2023-07-20.csv](data/fifa_ranking-2023-07-20.csv)
  - [data/fifa_ranking-2024-04-04.csv](data/fifa_ranking-2024-04-04.csv)
  - [data/fifa_ranking-2024-06-20.csv](data/fifa_ranking-2024-06-20.csv)
  - [data/results.csv](data/results.csv)

**Exploratory Data Analysis (EDA)**
- **Load & preview:** Read CSVs into pandas and inspect missing values and basic statistics.
- **Time alignment:** Align ranking snapshots to match the dates of interest for the tournament window.
- **Feature inspection:** Visualize distributions of rankings, goals for/against, and recent form indicators.
- **Correlation checks:** Check relationships between rankings, recent results, and points earned.

**Feature engineering**
- **Ranking features:** Latest FIFA ranking, ranking difference between opponents, ranking percentiles.
- **Form features:** Recent win/draw/loss counts, goals for/against in last N matches.
- **Head-to-head / aggregated stats:** Aggregated historical results between teams (when available).

**Modeling & methods**
- **Problem framing:** Predict group-stage outcomes (e.g., points or ordinal finishing position) per team.
- **Algorithms tried:** Typical approaches include logistic regression for pairwise match outcomes, gradient-boosted trees (e.g., XGBoost or LightGBM) for points prediction, and simple ensemble averaging for robustness.
- **Evaluation:** Use cross-validation and ranking-aware metrics (MAE for points, accuracy for top-2 qualifiers, and Kendall/Tau for ranking similarity).
- **Prediction pipeline:** Prepare match-up dataset → compute features → train model(s) → simulate group matches → aggregate predicted points → derive final standings.

**Results**
- The notebook produces predicted group standings and visualizations for each group.
- Final predicted standings image: add the image file to `images/predicted-standings.png` and it will be displayed below in this README.

![Predicted Standings](images/predicted-standings.png)

Note: The image shown above must be placed at `images/predicted-standings.png`. If you received the standings image as an attachment, save it to that path (create the `images/` folder if it doesn't exist).

**How to run**
- **Requirements:** A Python environment with `pandas`, `numpy`, `matplotlib`/`seaborn`, and an ML library such as `scikit-learn` and optionally `xgboost` or `lightgbm`.
- **Quick run (example):**
  ```powershell
  pip install -r requirements.txt  # if provided
  jupyter lab  # or jupyter notebook
  ```
- Open [group-stage-world-cup-2026-predictions.ipynb](group-stage-world-cup-2026-predictions.ipynb) and run all cells.

**Notes & next steps**
- You can improve predictions by adding more recent rankings, richer match-level features (Elo ratings, player availability), or by simulating match outcomes probabilistically (Monte Carlo).
- If you'd like, I can: run the notebook, commit these changes, or embed the provided attachment into `images/predicted-standings.png` for you.

---
Generated on 2026-06-12.
