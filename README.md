# CreditWise Loan System

CreditWise Loan System is a machine-learning project for predicting whether a loan application will be approved. The project is implemented in a Jupyter Notebook using Python, pandas, visualization libraries, and scikit-learn.

The notebook compares three supervised classification algorithms:

- Logistic Regression
- K-Nearest Neighbors (KNN)
- Naive Bayes

> **Note:** This is an educational/data-science project. Its predictions should not be used as the sole basis for real lending decisions.

## Project workflow

1. Load and inspect the loan application dataset.
2. Identify missing values and separate numerical and categorical columns.
3. Impute missing numerical values using the column mean.
4. Impute missing categorical values using the most frequent value.
5. Perform exploratory data analysis using charts and summary statistics.
6. Prepare the data for machine-learning models.
7. Train and compare Logistic Regression, KNN, and Naive Bayes classifiers.
8. Evaluate model performance using accuracy, precision, recall, F1-score, and a confusion matrix.

## Repository contents

| File | Description |
| --- | --- |
| [`CreditWise Loan System.ipynb`](./CreditWise%20Loan%20System.ipynb) | Main notebook containing data preprocessing, exploratory analysis, model training, and evaluation. |

The notebook loads a file named `loan.csv`. Place that file in the repository root before running the notebook, or update the `pd.read_csv("loan.csv")` path in the notebook.

## Dataset

The dataset contains 1,000 records and 20 columns. The expected fields are:

- `Applicant_ID`
- `Applicant_Income`
- `Coapplicant_Income`
- `Employment_Status`
- `Age`
- `Marital_Status`
- `Dependents`
- `Credit_Score`
- `Existing_Loans`
- `DTI_Ratio`
- `Savings`
- `Collateral_Value`
- `Loan_Amount`
- `Loan_Term`
- `Loan_Purpose`
- `Property_Area`
- `Education_Level`
- `Gender`
- `Employer_Category`
- `Loan_Approved` — the target label, generally `Yes` or `No`

The original data contains missing values. The notebook handles them by applying mean imputation to numerical columns and most-frequent-value imputation to categorical columns.

## Machine-learning models

### Logistic Regression

Logistic Regression provides a simple and interpretable baseline for binary loan-approval classification.

### K-Nearest Neighbors (KNN)

KNN predicts an applicant's approval outcome based on the outcomes of similar applicants in the feature space. Feature scaling is important for KNN because it relies on distance calculations.

### Naive Bayes

Naive Bayes is a probabilistic classifier based on Bayes' theorem. It provides a fast baseline and assumes that the input features are conditionally independent given the target class.

## Technology stack

- Python 3
- Jupyter Notebook
- pandas
- NumPy
- seaborn
- Matplotlib
- scikit-learn
  - Logistic Regression
  - K-Nearest Neighbors
  - Naive Bayes
  - train/test splitting
  - missing-value imputation
  - classification metrics

## Getting started

### 1. Clone the repository

```bash
git clone https://github.com/pradeeppateda/Creditwise-loan-system.git
cd Creditwise-loan-system
```

### 2. Create and activate a virtual environment (recommended)

#### macOS/Linux

```bash
python3 -m venv .venv
source .venv/bin/activate
```

#### Windows PowerShell

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

### 3. Install dependencies

```bash
python -m pip install --upgrade pip
pip install jupyter pandas numpy seaborn matplotlib scikit-learn
```

### 4. Add the dataset

Place `loan.csv` in the project root:

```text
Creditwise-loan-system/loan.csv
```

### 5. Run the notebook

```bash
jupyter notebook "CreditWise Loan System.ipynb"
```

Run the notebook cells from top to bottom. You can also launch JupyterLab with:

```bash
jupyter lab
```

## Exploratory data analysis

The notebook examines the distribution of loan approvals and investigates relationships between applicant attributes and approval outcomes, including credit-score patterns. The recorded target distribution is approximately 68.6% `No` and 31.4% `Yes`, so model performance should not be judged by accuracy alone.

## Evaluation metrics

The models are evaluated using:

- Accuracy
- Precision
- Recall
- F1-score
- Confusion matrix

For a lending-related classification problem, precision, recall, class balance, and the business cost of false approvals versus false rejections should be considered together.

## Potential improvements

- Add a reproducible `requirements.txt` or `environment.yml`.
- Use a scikit-learn `Pipeline` and `ColumnTransformer` to prevent preprocessing leakage.
- Apply explicit one-hot encoding to categorical features.
- Scale numerical features before training KNN.
- Exclude identifier fields such as `Applicant_ID` from model training.
- Use a stratified train/test split because the target classes are imbalanced.
- Add cross-validation, ROC-AUC, precision-recall curves, and calibration analysis.
- Compare and tune model hyperparameters, including the number of neighbors for KNN.
- Add fairness and bias checks before considering real-world use.
- Keep sensitive or proprietary applicant data outside the repository.

## License

No license is currently specified for this repository. Add a license file if you want to define how others may use, modify, or distribute this project.
