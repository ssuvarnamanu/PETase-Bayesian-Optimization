# Manuscript-to-code mapping

The mapping below reflects the supplied manuscript excerpts and past analysis summaries. It does **not** certify successful end-to-end numerical reproduction.

| Study component | Notebook | Manuscript outputs and sections | Verification limitation |
|---|---|---|---|
| GP model development and independent validation | `01_GP_Modeling/01_GP_Model_Development_Validation_SHAP.ipynb` | GP modeling, internal split, SHAP interpretation, 237-point hold-out calibration | Full SHAP section has not been fully rerun |
| Retrospective Bayesian optimization | `02_Bayesian_Optimization/02_Bayesian_Optimization_Master_Analysis.ipynb` | BO cycle analysis; manuscript Section 2.3; Figure 4a–c | Recorded campaign checked; replay depends on BayBE version |
| BO initialization robustness | Same BO notebook | Section 2.4; Figure 4d–e | Complete 180-campaign execution still needs verification |
| BO screening efficiency | Same BO notebook | Section 2.5; Table 2 | Random simulation reproduced; full 10,000-run space-filling rerun pending |
| Few-shot transfer learning | `03_Transfer_Learning/03_Transfer_Learning_and_Generalizability.ipynb` | Transfer-learning manuscript section and Figure 7 | Full 270 GP fits not independently completed; calibrated source counts vary per split |
| PET kinetic modeling | `04_Kinetic_Modeling/04_PET_Kinetic_Modeling_Uncertainty_and_Identifiability.ipynb` | Kinetic model B; Supporting Note S8; Tables S4–S8 and Figure S8 | Bootstrap, multistart and all-condition numerical outputs not fully rerun; reviewer diagnostic parametrization distinguished from MATLAB estimates |

**Scientific caution:** The historical BO campaign includes 25 evaluation rows but 18 unique conditions. The transfer-learning manuscript figure should use variable/median source counts for calibrated transfer. Kinetic alternate-pathway code contains an optional no-deactivation model not reported in the three-model manuscript table.
