# Data access

The simulated detector dataset was supplied by the project supervisor/professor. Redistribution permission is not established, so no raw data are included or uploaded.

Ask the course staff or data owner for authorised access and explicit sharing permission. No public download URL is assumed.

The guided notebook runs without this dataset, using aggregate confusion-matrix counts already reported in the coursework. To rerun the historical training logbook, obtain the authorised HDF5 files and set `NEUTRINO_DATA_DIR` to their absolute local folder path before starting Jupyter. This avoids dependence on the notebook's working directory. See `docs/REVIEW_NOTES.md` before rerunning.

Expected entries include `cvnmap` and `neutrino/{interaction,nuenergy,lepenergy,finalstate}`. Record the exact selected filenames locally for reproducibility. Do not commit them or event-level exports.

Existing historical notebook outputs may contain detector views. Redistribution permission for these outputs and any course-provided starter material has not been established.
