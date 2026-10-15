# PET hydrolysis: Gaussian processes, Bayesian optimization, transfer learning, and kinetics

Reproducibility materials for the PET hydrolysis study. This repository organizes four complementary analyses. Each notebook has its own experimental inputs and can be run independently of the other notebooks.

## Analyses

| Directory | Analysis | Input data |
|---|---|---|
| [`01_GP_Modeling/`](01_GP_Modeling/) | GP development, SHAP, independent calibration | 203-point constrained and 237-point hold-out Excel workbooks |
| [`02_Bayesian_Optimization/`](02_Bayesian_Optimization/) | Five-cycle BO, initialization robustness, screening efficiency | Seven historical/curated CSV datasets |
| [`03_Transfer_Learning/`](03_Transfer_Learning/) | Few-shot target-only/full/calibrated transfer | LCC (440) and PHL7/PES-H1 (30) Excel worksheets |
| [`04_Kinetic_Modeling/`](04_Kinetic_Modeling/) | PET kinetic model B, uncertainty, identifiability, pathway comparisons | Original kinetic workbook with measurements, conditions, MATLAB fits |

Each analysis folder includes its own `README.md` and `requirements.txt`.

## How to run

1. Download or clone this repository, then open a terminal in the desired analysis folder.
2. Create a new virtual environment (recommended to avoid dependency conflicts). For example, from that folder:

   ```bash
   python -m venv .venv
   # Windows PowerShell: .venv\Scripts\Activate.ps1
   # Linux/macOS: source .venv/bin/activate
   python -m pip install -r requirements.txt
   python -m pip install jupyterlab
   jupyter lab
   ```
3. Open the numbered `.ipynb` in that same analysis folder and run its cells sequentially. **Do not move the notebook away from its `data/` folder** (transfer learning uses an adjacent `.xlsx`).
4. Long-running BO and kinetic diagnostic sections may require substantial CPU time. Check saved outputs and paper values after execution.

## Dependencies

The four supplied workflows have different requirements and package/API compatibility constraints. Use **their folder-specific requirements**, not a single untested merged environment. In particular, the Bayesian optimization code depends on BayBE/BoTorch and should be tested with a compatible software release.

## Data and reproducibility

The original source datasets are preserved inside the relevant analysis folders; there is no requirement to execute notebooks in sequence. 

## Publication and citation

**Publication metadata:** TBD


