[<img src="https://drive.google.com/file/d/189kmnHG8hXONdJ8hPT0db9_bPSGFfwU8/view?usp=sharing" width="900"/>](https://drive.google.com/file/d/189kmnHG8hXONdJ8hPT0db9_bPSGFfwU8/view?usp=sharing)
# Fraud Detection from Customer Transactions

This project focuses on detecting fraudulent transactions in e-commerce data provided by Vesta Corporation. The goal is to build a robust machine learning model to classify transactions as fraudulent or non-fraudulent accurately.

## Key Challenges
- **Highly Imbalanced Dataset:** The dataset is severely imbalanced, with only a tiny fraction of fraudulent transactions (3% of dataset). This requires special handling to ensure the model does not become biased towards the majority class.
- **High Dimensionality:** The dataset contains **393 features**, many of which are masked or have missing values, adding complexity to the feature engineering process.
- **Temporal Nature:** The data is *time-sensitive*, requiring time-based splits for training and evaluation to avoid data leakage.

## Project Structure
**Data Exploration and Preprocessing**
1. Handling missing values by **imputing** numerical columns with their mean and categorical columns with 'Unknown'.
2. **Feature engineering** to create *time-based* features, *aggregated* features, and *interaction* features.
3. *Standardization* and *dimensionality reduction* using **PCA**.
4. **Hierarchical clustering** to group similar features and reduce redundancy.
                
 
**Feature Selection**
1. **Baseline Model:** A **LightGBM** model is trained as a baseline, with *feature importance* analysis to identify key predictors.
2. **Feature Selection:** **Correlation matrix** analysis and **Lasso regression** are used to select the most relevant features.
3. **Undersampling:** The majority class is undersampled to balance the dataset, preserving the temporal order of transactions.


       
**Modeling and Evaluation**
1. **CatBoost with Optuna:** Hyperparameter tuning is performed using **Optuna** to optimize the **CatBoost** model. 
2. The model is evaluated using **time-based cross-validation** to ensure robustness.
3. The final model is evaluated using **ROC-AUC** and **Precision-Recall AUC** scores.
4. A **confusion matrix** is generated to visualize the model's performance in classifying fraudulent and non-fraudulent transactions.
5. **Feature importance** is analyzed to understand the key drivers of the model's predictions.


## Results
| | Precision | Recall | F1-Score | Support |
| -------- | -------- | ------- | ------- | ------- |
| 0 | 0.95 | 1.00 | 0.97 | 37254 |
| 1 | 0.93 | 0.51 | 0.66 | 4072 |
| Accuracy |  | | 0.95 | 41326 |
| Macro Avg. | 0.94 |0.75 | 0.82 | 41326 |
| Weighted Avg. | 0.95 | 0.95 | 0.94 | 41326 |


- The final CatBoost model achieved an **ROC-AUC** score of **0.935** on the test set, indicating strong performance distinguishing between fraudulent and non-fraudulent transactions.

## Key Takeaways
- **Handling Imbalanced Data:** Undersampling the majority class helped improve the model's ability to detect fraudulent transactions without introducing significant bias.
- **Feature Engineering:** Time-based interaction features were crucial in improving model performance.
- **Hyperparameter Tuning:** Optuna was instrumental in finding the optimal hyperparameters for the CatBoost model, leading to improved performance.

## 👩‍💻 Author
📌 Developed by Sevilay Munire Girgin   
📧 [Contact Me](https://linktr.ee/sevilaymgirgin)   
🌐 [Portfolio](sevilaymuni.github.io/Girgin)
