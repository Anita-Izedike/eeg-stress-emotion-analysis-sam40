# EEG Stress & Emotion Analysis — SAM40

## Overview

This project investigates whether EEG-derived features contain systematic patterns that can distinguish between three experimental states: **NEGATIVE, NEUTRAL, and POSITIVE**.

The analysis uses the **SAM40 EEG-derived feature dataset**, which contains numerical features extracted from EEG recordings collected during experimental tasks designed to elicit different cognitive and emotional states. Rather than working directly with raw EEG recordings, this project focuses on pre-extracted features representing different characteristics of the underlying neural signals.

The analysis follows a structured machine-learning workflow, including data inspection, exploratory data analysis, feature-quality assessment, preprocessing, dimensionality reduction, classification, and model evaluation.

## Research Question

**Do EEG-derived features contain systematic patterns that can distinguish between negative, neutral, and positive emotional states?**

## Research Hypotheses

* **H₀:** EEG-derived features do not contain systematic differences that distinguish between the three emotional-state classes.
* **H₁:** EEG-derived features contain systematic differences that distinguish between the three emotional-state classes.

## Analysis Performed

* Data inspection
* Missing-value and infinite-value assessment
* Duplicate-feature detection
* Descriptive and exploratory analysis
* Feature distribution and skewness analysis
* Feature redundancy and correlation analysis
* Feature-family-aware preprocessing
* Dimensionality reduction using PCA
* Logistic Regression classification
* Random Forest classification
* Confusion matrix analysis
* Model performance comparison
* Interpretation of findings

## Tools

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn

## Key Findings

The exploratory analysis identified substantial redundancy within the EEG-derived feature space, with **732 duplicate feature columns** removed from the original 2,548 features, leaving **1,816 unique features**.

The remaining features showed substantial skewness, with **364 features having an absolute skewness greater than 5**. Particularly extreme values were observed among the high-order `moments_*` features, which created challenges during preprocessing and dimensionality reduction.

A feature-family-aware preprocessing approach was therefore used, followed by PCA. The feature space was reduced from **1,816 features to 13 principal components**, while retaining **95.58% of the variance** in the training data.

Two classification models were evaluated. Logistic Regression achieved **83.37% testing accuracy**, while Random Forest achieved **89.70%**, representing an improvement of **6.32 percentage points**.

The results provide empirical support for the alternative hypothesis that the EEG-derived feature space contains systematic patterns associated with the three observed classes. However, the findings should be interpreted within the limitations of the dataset, including the use of pre-extracted EEG features, the limited number of participants, participant-level dependence, and the use of a single train-test split.

## Project Notebook

The complete analysis and visualizations are available in the accompanying Jupyter Notebook.

## Kaggle

[View the published Kaggle notebook](https://www.kaggle.com/code/izedikeanita/eeg-stress-emotion-analysis-sam40)

## Author

**Izedike Benson Anita**

