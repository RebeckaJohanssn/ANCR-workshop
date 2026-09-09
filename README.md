# NORDCAN API Tutorial: Interactive Cancer Epidemiology in Python

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/IARC-CSU/ANCR-Workshop/HEAD?urlpath=%2Fdoc%2Ftree%2Fnordcan_api_tutorial.ipynb)

A step-by-step hands-on tutorial for querying the official **IARC NORDCAN REST API (v9.6)** and building publication-grade interactive epidemiological visualizations in Python.

---

## Launch on MyBinder (Zero Install & No Login Required)

You can run the tutorial interactively in your browser with zero installation or account requirements:

1. Push this repository to your GitHub account (e.g. `https://github.com/IARC-CSU/ANCR-Workshop`).
2. Go to **[mybinder.org](https://mybinder.org)** and paste your repository URL.
3. In the **"Path to a notebook file"** field, enter: `nordcan_api_tutorial.ipynb`.
4. Click **Launch** to start an interactive JupyterLab session.

---

## Tutorial Overview (`nordcan_api_tutorial.ipynb`)

This notebook guides participants through the complete data science pipeline using a real-world cancer registry case study: **Top 10 Cancer Mortality Sites for Females in Finland (Crude Rates, 1953–2024)**.

### What You Will Learn:
1. **REST API Architecture**:
 - Understand URL endpoint structures and parameters: `/data/population/{type}/{sex}/{population}/{cancers}/`
2. **Metadata Discovery**:
 - Query `/meta/populations/all/` and `/meta/cancers/all/` to dynamically resolve registry codes (`Finland -> 246`) and official cancer color schemes.
3. **Leaf vs. Grouped Sites**:
 - Bundle all 55 mutually exclusive leaf cancer site IDs with underscores (`_`) into a single high-efficiency API request.
4. **Executing HTTP Requests**:
 - Retrieve longitudinal cancer records using Python's `requests` library and inspect response payloads.
5. **Data Structuring with Pandas**:
 - Clean, type, and structure 3,600+ JSON records into an analysis-ready DataFrame.
6. **Epidemiological Ranking**:
 - Dynamically identify the most recent recording year (2024) and rank the top 10 causes of cancer death in Finland.
7. **Publication-Grade Plotly Trendlines**:
 - Build interactive trend charts with **direct line endpoint labels** (pinned to year 2024) and **rich hover tooltips** (Cancer Site, Year, Crude Rate per 100k, Total Deaths, ASR-World).
8. **Data Export & Interactive Tables**:
 - Download the curated dataset directly in the browser as a CSV file (`finland_female_cancer_mortality_top10.csv`) and explore with interactive `itables`.

---

## Running Locally

To run the tutorial locally on your own computer:

```bash
# 1. Clone the repository
git clone https://github.com/IARC-CSU/ANCR-Workshop.git
cd ANCR-Workshop

# 2. Create and activate a virtual environment
python3 -m venv .venv
source .venv/bin/activate # On Windows: .venv\Scripts\activate

# 3. Install dependencies
pip install -r requirements.txt

# 4. Launch JupyterLab
jupyter lab nordcan_api_tutorial.ipynb
```

---

## Requirements
- `python>=3.10`
- `requests>=2.28.0`
- `pandas>=2.0.0`
- `plotly>=5.15.0`
- `itables>=2.0.0`
- `ipywidgets>=8.0.0`
- `jupyterlab>=4.0.0`

---

## Citation
> Larønningen S, Arvidsson G, Bray F, Dahl-Olsen ED, Engholm G, Ervik M, Friis S, Guðmundsdóttir EM, Gulbrandsen J, Hansen HM, Johannesen TB, Kristensen S, Kønig SM, Lam F, Laversanne M, Lydersen LN, Malila N, Mangrud OM, Miettinen J, Pejicic S, Persson Å, Pettersson D, Skog A, Steig BÁ, Tian H, Aagnes B, Storm HH (2026). NORDCAN: Cancer Incidence, Mortality, Prevalence and Survival in the Nordic Countries, Version 9.5.1 (12.02.2026). Association of the Nordic Cancer Registries. Cancer Registry of Norway. Available from: https://nordcan.iarc.fr/
