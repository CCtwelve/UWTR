# Underwater 3D Structured Light Reconstruction with Polarization Imaging

## Overview
This repository contains the implementation of our novel underwater 3D reconstruction system that combines temporal-multiplexing structured light with polarization imaging to achieve accurate reconstruction in turbid underwater environments. Our method addresses the challenges posed by suspended particles in water that degrade traditional image-based 3D reconstruction methods.

Key features:
- Polarized structured light system for robust underwater imaging
- Underwater Turbidity Removal Network (UTR-Net) for enhanced image quality
- Comprehensive dataset of 300 underwater objects (648,000 high-res images)
- State-of-the-art reconstruction accuracy in turbid conditions

## Dataset
We provide a sample dataset captured using our polarization imaging system:
[Download Dataset Sample](https://drive.google.com/file/d/1QpZIhsUIWLAgQCXWXdj865gSNkjpCRrd/view?usp=drive_link)

The full dataset includes:
- 300 different underwater objects
- Images captured at 4 polarization angles (0°, 45°, 90°, 135°)
- Corresponding second Stokes parameter (S₂) and Degree of Polarization (DoP) maps
- Ground truth 3D models for evaluation

## Installation
1. Clone this repository:
```bash
git clone https://github.com/yourusername/underwater-3d-reconstruction.git
cd underwater-3d-reconstruction
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

## Usage
### Data Preparation
1. Download and extract the dataset
2. Organize the data in the following structure:
```
data/
├── raw_images/
│   ├── object_001/
│   │   ├── 0deg.png
│   │   ├── 45deg.png
│   │   ├── 90deg.png
│   │   └── 135deg.png
│   └── ...
├── stokes_maps/
└── dop_maps/
```

### Running the UTR-Net
To process images through our Underwater Turbidity Removal Network:
```python
from models.utr_net import UTRNet

model = UTRNet()
model.load_weights('weights/utr_net_weights.h5')

# Process a batch of polarization images
cleaned_images = model.predict([img_0deg, img_45deg, img_90deg, img_135deg])
```

### 3D Reconstruction
To perform full 3D reconstruction:
```python
from reconstruction.pipeline import StructuredLightReconstructor

reconstructor = StructuredLightReconstructor()
point_cloud = reconstructor.reconstruct(cleaned_images)
```

## System Architecture
Our polarized structured light system consists of:
1. A digital projector with polarizer
2. A division-of-focal-plane polarization camera
3. Our UTR-Net with:
   - Fringe Capture Block (FCB) for local feature extraction
   - Global Contour Capture Block (GCCB) for object edge detection

## Results
Our method demonstrates significant improvements over state-of-the-art methods in:
- Reconstruction accuracy (reduced RMSE by 37%)
- Edge preservation in turbid conditions
- Computational efficiency

Sample results are available in the `results/` directory.

## Citation
If you use this work in your research, please cite our paper:
```bibtex
@article{underwater2024,
  title={Underwater 3D Structured Light Reconstruction with Polarization Imaging},
  author={Your Name, Coauthors},
  journal={Journal Name},
  year={2024}
}
```

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contact
For questions or collaborations, please contact: your.email@institution.edu
