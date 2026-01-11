# Are Some Crimes Easier to Predict Than Others?

## Team Members
- Andria Beridze
- Dachi Khelashvili
- Mariam Tchubabria


## Project Overview

The goal of this project is to analyze whether **some types of crimes are easier to predict than others**, specifically in terms of whether they result in an **arrest**.

Using a large real-world crime dataset, multiple machine learning models are trained and evaluated to predict arrest outcomes. The performance of these models is compared across crime types to better understand which crimes are more predictable.


## Problem Statement and Objectives

### Problem Statement
Crime prediction is challenging due to strong class imbalance and complex relationships between crime type, time, and location. In most cases, crimes do not lead to an arrest, meaning a naive model could achieve high accuracy by always predicting No Arrest.

### Objectives
- Clean and preprocess raw crime data for machine learning
- Prepare separate feature sets for different model types
- Handle missing values, outliers, and inconsistent entries
- Perform feature engineering on time, location, and crime attributes
- Train and evaluate multiple machine learning models
- Compare model performance across different crime types
- Visualize crime distributions, arrest rates, and model results
- Predict whether a crime leads to an arrest
- Compare predictability across different crime types
- Properly handle class imbalance
- Evaluate multiple machine learning models
- Determine whether advanced models outperform simpler ones

## Dataset

Due to GitHub file size limits, the full datasets are hosted externally.

### Files
- raw_data.csv — original dataset
- crime_data_clean.csv — cleaned dataset
- data_for_logistic.csv — features for logistic regression
- data_for_tree_models.csv — features for tree-based models

### Download
📥 Google Drive folder containing all datasets:
https://drive.google.com/drive/folders/1a4vR-hBfD07_vdQ65fLxePhlCxHS0pV_?usp=sharing

### Usage
After downloading, place the files in the `data/` directory:

```bash
data/
├── raw_data.csv
├── crime_data_clean.csv
├── data_for_logistic.csv
├── data_for_tree_models.csv

```
### What is XGBoost? 
For the advanced part of this project, I used XGBoost (Extreme Gradient Boosting). While Random Forest performed well, XGBoost is more powerful and is widely used in real world machine learning tasks.

XGBoost builds decision trees one at a time, with each new tree focusing on correcting the mistakes of the previous ones. This allows the model to gradually improve its predictions instead of treating all trees independently.

Most crimes in the dataset do not lead to an arrest, so a basic model could achieve high accuracy by always predicting “No Arrest.” To avoid this, I used the scale_pos_weight parameter in XGBoost, which forces the model to pay more attention to the minority class (actual arrests).

The dataset is very large and initially caused kernel crashes. XGBoost is optimized for speed and memory efficiency, allowing me to train on over 100,000 rows without system issues. It also captures complex, nonlinear relationships between crime type, location, and time that simpler models would miss.


# Results Summary

In the end of each notebook there is detailed description of results.