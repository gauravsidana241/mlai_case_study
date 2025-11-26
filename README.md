# ML/AI Case Study 1: ECG Arrhythmia Detection

This repository contains the code for Case Study 1, focusing on the detection and classification of cardiac arrhythmia using the MIT-BIH Arrhythmia Database.

## 📂 Dataset Setup (Required)

**Note:** The raw dataset and the generated CSV files are **not included** in this repository (they are excluded via `.gitignore` to keep the repo clean). You must download the data manually to run the code.

1.  **Download** the MIT-BIH Arrhythmia Database from PhysioNet:  
    👉 **[https://physionet.org/content/mitdb/1.0.0/](https://physionet.org/content/mitdb/1.0.0/)**

2.  **Extract** the downloaded ZIP file.

3.  **Rename** the extracted folder to `mitbih`.

4.  **Place** the `mitbih` folder in the root directory of this project (the same folder where the `.ipynb` files are located).

## 🚀 How to Run

To generate the necessary data and reproduce the results, please execute the notebooks in the **exact order** listed below:

### 1. Data Preprocessing
* **File:** `data_preprocess.ipynb`
* **Action:** Run this first. It reads the raw signals from the `mitbih` folder, segments the heartbeats, and generates the initial `all_data.csv`.

### 2. Data Splitting & Resampling
* **File:** `data_split_resample.ipynb`
* **Action:** Run this second. It takes the processed data and creates the specific training and testing sets:
    * **Beat Split:** Standard shuffled split.
    * **Patient Split:** Intra-patient split (holding out specific patients for testing).
    * *Note: This step generates the `train_beats.csv`, `test_beats.csv`, `train_patients.csv`, and `test_patients.csv` files required for the model.*

### 3. Main Model & Analysis
* **File:** `model_clustering_and_training.ipynb` (or your main submission notebook)
* **Action:** Run this last. It loads the CSVs created in the previous steps to perform:
    * SVM & Random Forest Classification.
    * Permutation Feature Importance analysis.
    * Clustering analysis (K-Means / T-SNE).

## 🛠️ Requirements
* Python 3.x
* Jupyter Notebook
* **Libraries:** `numpy`, `pandas`, `matplotlib`, `seaborn`, `scikit-learn`, `wfdb`, `biosppy`
