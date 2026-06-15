# Trustworthy AI Course Projects

This repository contains the programming assignments I completed for the Trustworthy AI course at the University of Tehran. Each folder focuses on a different topic in trustworthy and interpretable machine learning, with the work organized as Jupyter notebooks and supporting datasets or model weights.

## Repository Overview

| Folder | Topic | Summary |
| --- | --- | --- |
| `CA1/Q1` | Robust training | Preprocessing, ERM training, error-set extraction, upsampling, retraining, and GCE-based training on MNIST-style data. |
| `CA1/Q2` | Adversarial attacks | Model loading, data loading, and implementation of adversarial attack methods such as FGSM and PGD. |
| `CA2/q1` | LIME | A full LIME pipeline including image segmentation, sample generation, weighting perturbed samples, and local linear explanation. |
| `CA2/q2` | Grad-CAM | Grad-CAM, guided Grad-CAM, and FinerGrad-CAM comparisons for visual explanation of model predictions. |
| `CA3/CA3.ipynb` | Causal / SCM analysis | Structural causal model implementation, course-effect analysis, and website engagement experiments with placebo testing. |

## Included Materials

- `CA1/Q1/Dataset/Mnist` contains the dataset used for the first assignment.
- `CA1/Q2/cifar10_resnet20-4118986f.pt` is the model checkpoint used in the adversarial attack notebook.
- `CA1/Q2/cifar10_correct_samples` stores correctly classified CIFAR-10 samples used for evaluation and visualization.
- `CA2/Model Weights (Q1 & Q2)/resnet18-f37072fd.pth` is the pretrained weight file used in CA2.
- `CA3/website_engagement_data.csv` is the dataset used in the causal analysis notebook.

## How To Use

1. Open the relevant notebook in Jupyter or VS Code.
2. Make sure the corresponding dataset or model file is available at the same relative path.
3. Run the notebook from top to bottom, since later cells often depend on earlier preprocessing and model setup.

## Project Structure

```text
CA1/
	Q1/  -> robust training on MNIST
	Q2/  -> adversarial attacks on CIFAR-10
CA2/
	q1.ipynb  -> LIME explanations
	q2.ipynb  -> Grad-CAM and FinerGrad-CAM
CA3/
	CA3.ipynb -> causal modeling and website engagement analysis
```

## Notes

- The notebooks are intentionally self-contained and include both analysis and implementation steps.
- Some outputs are saved in the notebooks, so opening them in a notebook viewer will preserve the visual explanations and plots.
- If you want, I can also add a cleaner Python environment section or a short per-assignment results summary.
