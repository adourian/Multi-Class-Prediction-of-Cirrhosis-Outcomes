# Multi-Class Prediction of Cirrhosis Outcomes

![image](https://github.com/user-attachments/assets/d5b9678f-8cd9-4011-9580-edaaf1ec63cd)
<sub>Figure 1: Cirrhosis liver tissue under microscopic examination.</sub>

This project is based on the Kaggle competition [Cirrhosis Patient Survival Prediction](https://www.kaggle.com/competitions/playground-series-s3e26/overview).

## 🎯 Background and Objective

Cirrhosis is a late stage of scarring (fibrosis) of the liver caused by many forms of liver diseases and conditions, such as hepatitis and chronic alcoholism. Each time the liver is injured, it tries to repair itself. In the process, scar tissue forms. As the cirrhosis progresses, more and more scar tissue forms, making it difficult for the liver to function (decompensated cirrhosis). Advanced cirrhosis is life-threatening.

The objective of this project is to build a predictive model that can accurately classify the outcomes of cirrhosis patients based on a provided set of features.

## 🔧 Tools and Libraries

The project was implemented using Python and the following libraries:

- **Pandas**: For data manipulation and analysis.
- **NumPy**: For numerical computations.
- **Matplotlib and Seaborn**: For data visualization.
- **Scikit-learn**: For machine learning tasks, including data preprocessing, model training, and model evaluation.
- **Gradient Boosting (e.g., XGBoost, LightGBM)**: For building high-performance models through ensemble methods.

## 📚 Dataset

The dataset includes various features related to cirrhosis patients. Each row represents a unique patient, and includes measurements such as Albumin, Bilirubin, Cholesterol, and more. The target variable is "Status," indicating the outcome (C: Censored, CL: Alive due to liver transplant, D: Deceased). The dataset is synthetically generated from a deep learning model trained on the Cirrhosis Patient Survival Prediction dataset.

### Dataset Features

1. **`Drug`**: The specific medication or treatment regimen administered to the patient during the monitoring period.

1. **`Sex`**: Sex of the patient being monitored. 

2. **`Bilirubin`**: A key blood marker indicating liver function; elevated levels may suggest liver dysfunction.

3. **`Cholesterol`**: The level of cholesterol in the blood, a lipid profile marker relevant to cardiovascular and metabolic health.

4. **`Albumin`**: A protein synthesized by the liver; low levels may indicate liver disease and affect overall protein balance

1. **`Alk_Phos`**: The level of alkaline phosphatase.

1. **`Hepatomegaly`**:  Enlargement of the liver, serving as an important clinical indicator of liver health.

1. **`Copper`**: The level of copper present in the urine. High levels can suggest liver damage.

2. **`Spiders`**: The presence of spider angiomas or spider nevi, visible vascular lesions on the skin associated with liver disease.

3. **`Edema`**: The abnormal accumulation of fluid, typically manifested as swelling, and often linked to liver-related complications.

4. **`Tryglicerides`**:  A type of fat present in the blood, influencing metabolic and cardiovascular health.

3. **`Platelets`**: Blood cell fragments, with abnormal levels potentially indicating liver dysfunction..

4. **`Prothrombin`**: A blood clotting factor, with variations affecting the coagulation proces.

3. **`Stage`**: The stage of liver disease, likely determined by specific diagnostic criteria and indicators.

3. **`N_Days`**: The duration in days for which a patient has been monitored, providing a temporal context for the observation.

4. **`Age`**: The age of the patient at the time of observation, contributing to the demographic profile.

3. **`Ascites`**:  Presence or absence of fluid accumulation in the abdominal cavity, a key clinical sign often associated with liver diseases.

4. **`SGOT`** (Serum Glutamic Oxaloacetic Transaminase): An enzyme indicating liver and heart health; elevated levels may suggest liver damage.

4. **`Status`**: The target variable indicating the patient's outcome, classified as censored (C), alive due to liver transplant (CL), or deceased (D).

## 📈 Workflow

The workflow for this project includes the following steps:

1. **Data Loading and Preprocessing**: Load the data and preprocess it for analysis and modeling, including handling missing values, encoding categorical variables, and scaling numerical variables.
2. **Exploratory Data Analysis (EDA)**: Explore the data to gain insights and understand relationships between features and the target variable, `Status`.
3. **Model Training**: Train the predictive model on the preprocessed data.
4. **Model Evaluation**: Evaluate the model's performance using appropriate metrics.

## 🔍 Exploratory Data Analysis (EDA) 

Understanding cirrhosis is crucial for interpreting the dataset. Cirrhosis has various causes, such as hepatitis B and C, and alcohol use disorder. The dataset reflects clinical, demographic, and laboratory variables, requiring careful consideration of complex relationships.

### Categorical Variables vs. Status

- Men are more likely to be deceased than women.
- Patients with conditions like Ascites and Edema have a higher likelihood of being deceased.

### Numerical Variables vs. Status

- Low albumin levels and high copper levels increase the likelihood of status `D` (deceased).
- Patients with a follow-up period under 900 days are less likely to have status `C` (censored).

### Biomedical Variables and Conditions

- The distribution of bilirubin is wider when conditions like Ascites or Spiders are present.
- High copper levels increase the likelihood of status `D`, except when Ascites is present.
  
## 🔧 Feature Engineering

Several features were engineered based on domain knowledge and exploratory data analysis insights, including:

- **Early N_Days**: Patients with N_Days under 900 and Age over 18,750.
- **Low Alb**: Low albumin levels, no Ascites or Edema.
- **Normal_Bili**: Normal bilirubin levels, no Spiders or Ascites.
- **Normal_Cu**: Normal copper levels, no Ascites.
- **Conditions_Count**: Total number of conditions a patient has.

## 🗒️ Predictive Modeling

### Model Selection

The following models were initially tested:

- ❌ RandomForest, AdaBoost, KNN, SVM, ANN
- ✅ XGBoost, LightGBM, CatBoost

### Hyperparameter Optimization

Optuna was used for hyperparameter tuning across multiple cross-validation (CV) folds to ensure robustness.

- **XGBoost**: Average Log Loss across 10 CV folds: 0.42097
- **LightGBM**: Average Log Loss across 10 CV folds: 0.41808
- **CatBoost**: Average Log Loss across 10 CV folds: 0.43562
- **HistGradientBoosting**: Average Log Loss across 10 CV folds: 0.43897

### Ensembling

Simple ensembling was used to combine the strengths of different models, leading to better overall performance.

- **Ensemble Log Loss**: 0.40398

### 📊 Incorporating Other Works

Incorporating predictions from other models can further enhance accuracy. The ensemble was refined using predictions from models in other notebooks, resulting in improved performance.

The final model was trained on the entire training set and used to make predictions on the test set, achieving a private score of 0.39974.


## Conclusion

This project successfully built a predictive model to classify cirrhosis outcomes, leveraging gradient boosting techniques, feature engineering, and ensembling. Future work could involve tailored feature selection for each model and potentially PCA to improve performance further.

**References**:
- [Notebook 1](https://www.kaggle.com/code/omega11/medical-analysis-added-18-features-xgb)
- [Notebook 2](https://www.kaggle.com/code/ashishkumarak/ps3e26-liver-cirrhosis-eda-model)
- [Notebook 3](https://www.kaggle.com/code/satyaprakashshukl/multi-class-prediction-of-cirrhosis-outcomes)
- [Notebook 4](https://www.kaggle.com/code/dreygaen/ps3e25-cirrhosis-multi-class-solution)

