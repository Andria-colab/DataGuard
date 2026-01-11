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
https://data.cityofchicago.org/Public-Safety/Crimes-2015/vwwp-7yr9/data_preview

### Chicago Crime Dataset - Column Descriptions

| Attribute | Data Type | Description |
| :--- | :--- | :--- |
| **ID** | `Integer` | Unique identifier for the record. |
| **Case Number** | `String` | The Chicago Police Department RD Number (Records Division Number). Unique to the incident. |
| **Date** | `String/DateTime` | Date and time the incident occurred. |
| **Block** | `String` | The address where the incident occurred. Note that the specific street number is partially redacted (e.g., `015XX`) for privacy. |
| **IUCR** | `String` | **Illinois Uniform Crime Reporting** code. A four-digit code that classifies the specific criminal incident. |
| **Primary Type** | `String` | Broad category of the crime (e.g., `THEFT`, `BATTERY`, `NARCOTICS`). |
| **Description** | `String` | Detailed sub-category description of the crime (e.g., `OVER $500`, `SIMPLE`, `TO VEHICLE`). |
| **Location Description** | `String` | Description of the location where the incident occurred (e.g., `STREET`, `APARTMENT`, `SIDEWALK`). |
| **Arrest** | `Boolean` | Indicates whether an arrest was made (`True` or `False`). |
| **Domestic** | `Boolean` | Indicates whether the incident was domestic-related as defined by the Illinois Domestic Violence Act. |
| **Beat** | `Integer` | The smallest police geographic area. A beat is a specific patrol area where police officers are assigned. |
| **District** | `Integer` | Indicates the police district where the incident occurred. Districts are comprised of multiple beats. |
| **Ward** | `Float` | The City Council district (political boundary) where the incident occurred. Chicago has 50 wards. |
| **Community Area** | `Float` | Identifies the community area (neighborhood) where the incident occurred. Chicago has 77 community areas. |
| **FBI Code** | `String` | The crime classification code used for FBI Uniform Crime Reporting (e.g., `06` for Larceny/Theft). |
| **X Coordinate** | `Float` | The x-coordinate of the location (State Plane Illinois East NAD 1983 projection). |
| **Y Coordinate** | `Float` | The y-coordinate of the location (State Plane Illinois East NAD 1983 projection). |
| **Year** | `Integer` | The year the incident occurred. |
| **Updated On** | `String/DateTime` | Date and time the record was last updated in the database. |
| **Latitude** | `Float` | The latitude of the location (WGS84). |
| **Longitude** | `Float` | The longitude of the location (WGS84). |
| **Location** | `String` | A combined tuple of the (Latitude, Longitude) formatted for mapping applications. |


# Due to GitHub file size limits, the full datasets are hosted externally.

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