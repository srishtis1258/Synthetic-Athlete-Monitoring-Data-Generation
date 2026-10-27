# Synthetic-Athlete-Monitoring-Data-Generation
Synthetic Athlete-Monitoring Data Generation: Statistical Fidelity, Predictive Utility and Distance-Based Privacy Proxies
Open it in Jupyter and use “Run all” to confirm it reproduces on your machine. It reads both CSVs from the same folder or from /mnt/user-data/uploads/, so change the two path lines at the top if yours differ.

What it runs

Loads and cleans both datasets: harmonises the week labels and turns the #DIV/0! entries in Monotony and Strain into missing values.
Verifies the facts quoted in the manuscript: 26 weeks, one athlete with 78 rows, 41.09% RSI missing, the identical asymmetry columns, and the Total g-Load ≈ Intensity × time identity.
Runs the leakage-controlled evaluation: athlete-grouped 75:25 splits over 10 seeds, median imputation fitted on training data only, a multivariate Gaussian generator, a Random Forest, and tests on untouched real records (observed RSI only for SHU).
Runs the α sensitivity analysis (0.6 to 1.2).
Computes the privacy checks: distance to closest record, nearest-neighbour distance ratio, exact duplicates and membership-inference AUC.
Runs the masked-imputation check of RF-MICE against median imputation.

Main results at α = 0.8

Measure	Plantiga	SHU
Real-data baseline R² (TRTR)	0.852 ± 0.061	0.303 ± 0.245
Synthetic-to-real R² (TSTR)	0.662 ± 0.153	0.374 ± 0.191
Membership-inference AUC	0.639	0.567

Both datasets give the lowest standardized Wasserstein distance at α = 1.0. No exact duplicates were found in any setting.
