# Semantic_Segmentation
Multi-Class Semantic Segmentation for PASCAL VOC
# Semantic Segmentation using MobileNetV2 + Attention

A lightweight semantic segmentation project built using PyTorch on the PASCAL VOC 2012 dataset.

The goal of this project was to design a segmentation model that achieves a good balance between **accuracy (Dice Score)** and **computational efficiency (FLOPs)**.

---

## Project Overview

Semantic segmentation is the task of assigning a class label to every pixel in an image.

Instead of simply detecting an object, the model identifies exactly which pixels belong to each object category.

This project was developed as part of a deep learning coursework/competition where both segmentation quality and model efficiency were evaluated.

---

## Dataset

**PASCAL VOC 2012**

* 21 classes (including background)
* RGB images
* Pixel-level annotations
* Custom train/validation split (80:20)

Example classes:

* Person
* Car
* Dog
* Cat
* Bicycle
* Bus
* Chair
* TV Monitor
* Train
* And more...

---

## Model Architecture

The model follows an Encoder–Decoder architecture.

### Encoder

* Pretrained MobileNetV2 backbone
* Transfer learning from ImageNet
* Efficient feature extraction

### Feature Enhancement

* Depthwise Separable Convolutions
* Residual Blocks
* Squeeze-and-Excitation (SE) Attention

### Bottleneck

* ASPP-lite module
* Multi-scale context aggregation

### Decoder

* Skip Connections
* Spatial Attention Gates
* Progressive Upsampling

---

## Training Strategy

### Data Preprocessing

* Image resizing (300 × 300)
* ImageNet normalisation

### Data Augmentation

* Horizontal flipping
* Spatial transformations
* Photometric augmentations

### Optimization

* AdamW Optimiser
* OneCycleLR Scheduler
* Mixed Precision Training (AMP)
* Early Stopping

### Loss Function

Hybrid Loss:

Loss = CrossEntropyLoss + DiceLoss

This helps improve segmentation quality while handling class imbalance.

---

## Evaluation Metric

### Macro Dice Score

The primary evaluation metric is Macro Dice Score across all 21 classes.

A higher Dice score indicates better overlap between predicted masks and ground truth masks.

---

## Results

### Final Performance

Macro Dice Score: **~65%**

The model successfully achieved strong segmentation performance while maintaining computational efficiency.

---

## Experiments Performed

* Dataset visualisation
* Data augmentation analysis
* Training and validation monitoring
* FLOPs calculation
* Parameter analysis
* Noise robustness testing
* Prediction visualization

## Technologies Used

* Python
* PyTorch
* TorchVision
* NumPy
* Matplotlib
* PIL
* ptflops
* Jupyter Notebook

## Future Improvements

* Transformer-based decoders
* Knowledge distillation
* TensorRT deployment
* Real-time inference optimisation

---

## Repository

GitHub Repository:

https://github.com/sakshiSakshi/Semantic_Segmentation

