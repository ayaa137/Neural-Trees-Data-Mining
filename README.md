# 🌳 Neural Trees: Data Mining Project

This project develops and evaluates **Neural Trees**, a differentiable tree-based machine learning approach that combines the structure of decision trees with neural-network training. The project also explores **Joint Neural Boosting** and **Greedy Neural Boosting** and compares their performance with established machine learning models across classification and regression datasets.

## 🔍 Project Objective

The main objective is to investigate how Neural Trees perform across different machine learning tasks and how they compare with traditional models.

The analysis focuses on:

- Single Neural Trees
- Joint Neural Boosting
- Greedy Neural Boosting
- Logistic and Linear Regression
- Random Forest
- Gradient Boosting
- XGBoost

The project evaluates these approaches across both classification and regression problems.

## 📊 Project Overview

The project includes:

- Dataset loading and exploration
- Data preprocessing and feature scaling
- Neural Tree implementation
- Single Neural Tree training
- Joint Neural Boosting
- Greedy Neural Boosting
- Classical baseline models
- Classification and regression evaluation
- Model comparison
- Result visualizations
- Neural Tree explainability
- Training diagnostics
- Confusion matrices
- Depth ablation analysis
- Final interpretation of model performance

## 📦 Datasets

Six datasets are used to evaluate the models across different types of machine learning problems.

| Dataset | Task | Rows | Features |
|---|---|---:|---:|
| Iris | Classification | 150 | 4 |
| Wine Quality | Regression | 6,497 | 12 |
| Student Performance | Regression | 395 | 32 |
| Adult | Classification | 32,561 | 14 |
| Bank Marketing | Classification | 45,211 | 16 |
| Breast Cancer WDBC | Classification | 569 | 30 |

Together, these datasets provide a mixture of small and large datasets, numerical and categorical features, and classification and regression tasks.

## 🌳 Neural Tree Model

The Neural Tree is implemented as a **soft decision tree**.

Instead of making hard binary decisions at each split, the model uses a sigmoid function to produce differentiable split probabilities. Each leaf contains a learnable prediction, allowing the entire tree to be trained using gradient-based optimization.

A tree of depth 2 contains:

- 3 soft split nodes
- 4 leaves

The final prediction is calculated by combining the probability of reaching each leaf with the prediction stored in that leaf.

## 🚀 Neural Boosting Approaches

Two Neural Tree ensemble approaches are evaluated.

### Joint Neural Boosting

Multiple Neural Trees are trained together. Their outputs are combined by averaging their predictions, while the trees are optimized jointly during training.

### Greedy Neural Boosting

Multiple Neural Trees are trained separately and their predictions are combined by averaging their outputs.

These approaches are compared with both a Single Neural Tree and established baseline models.

## 🤖 Baseline Models

The Neural Tree approaches are compared with commonly used machine learning models.

For classification:

- Logistic Regression
- Random Forest
- Gradient Boosting
- XGBoost

For regression:

- Linear Regression
- Random Forest
- Gradient Boosting
- XGBoost

## 📈 Classification Results

### Accuracy

| Dataset | Single Neural Tree | Joint Neural Boosting | Greedy Neural Boosting | Random Forest | Gradient Boosting | XGBoost |
|---|---:|---:|---:|---:|---:|---:|
| Iris | 1.000 | 1.000 | 0.933 | 1.000 | 1.000 | 1.000 |
| Adult | 0.800 | 0.815 | 0.820 | 0.815 | 0.850 | 0.830 |
| Bank Marketing | 0.855 | 0.845 | 0.880 | 0.865 | 0.880 | 0.880 |
| Breast Cancer WDBC | 0.974 | 0.982 | 0.982 | 0.965 | 0.956 | 0.956 |

The Neural Tree approaches perform especially well on **Iris** and **Breast Cancer WDBC**. On Adult and Bank Marketing, established baseline models remain competitive, although the boosting approaches sometimes improve over the Single Neural Tree.

Weighted F1 scores were also used for classification because they provide a better picture of performance when class distributions are less balanced.

## 📉 Regression Results

### R²

| Dataset | Single Neural Tree | Joint Neural Boosting | Greedy Neural Boosting | Linear Regression | Random Forest | Gradient Boosting | XGBoost |
|---|---:|---:|---:|---:|---:|---:|---:|
| Wine Quality | 0.199 | 0.218 | -0.102 | 0.238 | 0.335 | 0.328 | 0.275 |
| Student Performance | -1.475 | -1.487 | -2.980 | 0.724 | 0.802 | 0.808 | 0.773 |

