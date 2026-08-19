# Computational Experiments

This anonymous verification package contains the notebooks and saved outputs for the computational experiments reported in Section 6.

## Contents

- `Code and Notebooks/Centipede_Basins_Attraction_v2.ipynb`: experiment generator.
- `Code and Notebooks/Centipede_Basin_Diagnostics_v2.ipynb`: diagnostics and paper-figure generator.
- `Code and Notebooks/basin_runs/20260813T212655Z_9784ae45cca9/manifest.json`: immutable run configuration, environment information, and checksums recorded at run completion.
- `aggregate/`: compact aggregate arrays plus grid-level and trajectory-level CSV files for all 120,000 trajectories.
- `diagnostics/20260817T034812Z/`: the essential derived tables used to verify the reported results, including the enriched grid, value-clock comparisons, and representative temporal profiles.
- `selected_raw_cells/`: the raw cell archives selected by the diagnostics notebook for the representative temporal profiles, left unpacked for quick inspection.
- `Drafts/`: the three manuscript figures and two manuscript tables exported by the final diagnostic pass.
- `SHA256SUMS.txt`: checksums for every file in this package other than the checksum file itself.

Saved notebook outputs were cleared from the packaged copies because they contained local absolute paths. Notebook source cells were not edited for anonymization.

## Running the notebooks

Run the notebooks with `Code and Notebooks` as the working directory. The experiment notebook defaults to its full configuration and writes a new immutable directory under `basin_runs/`. The diagnostics notebook automatically selects a run only when exactly one complete run is present; otherwise, set `CENTIPEDE_BASIN_RUN_ID` to the exact run identifier.

The GitHub package omits the complete 7,500-file raw cell corpus to remain below 25 MB. The retained `replicate_summary.csv`, `grid_summary.csv`, and diagnostic tables contain the complete numerical results reported in the manuscript. To recreate every raw cell archive and rerun the diagnostics from the beginning, run the experiment notebook and then diagnose the newly generated run.

The recorded experiment environment used Python 3.12.4, NumPy 2.1.3, Matplotlib 3.9.3, Seaborn 0.13.2, and Ray 2.40.0. The diagnostics notebook also requires pandas.

## Provenance note

The completed run records experiment source hash `9784ae45cca9ee6d0bd0562ddb8b647e638be7eb1b3af2b34b61301e2f38d485`. The current generator notebook has source hash `f638d0d4dc1a589c985229eac820f2ccca3e149d07df0b002985621411de5153`; it was saved shortly after the run completed, and the exact saved source snapshot named by the manifest was not retained. The run package itself completed successfully, and its manifest records checksums for every original experiment output. This distinction is disclosed so that the current notebook is not represented as byte-identical to the source snapshot recorded by the completed run.
