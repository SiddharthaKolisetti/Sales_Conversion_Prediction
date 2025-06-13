# Classification_Models_on_Sales_Conversion_Dataset

A study on how different classification models performed on a sales conversion dataset containing user behavioral and session data to determine whether an online session results in a purchase.

## Objective

The objective of this repository is to compare the performance of various popular classification models on a sales conversion dataset. The dataset includes features such as user engagement metrics, page visit patterns, session duration, traffic source, and user type. The goal is to evaluate how well different models can predict whether a visitor will make a purchase (`Revenue` = True), using key performance metrics: Accuracy, Precision, Recall, and F1-Score. This comparison helps in identifying suitable models for real-world e-commerce conversion prediction and optimization tasks.

## Dataset

The dataset used in this project is a structured tabular dataset containing information about user sessions on an e-commerce website. Each row represents a session with behavioral and technical attributes, as well as whether it ended in a transaction.

- **Source:** [Online Shoppers Purchasing Intention Dataset – UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/468/online+shoppers+purchasing+intention+dataset)
- **Total Records:** 12,330  
- **Target Variable:** `Revenue` (True if a purchase occurred, otherwise False)  
- **Features include:**  
  - Numerical: `Administrative`, `Informational`, `ProductRelated`, `PageValues`, `BounceRates`, `ExitRates`, `SpecialDay`  
  - Categorical: `Month`, `VisitorType`, `Weekend`  
  - Technical: `OperatingSystems`, `Browser`, `Region`, `TrafficType`

## Classification Models Overview

**1. Logistic Regression**  
A linear model well-suited for binary classification. Serves as a baseline due to its simplicity and interpretability.

**2. Kernel Support Vector Machine (Kernel SVM)**  
Uses kernel trick to manage non-linear data. Known for high accuracy but can be slow with large datasets.

**3. K-Nearest Neighbors (KNN)**  
A distance-based algorithm that relies on the class of neighboring data points. Sensitive to feature scaling and high dimensionality.

**4. Naive Bayes**  
A probabilistic classifier assuming feature independence. Extremely fast and effective in many practical scenarios.

**5. Decision Tree**  
A rule-based model that splits data on feature values. Offers interpretability and captures non-linear relations.

**6. Random Forest**  
An ensemble method using multiple decision trees. Offers robust performance, reduces overfitting, and handles imbalanced data well.

## Model Performance Comparison

| Model               | Accuracy | Precision | Recall | F1-Score |
|---------------------|----------|-----------|--------|----------|
| Logistic Regression | 0.87     | 0.86      | 0.87   | 0.85     |
| Kernel SVM          | 0.88     | 0.87      | 0.88   | 0.87     |
| KNN                 | 0.87     | 0.86      | 0.87   | 0.85     |
| Naive Bayes         | 0.79     | 0.84      | 0.79   | 0.81     |
| Decision Tree       | 0.89     | 0.88      | 0.89   | 0.88     |
| Random Forest       | 0.89     | 0.88      | 0.89   | 0.88     |


## Key Insights

- **Logistic Regression:** This model delivered solid performance with 87% accuracy and an F1-score of 0.85. Its high precision and recall indicate it handles both positive and negative classes well. Due to its simplicity and interpretability, it serves as an excellent baseline for binary classification tasks, especially when transparency is important in business decision-making.
- **Kernel SVM:** Kernel SVM slightly outperformed Logistic Regression with 88% accuracy and a balanced F1-score of 0.87. It effectively captures complex patterns in the data due to the kernel trick. While more computationally intensive, it's well-suited for datasets where relationships between features are not linearly separable.
- **KNN:** KNN achieved comparable results to Logistic Regression with an accuracy of 87% and an F1-score of 0.85. It is a simple yet effective non-parametric method, but its performance may degrade with large datasets or high-dimensional data unless optimized with techniques like dimensionality reduction and scaling.
- **Naive Bayes:** Naive Bayes had the lowest accuracy at 79%, but surprisingly maintained a high precision of 0.84 and a decent F1-score of 0.81. This suggests it was conservative in predicting the positive class, possibly misclassifying many actual positives. It's extremely fast and scalable but may underperform when feature independence is a poor assumption.
- **Decision Tree:** This model tied for the highest performance with 89% accuracy and an F1-score of 0.88. It effectively captured non-linear interactions in the dataset and offered interpretability through its tree structure. However, decision trees are prone to overfitting if not properly tuned or pruned.
- **Random Forest:** Matching the Decision Tree’s performance, Random Forest also achieved 89% accuracy and an F1-score of 0.88. It reduced overfitting through ensemble learning and delivered stable, consistent results across metrics. This robustness and scalability make it a strong candidate for production use.

## Conclusion

Among the models tested, Decision Tree and Random Forest achieved the highest performance, each with 89% accuracy and an F1-score of 0.88, making them strong choices for predicting sales conversions. Kernel SVM also performed well, offering a good balance of precision and recall. Logistic Regression and KNN delivered reliable baseline results with solid accuracy and interpretability. While Naive Bayes lagged in accuracy, its speed and decent F1-score make it suitable for real-time or resource-constrained applications. Overall, Random Forest stands out as the most robust and production-ready model, while simpler models like Logistic Regression are still valuable for transparent and quick decision-making.
