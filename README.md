# Fraud Detection (PaySim-like)

A concise end-to-end notebook for detecting fraudulent transactions on the provided simulation-style dataset.

## What’s inside
- Data sanity checks and light cleaning (dupes, balance-delta flags, outlier flag, no missing values expected).
- Feature engineering: time (`hour`, `day`), log/amount/balance fields, balance deltas, merchant destination flag, negative-balance and amount-outlier flags, one-hot `type`.
- Class-weighted logistic regression baseline with stratified split, precision–recall threshold tuning, cost-based threshold selection.
- Visuals: PR curve with marked thresholds, confusion matrix at the chosen threshold, score distributions by class.
- Human-readable answers to the candidate expectation questions.

## Run it
1) Clone and open the repo.
2) Ensure the CSV path in the notebook points to your local data (default: `data/transactions.csv`).
3) Install deps: `pip install -r requirements.txt`
4) Run the notebook top-to-bottom to regenerate metrics, plots, cost/threshold table, and saved artifacts in `models/`.

## Key outputs to expect
- ROC-AUC and PR-AUC on validation.
- Threshold sweep table plus PR curve.
- Cost-ranked thresholds with selected operating point persisted to `models/threshold.json`.
- Confusion matrix and score distribution at the selected threshold.


