**Description:** This dataset contains insurance policy information of 614 individuals in Italy, collected in 2024. It includes 13 features related to insurance history, employment, personal status, and other financial information. The purpose of the analysis is to make insurance policy approval decisions.

**Use Case:** This dataset will be used by an insurance company in France to build a system that predicts the approval of insurance policy applicants. The system aims to provide a fair and accurate assessment of policy risk while ensuring that individuals are not discriminated against based on protected attributes.

**Features:**

* **Policy_ID** : Unique identifier for each insurance policy applicant.
* **Gender** : Gender of the insurance policy applicant. (Male/Female)
* **Married** : Marital status of the insurance policy applicant. (Yes/No)
* **Dependents** : Number of dependents the insurance policy applicant has. (1/2/3+)
* **Education** : Education level of the insurance policy applicant. (Graduate/Not Graduated)
* **Self_Employed** : Indicates whether the insurance policy applicant is self-employed or not. (Yes/No)
* **ApplicantIncome** : Income of the insurance policy applicant. (Continuous numerical values)
* **CoapplicantIncome** : Income of the co-applicant (if any). (Continuous numerical values)
* **CoverageAmount** : Amount of the insurance coverage applied for. (Continuous numerical values)
* **Coverage_Term** : Term of the insurance coverage in months. (Continuous numerical values)
* **Insurance_History** : Insurance history of the policy applicant. (1/0)
* **Property_Area** : Area where the property of the insurance policy applicant is located. (Rural/Urban/Semiurban)
* **Policy_Status** : Indicates whether the insurance policy was approved or not. (1/0)

**Model and Data Details**

- Policy_Status: It is the outcome of the model, which includes two classes: 1 (approve policy) and 0 (reject policy)
- Number of Classes: 2
- Dropped features: Policy_ID, CoverageAmount and Coverage_Term were dropped and were not used in any of the steps.
- Sensitive attribute: Gender
- Base rates for protected groups:
  - Male, Policy_Status 1: 70.6%
  - Female, Policy_Status 1: 62.8%
- Sample sizes for protected groups:
  - Female, Count: 86
  - Male, Count: 394
- Model Details: Logistic regression. 'Gender' and 'Policy_Status' were encoded into numeric values, and one-hot encoding was applied to categorical features 'Property_Area', 'Married', 'Dependents', 'Education', and 'Self_Employed'. Standardization of features using StandardScaler. Splitting of data into training and testing sets with a test size of 20% and initialization and training using the 'liblinear' solver, balanced class weights, and a maximum of 100 iterations.
- Model Performance:
  - Test performance: Accuracy; 0.69792, Precision: 0.73529, F1 Score: 0.77519, Recall: 0.81967
