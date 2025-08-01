# Customer Churn Prediction Project

**Project Status:** Completed | **Date:** August 2025

## 1. Objective

The primary goal of this project is to build a binary classification model to predict whether a customer will churn (cancel their service) from a telecommunications provider. By identifying customers at high risk of churning, the company can proactively offer incentives and improve retention rates.

---

## 2. Dataset

This project uses the **Telco Customer Churn** dataset, a popular public dataset for classification tasks. It contains customer account information, demographic data, and the services each customer has signed up for.

-   **Source:** IBM Sample Datasets
-   **Target Variable:** `Churn` ('Yes' or 'No')
-   **Features:** Include customer tenure, contract type, monthly charges, payment methods, and various service subscriptions.

---

## 3. Project Workflow

The project followed a standard machine learning workflow, broken down into four key steps:

1.  **Data Acquisition & Initial Exploration:** Loaded the dataset and performed an initial analysis of its structure, data types, and basic statistics.
2.  **Exploratory Data Analysis (EDA):** Used visualizations (histograms, count plots) to uncover patterns and relationships between features and customer churn. Key insights included that customers with shorter tenure, month-to-month contracts, and higher monthly charges were more likely to churn.
3.  **Data Preprocessing & Feature Engineering:** Cleaned the data by handling missing values, encoding categorical features into a numerical format using one-hot encoding, and scaling numerical features to a standard range.
4.  **Model Training & Evaluation:** Trained and evaluated two classification models. The data was split into training (80%) and testing (20%) sets to ensure an unbiased evaluation of model performance on unseen data.

---

## 4. Models & Evaluation

Two models were trained and compared:

| Model | Accuracy | Churn F1-Score | Churn Recall |
| :--- | :---: | :---: | :---: |
| **Logistic Regression** | **80.6%** | **0.60** | **0.56** |
| Random Forest | 78.6% | 0.55 | 0.49 |

### Key Findings:
-   The **Logistic Regression** model performed slightly better overall, achieving a higher F1-score and recall for the "Churn" class. This suggests that the relationships in the data are fairly linear and a simpler model is sufficient.
-   **Statistical analysis** of the Logistic Regression model identified the most significant predictors of churn.
-   **Top Predictors of Churn:**
    -   `Contract_Month-to-month`
    -   `InternetService_Fiber optic`
    -   `tenure` (negative correlation)

---

## 5. How to Run This Project

1.  **Clone the repository:**
    ```bash
    git clone <your-repository-url>
    cd your-churn-project
    ```

2.  **Create and activate a virtual environment:**
    ```bash
    python -m venv .venv
    source .venv/bin/activate  # On Windows, use `.venv\Scripts\activate`
    ```

3.  **Install the required libraries:**
    ```bash
    pip install -r requirements.txt
    ```

4.  **Run the Jupyter Notebook:**
    Open the `notebooks/01_eda.ipynb` file in a Jupyter environment (like VS Code) to see the full analysis from start to finish.

---

## 6. Libraries Used

-   `pandas`
-   `scikit-learn`
-   `matplotlib`
-   `seaborn`
-   `statsmodels`
-   `shap`