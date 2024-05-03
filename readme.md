### Final group exercise
---
**Introduction to Machine Learning**

**Request:** (MLP -> Final)
Description Banking.csv
- Apply all knowledge and techniques that you have learned for this
- You must organize your notebook based on the Homework
- Should not drop Na, drop missing
- Models: compare all models that you have learned or practiced
- Can use pytorch & tensorflow
- Automl (should not use)

Deadline:
- 3-4 weeks - (2023-07-04)

**Content**
1. Read and understand churn_rate_prediction.csv data
     Customer demographic data:
Borrower information.
- Loan_ID: ID code.
- Loan_Amount_Requested: Bank loan amount.
- Length_Employed: Working time in years.
- Home_Owner: Home ownership status.
- Annual_Income: Annual income.
- Income_Verified: Verify income.
- Purpose_Of_Loan: Purpose of using the loan.
- Debt_To_Income: Ratio of debt to income.
- Inquiries_Last_6Mo: Number of loan inquiries in the last 6 months.
- Months_Since_Deliquency: Number of months since the most recent debt violation.
- Number_Open_Accounts: Number of open accounts.
- Total_Accounts: Total number of credit accounts.
Gender: Gender.
Interest_Rate: Interest rate of the loan.

![Alt text](image/image.png)

2. Data Exploration

- Handling malformed data: \
- Handle values such as 'years','None',... to convert to NaN.
- Process data type 'str,object' into numeric format such as int, float.
- The value -1 appears during the process of converting discrete data to int type. Change these -1 values to NaN.
2. Handle empty data.
Handle NaN with estimation technique using the IterativeImputer model.
3. Select features Apply lightgbm to find important features 4. Remove outliers values.
The z_score method aims to eliminate continuous values.
IsolationForest method 5. Distributed processing.
Features with continuous values have a left-skewed distribution.
It is necessary to process the values to reach the closest normal distribution using the boxcox transform method.

     a. Export heatmap information

    ![Alt text](image/image-1.png)

     b. Data Preprocessing

       - Handling missing values

     ![Alt text](image/image-2.png)

     c. Select features using the lightgbm method

     ![Alt text](image/image-3.png)

         - Statistical graphs
     ![Alt text](image/image-4.png)

         - Handling outliers
     ![Alt text](image/image-5.png)

     - With the IsolationForest method

     ![Alt text](image/image-6.png)

     - Check distribution

     ![Alt text](image/image-7.png)

     d. Intuitive with Power Bi

![Alt text](image/image-8.png)

3. Build the model

- Build models including logistic regression, Naive Bayes, Decision trees, Random Forest, CatBoost, XGBoost, MLP

- Best model: XGBoost

     a. For training set

     ![Alt text](image/image-10.png)

     b. For test set

     ![Alt text](image/image-9.png)

- Found that the prediction values in both train and test sets are quite similar

- Tested with Dataset without relying on lightgbm

     a. For the training set of SVM

     ![Alt text](image/image-12.png)
  
     b. For the test set of SVM
    
     ![Alt text](image/image-11.png)
  
- Better prediction model

- Keep features that provide additional information. This improves recall and accuracy for the models
  
4. Evaluate the model

     - Use Smote to handle class imbalance in target Interest_Rate.
     - Through recall, the imbalance issue has been improved.

     - Models such as RandomForest, Logistic, DecisionTree, NaiveBayes are all Underfitting with accuracy as low as 50%. High imbalance even though using SMOTE.
     - Although NaiveBayes has a low value, the values in recall are nearly equal. This shows that NaiveBayes handles data imbalance relatively well.

5. Conclusion
     - The data processing process has limited information loss as much as possible.
     - Process data sets with near standard distribution
     - Haven't tested, evaluated and compared techniques such as PCA, Polynomial transform, Grid SearchCV,...
     - For the SVM model, the implementation cost is large so there are no test results yet.
