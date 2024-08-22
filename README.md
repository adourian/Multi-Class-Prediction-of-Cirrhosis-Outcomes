# Multi-Class Prediction of Cirrhosis Outcomes

![image](https://github.com/user-attachments/assets/d5b9678f-8cd9-4011-9580-edaaf1ec63cd)
<sub>Figure 1: Cirrhosis liver tissue under microscopic examination.</sub>


## Overview

This repository contains my solution to the **[Multi-Class Prediction of Cirrhosis Outcomes](https://www.kaggle.com/competitions/playground-series-s3e26)** competition on Kaggle. The goal of the competition was to predict outcomes for patients with cirrhosis using multi-class classification techniques. The challenge involved working with clinical data and developing models that could accurately categorize patients based on their disease outcomes.

## Project Structure

- `data/`: Contains the datasets used for training and testing the models.
- `s3e26-cirrhosis-outcome-prediction.ipynb`: Jupyter notebook containing the exploratory data analysis, feature engineering, model development, and evaluation.
- `requirements.txt`: A list of dependencies required to run the project.
- `README.md`: Overview of the project.

## Key Components

### 1. Problem Statement

The task was to develop a multi-class classification model to predict cirrhosis outcomes based on various patient features. The dataset provided included multiple clinical variables, and the challenge was to build a robust model that could generalize well on unseen data.

### 2. Data

The dataset consisted of anonymized clinical data of patients, including features such as age, gender, bilirubin levels, and more. The target variable was a categorical variable indicating the cirrhosis outcome. Data preprocessing steps included handling missing values, feature scaling, and encoding categorical variables.

### 3. Approach

The approach to solving this problem involved several steps:

- **Exploratory Data Analysis (EDA)**: Understanding the data distribution, feature importance, and relationships between variables.
- **Feature Engineering**: Creating new features that could potentially improve model performance.
- **Model Development**: Several models were trained and evaluated, including Logistic Regression, Random Forest, Gradient Boosting Machines, and Neural Networks.
- **Hyperparameter Tuning**: Models were fine-tuned using techniques like GridSearchCV and RandomizedSearchCV to optimize performance.
- **Model Evaluation**: The performance of the models was evaluated using metrics such as accuracy, F1 score, and ROC-AUC.

### 4. Results

The final model achieved a competitive performance on the leaderboard, demonstrating strong predictive power in classifying cirrhosis outcomes. The notebook contains detailed performance metrics and visualizations that highlight the model's strengths and weaknesses.

### 5. Conclusion

This project showcases my ability to handle clinical data, perform in-depth analysis, and build machine learning models for multi-class classification tasks. The final solution is a result of careful data preparation, model selection, and optimization.

## How to Use This Repository

1. **Clone the repository**:
    ```bash
    git clone https://github.com/yourusername/cirrhosis-outcome-prediction.git
    ```
   
2. **Install the required packages**:
    ```bash
    pip install -r requirements.txt
    ```

3. **Run the notebooks**:
    Open the Jupyter notebooks in the `notebooks` directory to explore the data analysis, model training, and evaluation steps.

4. **(Optional) Run the scripts**:
    Execute the scripts in the `scripts` directory (if available) to reproduce the data preprocessing, model training, or evaluation processes.

## Acknowledgements

- [Kaggle](https://www.kaggle.com) for hosting the competition and providing the dataset.
- My fellow Kaggle competitors for their insights and discussions.

## Contact

For any questions or collaborations, please reach out via [LinkedIn](your-linkedin-profile) or [Email](mailto:your.email@example.com).

