# Circular Task Analysis

Python analysis of a circular cursor-tracking task recorded with MouseReMoCo. The notebooks reproduce the reference figures, recompute the statistics table from the raw data, and repeat the analysis on our own recording.

## What we did

**Main work (assignment tasks)**
- Reproduced the reference figures from `001MoDe_R1.csv` and its marker file: raw trajectory, time series, and one figure per recording.
- Recomputed the statistics table (laps, radius, variability, error %, movement time, difficulty, throughput) from the raw data using only `numpy`, `matplotlib` and `os`.
- Ran the same analysis on our own MouseReMoCo recording (`data.csv`, `marker.csv`).  
  
**Additional work (`extra-analysis/`)**
- Descriptive comparison of the reference and our own recording: sampling rate, cycle durations and coverage, trajectories, and radial error.
- A written summary of the differences between the two recordings and their likely causes.
- The sampling-frequency printout in comparison-validation.ipynb is a whole-file estimate. The per-recording rates (about 21–28 Hz for our recording vs about 200 Hz for the reference), given in discrepancy-analysis.ipynb and the report, are the figures to use.

## Repository structure

- `main.ipynb`: runs both analysis notebooks in order 
- `data/`
  - `001MoDe_R1.csv`, `001MoDe_R1.marker.csv`: reference recording provided with the assignment
  - `data.csv`, `marker.csv`: our own MouseReMoCo recording
- `notebooks/`
  - `circular-task-001.ipynb`: analysis of the reference recording (figures + statistics table)
  - `circular-task.ipynb`: the same analysis on our own recording
- `extra-analysis/`: supplementary work beyond the assignment requirements
  - `comparison-validation.ipynb`: descriptive comparison of the two recordings (code and plots)
  - `discrepancy-analysis.ipynb`: written summary of the differences between the two recordings

## How to run

1. Clone the repository.
2. Open main.ipynb or another notebook in VS Code (or Jupyter) and click **Run all**.
   Only `numpy`, `matplotlib` and `os` are used, as required by the assignment.
   The notebooks work from either the project root or the `notebooks/` folder.

## Known limitation

The recomputed error % does not exactly match the reference table (e.g. Rec001: 5.39 vs 3.90). All other indicators (laps, radius, variability, movement time, difficulty, throughput) match. The most likely cause is how the initial approach phase is trimmed; this is discussed in the report.

## Team

- THEBUWANA Vidusha: repository management and pull request integration
- DADIGA Isah: core analysis notebooks
- BINCHE Werner: supplementary dataset comparison
- DEFFIN Elouan: report and documentation

## Workflow

Each member worked on their own branch and merged through a pull request. Only the repository manager merges. `main` is protected: a pull request is required, and force-pushes and deletion are blocked.