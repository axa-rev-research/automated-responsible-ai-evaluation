**Description:** This dataset contains information of 300 credit records. It is a consumer credit files collected in 1994, called the German Credit dataset in Tuff’ery (2011) and Nisbet et al. (2011). New applicants for credit and loans can be evaluated as good or bad payers using 21 explanatory variables.

**Use Case:** This dataset will be used by a French bank to build a system that predicts the creditworthiness of loan applicants in France. The model aims to enhance the loan approval process by providing insights into applicants' repayment behaviors based on historical data. By accurately classifying applicants as either good or bad credit risks, the bank can mitigate financial losses, streamline decision-making processes, and ensure compliance with regulatory requirements. Additionally, the system can help identify potential borrowers who are likely to repay their loans, thus fostering responsible lending practices and supporting the bank’s growth strategy.

**Features:**

* **checking_status**: Status of existing checking account in Deutsche Mark.
* **duration**: Duration of the credit in months.
* **credit_history**: Credit history (credits taken, paid back duly, delays, critical accounts).
* **purpose**: Purpose of the credit (car, television, etc.).
* **credit_amount**: Credit amount.
* **savings**: Status of savings account/bonds in Deutsche Mark.
* **employment**: Present employment in number of years.
* **installment_rate**: Installment rate in percentage of disposable income.
* **personal_status**: Gender (sex) and personal status.
* **other_parties**: Presence of other debtors or guarantors.
* **residence_since**: Number of years at present residence.
* **property_magnitude**: Type of property (e.g., real estate).
* **age**: Age in years.
* **other_payment_plans**: Presence of other installment plans (banks, stores).
* **housing**: Type of housing (rent, own, etc.).
* **existing_credits**: Number of existing credits at this bank.
* **job**: Job type.
* **num_dependents**: Number of people being liable to provide maintenance for.
* **telephone**: Presence of a telephone (yes/no).
* **foreign_worker**: Status as a foreign worker (yes/no).
* **class**: Binary variable where 0 stands for good and 1 stands for bad credit.

**Model and Data Details**

- class: It is the outcome of the model, which includes two classes: 0 (good credit) and 1 (bad credit)
- Number of Classes: 2
- Dropped features: purpose, installment_rate and credit_amount features were removed from the dataframe and were not used in any of the steps.
- Protected attribute: Gender
- Base rates for protected groups with positive outcomes:
  * Male, class 1: 27.68%
  * Female, class 1: 35.16%
- Sample sizes for protected groups:
  - Male, Count: 690
  - Female, Count: 310
- Model details : Logistic Regression was employed to predict the 'y_label' class in the dataset. Categorical features were transformed using one-hot encoding. The dataset was checked for class imbalance, and minority classes were oversampled to achieve balance. All numerical features were standardized using StandardScaler to ensure consistent scaling. The dataset was split into training and testing sets with a test size of 20%. Hyperparameter tuning was performed using GridSearchCV to optimize the model, testing various solvers, regularization strengths, and maximum iterations for improved performance. The final model used the best parameters from the grid search for prediction.
- Model Performance:
  - Test performance: Accuracy: 0.69643, Precision: 0.67361, F1 Score: 0.69534, Recall: 0.71852
