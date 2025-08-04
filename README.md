# Coffee Shop Purchasing Association Analysis
**Data Mining Foundations assignment evaluating logistic regression classification in
R**

## Overview 
Built a logistic regression classifier to predict simultaneous purchasing of
coffee/donut with 95% accuracy and 94% precision by analyzing 550 customer transactions
to find factors influencing the purchase behavior.  

**Feature Variables**
- Customer age
- Estimated months they have been a customer
- Estimated annual salary in dollar 


### Technical Stack
Environment: R, VS Code, Ubuntu  
Libraries:  

### Technical Approach 
**Import and Data Processing**
- Three data sheets in one file imported into their own data frame: One sheet includes 
  training/testing; one includes new data for predictions; and one that includes column 
  information.
- Target variable "LatteDonut" converted to a factor. 
- Seed was set for reproducibility; testing/training data was split using random stratified approach 
- 80% for training and 20% for testing.

**Logistic Regression Model Training**  
- *Features*: Age, EstMonthsCustomer, and EstSalary
- *Target*: LatteDonut
- *Family*: Binomial 

**Exploration of Different Models**
- Trained separate LR models with different feature variables combinations
- Analyzed multicollinearity through corelation matrices, variance inflation factors,
  and the determinant of the correlation matrices. 
- Found that although VIF did not find correlation, the matrix and determinant of the 
  matrix did find correlation and VIF is sometimes not a good indicator. 
- After evaluating the correlation of features, validated models of 1,2,3 features and
  evaluated their metrics. 
- Balance between minimizing feature corelation and performance was found using 2
  variables (age/estsalary). 

**Logistic Regression Equation:** P(LatteDonut = 1) = e^(-14.44 + 0.07032×Age +
0.0001646×EstSalary) / (1 + e^(-14.44 + 0.07032×Age + 0.0001646×EstSalary))

### Results 
***Multicollinearity***

***Feature Importance***
Estimated Salary: Variable importance 5.15 with statistical significance alpha =
2.63e-07
Age: Variable importance 2.05 with statistical significance alpha = 0.04. 

***Odds Ratio***
In relation to buying coffee/donut simultaneously, we can expect:
- Increase in $10K salary to correlate to about 5.2 times more likely
- 5 years of age increase to correlate to about 1.42 times more likely 

***Metrics***
- High accuracy - 95.45% of predictions correct
- High precision - 93.75% of dual purchases caught
- Excellent recall - 100% of dual purchases predicted were correct
- Excellent F-score of 96.77% measuring combined precision and recall


