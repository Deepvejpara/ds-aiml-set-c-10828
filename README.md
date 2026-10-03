# DS & AI/ML Set C — 10828

A complete Data Science and Artificial Intelligence / Machine Learning assessment project covering data preprocessing, statistics, clustering, classification, and Artificial Neural Network (ANN) modeling.

## 📌 Project Overview

This project uses a structured dataset containing operational factors such as **distance, load, traffic, staff**, and **group**, with **late** as the binary target variable.

The workflow covers:

* Data generation and inspection
* Data cleaning and duplicate removal
* Missing-value analysis
* Stratified train/validation/test splitting
* Descriptive statistics
* Statistical and mathematical analysis
* Unsupervised learning and cluster profiling
* Logistic Regression as a baseline classifier
* Artificial Neural Network (ANN) classification
* Model evaluation and comparison
* Prediction export and reproducibility artifacts

The main analysis is contained in `notebook/exam.ipynb`.

## 📂 Repository Structure

```text
ds-aiml-set-c-10828/
│
├── data/
│   └── raw/
│       └── set_b.csv
├── models/
│   ├── ann_model.keras
│   └── preprocessor.joblib
├── notebook/
│   └── exam.ipynb
├── outputs/
│   ├── ann_test_predictions.csv
│   ├── baseline_logistic_test_predictions.csv
│   ├── cluster_profiles.csv
│   ├── inference_results.json
│   ├── k_selection_diagnostics.json
│   ├── linear_algebra_results.json
│   ├── model_comparison_metrics.json
│   ├── preprocessing_audit.json
│   ├── splits.csv
│   ├── statistics_summary.json
│   └── figures/
├── src/
│   └── generate_data.py
├── requirements.txt
└── .gitignore
```

## 📊 Dataset

The raw dataset is stored at `data/raw/set_b.csv`.

| Column      | Description                                         |
| ----------- | --------------------------------------------------- |
| `record_id` | Unique record identifier                            |
| `distance`  | Distance-related numerical feature                  |
| `load`      | Load-related numerical feature                      |
| `traffic`   | Traffic-related numerical feature                   |
| `staff`     | Staff-related numerical feature                     |
| `group`     | Categorical group: G1 or G2                         |
| `late`      | Binary target indicating whether the event was late |

The raw dataset contains **305 rows**, including **5 exact duplicate rows**. After duplicate removal, **300 records** remain.

Missing values are present in the `distance` and `load` features.

## 🔄 Machine Learning Workflow

### 1. Data Preprocessing

The notebook:

1. Loads the raw CSV dataset.
2. Checks dimensions and duplicates.
3. Removes exact duplicate records.
4. Audits missing values.
5. Examines target-class distribution.
6. Creates disjoint training, validation, and test partitions.
7. Uses stratification to preserve the target distribution.
8. Saves preprocessing and split information under `outputs/`.

Partition sizes:

* **Fit/Training:** 192
* **Validation:** 48
* **Test:** 60

A fixed random seed of **42** is used for reproducibility.

### 2. Descriptive Statistics

The notebook calculates:

* Number of observations
* Mean
* Median
* Sample standard deviation

Results are saved to `outputs/statistics_summary.json`.

### 3. Unsupervised Learning

The project includes clustering analysis and diagnostics for selecting the number of clusters.

Generated artifacts:

* `outputs/cluster_profiles.csv`
* `outputs/k_selection_diagnostics.json`

### 4. Baseline Classification

**Logistic Regression** is used as a baseline binary classifier for predicting `late`.

Evaluation metrics include:

* Accuracy
* Precision
* Recall
* F1-score

Predictions are exported to `outputs/baseline_logistic_test_predictions.csv`.

### 5. Artificial Neural Network

An **Artificial Neural Network (ANN)** is trained for the same binary classification task.

Saved artifacts:

* Model: `models/ann_model.keras`
* Preprocessor: `models/preprocessor.joblib`
* Predictions: `outputs/ann_test_predictions.csv`

## 📈 Model Evaluation

The current notebook execution recorded the following test-set results:

| Model               | Accuracy | Precision | Recall | F1-Score |
| ------------------- | -------: | --------: | -----: | -------: |
| Dummy Baseline      |    0.517 |         — |      — |        — |
| Logistic Regression |    0.817 |     0.846 |  0.759 |    0.800 |
| ANN                 |    0.783 |     0.786 |  0.759 |    0.772 |

Detailed metrics are stored in `outputs/model_comparison_metrics.json`.

Confusion-matrix figures and other visual outputs are stored under `outputs/figures/`.

> **Note:** These are the recorded results from the current notebook execution. Results can change if preprocessing, dependency versions, random seeds, or the dataset are changed.

## 🧮 Additional Analysis

The project also stores outputs for:

* Linear algebra calculations
* Preprocessing audits
* K-selection diagnostics
* Cluster profiles
* Inference results
* Train/validation/test split tracking

## 🛠️ Technologies Used

* **Python 3.13**
* **NumPy**
* **Pandas**
* **SciPy**
* **Scikit-learn**
* **Matplotlib**
* **Seaborn**
* **TensorFlow / Keras**
* **Joblib**
* **Jupyter Notebook**

## ⚙️ Installation

Clone the repository:

```bash
git clone https://github.com/Deepvejpara/ds-aiml-set-c-10828.git
cd ds-aiml-set-c-10828
```

Create a virtual environment:

```bash
python -m venv .venv
```

Activate it on Windows:

```bash
.venv\Scripts\activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

## ▶️ Running the Project

### Generate the dataset

From the project root:

```bash
python src/generate_data.py
```

This creates `data/raw/set_b.csv`.

### Run the notebook

Start Jupyter:

```bash
jupyter notebook
```

Open `notebook/exam.ipynb` and run the cells.

Run the notebook from the project root so that relative paths such as `data/raw/`, `models/`, and `outputs/` resolve correctly.

## 📦 Main Artifacts

| Artifact                                         | Purpose                         |
| ------------------------------------------------ | ------------------------------- |
| `models/ann_model.keras`                         | Trained ANN model               |
| `models/preprocessor.joblib`                     | Saved preprocessing pipeline    |
| `outputs/ann_test_predictions.csv`               | ANN test predictions            |
| `outputs/baseline_logistic_test_predictions.csv` | Logistic Regression predictions |
| `outputs/cluster_profiles.csv`                   | Cluster-level profiles          |
| `outputs/model_comparison_metrics.json`          | Model evaluation metrics        |
| `outputs/preprocessing_audit.json`               | Data-quality and split audit    |
| `outputs/splits.csv`                             | Dataset partition mapping       |

## 🎯 Learning Objectives

This project demonstrates practical understanding of:

* Data cleaning and quality checks
* Missing-value analysis
* Stratified dataset splitting
* Descriptive statistics
* Statistical and mathematical analysis
* Unsupervised learning
* Supervised classification
* Logistic Regression
* Artificial Neural Networks
* Model evaluation
* Reproducible ML workflows
* Saving and reusing trained models
* Exporting predictions and analysis artifacts

## 👤 Author

**Deep Vejpara**

GitHub: [Deepvejpara](https://github.com/Deepvejpara)

---

⭐ If you find this project useful, consider giving the repository a star.
