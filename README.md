# CIFAR-10 Image Classification with PyTorch

A Convolutional Neural Network (CNN) implemented in PyTorch for image classification on the CIFAR-10 dataset.

## Features

- PyTorch implementation
- Custom CNN architecture
- Batch Normalization
- Dropout Regularization
- AdamW Optimizer
- Data Augmentation
  - Random Crop
  - Random Horizontal Flip
- Normalization
- GPU support (CUDA)
- Training history tracking
- Test evaluation

## Dataset

This project uses the **CIFAR-10** dataset loaded from the Hugging Face `datasets` library.

Dataset contains:

- 50,000 training images
- 10,000 test images
- 10 classes

Classes:

- Airplane
- Automobile
- Bird
- Cat
- Deer
- Dog
- Frog
- Horse
- Ship
- Truck


## Model Architecture

```text
Input (3×32×32)

↓

Conv2D (32)
BatchNorm
ReLU
MaxPool

↓

Conv2D (64)
BatchNorm
ReLU
MaxPool

↓

Conv2D (128)
BatchNorm
ReLU
MaxPool

↓

Flatten

↓

Linear (2048 → 256)

↓

BatchNorm

↓

ReLU

↓

Dropout (0.5)

↓

Linear (256 → 10)
```

## Training Configuration

| Parameter | Value |
|-----------|------:|
| Optimizer | AdamW |
| Learning Rate | 1e-3 |
| Weight Decay | 1e-4 |
| Loss Function | CrossEntropyLoss |
| Batch Size | 128 |
| Epochs | 20 |

## Data Augmentation

Training images:

- RandomCrop(32, padding=4)
- RandomHorizontalFlip()
- ToTensor()
- Normalize()

Test images:

- ToTensor()
- Normalize()

## Requirements

```bash
pip install torch torchvision datasets matplotlib numpy
```

## Run

```bash
jupyter-notebook model.ipynb
```

## Output

During training, the script displays:

- Training Loss
- Training Accuracy

Finally, the model is evaluated on the test dataset.

## License

This project is released under the MIT License.
