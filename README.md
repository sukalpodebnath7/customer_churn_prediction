## **PROJECT : CUSTOMER CHURN PREDICTION**





### Overview:



The project is about predicting the customer churn of a telecom company using machine learning algorithms(Classification).

The main goal is to identify customers who tend to leave membership of company services by analyzing the given features of the dataset and creating a model for further prediction.

### 

### Dataset Info:



* The dataset consists of 7043 rows and 21 columns
* Target feature : Churn (Yes(1)/No(0)) - { No: 76%, Yes: 26%}
* Other features:

  * Demographics (5 features)
  * Company connection (1 feature1)
  * Internet Services (7 features)
  * Phone Services (2 features)
  * Membership and Billing(3 features)
  * Charges (2 features)





### Exploratory Data Analysis (EDA):



* Low tenure(new customers) tend to have higher rate of churn
* New customers paying high monthly charges tend to leave more
* Customers who are new and selecting month to month membership have a higher trend towards Churn
* Poor combination of service such as any internet service without backup, security and tech support shows high number of dissatisfied customers
* Senior Citizens without dependencies show high churn







### Feature Engineering:



After the EDA the features that seemed to be valuable are:

* new\_customer : tenure <= 3
* tenure\_log and tenure\_sqrt : for feeding the non-linear behaviour of the tenure to the models
* low\_tenure\_high\_monthly\_charge : tenure <= 20 and monthly\_charge >= 60
* low\_tenure\_month : tenure <= 20 and contract = Month-to-month
* non\_automated\_payment : PaperlessBilling = Yes and PaymentMethod = Electronic check
* poor\_service : Services without security, bacup and tech support
* senior\_no\_partner : Senior Citizens without partners
* senior\_no\_dependets : Senior Citizens without dependents







### Data Preprocessing:



* Handled Missing values in Total Charges by median as the TotalCharges was right-skewed data
* Feature Transformation:

  * Log transformation
  * Sqrt transformation
* Scaled the features using MinMaxScalar
* Addressed class imbalanced using:

  * Under Sampling
  * Over Sampling
  * SMOTE (with best results)





### Model Training:



* Logistic Regression
* Random Forest (with SMOTE)
* XGBoost
* XGBoost (with SMOTE + Hyperparameter tuning using Optuna)







### Model Evaluation:





&#x09;	model		accuracy	precision	 recall	   	   f1		roc\_auc

\------------------------------------------------------------------------------------------------------------

0	Logistic Regression	0.785882	0.581508	0.69661		0.633265	0.845565

\------------------------------------------------------------------------------------------------------------

1	Random Forest(SMOTE)	0.677696	0.447426	0.89513		0.595721	0.843019

\------------------------------------------------------------------------------------------------------------

2	XGBoost			0.740448	0.507997	0.81380		0.625018	0.844196

\------------------------------------------------------------------------------------------------------------

3	XGBoost(SMOTE)		0.833168	0.644946	0.82611		0.724373	0.912416







### Model Selection:



Best Model : XGBoost with SMOTE and Hyperparameter tuning







### Business Insights:



Business Insights:

* The Fiber Optic Internet Service is responsible in dissatisfying the customers, which should be improved
* The customers who are taking services without security, backup and support tend to have high Churn rate
* Combo offers with security and backup service might be helpful for the customers
* Automated payment system should be encouraged more
* Offer long term service membership to the customers
* The newly arrived customers should get the highest attention (Like: Sales, offers, campaigns etc)









&#x09;

