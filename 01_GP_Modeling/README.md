# Gaussian-process modeling and independent validation

This folder supports the GP analyses reported in the JACS Au manuscript revisions.

## Notebook

`01_GP_Model_Development_Validation_SHAP.ipynb` combines (i) the constrained-set internal split, GP evaluation and SHAP interpretation, and (ii) independent hold-out testing and uncertainty calibration. It preserves the modeling specifications and calculations of the two input notebooks, while removing the duplicate GP factory and redundant imports.

## Data

- `constrained_203.xlsx` — `constrained` sheet, 203 observations.
- `holdout_237.xlsx` — `clean` sheet, 237 observations.

Place both input files next to the notebook, or in `data/` with the notebook in the repository root or `notebooks/`.

## Reproduce

1. Install requirements from `requirements_gp.txt`.
2. Open the notebook and select **Restart & Run All**.
3. Check `gp_outputs/` for internal-validation and SHAP exports and `gp_calibration_outputs/` for external-validation outputs.

The internal 80:20 model and the all-203-observation refit are different fitted objects. The hold-out observations are not used to fit the GPs. SHAP runtime may be substantial depending on hardware.
