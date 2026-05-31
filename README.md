# Markov Chain Modelling

This repository explores Markov chain models and cost analysis for a logistics problem: comparing third-party logistics (3-PL) costs against truck rental costs under different inventory, demand, and threshold policies.

## Project Overview

The goal is to model order arrival and shipment decisions using Markov chains, then use the resulting state distributions to compare:

- expected daily 3-PL shipping costs
- expected daily truck rental costs
- optimal shipment threshold policies

Various scripts generate and analyze transition matrices, compute cost comparisons, and examine due-date based volume distributions.

## Repository Structure

- `initial_model/`
  - `initial_model.py` — builds a Markov transition matrix for a 4-day cycle, computes expected shipment volumes, and compares 3-PL versus truck rental cost.
  - `acme_transition_matrix.csv` — generated transition matrix output.

- `final_matrix/`
  - `prof_suggested_model.csv` — a suggested transition matrix for the final analysis.
  - `prof_suggested_model.py` — script related to the final model.

- `q4_modelandcost/`
  - `cost_analysis.py` — loads a transition matrix, computes steady-state probabilities, and evaluates cost and threshold policies for 3-PL and truck rental options.
  - `extended_transition_matrix.csv` — transition matrix used for cost evaluation.
  - `cost_analysis.csv` — output cost analysis results.

- `delivery_schedule/`
  - `due_date_model.py` — builds a due-date-based order volume distribution and exports it to `due_date_distribution.csv`.
  - `due_date_distribution.csv` — sample output distribution.

- `one_day_matrix/`
  - `modified_model.py` — alternative model for one-day shipment or volume state evolution.
  - `one_day_transition_matrix.csv` — model output.

- `cost_analysis/`
  - `markov_cost_analysis.py` — additional cost analysis scripts for threshold and policy evaluation.
  - `threshold_policy_costs.csv` — sample threshold policy results.

- `no_matrix.py`
  - a simulation-style implementation that uses stochastic order arrivals and shipment thresholds without explicit transition matrices.

## Getting Started

### Requirements

- Python 3.9+
- `numpy`
- `pandas`
- `matplotlib`
- `seaborn` (optional, for plotting in some scripts)

Install dependencies with:

```bash
python -m pip install numpy pandas matplotlib seaborn
```

### Running the main scripts

Run the initial transition matrix generator:

```bash
python initial_model/initial_model.py
```

Run the threshold cost analysis in the final model:

```bash
python q4_modelandcost/cost_analysis.py
```

Run the due-date distribution generator:

```bash
python delivery_schedule/due_date_model.py
```

Run the simulation without a matrix:

```bash
python no_matrix.py
```

## Analysis Notes

- `initial_model.py` builds and saves a Markov transition matrix for a 4-day production/shipment cycle.
- `cost_analysis.py` loads a saved matrix, computes the steady-state distribution, and compares shipping costs for different threshold policies.
- `due_date_model.py` generates a probability distribution of daily volumes by due date.
- `no_matrix.py` demonstrates an alternate simulation-based approach using Poisson arrivals and shipment triggers.

## Output Files

Generated CSV files contain transition matrices or cost-analysis results that can be reused for visualization and further analysis.

## Contact

For questions or improvements, update the scripts and add detailed comments to document each model assumption and parameter choice.
