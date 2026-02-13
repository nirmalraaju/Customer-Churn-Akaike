Customer Churn Prediction Analysis
This project aims to predict customer churn for a banking institution using various machine learning techniques and provide actionable insights for customer retention.

1. Approach
Our approach involved several key steps:

Data Loading & Initial Exploration: Loaded the Churn_Modelling.csv dataset and performed initial checks.
Data Preprocessing:
Dropped irrelevant columns (RowNumber, CustomerId, Surname).
Converted categorical features (Gender, Geography) into numerical representations.
Feature Engineering:
Created BalanceSalaryRatio by dividing Balance by EstimatedSalary to capture a new dimension of customer financial behavior.
Grouped Age into categorical AgeGroup bins (Young Adult, Adult, Middle-Aged, Senior, Elder).
Class Imbalance Analysis: Examined the distribution of the target variable (Exited) to identify class imbalance.
Model Building:
Split the dataset into training (80%) and testing (20%) sets.
Applied StandardScaler to numerical features for normalization.
Trained two classification models:
Logistic Regression
Random Forest Classifier
Model Evaluation:
Calculated and compared the accuracy scores of both models.
Analyzed feature importance for the Random Forest model.
Generated a confusion matrix for the Random Forest model to understand its classification performance.
2. Findings
Data Insights:
Class Imbalance: The dataset showed an imbalance, with approximately 79.63% of customers not churning (class 0) and 20.37% churning (class 1).
Average Balance per Product:
Customers with 1 product had the highest average balance (98551.87).
Customers with 2 products had the lowest average balance (51879.15).
Customers with 3 or 4 products also had significant average balances (75458.33 and 93733.14 respectively).
Average Balance per Age Group:
'Senior' customers had the highest average balance (83632.94).
'Young Adult' customers had the lowest average balance (73698.72).
Model Performance:
Logistic Regression Model: Achieved an accuracy of approximately 0.825 (82.5%).
Random Forest Model: Achieved a higher accuracy of approximately 0.864 (86.4%).
Confusion Matrix (Random Forest):
True Negatives: 1543 (Correctly predicted non-churn)
False Positives: 50 (Incorrectly predicted churn)
False Negatives: 222 (Incorrectly predicted non-churn, but they churned)
True Positives: 185 (Correctly predicted churn)
Key Factors Driving Churn (Random Forest Feature Importance):
According to the Random Forest model, the most influential factors contributing to customer churn are (in descending order of importance):

Age: The most significant predictor of churn.
Estimated Salary: A strong indicator of churn likelihood.
CreditScore: Lower scores often correlate with higher churn risk.
Balance: The amount of money in a customer's account.
NumOfProducts: The number of banking products held by a customer.
3. Business Recommendations
Based on these findings, here are actionable recommendations for customer retention:

Targeted Retention Programs for Age Groups: Since 'Age' is the strongest predictor, develop specific retention strategies for different age segments, particularly focusing on older customers who seem to be at higher risk of churn.
Financial Health Support: Customers with lower credit scores or estimated salaries show higher churn propensity. Offer financial advisory services, personalized loan/investment options, or educational content to improve their financial health and loyalty.
Product Engagement Enhancement:
Investigate why customers with 2 products have the lowest average balance; this could indicate dissatisfaction or a lack of suitable offerings.
Develop strategies to encourage engagement with additional products for customers holding fewer products, or ensure satisfaction for those with many.
Proactive Intervention on False Negatives: The model missed 222 actual churners (False Negatives). Implement strategies to identify customers exhibiting behaviors similar to these false negatives. This could involve real-time monitoring or more nuanced segmentation to intervene before they churn.
Personalized Offers: Leverage insights from Balance, EstimatedSalary, and CreditScore to craft personalized retention offers, such as exclusive benefits for high-value customers or tailored solutions for those showing signs of financial stress.
Continuous Model Improvement: Explore advanced techniques (e.g., SMOTE for class imbalance, more complex models, hyperparameter tuning) to reduce False Negatives and improve the model's predictive power further
