# MSBA 265 – Module 2: Two-Feature Linear Regression

A beginner-friendly project for learning linear regression using real insurance data.

This assignment extends a single-feature linear regression model by adding age as a second feature to predict insurance expenses.

The project uses two methods to train the same model:

- Normal Equation (analytical solution)
- Gradient Descent (iterative optimization)

The goal is to compare both methods and evaluate whether adding age improves prediction performance compared to using BMI alone.

## What You Are Downloading

This repository contains:

- A Python script implementing two-feature linear regression
- A local copy of the insurance dataset
- A CSV file containing model comparison results
- A written memo discussing the results and business implications

## Learning Objectives

By the end of this assignment, students should be able to:

1. Load and inspect a real insurance dataset.
2. Identify BMI and age as features and insurance expenses as the target variable.
3. Train a two-feature linear regression model using the Normal Equation.
4. Train the same model using Gradient Descent.
5. Standardize both BMI and age to improve Gradient Descent optimization.
6. Evaluate model performance using MSE, RMSE, MAE, and R².
7. Compare the two-feature models with a BMI-only baseline.
8. Interpret model results and explain their business implications.

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

- Python 3.10 or newer recommended
- Git
- Internet access for the initial clone and package installation

## 1) Clone the Project

Open a terminal and run:

```bash
git clone https://github.com/nguyenmysan/MSBA265_Module2_NguyenMy.git
cd MSBA265_Module2_NguyenMy
```

## 2) Create and Activate a Virtual Environment

### Windows (PowerShell)

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

If script execution is blocked:

```powershell
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
.\.venv\Scripts\Activate.ps1
```

### macOS (Terminal or zsh)

```bash
python3 -m venv .venv
source .venv/bin/activate
```

## 3) Install Dependencies

This assignment requires NumPy.

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

## 4) Run the Assignment Script

Make sure you are in the repository's root directory.

### Windows

```powershell
python assignment_two_feature_nguyenmy.py
```

### macOS

```bash
python3 assignment_two_feature_nguyenmy.py
```

The script will:

1. Load BMI, age, and expenses from the insurance dataset.
2. Train a two-feature model using the Normal Equation.
3. Standardize both features and train the model using Gradient Descent.
4. Convert the Gradient Descent weights back to their original units.
5. Calculate MSE, RMSE, MAE, and R² for both models.
6. Compare the results with the BMI-only baseline.
7. Print a model comparison table and export the results to `reports/assignment_results.csv`.

## 5) Review the Results

After running the script, open:

`reports/assignment_results.csv`

The file contains the model weights and evaluation metrics for all three models.

### Model Comparison

| Model | R² | RMSE |
|---|---:|---:|
| BMI-only Baseline | 0.0394 | 11,864.41 |
| Normal Equation (BMI + Age) | 0.1173 | 11,373.64 |
| Gradient Descent (BMI + Age) | 0.1173 | 11,373.64 |

Adding age improved R² by approximately 0.0778, or 7.78 percentage points.

The Normal Equation and Gradient Descent produced nearly identical weights.

## 6) Read the Written Memo

Open `assignment_memo.md` to review the interpretation of the model results.

The memo discusses:

- The improvement in R² after adding age
- The agreement between Normal Equation and Gradient Descent weights
- The interpretation of the age coefficient
- Whether the two-feature model is suitable for deployment

## Key Concepts Students Should Notice

- The Normal Equation and Gradient Descent should produce nearly identical model weights when Gradient Descent converges.
- Standardizing BMI and age helps improve optimization stability.
- Adding age improves the model's predictive performance compared with using BMI alone.
- A model with low R² may have limited predictive power, even when adding another feature improves its performance.
- Model evaluation should consider prediction errors and business requirements before deployment.

## Troubleshooting

### ModuleNotFoundError: No module named 'numpy'

Make sure your virtual environment is activated and install NumPy:

```bash
python -m pip install numpy
```

### FileNotFoundError: insurance.csv

Make sure the dataset is located at:

`data/insurance-premium-prediction/insurance.csv`

Run the script from the repository's root directory.

### Wrong Python Interpreter in VS Code

Open the Command Palette and select:

Python: Select Interpreter

Choose the Python interpreter from your `.venv` environment.

## License and Data

- Educational use for MSBA 265 coursework.
- Dataset source: Kaggle Insurance Premium Prediction Dataset.

## Author

Nguyen My San

Master of Science in Business Analytics

University of the Pacific
