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



### What is XGBoost? 
For the advanced part of this project, I used XGBoost (Extreme Gradient Boosting). While Random Forest performed well, XGBoost is more powerful and is widely used in real world machine learning tasks.

XGBoost builds decision trees one at a time, with each new tree focusing on correcting the mistakes of the previous ones. This allows the model to gradually improve its predictions instead of treating all trees independently.

Most crimes in the dataset do not lead to an arrest, so a basic model could achieve high accuracy by always predicting “No Arrest.” To avoid this, I used the scale_pos_weight parameter in XGBoost, which forces the model to pay more attention to the minority class (actual arrests).

The dataset is very large and initially caused kernel crashes. XGBoost is optimized for speed and memory efficiency, allowing me to train on over 100,000 rows without system issues. It also captures complex, nonlinear relationships between crime type, location, and time that simpler models would miss.