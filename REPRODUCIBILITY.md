# Reproducibility: training & evaluation protocol

- Repeats & splits:
  - Experiments use stratified cross-validation (stratified 5-fold) repeated for multiple seeds (reported runs: n = 10 replicates in main experiments). Mean ± SD are reported across replicates. 

- Random seeds:
  - Reproducibility uses `numpy.random.seed(...)` and `torch.manual_seed(...)` (seeds and environment specifications are provided in the repo/supplementary material). 

- Model training defaults (used in reported experiments):
  - Optimizer: Adam. Learning rate: 1e-3. Batch size: 64. Early stopping on validation loss used. LSTM: 50 units (where used). Aggregated results across `n=10` independent runs. 

- Metrics & statistical tests:
  - Metrics: accuracy, precision, recall, F1 (macro/micro); bootstrapped 95% CIs reported. Group comparisons use Wilcoxon signed-rank test and report effect sizes. 

- How to run (high-level):
  1. Create venv and `pip install -r requirements.txt`.
  2. `python scripts/generate_synthetic.py --out data/synthetic.csv` (generator in `scripts/` — see `DATASET_README.md`).
  3. `python scripts/preprocess.py data/synthetic.csv --out data/preprocessed/`  
  4. `python scripts/train.py --config configs/exp_hyperparams.yaml`  
  5. `python scripts/evaluate.py --models models/ --out results/`  
