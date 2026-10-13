# Yuva Intern – Week 3: Feature Engineering

## 📌 Project Overview

This repository contains the work completed for Week 3 of my Junior Data Scientist Internship at Yuva Intern.

The project focuses on feature engineering using Python and Pandas on a publicly available paneer storage study dataset. The objective is to transform existing variables into meaningful features that can support further data analysis and future machine learning experiments.

Feature engineering helps represent changes in food quality measurements over storage time and provides additional information beyond the original dataset.

## 🎯 Objectives

- Understand the structure of the cleaned paneer dataset.
- Create meaningful features from existing variables.
- Calculate changes in microbial and physicochemical measurements relative to baseline observations.
- Categorize storage duration into exploratory phases.
- Examine relationships between storage time and engineered features.
- Export the feature-engineered dataset for further analysis.
- Document the purpose and potential use of each engineered feature.

## 📊 Dataset Information

**Dataset:** Storage study data for paneer in controlled RH and Temperature environment

**Source:** Mendeley Data  
**DOI:** [10.17632/rd9dmr54xx.2](https://doi.org/10.17632/rd9dmr54xx.2)  
**License:** CC BY 4.0

The dataset contains observations related to paneer storage, including microbial measurements, pH, moisture content, and other food-quality attributes.

### Dataset characteristics

- 70 observations
- 14 storage days, from Day 0 to Day 13
- 5 replicates per day
- 24 original columns in the cleaned dataset
- 33 columns after feature engineering

## 🛠️ Tools and Technologies

- Python
- Jupyter Notebook
- Pandas
- NumPy
- Matplotlib
- Seaborn

## ⚙️ Feature Engineering Process

The feature engineering workflow uses the cleaned dataset produced during Week 2.

### 1. Storage Phase

Created a categorical feature named `Storage_Phase`:

- **Early:** Days 0–3
- **Middle:** Days 4–8
- **Late:** Days 9–13

These boundaries are exploratory groupings chosen for this analysis, not validated food-safety or shelf-life thresholds.

### 2. Baseline Features

Created baseline reference features using each replicate's Day 0 observation:

- `Baseline_TPC_Log10`
- `Baseline_pH`
- `Baseline_Moisture_Percent`
- `Baseline_TPC_Count`

These features provide a reference point for comparing later observations from the same replicate.

### 3. Change-from-Baseline Features

Calculated changes relative to Day 0:

- `TPC_Log_Change`
- `pH_Change_From_Baseline`
- `Moisture_Change_From_Baseline`

These features help describe how microbial counts, pH, and moisture change during the observed storage period.

### 4. TPC Growth Ratio

Created `TPC_Growth_Ratio`, calculated as:

Current TPC Count / Baseline TPC Count

A zero baseline count is handled by assigning an undefined value rather than dividing by zero.

## 📁 Repository Structure

```text
yuva-intern-week3-feature-engineering/
├── notebooks/
│   └── 03_feature_engineering.ipynb
├── data/
│   └── paneer_feature_engineered.csv
├── paneer_feature_summary.csv
└── README.md
