# PET kinetic modeling 
## Contents
- `04_PET_Kinetic_Modeling_Uncertainty_and_Identifiability.ipynb`: eight-section consolidated notebook
- `data/PET_kinetic_data.xlsx`: source workbook (`Experiment_Data`, `Conditions`, `MATLAB_Results`, plus README)
- `requirements.txt`: scientific Python packages

## Run
From this folder, create a fresh Python environment, install `pip install -r requirements.txt`, open the notebook and use **Restart & Run All**. Bootstrapping (500 fits per EG condition), 80-start identifiability studies, and alternative pathway fits across all 55 conditions may take substantial time. The notebook writes CSV files under `results/`.

## Scientific notes
- The original MATLAB source parameters are retained in the supplied workbook; the Python kinetics are fit in an effective-rate representation (`beta_B`, `beta_M`, `beta_T`, `k6`, `k7`, `k8`). These numerical parameters are **not interchangeable** with the original eight-rate parameter list.
- The model includes enzyme deactivation (`k8`), which is not used and reported in the manuscript
- The notebook tests four pathways, while SI Table S8 reports three. Mapping: full M1, no-direct-TPA M3→SI M2, sequential M4→SI M3. No-deactivation M2 is code-only.
- All-condition t intervals and the two-condition bootstrap intervals are different uncertainty procedures.

