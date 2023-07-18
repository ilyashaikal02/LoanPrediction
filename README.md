# LoanPrediction
Develop a robust classification model that accurately predicts potential loan defaulters and provide the bank with insightful recommendations regarding crucial factors to consider during the loan approval process

Data Description
The Home Equity dataset (HMEQ) contains baseline and loan performance information for 5,960 recent home equity loans. The target (BAD) is a binary variable that indicates whether an applicant has ultimately defaulted or has been severely delinquent. This adverse outcome occurred in 1,189 cases (20 percent). 12 input variables were registered for each applicant.


* **BAD:** 1 = Client defaulted on loan, 0 = loan repaid

* **LOAN:** Amount of loan approved.

* **MORTDUE:** Amount due on the existing mortgage.

* **VALUE:** Current value of the property. 

* **REASON:** Reason for the loan request. (HomeImp = home improvement, DebtCon= debt consolidation which means taking out a new loan to pay off other liabilities and consumer debts) 

* **JOB:** The type of job that loan applicant has such as manager, self, etc.

* **YOJ:** Years at present job.

* **DEROG:** Number of major derogatory reports (which indicates a serious delinquency or late payments). 

* **DELINQ:** Number of delinquent credit lines (a line of credit becomes delinquent when a borrower does not make the minimum required payments 30 to 60 days past the day on which the payments were due). 

* **CLAGE:** Age of the oldest credit line in months. 

* **NINQ:** Number of recent credit inquiries. 

* **CLNO:** Number of existing credit lines.

* **DEBTINC:** Debt-to-income ratio (all your monthly debt payments divided by your gross monthly income. This number is one way lenders measure your ability to manage the monthly payments to repay the money you plan to borrow.


Final Solution Design

- I have tried multiple models and was able to identify the key factors involved with loan default.
- The prominent feature that is the most impactful in the change to default on a loan is the DEBTINC_missing_values_flag followed by DEBTINC. This emphasizes the impact of missing values on the prediction and should be communicated to the data entry team. A high debt-to-income ratio indicates that the applicant can not afford his/hers monthly mortgage payments, and having too much debt can be a sign of missing a payment or defaulting on the loan. The bank should consider this as a top feature to consider while processing a loan request.
- More feature that positively affect loan default is the age of the oldest credit line in months.
- We can see that the financial background is more relevant than the job profile, the reason for the loan, the actual amount of the mortgage, the value of the property, and the amount of loan that was requested. 
- The bank should consider CLAGE, VALUE, LOAN, MORTDUE, and CLNO as a set of features that have a high impact on defaulting on a loan.
- The 'personal' features like the employment profile, and the loan reason request are nice to have rather than must have, and therefore should not be the main focus when processing a loan application.
- The best model we have got is the tuned random forest model which is giving an average of 84% recall for class 1 on the test data, 82% precision score, and 88% accuracy- These parameters are meeting the model evolution criteria that were defined in the begging of the project. 
- This model is good and does not requires further tuning.
- The bank can use this model to predict clients who are likely to default on their loan 
- In boosting algorithms, XGBoost has given good scores among other algorithms, but since we are focused on getting a high recall score the tuned RF classifier is a better fit for our case. 
- The final model, a hyperparameter-tuned K-NN classifier, is overfitting on the training dataset and gives low recall on the testing datasets. 
- Based on the models that were tested we can conclude that the debt-to-income ratio is the most impact feature in the chance to default on a loan. 
