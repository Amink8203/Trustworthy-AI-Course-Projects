# CA4 · Fairness and privacy

[← All projects](../README.md) · [Report](CA4_report.pdf) · [Assignment specification](TAI_CA4_Description.pdf)

## Q1 — Fairness on COMPAS

[Open the notebook](Q1/Q1.ipynb)

The notebook audits group differences in the COMPAS dataset, explores features that act as proxies for race, builds a logistic regression baseline, tests fairness through unawareness, and compares mitigation strategies and their trade-offs.

Run from `CA4/Q1/`. Download `compas-scores-two-years.csv` from ProPublica into that folder first; it is not bundled. The [setup guide](../docs/DATASETS.md#ca4-q1--compas) includes the source and a download command.

## Q2 — Federated learning, membership inference, and differential privacy

[Open the notebook](Q2/Q2.ipynb)

The notebook loads FEMNIST, partitions writers across eight silos, trains a federated model, and evaluates membership inference at both record and subject levels. Later sections compare differential privacy defenses and the resulting privacy–utility trade-offs.

Install `requirements-federated.txt` using the root [environment instructions](../README.md#getting-started), then run from `CA4/Q2/`.

- The first data-loading cell downloads `flwrlabs/femnist` from Hugging Face. Internet access and space for its cache are required.
- Run data preparation, federated training, and membership inference before the differential privacy experiments. Those sections reuse partitions, checkpoints, and evaluation artifacts.
- The baseline trains for 10 rounds. A later continuation section adds another 10; rerunning that section can extend an existing run again.
- Training and the differential privacy comparisons can be expensive. GPU access helps, and reducing round counts changes the experiment settings and results.
- Generated `femnist_*` directories are ignored by Git. Keep any outputs you want to archive separately before cleaning them.

Saved outputs are retained for inspection without retraining. Consult the report for the experimental comparisons.
