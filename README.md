# Cyclic peptide benchmark

Supporting materials for **A benchmark framework to guide automated cyclic peptide discovery** (manuscript in preparation).

The framework evaluates the contribution of model updating, transfer across experimental sources, and calibration of benchmark-validity decisions. The study uses retrospective permeability and binding analyses.

## Contents

This initial public package provides the four manuscript figures, their frozen aggregate input records, extracted plotted values, legends and figure-generation code. It supports figure-level reproduction. It is not yet a complete release of the training, dataset reconstruction or statistical-analysis pipelines.

- `scripts/render_figures.py`: renders the four figures from frozen results and checks input SHA-256 hashes before loading them.
- `results/cluster.json`: source-cluster analysis summaries.
- `results/gate.json`: benchmark-validity calibration summaries.
- `results/transfer.json`: exact-potency screening summaries.
- `results/sources.json`: source-record hashes and historical provenance. Historical paths and commit identifiers refer to the original research checkout, not this repository.
- `figures/`: PDF/PNG figures, legends and plotted values.
- `MANIFEST.json`: SHA-256 inventory of this release's files (excluding the manifest itself).

## Reproduce the figures

On a compute worker with Python 3.10 or later:

```sh
python -m venv .venv
. .venv/bin/activate
python -m pip install -r requirements.txt
python scripts/render_figures.py --data results --out reproduced
```

The dependency ranges describe compatibility requirements, not an exact lockfile for the original rendering environment. This public packaging has not been independently rerun. The frozen inputs and generator were previously used to render the included figures; cross-version rendering may differ. Rendering does not refit models or repeat experiments. Hash checks establish file identity, not scientific validation of every manuscript claim.

## Source data

Original measurements are obtained from [CycPeptMPDB](http://cycpeptmpdb.com/download/), [BindingDB](https://www.bindingdb.org/) and [ChEMBL](https://www.ebi.ac.uk/chembl/). This repository distributes aggregate research outputs, not copies of those databases. Consult each provider for access and applicable terms. Dataset reconstruction scripts, complete split manifests and the remaining analysis code are not included in this initial package.

## Interpretation

Permeability acquisition results use transductive source standardisation. Literature sources are proxies for experimental sites. Held-out ranking and acquisition yield are separate evaluations. Calibration results apply to the tested designs. This package does not establish prospective automated-laboratory discovery gains.

## Citation and reuse

A manuscript DOI and archival release DOI have not yet been assigned. Cite this repository URL and the exact commit when referring to this package. A software reuse licence has not yet been designated; no licence for the underlying databases is conferred by publication of this repository.
