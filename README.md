# Associations Project ANLP 2025

**Submitted by**: Daniel Ruderman | Hodaya Stern Zuckerman | Tamar Gozlan

This repository contains the scripts and notebooks that were used to **clean**, **standardize**, and **analyze** free‑association datasets, plus simple training and evaluation notebooks for downstream modeling.

---
## Prerequisites 
### If you want to perform the preprocessing
1. Download SWOW-EN from <>
2. Install Python requirements from Preprocessing/requirements.txt

```pip install -r Preprocessing/requirements.txt```

### Training, metrics and benchmarking
3. Make sure you populate HF_TOKEN environment variable with your HuggingFace token.
4. If not using Colab, change BASE_PATH to the directory of the project.

---
## Pipeline Steps
The steps for reproducing the flow used in our article are:

1. Data cleaning adapted from the LWOW github which we reference in our article
2. Second preprocessing to create our required format, namely downsamples to exactly 80 rows per cue.
3. Training - Fine-tuning the LLlaMa model (meta-llama/Meta-Llama-3-8B-Instruct) to human-like associations
4. Metrics - gathering metrics about the fine-tuning.
5. Benchmarking - currently on summarization task.



---

## Steps using the Repo Contents

### Preprocessing
#### 1) 
`Preprocessing/1_FA_data_Cleaning.py`
End‑to‑end **data cleaning pipeline** used to process human SWOW data and multiple LLM free‑association (FA) datasets into clean, aligned CSVs and a summary table.
This script was downloaded from the LWOW repo: https://github.com/LLMWorldOfWords/LWOW

---

#### 2) 
`Preprocessing/2_second_preprocessing.py`
A lightweight, task‑focused preprocessor for SWOW CSVs with columns `cue`, `R1`, `R2`, `R3`. It cleans, filters, and downsamples to exactly 80 rows per cue, then writes the result to an Excel file.

---

### Training
#### 3) `Training/ANLP_training.ipynb`
A **training notebook** (Jupyter) that demonstrates how to train a model using the cleaned FA datasets.

---

### Metrics
#### 4) `Metrics/ANLP_metrics.ipynb`
An **evaluation/metrics notebook** (Jupyter) for analyzing model outputs.

---
### Benchmarking
### 5) `Benchmarks/ANLP_benchmarks.ipynb`


---
