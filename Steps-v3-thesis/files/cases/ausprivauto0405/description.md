**Description:** The dataset contains information on 67,856 one-year vehicle insurance policies in Australia, taken out in 2004 or 2005, with a focus on policyholder characteristics, vehicle characteristics, and claim outcomes. The dataset is used to build a system that predicts claim approval based on policyholder and vehicle characteristics, with the goal of improving risk assessment in the French market.

**Use Case:** This dataset will be used by a French automobile insurance company to build a system that predicts whether a claim is granted based on policyholder and vehicle characteristics, with the goal of improving its risk assessment in the French market.

**Features:**

* **Exposure**: Number of policy years
* **VehValue**: Vehicle value in thousands of AUD
* **VehAge**: Vehicle age group
* **VehBody**: Vehicle body group
* **Gender**: Gender of the policyholder
* **DrivAge**: Age of the policyholder
* **ClaimOcc**: Indicator for occurrence of a claim (1 if claim, 0 otherwise)
* **ClaimNb**: Number of claims
* **ClaimAmount**: Sum of claim payments

**Model and Data Details**

- ClaimNb: It is the outcome of the model, which includes two classes: 0 (rejected) and 1 (approved)
- Number of Classes: 2
- Dropped features: ClaimOcc and ClaimAmount features were removed from the dataframe and were not used in any of the steps.
- Protected attribute: Gender
- Base rates for protected groups with positive outcomes:
  * Male, ClaimNb 1: 6.75%
  * Female, ClaimNb 1: 6.86%
- Sample sizes for protected groups:
  - Female, Count: 38603
  - Male, Count: 29253
- Model details: Logistic regression was employed to predict 'ClaimNb' in the dataset. Categorical features ('VehAge', 'VehBody', 'Gender', 'DrivAge') were transformed using one-hot encoding. 'Exposure' and 'VehValue' numerical features were standardized using StandardScaler to ensure consistent scaling. The dataset was split into training and testing sets with a test size of 20%. Training utilized the 'liblinear' solver with balanced class weights and a maximum of 100 iterations to address class imbalance and optimize performance.
- Model Performance:
  - Test performance: Accuracy; 0.60662, Precision: 0.09745, F1 Score:, 0.16799, Recall: 0.60835
