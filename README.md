# Cancer Gene Expression Classification Using Machine Learning

Transcriptomics-Based Cancer Prediction Using GEO Gene Expression Data

---

## Project Overview

This project presents an end-to-end bioinformatics and machine learning workflow for classifying cancer samples using transcriptomic gene expression data.

The workflow includes biological data extraction from GEO, preprocessing, feature selection, dimensionality reduction, machine learning model training, and performance evaluation.

---

## Objective

Build a machine learning pipeline capable of classifying biological samples into:

- Tumor
- Normal

using transcriptomic gene expression profiles.

---

## Dataset

### Source
GEO (Gene Expression Omnibus)

### Dataset
GSE70947

### Dataset Characteristics

| Parameter | Value |
|---|---|
| Samples | 296 |
| Features | 62,976 |
| Classes | Tumor / Normal |

Input:
Gene Expression Matrix

Output:
Cancer Classification

---

## Important Note About Dataset

The complete processed expression matrix is **not included in this repository**.

Reason:
The original processed dataset exceeded GitHub file size limitations.

To keep this repository lightweight and reproducible:

- A **small sample portion of the processed expression matrix** is included in `/data`
- The included dataset is intended only for demonstration purposes
- All reported results were generated using the complete dataset

---

## Workflow

```text
GEO SOFT File
↓
Expression Matrix
↓
Missing Value Handling
↓
Variance Filtering
↓
Scaling
↓
Train/Test Split
↓
Model Training
↓
Evaluation
```

---

## Data Preprocessing

Performed preprocessing steps:

- Parsed GEO SOFT files using GEOparse
- Constructed expression matrix
- Missing value imputation
- Variance filtering
- Standardization

---

## Exploratory Data Analysis

### Principal Component Analysis (PCA)

PCA was applied to reduce high-dimensional transcriptomic data into two principal components.

Observations:

- Partial separation observed between classes
- Biological variability present
- Gene expression patterns support classification

---

## Models Evaluated

| Model | Accuracy |
|---|---|
| XGBoost | 91.7% |
| Gradient Boosting | 85.0% |

Final Selected Model:

**XGBoost Classifier**

---

## Performance

| Metric | Value |
|---|---|
| Accuracy | 91.7% |
| ROC–AUC | 0.96 |

Key Findings:

- Correctly classified 55 of 60 test samples
- Strong discrimination capability
- Low false negative rate

---

## Repository Structure

```text
Cancer-Gene-Expression-Classification/

├── data/
│   └── expression_matrix.csv
│
├── Figures/
│   ├── pca.png
│   ├── confusion_matrix.png
│   └── ROC_Curve.png
│
├── Notebook/
│   └── Analysis.ipynb
│
├── Presentation/
│   └── Cancer Gene Expression Prediction.pdf
│
├── requirements.txt
└── README.md
```

---

## Technologies Used

- Python
- Pandas
- GEOparse
- Scikit-learn
- XGBoost
- Matplotlib
- Seaborn
- Jupyter Notebook

---

## Future Improvements

- Gene annotation
- Biomarker discovery
- Explainable AI
- Model deployment

---

## Author

Rahul Singh

GitHub:
https://github.com/rahuls472
