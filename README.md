# Aimonk Multi-label Classification Assignment

## Overview
This project implements a multi-label image classification system using a pretrained ResNet18 model. 
Each image can have multiple labels (4 attributes), and missing labels (NA) are handled using masking during training.

## Model Architecture
- Pretrained ResNet18 (Torchvision)
- Final fully connected layer modified to 4 outputs
- Sigmoid activation for multi-label prediction

## Dataset Handling
- Custom PyTorch Dataset class (MultiLabelDataset)
- Handles NA labels safely using masks
- Image resizing: 224x224
- ImageNet normalization applied

## Loss Function
- BCEWithLogitsLoss for multi-label classification
- Masking applied to ignore NA labels
- NaN-safe loss computation implemented

## Training Details
- Optimizer: Adam
- Epochs: 3
- Image Size: 224x224
- Framework: PyTorch
- Loss curve title: "Aimonk_multilabel_problem"

## Key Challenges Solved
- Fixed NaN loss issue
- Handled missing labels (NA)
- Corrected output dimension mismatch (1000 → 4)
- Implemented stable masked loss function

## Inference
Single image inference implemented using:
- model.eval()
- torch.no_grad()
- Sigmoid probability output
- Binary thresholding for final labels

## Files Included
- train.ipynb → Training + inference code
- multilabel_model.pth → Trained model weights
- README.md → Project explanation

## Author
Hari Priya R