Regression is the clearest weakness of the Neural Tree approach in this project.

For Wine Quality, the Single and Joint Neural Tree models achieve positive R² values, but the baseline regression models perform better.

For Student Performance, the Neural Tree models produce negative R² values, meaning they perform worse than simply predicting the average target value.

## 💡 Key Findings

- Neural Trees can perform well on classification problems.
- The strongest Neural Tree results appear on Iris and Breast Cancer WDBC.
- Joint and Greedy Neural Boosting can improve over the Single Neural Tree, but the improvement is not consistent across every dataset.
- Traditional models remain very competitive on Adult and Bank Marketing.
- Regression is considerably more difficult for the Neural Tree implementation used in this project.
- Random Forest, Gradient Boosting, and XGBoost generally provide stronger regression performance.
- Increasing Neural Tree depth from 1 to 3 does not improve Iris classification accuracy.
- Neural Trees provide useful interpretability because their split weights and leaf probabilities can be inspected.

## 🔎 Explainability

The project examines how the Neural Tree makes its decisions using:

- Neural Tree split weights
- Split-weight heatmaps
- Leaf probabilities
- Random Forest feature importance for comparison

For Iris, the split weights show how strongly individual features influence each soft decision node.

The leaf-probability analysis also shows how test observations are distributed across the leaves of the tree.

## 📊 Training Diagnostics

Training loss curves are used to examine the learning behavior of the Neural Tree models.

The loss decreases during training and eventually stabilizes, indicating that the soft splits and leaf predictions are learning from the training data.

Confusion matrices are also examined for **Adult** and **Bank Marketing**, where class imbalance makes accuracy alone less informative.

## 🌲 Depth Ablation Study

The effect of tree depth is tested on the Iris dataset using depths 1, 2, and 3.

All three depths achieve approximately the same performance:

- Accuracy: **0.9667**
- Weighted F1: **0.9666**

Increasing tree depth therefore does not improve performance on Iris. A shallow Neural Tree is already sufficient for this relatively simple classification problem.

## 🛠️ Technologies Used

- Python
- pandas
- NumPy
- Matplotlib
- scikit-learn
- PyTorch
- XGBoost
- Jupyter Notebook

## 📁 Repository Structure

    Neural-Trees-Data-Mining/
    ├── data/
    │   ├── adult/
    │   ├── bank+marketing/
    │   ├── breast+cancer+wisconsin+diagnostic/
    │   ├── iris/
    │   ├── student+performance/
    │   └── wine+quality/
    ├── images/
    ├── results/
    ├── Neural_Trees.ipynb
    ├── Neural_Trees.html
    ├── README.md
    ├── LICENSE
    └── .gitignore

## 🌐 Project Website

Explore the interactive project portfolio, key results, model comparisons, and full analysis:

👉 **[View the Neural Trees Project Website](https://ayaa137.github.io/Neural-Trees-Data-Mining/)**

## 📓 Full Analysis

The complete analysis is available in:

- `Neural_Trees.ipynb` – complete Jupyter Notebook
- `Neural_Trees.html` – exported HTML version of the analysis

The notebook contains the complete workflow, including data preparation, Neural Tree implementation, model training, baseline comparisons, visualizations, explainability, diagnostics, and final interpretation.

## ⚠️ Limitations

The Neural Tree models are sensitive to training settings and do not consistently outperform established machine learning models.

The regression experiments in particular show that the current Neural Tree implementation has difficulty capturing some relationships in the data.

The experiments also use relatively shallow trees and a specific training configuration. Different architectures, optimization strategies, hyperparameters, or ensemble methods could produce different results.

## 🎯 Conclusion

The experiments show that Neural Trees can work well for classification while maintaining a tree-like structure that provides some interpretability.

The Neural Tree approaches perform particularly well on Iris and Breast Cancer WDBC, while results on Adult and Bank Marketing are more mixed. Joint and Greedy Neural Boosting sometimes improve over the Single Neural Tree, but the improvement is not consistent across all datasets.

Regression remains the main weakness of the current implementation. Random Forest, Gradient Boosting, and XGBoost generally provide stronger and more reliable performance across the regression experiments.

Overall, Neural Trees provide an interesting combination of neural-network optimization and decision-tree structure, but established ensemble methods remain stronger general-purpose models for the datasets evaluated in this project.

## 👩‍💻 Authors

**Aya Abdine**  
**Meriam El Askri — Contributor**

MSc Data Science for Society and Business  
Constructor University, Bremen, Germany
