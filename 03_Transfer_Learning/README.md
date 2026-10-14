# Transfer learning for BHET yield — JACS Au

Third analysis notebook accompanying the study: LCCICCG source enzyme → PES-H1 (PHL7) target enzyme.

## Included input

`PET_DegradationTrain_Test.xlsx` (provided experimental workbook), containing `LCC` (440 rows) and `PHL7` (30 rows). Its columns include `family`, `time`, `substrate`, `enzyme`, `solvent`, `temperature`, `ph`, and `Mean_BHET`.

## Reproduce

1. Install packages listed in `requirements.txt` in a suitable Python environment.
2. Open `03_Transfer_Learning_and_Generalizability.ipynb` and run **Restart & Run All**, with the workbook next to it.
3. Inspect generated `yield_r2_results/` for split-wise R², summary statistics, calibration source counts, selected source rows, optimizer warnings, and parity plots.

The notebook retains the original GP kernel, training protocol, split seeds, 30 repeats per target size (8, 10, 12), and response-range filtering. The filtering is based on the **PHL7 training yields only**, not the held-out PHL7 test yields. Source + target observations are pooled and the GP is refitted; this is not fine-tuning a pretrained GP.

## Verification status (2026-10-10)

- Workbook present. All required columns nonmissing; 440 LCC and 30 PHL7 rows, no duplicate input feature rows within either sheet.
- Calibrated LCC source subset size across 30 repeats: n=8: min 88, median 145, max 229; n=10: min 97, median 145, max 210; n=12: min 111, median 155, max 229.
- The target-only section executed, but the complete 270 fits could **not** be rerun within the runtime limit. The notebook is distributed with cell outputs cleared so readers do not mistake partial or stale outputs for reproduced results.
- The published Figure 7 R² numbers should be rechecked after the full run. The figure's fixed calibrated transfer source counts (230, 232, 234) do **not** reflect the code's varying source subset sizes.

The notebook may take substantial time to run due to repeated optimization of GP hyperparameters on up to ~452 observations.
