# Methodology: Biological Species Classification (Iris)

## 1. Refined Research Question
Can continuous physical dimensions (sepal and petal lengths/widths) accurately determine if an observed flower is the *Iris-Virginica* species using highly interpretable models?

## 2. Dataset Description
*   **Features:** Sepal length (cm), sepal width (cm), petal length (cm), and petal width (cm).
*   **Target:** `Is_Virginica` (Binary: 1 if Iris-Virginica, 0 if any other species).
*   **Size:** 150 entries (50 Virginica, 100 non-Virginica).
*   **Limitations:** The dataset is very small (150 rows), making complex models prone to variance and overfitting.

## 3. Data Cleaning Plan
*   **Missing Values:** The native Iris dataset contains no missing fields, maintaining absolute structural integrity out-of-the-box.
*   **Outliers:** Inspect features for extreme measurement errors and use robust data scaling rather than deleting records.
*   **Consistency:** Extract data natively as a Pandas DataFrame with structured feature naming columns.

## 4. Feature Engineering Plan
*   **Categorical Encoding:** Not required, as all baseline inputs are purely continuous physical dimensions.
*   **Scaling:** Apply `StandardScaler` to ensure all measurements have a mean of 0 and variance of 1, allowing stable convergence for Logistic Regression.
*   **New Features:** Construct a custom biological dimension, `Petal_Ratio` (`petal length / petal width`), to capture the geometric shape proportion of the flower's petals.

## 5. Model Selection
*   **Model 1: Logistic Regression:** Chosen for its clean coefficient outputs, acting as a reliable linear classifier baseline.
*   **Model 2: Decision Tree Classifier:** Chosen to generate intuitive, flowchart-like classification rules based on specific boundary thresholds.

## 6. Evaluation Metrics
*   **Primary Metric: F1-Score:** Selected to maintain a balanced measure of performance between Precision and Recall.
*   **Secondary Metric: Recall & ROC-AUC:** Recall ensures we catch as many target species as possible, while ROC-AUC tracks overall separation performance across all confidence levels.
