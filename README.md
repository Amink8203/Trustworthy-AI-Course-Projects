# Trustworthy AI · Course Projects

**University of Tehran** · **Amin Aghakasiri**

![Python](https://img.shields.io/badge/Python-3.12-3776AB?logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebooks-F37626?logo=jupyter&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-Deep%20Learning-EE4C2C?logo=pytorch&logoColor=white)
![Assignments](https://img.shields.io/badge/Assignments-4-2563EB)

Programming assignments exploring how machine learning systems behave under spurious correlations, adversarial perturbations, causal interventions, demographic bias, and privacy attacks. Each project includes implementation notebooks, a written report, and the assignment specification.

**[Projects](#projects)** · **[Getting started](#getting-started)** · **[Data and model setup](docs/DATASETS.md)**

## Projects

| Project | Focus | Implementation | Written work |
| --- | --- | --- | --- |
| **[CA1](CA1/README.md)** | Robustness & adversarial attacks | [Robust training](CA1/Q1/CA1_Q1.ipynb): ERM, JTT-style upsampling, and generalized cross entropy. [Adversarial attacks](CA1/Q2/CA1_Q2.ipynb): FGSM and PGD on CIFAR-10. | [Report](CA1/CA1_report.pdf) · [Specification](CA1/TAI_CA1_Description.pdf) |
| **[CA2](CA2/README.md)** | Visual interpretability | [LIME](CA2/Q1/q1.ipynb): segmentation, perturbation sampling, and a local surrogate. [Class activation maps](CA2/Q2/q2.ipynb): Grad-CAM, guided Grad-CAM, and FinerGrad-CAM. | [Report](CA2/CA2_report.pdf) · [Specification](CA2/TAI_CA2_Description.pdf) |
| **[CA3](CA3/README.md)** | Causal reasoning | [Structural causal models](CA3/CA3.ipynb): course-effect and smoking examples, website engagement analysis, and a placebo test. | [Report](CA3/CA3_report.pdf) · [Specification](CA3/TAI_CA3_Description.pdf) |
| **[CA4](CA4/README.md)** | Fairness & privacy | [COMPAS fairness audit](CA4/Q1/Q1.ipynb): proxy features, unawareness, mitigation, and trade-offs. [Federated privacy](CA4/Q2/Q2.ipynb): FEMNIST training, membership inference, and record- and subject-level differential privacy. | [Report](CA4/CA4_report.pdf) · [Specification](CA4/TAI_CA4_Description.pdf) |

## Getting started

To explore the work, open a notebook on GitHub or read its report. Saved plots and outputs are retained in the notebooks.

To run the experiments locally, use Python 3.12, matching the notebook metadata, and create a virtual environment from the repository root.

### Windows / PowerShell

```powershell
python -m venv .venv
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
.\.venv\Scripts\jupyter.exe lab
```

### macOS / Linux

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
jupyter lab
```

CA4 Q2 additionally needs Hugging Face Datasets, Opacus, and notebook progress widgets. Before launching Jupyter, install `requirements-federated.txt` with the same environment's Python:

```powershell
# Windows
.\.venv\Scripts\python.exe -m pip install -r requirements-federated.txt
```

```bash
# macOS / Linux, with the environment activated
python -m pip install -r requirements-federated.txt
```

Open the desired notebook and select the environment's Python kernel. **Run with the notebook's containing folder as the working directory**, since dataset and model paths are relative to it. Execute cells in order; later sections use variables and artifacts created earlier.

Check the [data and model setup guide](docs/DATASETS.md) before running: CA2 needs external images and Tiny ImageNet, and CA4 Q1 needs the COMPAS CSV. CA4 Q2 downloads FEMNIST on its first run and performs substantial training; GPU access helps. CA1 Q2 explicitly defaults to CPU.

## Repository layout

```text
.
├── CA1/
│   ├── Q1/                     # Robust training + MNIST + reference papers
│   ├── Q2/                     # Adversarial attacks + CIFAR-10 samples/model
│   ├── CA1_report.pdf
│   └── TAI_CA1_Description.pdf
├── CA2/
│   ├── Q1/q1.ipynb             # LIME
│   ├── Q2/q2.ipynb             # Grad-CAM variants
│   ├── assets/                 # Shared pretrained ResNet-18 weights
│   ├── CA2_report.pdf
│   └── TAI_CA2_Description.pdf
├── CA3/
│   ├── CA3.ipynb               # Causal modeling and analysis
│   ├── website_engagement_data.csv
│   ├── CA3_report.pdf
│   └── TAI_CA3_Description.pdf
├── CA4/
│   ├── Q1/Q1.ipynb             # Fairness on COMPAS
│   ├── Q2/Q2.ipynb             # Federated learning and privacy on FEMNIST
│   ├── CA4_report.pdf
│   └── TAI_CA4_Description.pdf
├── docs/DATASETS.md
├── requirements.txt
└── requirements-federated.txt
```

Each assignment folder also contains a README with its notebook links and execution notes. Downloaded datasets, virtual environments, and generated CA4 training artifacts are excluded from version control; the bundled course inputs and saved notebook outputs are retained.

## Reproducibility and credits

The dependency lists are based on the notebook imports and are not a locked environment. Saved outputs reflect the original experiments; new runs can vary with library versions, hardware, data, and random seeds. See the reports for the experiment settings and interpretation of results.

The CIFAR model implementation under `CA1/Q2/pytorch-cifar-models/` comes from [chenyaofo/pytorch-cifar-models](https://github.com/chenyaofo/pytorch-cifar-models); its upstream license is preserved. Dataset and model sources are listed in the [setup guide](docs/DATASETS.md).
