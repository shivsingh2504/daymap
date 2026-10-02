# Daymap

Daymap is a city-independent activity recommendation and itinerary-planning project, starting with Bengaluru. The shared data schema and processing logic should support additional cities through data and configuration changes.

## Project status

This repository currently contains the initial project scaffold. Data collection and recommendation code have not yet been implemented.

## Project layout

- `data/raw/` — source snapshots and intermediate downloads; keep licensed or restricted source data out of Git unless its terms allow redistribution.
- `data/processed/` — normalized activity datasets and validation reports.
- `data/synthetic/` — generated profiles and synthetic preference labels, kept separate from real activity data.
- `notebooks/` — exploratory analysis and project experiments.
- `src/daymap/` — reusable Python package modules for data, features, models, recommendation, optimization, and utilities.
- `tests/` — automated checks for schemas and pipeline behavior.
- `configs/` — city metadata, source settings, shared taxonomy, and generation configuration.
- `scripts/` — command-line entry points for pipeline tasks.

## Data and model limitations

No survey or human preference-rating data will be collected. Synthetic labels are generated from explicit rules and must never be described as observed human preferences. Good performance on synthetic holdouts does not establish real-world preference accuracy.

Missing real-world values must remain explicit: unknown price is not free, unknown ratings are not fabricated, and imputed values must be marked as imputed with their method recorded.

## Setup

Use the project virtual environment and the dependencies in `requirements.txt`. The dependency list will be reviewed and narrowed to the needs of each implementation phase before adding new packages.

## Data-source policy

Record source and retrieval provenance for imported fields. Check each source's license, attribution, storage, and redistribution rules before retaining or publishing its data. OpenStreetMap-derived data requires appropriate attribution and ODbL handling. Do not bulk-copy BLR // EATS data unless its owner provides clear reuse permission or licensing terms.
