# Insurance Expense Prediction Using BMI and Age

### MSBA 265 – Module 2: Linear Regression Assignment

## Project Overview

This project examines how BMI and age can be used to predict insurance expenses through linear regression. It extends a model that uses only BMI by including age as an additional feature to explore whether the second variable improves prediction performance.

Two methods are used to train the two-feature model:

- Normal Equation (analytical solution)
- Gradient Descent (iterative optimization)

The project compares both methods with a BMI-only baseline and evaluates their performance using MSE, RMSE, MAE, and R².

## What This Repository Contains

This repository includes:

- A Python script implementing linear regression with BMI and age
- An insurance dataset containing 1,338 observations
- A CSV file containing model weights and evaluation metrics
- A written memo explaining the results and business implications

## Project Objectives

The objectives of this assignment are to:

1. Load and prepare insurance data for regression analysis.
2. Build a linear regression model using BMI and age.
3. Implement the Normal Equation using a general matrix solver.
4. Train the same model using Gradient Descent with standardized features.
5. Convert the Gradient Descent weights back to their original units.
6. Evaluate model performance using MSE, RMSE, MAE, and R².
7. Compare the two-feature models with a BMI-only baseline.
8. Interpret the results and discuss whether the model is suitable for deployment.

## Repository Structure

```text
MSBA265_Module2_NguyenMy/
│
├── README.md
├── assignment_two_feature_nguyenmy.py
├── assignment_memo.md
│
├── data/
│   └── insurance-premium-prediction/
│       └── insurance.csv
│
└── reports/
    └── assignment_results.csv
```

## Prerequisites

Before running the project, make sure you have:

- Python 3.10 or newer
- Git
- Internet access for cloning the repository and installing dependencies

## 1. Clone the Repository

Open a terminal and run:

```bash
git clone https://github.com/nguyenmysan/MSBA265_Module2_NguyenMy.git
cd MSBA265_Module2_NguyenMy
```

## 2. Create and Activate a Virtual Environment

### Windows (PowerShell)

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

If script execution is blocked, run:

```powershell
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
.\.venv\Scripts\Activate.ps1
```

### macOS (Terminal or zsh)

```bash
python3 -m venv .venv
source .venv/bin/activate
```

## 3. Install Dependencies

This project requires NumPy for numerical calculations and matrix operations.

### Windows

```powershell
python -m pip install --upgrade pip
python -m pip install numpy
```

### macOS

```bash
python3 -m pip install --upgrade pip
python3 -m pip install numpy
```

## 4. Run the Python Script

Make sure you are in the repository's root directory.

### Windows

```powershell
python assignment_two_feature_nguyenmy.py
```

### macOS

```bash
python3 assignment_two_feature_nguyenmy.py
```

The script performs the following steps:

1. Loads BMI, age, and expenses from the insurance dataset.
2. Fits a two-feature linear regression model using the Normal Equation.
3. Standardizes BMI and age before training with Gradient Descent.
4. Converts the Gradient Descent weights back to their original units.
5. Calculates MSE, RMSE, MAE, and R² for both methods.
6. Fits a BMI-only baseline model for comparison.
7. Prints a comparison table and exports the results to `reports/assignment_results.csv`.

## 5. Model Results

### Model Comparison

| Model | R² | RMSE |
|---|---:|---:|
| BMI-only Baseline | 0.0394 | 11,864.41 |
| Normal Equation (BMI + Age) | 0.1173 | 11,373.64 |
| Gradient Descent (BMI + Age) | 0.1173 | 11,373.64 |

Adding age improved R² by approximately 0.0778, or 7.78 percentage points.

Both the Normal Equation and Gradient Descent produced nearly identical model weights.

### Two-Feature Model Weights

| Parameter | Value |
|---|---:|
| Intercept (w0) | -6437.35 |
| BMI coefficient (w1) | 333.39 |
| Age coefficient (w2) | 241.90 |

The positive age coefficient indicates that predicted insurance expenses increase by approximately $241.90 for each additional year of age when BMI remains constant.

Although adding age improves the model's performance, the two-feature model explains only about 11.73% of the variation in insurance expenses.

## 6. Review the Exported Results

After running the Python script, open:

`reports/assignment_results.csv`

The CSV file contains the model weights and evaluation metrics for all three models.

## 7. Written Memo

The file `assignment_memo.md` provides a short discussion of the model results.

The memo addresses four questions:

1. How much did adding age improve R²?
2. Why do the Normal Equation and Gradient Descent produce similar weights?
3. What does the age coefficient mean for a non-technical stakeholder?
4. Is the two-feature model suitable for deployment?

## Troubleshooting

### ModuleNotFoundError: No module named 'numpy'

Make sure the virtual environment is activated and install NumPy:

```bash
python -m pip install numpy
```

### FileNotFoundError: insurance.csv

Make sure the dataset is located at:

`data/insurance-premium-prediction/insurance.csv`

The dataset must remain in this location for the Python script to run correctly.

### Wrong Python Interpreter in VS Code

Open the Command Palette and select:

`Python: Select Interpreter`

Choose the Python interpreter from the `.venv` environment.

## Dataset and Acknowledgment

- Dataset source: Kaggle Insurance Premium Prediction Dataset.
- This assignment builds on the Module 2 Linear Regression Learning Lab materials provided by Professor Shyla Solis.

## Author

Nguyen My San

Master of Science in Business Analytics

University of the Pacific
