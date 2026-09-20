# Neutrino Event Classification

**Chloe Lin · University College London · Python scientific computing**

**When 88% accuracy hides missed background events.**

Developed TensorFlow/Keras CNNs for simulated neutrino interactions and investigated how class imbalance changes signal detection and background rejection (2026).

![Historical test-set counts, redrawn as row-normalised confusion matrices. Additional weighted training improves background rejection at the cost of signal recall.](figures/classification_comparison.png)

*Historical test-set counts, redrawn as row-normalised confusion matrices. Additional weighted training improves background rejection at the cost of signal recall.*

**[Start the guided notebook](notebooks/main_analysis.ipynb)** · [Detailed logbooks](notebooks/logbooks) · [Presentation provenance](docs/PRESENTATION_NOTES.md)

## What this demonstrates

- HDF5 processing and two-channel CNN inputs from 21,016 simulated events.
- Model evaluation beyond overall accuracy, including class-wise recall and ROC analysis.
- Interpreting performance across energy ranges and interaction topologies.

| Saved evaluation | Unweighted | After additional weighted training |
|---|---:|---:|
| Balanced accuracy | 53.5% | 81.8% |
| Background rejection | 8.3% | 91.1% |
| Signal recall | 98.7% | 72.4% |

The saved ROC curve reports **AUC 0.879** on 3,153 test events. These are historical outputs, not newly retrained results. The same model continued training with class weights; this is not an isolated causal comparison of weighting alone.

## Data access and evaluation status

**The professor-provided dataset is not included. Redistribution permission is unknown.** The guided notebook runs without it, reconstructing aggregate metrics from saved confusion-matrix counts. It does not train a CNN or reproduce the AUC from raw scores.

See [data access instructions](data/README.md) for authorised local use and [evaluation review notes](docs/REVIEW_NOTES.md) for the remaining training and validation corrections. Existing logbook outputs remain private while permissions are clarified.

## Run the guided notebook

From the repository root, create and activate a Python virtual environment, then:

```sh
python -m pip install -r requirements-demo.txt
python -m jupyter lab notebooks/main_analysis.ipynb
```

The short notebook has saved outputs for browsing and runnable cells that regenerate the opening figure. It supports a working directory of either the repository root or `notebooks/`. The original project dependencies are listed separately in `requirements.txt`.

## Repository map

```text
README.md
notebooks/
  main_analysis.ipynb      # Start here
  logbooks/               # Original detailed work
figures/                  # Generated README figure
docs/                     # Review and provenance notes
requirements-demo.txt      # Guided notebook
requirements.txt           # Original project dependencies
```


## Status and attribution

Private working draft; visibility will change only at Chloe's request. The guided notebook is a new presentation of the project, and does not validate all historical results. Original sources and teaching-material references remain in the logbooks. Confirm sharing conditions before publication; no open-source licence has been selected.
