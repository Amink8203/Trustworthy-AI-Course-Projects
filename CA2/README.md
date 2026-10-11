# CA2 · Visual interpretability

[← All projects](../README.md) · [Report](CA2_report.pdf) · [Assignment specification](TAI_CA2_Description.pdf)

## Q1 — LIME from scratch

[Open the notebook](Q1/q1.ipynb)

The implementation segments images with a NumPy k-means routine, samples masked perturbations, weights them by proximity, and fits a sparse local surrogate with Lasso. Cat and polar bear examples visualize the resulting segment contributions.

Run from `CA2/Q1/`. The notebook uses the shared checkpoint at `../assets/resnet18-f37072fd.pth`. Supply `cat.jpg` and `polarBear.png` in `Q1/` before running. The original example images are absent from the supplied folders and the previous repository; replacing them changes the resulting explanations.

The examples inspect ImageNet class indices 282 and 296. If using other kinds of images, update the target class indices as well as the image paths.

## Q2 — Grad-CAM and its variants

[Open the notebook](Q2/q2.ipynb)

The notebook implements Grad-CAM, guided Grad-CAM, and FinerGrad-CAM, then compares the visual explanations of ResNet-18 predictions.

Run from `CA2/Q2/`. It uses the same shared checkpoint as Q1. Extract Tiny ImageNet into `Q2/tiny-imagenet-200/`, preserving its `train/`, `val/`, `test/`, `wnids.txt`, and `words.txt` structure.

See the [data and model setup guide](../docs/DATASETS.md) for download links and the root [installation instructions](../README.md#getting-started) for Python dependencies.
