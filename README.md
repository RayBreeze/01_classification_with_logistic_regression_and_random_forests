# Comparative Analysis of Classification Models: Logistic Regression vs. Random Forest

**Author:** Samman Das (Section I Intern)

**Organization:** IDEAS - Institute of Data Engineering, Analytics and Science Foundation

**Project for:** Autumn Internship Program 2025

## 1. Project Overview

This project provides a hands-on comparison between two fundamental classification algorithms: **Logistic Regression** and **Random Forest**. The primary goal is to demonstrate how the performance of these models is heavily influenced by the underlying complexity and structure of the dataset.

To achieve this, the models were evaluated on three distinct datasets:

1. The classic, linearly separable **Iris Flower Dataset**.

2. The complex, real-world **Oxford Parkinson's Disease Dataset**.

3. An **AI-generated Synthetic Parkinson's Dataset** from [SynGenData.ai](https://www.syngendata.ai) to explore model performance on artificially generated data.

The analysis involves data visualization, model training, performance evaluation, and hyperparameter tuning to draw clear conclusions about which model is better suited for different types of classification problems.

## 2. Datasets Used

### a. Iris Flower Dataset

* **Description:** A simple, multivariate dataset containing 150 samples of Iris flowers from three species (Setosa, Versicolor, Virginica).

* **Features:** Sepal Length, Sepal Width, Petal Length, Petal Width (in cm).

* **Key Characteristic:** The classes are largely **linearly separable**, making it an ideal test case for simple linear models.

### b. Oxford Parkinson's Disease Dataset

* **Source:** [UCI Machine Learning Repository](http://archive.ics.uci.edu/dataset/174/parkinsons)

* **Description:** A complex dataset featuring biomedical voice measurements from 195 individuals, used to distinguish healthy people from those with Parkinson's disease.

* **Features:** 22 voice-based features like `MDVP:Fo(Hz)`, `jitter`, `shimmer`, `HNR`, etc.

* **Key Characteristic:** The data exhibits high **multicollinearity** and **non-linear patterns**, representing a more challenging, real-world classification problem.

### c. Synthetic Parkinson's Dataset

* **Source:** Generated via [SynGenData.ai](https://www.syngendata.ai)

* **Description:** An AI-generated dataset mirroring the statistical properties of the original Parkinson's dataset. Used to validate model performance and explore the utility of synthetic data in machine learning.

## 3. Methodology

The analysis for each dataset followed these steps:

1. **Data Loading and Exploration:** The data was loaded and inspected.

2. **Exploratory Data Analysis (EDA):** Visualizations like **pairplots** (for Iris) and **correlation heatmaps** were used to understand feature relationships and data separability.

3. **Data Splitting:** The data was split into training (70%) and testing (30%) sets.

4. **Model Training:** Both Logistic Regression and Random Forest models were trained on the training data.

5. **Performance Evaluation:** Models were evaluated on the test set using:

   * **Accuracy Score**

   * **Classification Report** (Precision, Recall, F1-Score)

   * **Confusion Matrix**

6. **Hyperparameter Tuning:** The `n_estimators` (number of trees) for the Random Forest model was increased from 100 to 500 to observe its effect on performance.

## 4. Key Findings & Results

The project clearly demonstrates the "No Free Lunch" theorem: the best model is dependent on the dataset.

### Analysis on the Iris Dataset (Simple, Linear Data)

* **Logistic Regression Accuracy:** **93.3%**

* **Random Forest Accuracy:** **91.1%**

* **Conclusion:** The simpler **Logistic Regression** model outperformed the more complex Random Forest. Its assumption of a linear decision boundary was a perfect match for this linearly separable dataset.

| Model | Accuracy | Key Insight | 
| ----- | ----- | ----- | 
| **Logistic Regression** | **`93.3%`** | **Winner:** Excels on simple, linearly separable data. | 
| Random Forest | `91.1%` | Overkill for this dataset; complexity not needed. | 

### Analysis on the Parkinson's Dataset (Complex, Non-Linear Data)

* **Logistic Regression Accuracy:** **83.0%**

* **Random Forest Accuracy:** **93.2%**

* **Conclusion:** The **Random Forest** model was significantly better. It successfully captured the complex, non-linear relationships and handled the high correlation between features, which the linear model struggled with. Increasing `n_estimators` did not significantly change the result, indicating the model had converged.

| Model | Accuracy | Key Insight | 
| ----- | ----- | ----- | 
| Logistic Regression | `83.0%` | Struggles with non-linear patterns and correlated features. | 
| **Random Forest** | **`93.2%`** | **Winner:** Robustly handles complex, real-world data. | 

### Analysis on the Synthetic Parkinson's Dataset

The results on the synthetic data were consistent with the original dataset, further validating our conclusions.

* **Logistic Regression Accuracy:** `81.4%`

* **Random Forest Accuracy:** `93.2%`

* **Conclusion:** The Random Forest model remained superior, demonstrating that high-quality synthetic data can be effectively used to replicate and validate machine learning experiments.

## 5. How to Run This Project

### Prerequisites

Ensure you have Python 3 and the following libraries installed:

```
pip install numpy pandas matplotlib seaborn scikit-learn ucimlrepo
```

### Instructions

1. Clone this repository to your local machine:

```
git clone https://github.com/your-username/01_classification_with_logistic_regression_and_random_forests.git
```

3. The project is contained within a Jupyter Notebook (`.ipynb` file). Open it using Jupyter Notebook or JupyterLab to view and run the code cells sequentially.

This project effectively illustrates the critical importance of understanding your data's characteristics before selecting a machine learning model.

2. Navigate to the project directory:

```
cd 01_classification_with_logistic_regression_and_random_forests
```
