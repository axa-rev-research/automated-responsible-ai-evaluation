# Demographic Parity Difference

from fairlearn.metrics import demographic_parity_difference

fairlearn.metrics.demographic_parity_difference(y_true, y_pred, *, sensitive_features, method='between_groups')
Calculate the demographic parity difference.

The demographic parity difference is defined as the difference between the largest and the smallest group-level selection rate, across all values of the sensitive feature(s). The demographic parity difference of 0 means that all groups have the same selection rate.

Parameters:
y_true (array-like) – Ground truth (correct) labels.
y_pred (array-like) – Predicted labels returned by the classifier.
sensitive_features – The sensitive features over which demographic parity should be assessed
method (str) – How to compute the differences. See fairlearn.metrics.MetricFrame.difference() for details.

Returns: The demographic parity difference
Return type: float

# Equalized Odds Difference

from fairlearn.metrics import equalized_odds_difference

fairlearn.metrics.equalized_odds_difference(y_true, y_pred, *, sensitive_features, method='between_groups')
Calculate the equalized odds difference.

The greater of two metrics: `true_positive_rate_difference` and `false_positive_rate_difference`. The former is the difference between the largest and smallest of `P[h(X)=1 | A=a, Y=1]`, across all values `a` of the sensitive feature(s). The latter is defined similarly, but for
`P[h(X)=1 | A=a, Y=0]`.

The equalized odds difference of 0 means that all groups have the same true positive, true negative, false positive, and false negative rates.

Parameters:
y_true (array-like) – Ground truth (correct) labels.
y_pred (array-like) – Predicted labels returned by the classifier.
sensitive_features – The sensitive features over which demographic parity should be assessed
method (str) – How to compute the differences.

Returns: The equalized odds difference
Return type: float

# Exponentiated Gradient

from fairlearn.reductions import Exponentiated Graditent, DemographicParity

or

from fairlearn.reductions import Exponentiated Graditent, EqualizedOdds

fairlearn.reductions.ExponentiatedGradient(estimator, constraints, max_iter=1000)

estimator (estimator) – An estimator implementing methods fit(X, y) and predict(X), where X is the matrix of features, y is the vector of labels (binary classification)

constraints (fairlearn.reductions.Moment) – The fairness constraints expressed as a Moment. Possible constraints are: fairlearn.reductions.DemographicParity() or fairlearn.reductions.EqualizedOdds()

# Threshold Optimizer

from fairlearn.postprocessing import ThresholdOptimizer

fairlearn.postprocessing.ThresholdOptimizer(estimator, constraints='demographic_parity', objective='balanced_accuracy_score')

A classifier based on the threshold optimization approach.

The classifier is obtained by applying group-specific thresholds to the provided estimator. The thresholds are chosen to optimize the provided performance objective subject to the provided fairness constraints.

estimator (object) – A scikit-learn compatible estimator whose output is postprocessed.

constraints (str, default='demographic_parity') – Fairness constraints under which threshold optimization is performed. Possible constraints are: 'demographic_parity' and 'equalized_odds'
