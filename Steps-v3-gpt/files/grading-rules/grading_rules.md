**ethics-analysis**
- Consider relevant laws and regulations as recommendations. If the laws accurately fit the context, mark them as a MATCH.
- Treat measurement and mitigation suggestions as recommendations. If they align with the context, mark them as a MATCH.
- Presence for numerical results such as performance, train-test splits, dataset size is enough.

**model-card**
- Compare both structure and formatting.
- Consider relevant laws and regulations as recommendations. If the laws accurately fit the context, mark them as a MATCH.
- Ensure that sensitive attributes are explicitly listed.
- Verify that sample sizes and base rates are provided.
- Presence for numerical results such as performance, train-test splits, dataset size is enough.
- Data features should be fully included.

**fairness-analysis**
- Validate the logic used in decisions related to fairness metrics.
- Ignore differences in the selection of mitigation metrics.
- The suggested mitigation method must include the constraint.

**model-card-updated**
- Evaluate the interpretation of interventions under the Analysis section.
- Consider relevant laws and regulations as recommendations. If the laws accurately fit the context, mark them as a MATCH.
- Ensure that post-mitigation performance data is complete.
- The pre-intervention fairness results must be included.
- Presence for numerical results such as performance, train-test splits, dataset size is enough.