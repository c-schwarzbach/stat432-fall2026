---
name: unsupervised-cluster-report
description: Explicitly invoked workflow for comparing clustering algorithms and producing a one-page, evidence-based clustering report.
---

# Invocation
Run only when explicitly invoked by name. Receive the dataset path, observation unit, feature columns, identifier columns, optional external labels, and output path as invocation inputs. Never assume a particular dataset.

# Workflow
1. Audit row count, feature types, missingness, duplicates, and scale. Exclude IDs and external outcome/class labels from all fitting, tuning, and method selection. Explain missing-value handling. Apply defensible transformations and feature scaling fitted on the data; avoid leakage from external labels.
2. If dimension reduction is useful, fit PCA on the feature matrix (not on labels), record explained variance, and compare a small set of defensible retained dimensions. An embedding is not a clustering method. Keep a consistent feature representation for comparisons, or explicitly disclose differences.
3. Try at least three actual algorithms: K-means, agglomerative hierarchical clustering (e.g., Ward), and spectral clustering. Explore plausible numbers of clusters (typically 2–5, restricted by sample size). Tune relevant parameters such as linkage, neighborhood size, and initialization; fix random seeds.
4. Select using only unsupervised evidence: silhouette/separation, sensible cluster sizes, reproducibility under seeds or resampling, robustness to preprocessing, and interpretability. Do not maximize an external-label agreement score. Avoid trivial singleton-driven solutions and acknowledge competing criteria. Record why the final choice beats alternatives.
5. Refit the chosen configuration. Summarize its cluster counts and structure. Use a clear, labeled 2-D PCA scatterplot colored by the selected cluster assignments; explain that the plot is a projection and that clustering may have used more dimensions. Optionally interpret the selected clusters using held-out external labels only after selection; distinguish association from validation or causation.
6. Audit consistency of totals, figure labels, metrics, and narrative. State limitations including small samples, high dimension, scaling choices, and potential instability.

# Output contract
Generate an analysis report limited to **one printed page total**, including every title, sentence, figure, and table. Present clustering results from **only the single selected method**. Other methods may be named briefly to justify selection, but show no assignments, scores, tables, or figures for those alternatives. Include a concise method/selection rationale, one informative figure, key selected-method evidence, interpretation, and limitations. Put the full skill definition in an appendix **after** the one-page report; the appendix is exempt from the page limit. Supply both the report and this complete SKILL.md as requested.
