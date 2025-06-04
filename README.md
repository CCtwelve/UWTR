# High-Precision Underwater Turbidity Removal for 3D Structured Light Reconstruction Using Division-of-Focal-Plane Polarization

## Overview
This repository contains the implementation of our novel underwater 3D reconstruction system that combines temporal-multiplexing structured light with polarization imaging to achieve accurate reconstruction in turbid underwater environments. Our method addresses the challenges posed by suspended particles in water that degrade traditional image-based 3D reconstruction methods.

## Dataset
We provide a sample dataset captured using our polarization imaging system:
[Download Dataset Sample](https://drive.google.com/file/d/1QpZIhsUIWLAgQCXWXdj865gSNkjpCRrd/view?usp=drive_link)

The full dataset includes:
- various different underwater objects
- Images captured at 4 polarization angles (0°, 45°, 90°, 135°)

## Usage
### Data Preparation
1. Download and extract the dataset
2. Organize the data in the following structure:
```
data/
├── Pomfret/
│   ├── 1/          # 0° polarization images
│   │   ├── 1.bmp
│   │   ├── 2.bmp
│   │   └── ...     # up to 18.bmp
│   ├── 2/          # 45° polarization images
│   ├── 3/          # 90° polarization images
│   └── 4/          # 135° polarization images
├── Conch/
│   ├── 1/
│   ├── 2/
│   ├── 3/
│   └── 4/
├── Stone/
│   ├── 1/
│   ├── 2/
│   ├── 3/
│   └── 4/
└── ...             # other objects

Here's the updated GitHub README section that clearly explains the code availability status and future release plans:

## Code Availability
### Release Plan:
- We will open-source the complete codebase upon paper acceptance


