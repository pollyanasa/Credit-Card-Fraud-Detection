# Credit Card Fraud Detection

This project focuses on detecting fraudulent credit card transactions using machine learning. The dataset is highly imbalanced, with fraudulent transactions representing less than 0.2% of all records.

## Project Highlights

* **Dataset**: [SecurePay Credit Card Fraud Detection Data (Kaggle)](https://www.kaggle.com/datasets/eshummalik/securepay-credit-card-fraud-detection-data)
* **Goal**: Build models that can effectively detect fraud while minimizing false positives.
* **Challenge**: Strong class imbalance → only a small fraction of transactions are fraud.

## Approach

1. **Data Exploration & Preprocessing**

   * Checked missing values and data distributions.
   * Engineered features such as `log_Amount` and `Hour`.

2. **Handling Class Imbalance**

   * Tested **SMOTE**, but it led to overfitting.
   * Instead, used **tree-based models’ built-in imbalance handling**:

     * `class_weight="balanced"` for Random Forest, Extra Trees, and LightGBM.
     * `scale_pos_weight` for XGBoost.

3. **Models Trained**

   * Random Forest
   * Extra Trees
   * XGBoost
   * LightGBM

4. **Evaluation Metrics**

   * F1 Score → balances fraud detection (recall) and false alarms (precision).
   * ROC-AUC → measures ranking ability.
   * PR-AUC → more informative in imbalanced datasets.
   * Cross-validation used to reduce overfitting risk.

5. **Results (Cross-Validation)**

   * LightGBM achieved the best balance across F1, ROC-AUC, and PR-AUC.
   * Extra Trees was a strong competitor.
   * Random Forest performed worst among the four.

## Key Insights

* SMOTE oversampling caused overfitting, while tree models handled imbalance better with class weights.
* F1 and PR-AUC are more reliable than accuracy in fraud detection.
* Threshold tuning is crucial: lowering the probability cutoff improves recall at the cost of precision.

---

Do you also want me to write a **short summary (2–3 sentences)** for the GitHub repository description box?
