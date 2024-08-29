**Description:** This dataset contains information on 1,144 automobile insurance policies in Norway, with a focus on policyholder characteristics, policy details, and claim outcomes over a one-year period. Each record represents a policyholder and their insured vehicle, with features related to risk characteristics, policy details, and claim outcomes.

**Use Case:** This dataset will be used by a French automobile insurance company to build a system that predicts claim approval based on policyholder and vehicle characteristics, with the goal of improving its risk assessment in the French market.

**Features:**

* **Male**: Indicator for male policyholder (1 if male, 0 otherwise)
* **Young**: Indicator for young policyholder (1 if age below 26 years, 0 otherwise)
* **DistLimit**: Distance limit as stated in the insurance contract (categorical value)
* **GeoRegion**: Density of the geographical region (categorical value)
* **Expo**: Exposure as a fraction of year
* **ClaimAmount**: 0 or the average claim amount if NbClaim > 0.
* **ClaimAmount**: Average claim amount (0 if no claims, otherwise 1)

**Model and Data Details**

- ClaimAmount: It is the outcome of the model, which includes two classes: 0 (rejected) and 1 (approved)
- Number of Classes: 2
- Dropped features: ClaimAmount was removed from the dataframe and was not used in any of the steps.
- Protected attribute: Male
- Base rates for protected groups:
  - Male: 0, ClaimAmount 1:  50.00%
  - Male: 1, ClaimAmount 1:  50.00%
- Sample sizes for protected groups:
  - Male: 0, Count: 572
  - Male: 1, Count: 572
- Model details: The model uses the HistGradientBoostingClassifier from scikit-learn to predict 'ClaimAmount' in the 'norauto' dataset. Categorical features are one-hot encoded with handling of unknown categories, while numerical features are passed through unchanged. Data is split into training and testing sets with an 80%-20% ratio. The model training involves fitting the pipeline to the training data, utilizing features from the dataset.
- Model Performance:
  - Test performance: Accuracy; 0.63319, Precision: 0.68868, F1 Score:, 0.63478, Recall: 0.58871
