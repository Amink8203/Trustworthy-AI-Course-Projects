# Data and model setup

[← Repository overview](../README.md)

All paths below are relative to the repository root. Run each notebook from its containing directory.

## Input inventory

| Notebook | Input | Expected location | Availability |
| --- | --- | --- | --- |
| CA1 Q1 | Four MNIST IDX gzip files | `CA1/Q1/Dataset/Mnist/` | Included |
| CA1 Q2 | CIFAR-10 ResNet-20 checkpoint | `CA1/Q2/cifar10_resnet20-4118986f.pt` | Included |
| CA1 Q2 | 25 labeled CIFAR-10 images | `CA1/Q2/cifar10_correct_samples/` | Included |
| CA2 Q1 & Q2 | ImageNet ResNet-18 checkpoint | `CA2/assets/resnet18-f37072fd.pth` | Included; shared by both notebooks |
| CA2 Q1 | Cat and polar bear examples | `CA2/Q1/cat.jpg`, `CA2/Q1/polarBear.png` | Supply locally |
| CA2 Q2 | Tiny ImageNet | `CA2/Q2/tiny-imagenet-200/` | Download separately |
| CA3 | Website engagement CSV | `CA3/website_engagement_data.csv` | Included |
| CA4 Q1 | COMPAS two-year scores CSV | `CA4/Q1/compas-scores-two-years.csv` | Download separately |
| CA4 Q2 | FEMNIST | `CA4/Q2/femnist_cache/` | Downloaded by the notebook |

## CA1 — Bundled inputs

The MNIST folder contains `train-images-idx3-ubyte.gz`, `train-labels-idx1-ubyte.gz`, `t10k-images-idx3-ubyte.gz`, and `t10k-labels-idx1-ubyte.gz`. Leave them compressed: Q1 reads them with Python's gzip module.

Q2 uses the included model implementation from [chenyaofo/pytorch-cifar-models](https://github.com/chenyaofo/pytorch-cifar-models), its ResNet-20 checkpoint, and the labeled PNG samples. Their existing filenames are used to extract the true labels.

## CA2 — Shared model and external images

Both notebooks load `../assets/resnet18-f37072fd.pth`. One shared copy is included so the model does not need to be duplicated in each question folder. The checkpoint is the torchvision ResNet-18 weight file; its upstream download is [download.pytorch.org/models/resnet18-f37072fd.pth](https://download.pytorch.org/models/resnet18-f37072fd.pth).

For Q1, provide the original `cat.jpg` and `polarBear.png` if available. Otherwise, use your own examples and adjust the notebook's image paths and target ImageNet class indices. The saved plots represent the original images and will differ when other images are used.

For Q2, download the [Tiny ImageNet archive hosted by Stanford](http://cs231n.stanford.edu/tiny-imagenet-200.zip) and extract the `tiny-imagenet-200` folder into `CA2/Q2/`:

```text
CA2/Q2/tiny-imagenet-200/
├── train/
├── val/
├── test/
├── wnids.txt
└── words.txt
```

The extracted dataset is ignored by Git.

## CA3 — Website engagement

The CSV is bundled beside `CA3.ipynb` and was preserved from the previous version of this course repository. No separate download is needed.

## CA4 Q1 — COMPAS

Use ProPublica's [compas-scores-two-years.csv](https://github.com/propublica/compas-analysis/blob/master/compas-scores-two-years.csv) from the original [COMPAS analysis repository](https://github.com/propublica/compas-analysis). Download the raw CSV rather than saving the GitHub HTML page.

From the repository root in PowerShell:

```powershell
Invoke-WebRequest -Uri "https://raw.githubusercontent.com/propublica/compas-analysis/master/compas-scores-two-years.csv" -OutFile "CA4/Q1/compas-scores-two-years.csv"
```

The downloaded CSV is ignored by Git. The notebook applies its own filtering before splitting and analyzing the data.

## CA4 Q2 — FEMNIST

The notebook calls `datasets.load_dataset("flwrlabs/femnist", split="train", ...)` and stores the download in `femnist_cache/`. See the [Flower Labs FEMNIST dataset card](https://huggingface.co/datasets/flwrlabs/femnist) for source details.

It creates local directories for prepared data, baseline federated training, attacks, and differential privacy experiments. These generated `femnist_*` folders are excluded from version control. They are needed by later cells during a run, so do not remove them between experiment stages.
