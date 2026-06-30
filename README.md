# 🔍🧐 Missing Value Imputation Study — Ames Housing Dataset

This repository contains the practical component of a study on how different missing value handling strategies affect the performance of a regression model for predicting house sale prices.

## Dataset

**Ames Housing Dataset** ([Kaggle](https://www.kaggle.com/datasets/prevek18/ames-housing-dataset))
A rich dataset with a large number of numeric and categorical features describing residential properties in Ames, Iowa. The target variable is `SalePrice`. The dataset is well-suited for this study because it contains structured, non-uniform missingness across many columns.

## What This Notebook Covers

**1. Exploratory Data Analysis of Missing Values**
- Overall missing rate across the dataset
- Per-column and per-row missing counts
- Visualization using `missingno` (bar chart, matrix, heatmap)
- Correlation between missingness and `SalePrice`

A key finding is that several columns with very high missing rates (e.g., `Pool QC` at 99.6%, `Alley` at 93.2%) represent the *absence of a feature* rather than unknown data — an important distinction when choosing an imputation strategy.

**2. Imputation Strategies Compared**
- Classical approaches (mean, median, mode, constant fill)
- Statistical and iterative methods
- Machine learning-based imputation
- Modern approaches including HyperImpute

Where possible, imputation quality is also evaluated directly by artificially masking known values and measuring reconstruction accuracy — not just downstream model performance.

**3. Model Evaluation**
Each imputation strategy is assessed based on its effect on a regression model predicting `SalePrice`, using RMSE, MAE, and R² as metrics.

## Goal

To determine which missing value handling strategy produces the best combination of imputation quality and final model performance, and whether more complex methods consistently outperform simpler baselines.

## Requirements

```
pandas
numpy
matplotlib
seaborn
scikit-learn
missingno
hyperimpute
```
