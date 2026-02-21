What this repository contains

A reproducible codebase that implements the experiments and simulation pipeline described in the manuscript Adaptive Serious Games with Multimodal Sensor Data for the Internet of Things. The repo includes the synthetic dataset generator, preprocessing pipelines, training / evaluation scripts, and Jupyter notebooks used for experiments and figure reproduction.

Key points (what you need to know)

•	The experiments use synthetic IoT–Serious-Game datasets (generator included). Any human-subject pilot data referenced in the paper is available only under the stated ethics/consent conditions — contact the corresponding author for access.
•	Implemented methods include a hybrid HMM–LSTM–CNN classifier, a simulated DQN agent for adaptive difficulty, and privacy/resource simulations (federated aggregation + additive-noise DP). Hyperparameters used in reported experiments (Adam, lr=1e-3, batch_size=64, early stopping; LSTM 50 units) are recorded and provided with the code.
•	Reproducibility: experiments were repeated (e.g., n=10 independent runs) with fixed random seeds and stratified cross-validation; seeds, environment specs and run scripts are available in the repo.

Requirements / Software stack

•	Python 3.10
•	Core libraries used in development and experiments (as provided in the repo): NumPy 1.24, pandas 2.0, Matplotlib 3.7, TensorFlow 2.12. The codebase also references PyTorch and scikit-learn for specific routines. Exact versions and a requirements.txt (or environment file) are included in the repository.

Quick start (run locally)

1.	Clone the repository:
2.	git clone https://github.com/ShyamsSihare/SeriousGames.git
3.	cd SeriousGames
(Repository and reproducibility artifacts are referenced in the manuscript.)
4.	Create & activate a virtual environment, then install dependencies:
5.	python -m venv .venv
6.	source .venv/bin/activate   # on Windows use: .venv\Scripts\activate
7.	pip install -r requirements.txt
8.	Open the notebooks (examples provided):
9.	jupyter notebook
Then open SGs1.ipynb or SGs2.ipynb to run the analysis and reproduce figures/tables. The repository contains generator, preprocessing and training scripts referenced by the notebooks.
10.	To reproduce full experiments:
o	Run the dataset generator (script included in repo) to create the synthetic dataset.
o	Run preprocessing and training scripts (the repo encodes cross-validation and repeated-run protocols).
o	See the repo README & scripts/ folder for the exact command sequence and seed settings.

Reproducibility & evaluation protocol

•	Stratified 5-fold cross-validation repeated across multiple seeds (reported means ± SD), paired nonparametric tests (Wilcoxon signed-rank), and bootstrap CIs for comparisons — all encoded in the evaluation scripts. See the evaluation scripts in the repo for exact commands.
Data & ethics
•	Primary results are based on synthetic datasets (details and generator included). Any real pilot/human data referenced is under ethics/consent restrictions and requires contacting the authors for access procedures.

Notes & contact

•	Hardware used for reported runs: Intel Xeon workstation, 64 GB RAM and an NVIDIA RTX GPU (details & driver info recorded in the appendix / repo).
•	If the repository lacks a LICENSE file, or you need access to restricted datasets, open an issue on the GitHub repository or contact the corresponding author.


