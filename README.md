# Neutrino Event Classification

An academic machine-learning project by Chloe Lin for PHAS0056 Practical Machine Learning for Physicists at University College London (2026).

This project explores convolutional neural networks for simulated neutrino interactions in a NOvA-like detector. Each event contains two 100 × 80 detector projections. The selected dataset contains 21,016 events from three HDF5 files.

## Status

Private working draft. The notebook preserves historical outputs from the coursework; these have not been regenerated for this repository. The evaluation checks in [REVIEW_NOTES.md](REVIEW_NOTES.md) must be addressed before describing the results as independently reproduced. Repository visibility must remain private until Chloe chooses to change it.

## Investigations

- Muon-neutrino charged-current signal classification and class imbalance.
- Signal efficiency and background acceptance across energy, interaction type, and final-state categories.
- Neutrino energy and lepton-to-neutrino energy-ratio regression.
- Muon/electron neutrino flavour classification.
- Three-class and binary interaction-mode classification.

## Methods

Python, TensorFlow/Keras, NumPy, h5py, scikit-learn, and Matplotlib. CNNs use convolution and max pooling, dense layers, dropout, and task-specific outputs and losses. Selected experiments use early stopping and class weighting.

## Historical signal-classifier results

The saved evaluation uses 3,153 test events from a stratified 70/15/15 training/validation/test split.

| Metric | Before additional weighted training | After additional weighted training |
|---|---:|---:|
| Signal recall | 98.7% | 72.4% |
| Background rejection | 8.3% | 91.1% |
| Balanced accuracy | 53.5% | 81.8% |

The saved ROC plot reports AUC = 0.879. Balanced accuracy is calculated from the saved confusion matrices. The weighted stage continues training the existing network, so this is not a controlled comparison between independently initialised models.

## Files

- `neutrino_classification.ipynb`: working copy with historical outputs and a portable data-location setting.
- `requirements.txt`: direct notebook dependencies (not a tested, version-pinned environment).
- `REVIEW_NOTES.md`: evaluation and reproducibility work remaining.

## Data

The dataset is not included. Obtain the course-provided HDF5 data through the authorised course source. Place the files in a local `data/` folder alongside the notebook, or set `NEUTRINO_DATA_DIR` to the directory containing them. HDF5 files are excluded from Git by `.gitignore`.

Expected HDF5 entries include `cvnmap` and the `neutrino` metadata group, including `interaction`, `nuenergy`, `lepenergy`, and `finalstate`.

## Local setup

Create and activate a Python virtual environment, then run:

```sh
python -m pip install -r requirements.txt
python -m jupyter lab
```

Open the notebook with its containing directory as the working directory. Inspect the saved results first. Resolve the review notes before attempting a clean end-to-end training run; the current draft is not represented as fully reproducible.

## Attribution

This repository is coursework, not an official NOvA collaboration project. The notebook includes assignment text, dataset definitions, and introductory material; the exact attribution of course-provided starter material should be confirmed before public release. No open-source licence has been applied at this draft stage.
