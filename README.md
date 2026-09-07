# Explainable Deep Learning for Diabetic Retinopathy Detection

Detecting diabetic retinopathy from fundus (retinal) images using deep learning, with a focus on model explainability (XAI).

## Overview

This project compares multiple convolutional neural network (CNN) architectures for diabetic retinopathy classification into five severity levels (No DR, Mild, Moderate, Severe, Proliferative DR), and applies explainability techniques to interpret model predictions on fundus images.

## Models

| Model | Architecture Summary | Notebook |
|---|---|---|
| ResNet34 | Residual CNN architecture, pretrained on ImageNet and fine-tuned for retinopathy classification | [Open in Colab](https://colab.research.google.com/drive/13d3WHKgJgDnEPj0fYntycsPOemWW2dAA?usp=sharing) |
| MobileNetV2 | Lightweight CNN using depthwise separable convolutions, pretrained on ImageNet and fine-tuned | [Open in Colab](https://colab.research.google.com/drive/1nVmCbu8THIfJ3IUBZswNJ4rhBLTDCk9Z?usp=sharing) |
| AlexNet | Classic deep CNN architecture, pretrained on ImageNet with a fine-tuned classification head | [Open in Colab](https://colab.research.google.com/drive/17PDp7ANIupZNp05_Y2ldM1Ii5WKzmgjz?usp=sharing) |

> Note: These notebooks are hosted on Google Colab. Make sure sharing/view access is enabled if you'd like others to open them. Local copies are also included under [`notebooks/`](./notebooks).

## Libraries & Tools

- **PyTorch / torchvision** — model definition, training, and transfer learning
- **scikit-learn** — evaluation metrics (classification report, confusion matrix)
- **Captum** — Integrated Gradients for explainability
- **OpenCV, Matplotlib, Seaborn** — image processing and visualization
- **NumPy, Pillow** — data handling and image I/O

## Explainability

Two explainability techniques are used to interpret model predictions:
- **Integrated Gradients** (via Captum) — highlights the pixels most responsible for a given prediction.
- **Grad-CAM** — produces class activation heatmaps over the final convolutional layer, showing which regions of the retinal image the model focused on.

## Results

| Model | Test Accuracy |
|---|---|
| ResNet34 | 76.4% |
| MobileNetV2 | 76.7% |
| AlexNet | 74.0% |

## Paper

The full research write-up is included in this repository: [`Explainable_Deep_Learning_for_Diabetic_Retinopathy_Detection.pdf`](./Explainable_Deep_Learning_for_Diabetic_Retinopathy_Detection.pdf)

## Repository structure

```
.
├── notebooks/
│   ├── resnet34.ipynb
│   ├── mobilenet.ipynb
│   └── alexnet.ipynb
├── Explainable_Deep_Learning_for_Diabetic_Retinopathy_Detection.pdf
├── requirements.txt
└── README.md
```

## Getting started

1. Clone the repo and install dependencies:
   ```bash
   git clone https://github.com/Areen-Al04/Diabetic-Retinopathy-Detection.git
   cd Diabetic-Retinopathy-Detection
   pip install -r requirements.txt
   ```
2. Open any notebook in `notebooks/` locally (Jupyter) or in Colab, point the dataset path to a fundus image dataset organized into class folders (`0`–`4`), and run.

## Team

The Python Pirates
