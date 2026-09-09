# Neural Trees for Classification and Regression

This project explores Neural Trees, a machine learning approach that combines
the structure of decision trees with neural network optimization.

## Project Overview

The project evaluates Neural Tree models on several classification and regression
datasets and compares their performance with traditional machine learning models.

## Datasets

The following datasets are used:

- Iris
- Wine Quality
- Student Performance
- Adult Income
- Bank Marketing
- Breast Cancer Wisconsin Diagnostic

## Models

The project compares:

- Single Neural Tree
- Joint Neural Boosting
- Greedy Neural Boosting
- Logistic Regression
- Linear Regression
- Random Forest
- Gradient Boosting
- XGBoost

## Project Workflow

1. Load and explore the datasets
2. Preprocess the data
3. Build and train the Neural Tree model
4. Train Joint and Greedy Neural Boosting models
5. Train baseline machine learning models
6. Compare model performance
7. Visualize the results
8. Analyze model explainability
9. Review training diagnostics
10. Perform a depth ablation study

## Main Findings

The experiments show that Neural Trees can perform well on classification tasks,
especially on Iris and Breast Cancer WDBC. The boosting variants sometimes improve
the performance of a single Neural Tree, but the improvement is not consistent
across all datasets.

The regression experiments show that the Neural Tree models are weaker on some
datasets, especially Student Performance, where traditional baseline models perform
better. This highlights both the strengths and limitations of the Neural Tree approach.

## Technologies

- Python
- PyTorch
- Pandas
- NumPy
- Scikit-learn
- XGBoost
- Matplotlib

## Repository Structure

- `Neural_Trees.ipynb` – complete analysis and experiments
- `README.md` – project overview
- `data/` – datasets used in the project
- `images/` – generated visualizations
- `results/` – experiment outputs

## Authors

Aya Abdine  
Meriam El Askri