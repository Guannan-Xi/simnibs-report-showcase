# Data and Code Availability

## Data

This delivery contains the derived elementwise fields, ROI masks, summary tables, figure-support data, and publication figures used in the report. The primary machine-readable files are `../raw/violante2023_reproduction_fields.h5`, `../raw/violante2023_reproduction_fields.msh`, the NIfTI files under `../raw/nifti/`, `../result.json`, and the CSV/Excel tables.

The analysis uses the public SimNIBS example subject `ernie` and the Harvard-Oxford subcortical 25% maximum-probability atlas. Upstream anatomical and atlas source files remain subject to their original distribution terms and are not represented as participant data collected for this report. This package contains no original Violante et al. participant MRI data and is not a numerical reproduction of the paper's MIDA or participant cohort.

## Code

Frozen snapshots of the analysis and delivery generators are included in this directory:

- `run_violante2023_ti_reproduction.py`
- `build_violante2023_ti_delivery.py`

The Python and package versions used for this build are recorded in `python_environment.json` and `requirements-lock.txt`. The scripts use repository-relative paths and do not contain API keys or provider credentials.

## Reproduction boundary

From the repository root, place the frozen snapshots under `scripts/` (or confirm they match the working copies) and rebuild the report from the existing derived FEM outputs with:

```text
python scripts/build_violante2023_ti_delivery.py
```

A full FEM rerun additionally requires the SimNIBS `ernie` head model, the Harvard-Oxford atlas inputs, and the solver environment described above. The implemented FT7-Fp2 and TP7-TP8 montage is a 10-10 substitute for the continuous scalp coordinates in Violante et al. (2023). Mesh-convergence, electrode-position, conductivity, segmentation, DTI-direction, MNI-registration, and cross-subject uncertainty analyses were not performed.

## Integrity

Every delivered file except the manifest itself is listed with byte size and SHA-256 in `../manifest.json`. Report run ID: `ernie-violante2023-ti-forward-reproduction-20260729`.
