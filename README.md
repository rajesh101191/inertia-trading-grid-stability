<p align="center">
  <img src="banner.png" width="100%" alt="Grid Inertia Trading and Stability Optimization">
</p> 

📘 Grid Inertia Analysis & Optimization in Renewable-Rich Power Systems (India)

A Python–MATLAB Integrated Framework for Frequency Stability, Inertia Shortfall Detection, and Metaheuristic Optimization

🌍 Overview

This repository contains a complete end-to-end pipeline to analyse inertia issues in the Indian power system under increasing renewable energy penetration.
The workflow integrates Python (data extraction & analysis) and MATLAB (AGC–LFC simulation & optimization) to study frequency stability using:

3 years of GRID-India frequency reports

1 year of VRE (solar + wind) variability datasets

Metaheuristic optimization algorithms (DE, PSO, GWO)

4 simulation cases representing different grid scenarios

The goal is to identify inertia shortfall, quantify its impact on system frequency, and implement optimal inertia trading strategies for enhanced stability.

🧰 Key Components
🔹 1. Data Extraction & OCR (Python)

Extracted text tables from GRID-India frequency PDFs using

Tesseract OCR

pdfplumber

Converted unstructured reports into structured Excel/CSV files.

Automated cleaning of:

missing timestamps

malformed strings

multi-column merges

erroneous text blocks

🔹 2. Frequency & VRE Data Processing

Merged 36 months of daily frequency reports

Combined with one-year VRE (solar/wind) generation profiles

Extracted indicators:

ROCOF

Variability windows

Peak/min frequency

Inertia shortfall days

Generated visual composite plots for quick interpretation.

🔹 3. Case Creation for Simulation

Prepared four system scenarios (CASE 1–4) representing:

Low RE, high inertia

High RE, low inertia

Mixed variability

Extreme conditions

Each case includes:

Raw system data (CASE1_RAW, etc.)

KPIs

Convergence plots

Tie-line & frequency overlays

⚙️ 4. MATLAB AGC–LFC Simulation & Optimization

For each scenario, inertia trading was optimized using:

🐺 Grey Wolf Optimizer (GWO)
🐦 Particle Swarm Optimization (PSO)
🧬 Differential Evolution (DE)

MATLAB scripts include:

compute_kpis.m

gwo_inertia_trade.m

pso_inertia_trade.m

de_inertia_trade.m

simulate_case.m

plot_convergence.m

plot_freq_overlays.m

objective_itae.m

KPIs computed:

ITAE, IAE, ISE

Peak |Δf1|, |Δf2|

Tie-line deviations

Settling time improvements

📊 5. Visual Analytics & Outputs

Key visual outputs:

Frequency overlays per case

Optimization convergence curves

Boxplots & histograms of VRE variability

Correlation heatmaps

Composite figures combining multiple diagnostic charts
├── data/
│   ├── cleaned_frequency_report/
│   ├── vre_profiles/
│   ├── inertia_shortfall_days.xlsx
│   └── india_yearly_full_release.xlsx
│
├── python/
│   ├── OCR_extract.ipynb
│   ├── Frequency_analysis.ipynb
│   ├── Inertia_Trading.ipynb
│   ├── Variable_Renewable_Energy.ipynb
│   └── utils/
│
├── matlab/
│   ├── de_inertia_trade.m
│   ├── pso_inertia_trade.m
│   ├── gwo_inertia_trade.m
│   ├── simulate_case.m
│   ├── compute_kpis.m
│   └── plotting_scripts/
│
├── cases/
│   ├── CASE1_RAW.xlsx
│   ├── CASE1_KPI.xlsx
│   ├── CASE1_convergence.png
│   ├── CASE1_freq_overlays.png
│   └── ...
│
└── README.md
⭐ Highlights

Fully reproducible Python + MATLAB hybrid workflow

Real-world power system datasets (GRID-India)

Multiple optimization frameworks

Clean visual results for publication

Ready for extension into storage scheduling, virtual inertia, or grid-forming converters

📚 Technologies Used

Languages: Python, MATLAB
Libraries:

Python → pandas, numpy, pdfplumber, pytesseract, matplotlib, seaborn

MATLAB → Control Toolbox, Optimization scripts
---

## 🚀 How to Run This Project

This repository includes both Python and MATLAB components. Follow the instructions below to execute the full pipeline.

---

## 🐍 1. Python Setup

### Install required libraries
Make sure you have Python 3.8+ installed. Then run:

```bash
pip install pytesseract pdfplumber pandas numpy matplotlib openpyxl
Required external installation

Install Tesseract OCR (needed for text extraction):

Windows: https://github.com/UB-Mannheim/tesseract/wiki

Linux: sudo apt install tesseract-ocr

Run Python scripts (order)
python 1_extract_frequency_reports.py
python 2_extract_vre_reports.py
python 3_clean_merge_frequency.py
python 4_inertia_shortfall_analysis.py

These scripts correspond to:

OCR extraction

PDF table extraction

Data cleaning

Frequency profile computation

Inertia shortfall detection

📊 2. MATLAB Setup
Add folder to MATLAB path

Open MATLAB

Go to: Home → Set Path → Add Folder

Select the folder containing the .m files (e.g., matlab_code)

Run MATLAB simulations
Step 1 — Load case and compute KPIs
These scripts correspond to:

OCR extraction

PDF table extraction

Data cleaning

Frequency profile computation

Inertia shortfall detection

📊 2. MATLAB Setup
Add folder to MATLAB path

Open MATLAB

Go to: Home → Set Path → Add Folder

Select the folder containing the .m files (e.g., matlab_code)

Run MATLAB simulations
Step 1 — Load case and compute KPIs
simulate_case
compute_kpis
Step 2 — Run optimization models
gwo_inertia_trade
pso_inertia_trade
de_inertia_trade
Step 3 — Plot results
plot_convergence
plot_freq_overlays
plot_tieline_overlay
KPIs generated:

ITAE, IAE, ISE

Peak |Δf1| and |Δf2|

Tie-line deviations

Settling time
🔄 Workflow Diagram

Below is the complete workflow used in this project:

Extract GRID-India PDFs

OCR + Table extraction

Clean + Merge data

Frequency deviation analysis

Calculate inertia shortfall

Create simulation cases

MATLAB AGC–LFC modelling

Optimization using GWO, PSO, DE

KPI extraction and comparison

---


Dr. Rajesh Kumar
Prestige Institute of Engineering Management & Research, Indore
Assistant Professor — Electrical Engineering / AI & DS
Power system analytics | Renewable energy | Optimization | AI in grids
📝 Citation

If you use this repository, please cite:

Kumar, R. (2025). Grid Inertia Analysis & Optimization in Renewable-Rich Indian Power Systems. GitHub Repository.
