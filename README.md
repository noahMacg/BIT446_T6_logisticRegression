# Coffee Shop Purchasing Association Analysis
**Data Mining Foundations assignment evaluating logistic regression classification in
R**

## Overview 
Built a logistic regression classifier to predict simultaneous purchasing of
coffee/donut with 95% accuracy and 94% precision by analyzing 550 customer transactions
to find factors influencing purchase behavior.  

**Feature Variables**
- Customer age
- Estimated months as a customer
- Estimated annual salary 


### Technical Stack
Environment: R, VS Code, Ubuntu  
Libraries: readxl, caret, ggplot2, metrica, car, caTools 

### Technical Approach 
**Import and Data Processing**
- Imported three data sheets from Excel into separate data frames: training/testing
  data, new prediction data, and column information.
- Target variable "LatteDonut" converted to a factor type. 
- Applied stratified random sampling for 80/20 train-test split with reproducible seed

**Logistic Regression Model Training**  
- *Features*: Age, EstMonthsCustomer, EstSalary
- *Target*: LatteDonut (binary classification)
- *Family*: Binomial distribution 

**Multicollinearity Analysis and Feature Selection**
- Trained separate LR models with different feature combinations
- Analyzed multicollinearity through correlation matrices, variance inflation factors (VIF), and correlation matrix determinants. 
- After evaluating the correlation of features, validated models of 1,2,3 features and
  evaluated their metrics. 
- Balance between minimizing feature corelation and performance was found using 2
  variables (age/estsalary). 

**Final Model Equation:** P(LatteDonut = 1) = e^(-14.44 + 0.07032×Age +
0.0001646×EstSalary) / (1 + e^(-14.44 + 0.07032×Age + 0.0001646×EstSalary))

### Results 
**Multicollinearity:** Although VIF scores appeared acceptable, correlation matrix and
it's determinant revealed strong correlation, demonstrating VIF is not always reliable. 

**Corelation Matrix**(all vars)

                        Age EstMonthsCustomer EstSalary
Age               1.0000000         0.8194954 0.9229264
EstMonthsCustomer 0.8194954         1.0000000 0.8865444
EstSalary         0.9229264         0.8865444 1.0000000

**VIF**(all vars)

Age          EstMonthsCustomer      EstSalary 
1.152303          1.003551          1.149028

**Determinant of Matrix**(all vars): 0.0317204

**Feature Importance**
Estimated Salary: Variable importance 5.15 with statistical significance alpha =
2.63e-07
Age: Variable importance 2.05 with statistical significance alpha = 0.04. 

**Odds Ratio:**For simultaneous coffee/donut purchase, we can expect:
- $10K salary --> 5.2 times more likely to purchase 
- 5 years of age --> 1.42 times more likely to purchase 

**Model Performance Metrics**
- Accuracy: 95.45% of predictions correct
- Precision: 93.75% of dual purchases caught
- Recall:  100% of dual purchases predicted were correct
- F-score of 96.77% measuring combined precision and recall

### Business Insight
This model demonstrates strong predict power for simultaneous donut/coffee purchases
with 95% accuracy. 
- Estimated salary was the most predictive feature with highes statistical significance. 
- Age appeared to have some influence with statistical significance alpha = 0.04. 
- Customer tenure appears to be highly correlated with other features. 

**Recommendations** The coffee shop can investigate and use these insights towards
marketing to the the customers in the lower feature importance (age/length) to increase
dual purchase sales. 

### Technical Challenges Learned
- Multicollinearity detection 
- Feature engineering 
- Multiple model validations 
- Business translations 

