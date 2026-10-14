# JACS Au — Bayesian optimization master analysis

One notebook aligned with manuscript Sections 2.3–2.5:

1. Historical BO campaign (qLogEI and qPI; five cycles), recorded conditions and cycle audit.
2. BO robustness to 20, 50, 100 initial experiments using random and space-filling initial sets (30 replications each).
3. Independent random and sequential-maximin space-filling screening (10,000 campaigns each; Table 2).

## Run
Create a Python environment with the `requirements.txt` dependencies. Run Jupyter from the directory containing the notebook and `data/`, and run cells in order. The 180 BayBE robustness runs and 10,000 space-filling permutations can be time-consuming. Historical Bayesian-optimization replay is **opt-in**; the manuscript results are drawn from supplied recorded evaluations.

**Data:** The seven supplied CSVs are in `data/`; no external Excel files are required. Part III converts historical substrate disc-count values to g/L using 32 g/L per disc before matching; all 25 BO rows match uniquely and yield/selectivity values agree numerically. Output files are placed in `outputs/`.

## Verification
- Cycle audit checks the historical optimum (D ≈ 0.739064731).
- Part III contains fixed-seed consistency assertions against the manuscript's Table 2 (random 10.15%, 119.7552 mean, 121 median; space-filling 42.48%, 55.6006 mean, 38 median).
- These baseline output values were **reported in the source notebook**; they should be rerun in your local environment before releasing.
- The corrected nominal additional-evaluation efficiency is ~4.79× vs random and ~2.22× vs space-filling.
- Original BO had 25 selected evaluation rows representing 18 distinct conditions; baselines draw without replacement. This caveat must accompany any experimental savings claim.

## Source notebooks
`BO_campaign.ipynb`, `BO_initialization_robustness_self_contained.ipynb`, and `Experimental_efficiency_analysis.ipynb`. The third is used verbatim for the sampling algorithm, with the original Excel-only load cells adapted to the supplied measured CSV files.

## Validation performed for this master package
- Notebook syntax and structure checked (109 cells).
- Exact mapping of all 25 BO evaluations to the 237-condition candidate file confirmed after translating PET-disc count to substrate loading at 32 g/L per disc. Yield/selectivity matched within floating-point rounding.
- Part III random Monte Carlo campaign rerun: 10.15% within 25 evaluations; 119.7552 mean evaluations; median 121.
- The full 10,000-run sequential maximin space-filling campaigns and the 180 BayBE robustness campaigns have **not** been independently rerun in this session. Original source outputs support manuscript values, with full-run assertions in the notebook.
