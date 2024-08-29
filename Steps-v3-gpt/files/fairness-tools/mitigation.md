## For Equalized Odds:

### 1. Threshold Optimizer (fairlearn.postprocessing.ThresholdOptimizer with "equalized_odds" constraint)

When to use:

- Binary classification tasks
- Need to balance error rates across demographic groups
- Significant differences in base rates between groups
- Sufficient samples per group (e.g., at least 100)

Why:
Adjusts prediction thresholds for each group to ensure similar error rates, promoting fairness without retraining the model.

### 2. Exponentiated Gradient (fairlearn.reductions.ExponentiatedGradient with fairlearn.reductions.EqualizedOdds() constraint)

When to use:

- Complex binary classification problems
- Multiple fairness constraints to consider
- Simple threshold adjustments are insufficient
- Training process can be modified

Why:
Optimizes the model during training to minimize disparities in error rates across groups, ensuring a fairer model.

## For Demographic Parity:

### 1. Threshold Optimizer (fairlearn.postprocessing.ThresholdOptimizer with "demographic_parity" constraint)

When to use:

- Binary classification tasks
- Need to equalize positive prediction rates across demographic groups
- Differences in group sizes or base rates
- Sufficient samples per group (e.g., at least 100)

Why:
Adjusts prediction thresholds for each group to ensure similar positive prediction rates, promoting fairness without retraining the model.

### 2. Exponentiated Gradient (fairlearn.reductions.ExponentiatedGradient with fairlearn.reductions.DemographicParity() constraint)

When to use:

- Complex binary classification problems
- Multiple fairness constraints to consider
- Simple threshold adjustments are insufficient
- Training process can be modified

Why:
Optimizes the model during training to minimize disparities in positive prediction rates across groups, ensuring a fairer model.
