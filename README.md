# Diabetes Classification with K-Nearest Neighbors (KNN)

A K-Nearest Neighbors (KNN) classifier that predicts diabetes risk from patient health metrics, built as a ready-to-run Google Colab notebook.

## Overview

This project trains a KNN model on the **Pima Indians Diabetes** dataset (768 patients, 8 clinical features) to classify patients as diabetic or non-diabetic. The dataset is fetched directly from a public URL at runtime, so no manual download is required.

## Dataset

| Feature | Description |
|---|---|
| Pregnancies | Number of times pregnant |
| Glucose | Plasma glucose concentration |
| BloodPressure | Diastolic blood pressure (mm Hg) |
| SkinThickness | Triceps skinfold thickness (mm) |
| Insulin | 2-hour serum insulin (mu U/ml) |
| BMI | Body mass index |
| DiabetesPedigreeFunction | Diabetes likelihood based on family history |
| Age | Age in years |
| Outcome | 0 = No Diabetes, 1 = Diabetes (target) |

Source: [Pima Indians Diabetes Dataset](https://raw.githubusercontent.com/jbrownlee/Datasets/master/pima-indians-diabetes.data.csv)

## Pipeline

1. **Load data** — read the dataset directly from its source URL.
2. **Clean data** — replace biologically invalid zero-values (e.g. BMI = 0) with `NaN` and impute using the median.
3. **Explore data** — visualize class balance and feature correlations.
4. **Split data** — 80% train / 20% test, stratified by outcome.
5. **Scale features** — standardize with `StandardScaler`, since KNN relies on distance calculations.
6. **Tune k** — use 10-fold cross-validation across k = 1–30 to find the optimal number of neighbors.
7. **Train model** — fit the final `KNeighborsClassifier` on the scaled training data.
8. **Evaluate model** — report accuracy, a classification report, a confusion matrix, and an ROC curve with AUC score.
9. **Predict new data** — example cell for scoring a new patient's measurements.

## Tech Stack

- Python
- pandas, NumPy
- scikit-learn
- matplotlib, seaborn

## Usage

1. Open `diabetes_knn_classification.ipynb` in [Google Colab](https://colab.research.google.com/).
2. Run all cells (**Runtime → Run all**). No setup or file upload needed.
3. Review the accuracy, confusion matrix, and ROC curve in the output.
4. Edit the final cell with your own values to get a prediction for a new patient.

## Disclaimer

This notebook is for educational purposes only and is **not** a medical diagnostic tool. Predictions should not be used for real clinical decision-making.
