# CA1 · Robustness and adversarial attacks

[← All projects](../README.md) · [Report](CA1_report.pdf) · [Assignment specification](TAI_CA1_Description.pdf)

## Q1 — Learning with spurious correlations

[Open the notebook](Q1/CA1_Q1.ipynb)

The notebook preprocesses MNIST, trains an empirical risk minimization (ERM) baseline, extracts its error set, and uses JTT-style upsampling to retrain a model. It also implements training with generalized cross entropy (GCE).

Run from `CA1/Q1/`. The four compressed MNIST files are included under `Dataset/Mnist/`. Supporting papers are in `Q1/Articles/`.

## Q2 — Adversarial attacks on CIFAR-10

[Open the notebook](Q2/CA1_Q2.ipynb)

The notebook loads a pretrained ResNet-20 and correctly classified CIFAR-10 samples, constructs FGSM and PGD attacks, and compares clean and attacked predictions.

Run from `CA1/Q2/`. The model checkpoint, 25 sample images, and the local `pytorch-cifar-models` implementation are included. The notebook adds that local implementation to its import path, so a separate package installation is unnecessary.

`DEVICE` defaults to `"cpu"`. Adapt its selection cell if using CUDA or Apple MPS.

See the root [installation instructions](../README.md#getting-started) and [input inventory](../docs/DATASETS.md).
