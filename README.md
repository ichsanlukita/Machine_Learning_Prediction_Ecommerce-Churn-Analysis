# **E-commerce Customer Churn Analysis**
**by: Muhammad Ichsan Lukita**

## **1. Background**
E-commerce businesses need to continuously adapt their strategies to reduce **customer churn**, which directly impacts revenue. Retaining existing customers is more cost-effective than acquiring new ones.

To tackle this issue, **Machine Learning (ML) is used** to predict which customers are likely to churn. This allows businesses to allocate promotional resources effectively, minimizing unnecessary expenses while maximizing customer retention.

## **2. Business Problem**
### **Problem Statement**
- What factors contribute to customer churn?
- How can businesses use predictive analytics to reduce churn and retain customers?

### **Business Goals (Measurable)**
- Reduce **churn rate from 20% to 15% within 6 months**.
- Optimize marketing expenses by **targeting promotions only to at-risk customers**.
- Reduce **unnecessary promotional spending by at least 50%**.

### **Implementation Plan**
- **Who will use the model?** Marketing and customer retention teams.
- **When is the model used?** Every **end of the month** to identify potential churners.
- **How is it implemented?** The model outputs a **list of high-risk customers**, who will receive targeted promotions to retain them.

---

## **3. Data Understanding**
### **Dataset Description**
The dataset includes customer transactional data with the following key features:
- **Tenure** (length of customer relationship)
- **WarehouseToHome** (distance from warehouse to home)
- **NumberOfDeviceRegistered** (number of registered devices)
- **PreferedOrderCat** (preferred order category)
- **SatisfactionScore** (customer satisfaction score)
- **MaritalStatus** (marital status)
- **NumberOfAddress** (number of registered addresses)
- **Complain** (customer complaint history)
- **DaySinceLastOrder** (days since last purchase)
- **CashbackAmount** (total cashback received)
- **Churn** (target variable: whether the customer churned or not)

### **Data Summary**
- **Total records:** 3941
- **Churned Customers:** 107
- **Loyal Customers:** 546
- **Missing Values:** Present in `Tenure`, `WarehouseToHome`, and `DaySinceLastOrder`.
- **Handling Missing Values:** Used **IterativeImputer** and **SimpleImputer**.
- **Duplicate Data:** **672 duplicate rows (17.05%)** were removed.

---

## **4. Machine Learning Approach**
### **Chosen Model: Tuned XGBoost Classifier**
- **Selected as the final model** due to superior Recall performance.
- Compared against **Logistic Regression, Random Forest, Gradient Boosting, AdaBoost, and SVM**.
- **Hyperparameter tuning** was performed using GridSearchCV to improve recall.

### **Evaluation Metrics Selection**
We prioritize **Recall over Precision** because:
- **False Negatives (FN) are more costly than False Positives (FP).**
- Losing a customer costs **$500**, while a wasted promotion costs only **$100**.
- Using **F-beta score (β = 2)** ensures **Recall is given more weight**.

#### **Final Model Performance (Tuned XGBoost)**
| Metric       | Value |
|-------------|-------|
| **Precision (Churner)** | 0.67 |
| **Recall (Churner)** | 0.86 |
| **F1-Score (Churner)** | 0.75 |
| **Accuracy** | 91% |
| **Macro Avg Recall** | 0.89 |
| **Weighted Avg Recall** | 0.91 |

📌 **Key Takeaway:** Prioritizing Recall helps capture more churned customers, reducing customer loss despite a small drop in Precision.

---

## **5. Handling Imbalanced Data**
### **Why Use Both `class_weight='balanced'` and SMOTE?**
- **SMOTE (Synthetic Minority Over-sampling Technique)** generates synthetic samples of churners to balance the dataset.
- **Class weight balancing** ensures the model does not favor the majority class (non-churners).
- **Both were used together** to improve recall while minimizing overfitting.

---

## **6. Model Interpretation: SHAP Analysis**
Using **SHAP (SHapley Additive Explanations)**, we identified the most important factors influencing churn:
1. **DaysSinceLastOrder** → Customers inactive for 9+ months are more likely to churn.
2. **Tenure** → New customers (<3 months) have higher churn rates.
3. **Warehouse Distance** → Customers living **5-15 KM** from the warehouse have higher churn tendencies.

📌 **Business Implication:** These factors should be the **main focus of retention strategies**.

---

## **7. Results & Business Impact**
### **Cost Comparison: Without vs. With ML**
| Scenario  | Cost of False Actions | Total Cost |
|-----------|----------------------|------------|
| **Without ML** (Target all customers) | $81,900 | $97,950 |
| **With ML** (Targeted promotions) | $17,020 | 🔽 **$17,020** (Reduction of **79.21%**) |

**ML successfully reduced unnecessary expenses and minimized churn-related losses.**

---

## **8. Recommendations**
### **For Business Strategy**
✔ **Customers with <3 months tenure** → Offer cashback & discounts to increase engagement.
✔ **Customers with 5-15 KM warehouse distance** → Provide free delivery incentives.
✔ **Customers inactive for 9+ months** → Run re-engagement campaigns.
✔ **Deploy ML model monthly** to continuously improve churn prediction accuracy.

---

## **9. Conclusion**
✅ **ML significantly reduces promotional waste and improves customer retention strategies.**
✅ **F2 Score prioritizing Recall helped minimize costly False Negatives.**
✅ **SHAP insights guide targeted retention efforts, improving decision-making.**
✅ **Future improvements:** Further hyperparameter tuning & real-time integration with CRM.

---

🚀 **This project successfully demonstrates how Machine Learning can be leveraged to minimize churn and optimize marketing costs in e-commerce.** 🎯

