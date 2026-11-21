# PatientPrivacyAI

**Authors**

- Cameron Hafer
- Rohan Gottipati
- Gabriela Rodriguez
- Atirath Kosireddy

For our CSC 260D final project, we wanted to see whether hospitals can train a heart-disease model together while keeping their patients private, and who pays the price when privacy gets stronger.

We simulate four real hospitals from the UCI Heart Disease data: Cleveland, Hungary, Switzerland and VA Long Beach. Each one keeps its own records and protects every patient with differential privacy. We compare three ways of training:

- each hospital on its own
- FedAvg, where they share one model
- MR-MTL, where each hospital keeps a personalized model

We look at every hospital separately, especially whichever one ends up worst off.

This is a simulation on old public data (using FLamby's version of the split), not a clinical tool.

## Setup (Windows PowerShell)

```powershell
python -m venv .venv
.\.venv\Scripts\python.exe -m pip install torch==2.15.0 --index-url https://download.pytorch.org/whl/cpu
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
```

On Mac or Linux, use `.venv/bin/python` instead of `.\.venv\Scripts\python.exe`.

The data (one zip file of about 130 KB) downloads automatically from UCI, and its SHA-256 hash is checked.

## Notebooks

We kept all the code in four notebooks. Run them in this order: data, methods, experiments, results. Each one loads what it needs from the earlier ones, so you can also open any of them on its own.

| notebook | what it does |
|---|---|
| `notebooks/data.ipynb` | download, FLamby split, features, data audit, data checks |
| `notebooks/methods.ipynb` | settings, model, DP-SGD + privacy accounting, local / FedAvg / MR-MTL, metrics, method checks |
| `notebooks/experiments.ipynb` | learning-rate pick, noise levels, runs the whole experiment (about 3 min; finished runs are skipped) |
| `notebooks/results.ipynb` | summary tables, bootstrap, figures, report tables (`results/tables.md`) |

## Folders

| folder | contents |
|---|---|
| `results/` | all saved results (CSV) and the data audit |
| `figures/` | PNG figures |
| `data/raw/` | downloaded data (not in git) |

## Data credit

- **Dataset:** A. Janosi, W. Steinbrunn, M. Pfisterer, R. Detrano. *Heart Disease* [dataset]. UCI Machine Learning Repository, 1989. https://doi.org/10.24432/C52P4X. Licensed under CC BY 4.0.
- **Split and filtering** follow FLamby's Fed-Heart-Disease benchmark: J. Ogier du Terrail et al., *FLamby: Datasets and Benchmarks for Cross-Silo Federated Learning in Realistic Healthcare Settings*, NeurIPS 2022 Datasets and Benchmarks (https://github.com/owkin/FLamby, commit `edacf54`).
