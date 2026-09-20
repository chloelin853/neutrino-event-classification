# Review before public release

The original supplied notebook remains unchanged outside this repository. The repository copy retains historical outputs; changes to the data path and the introductory note do not regenerate them.

## Evaluation and reproducibility

- Fit pixel normalisation on training data only, then apply it to validation/test sets. The existing notebook uses a global maximum before splitting.
- Align raw-energy regression sample weights with the training rows. The current expression derives weights from the full signal subset.
- Initialise a fresh network for the binary interaction-mode experiment, or explicitly design a leakage-free transfer-learning experiment. The current experiment reuses the signal classifier with a different split.
- For controlled class-weight comparisons, train fresh weighted and unweighted networks with the same split and training budget.
- Use fresh callbacks for independent experiments, restart the kernel, execute in order, and record final outputs and dependency versions.
- Keep an explicit manifest of selected data files. The current selection takes the first three filenames in lexicographic order.
- Review binned plots: empty bins should be marked missing, the maximum bin edge should include the final observation, and uncertainty estimates should account for sparse bins.

## Interpretation

- The saved weighted signal recall is 72.4%; approximately 81.8% is macro-averaged recall/balanced accuracy.
- Fixed `random_state=42` makes the data splits repeatable for unchanged input data. Training can still vary; do not explain variability as random test-set changes in this version.
- Weak performance alone does not establish an intrinsic detector-information limit; model, data, and training limitations also need consideration.
- Avoid comparing three-class and binary accuracy as a like-for-like improvement: the label definitions differ.
- Retain limitations when reporting flavour recall: the saved electron-neutrino precision is approximately 5%.

## Publication preparation

- Confirm attribution and permission to share any course-provided starter material.
- Keep the dataset excluded unless redistribution rights are established.
- Choose a licence only after ownership and sharing conditions are clear.
