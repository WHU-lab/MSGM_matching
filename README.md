# MSGM: Whole Slide Image Matching
This repository contains the source code for MSGM, an open-source tool designed to match whole slide histopathology images (WSIs) to provide comprehensive information on homologous tissues, aiding in cancer diagnosis. 

## Overview
Accurately matching giga-pixel WSIs is crucial for cancer diagnosis but challenging due to their size. MSGM integrates traditional and learning-based methods to enhance accuracy, even for large WSIs. Our matching error is generally less than 200 micrometers compared to manually annotated gold standards, demonstrating potential to assist pathologists in routine diagnostics.

## Features
- **High Accuracy**: Achieves high-accuracy matching using multi-size guiding methods.
- **Advanced Descriptors**: Utilizes TDescNet for training deep descriptors (C64 and C256) and 3D-ring descriptors to handle staining variation and low visibility.
- **Progressive Matching**: Employs C64, C256, and 3D-ring descriptors for refined local matching with geometric consistency.
- **Performance**: Matches 4096×4096 pixel WSIs with an average error of 123.48 μm and a 93.02% success rate.

## Installation
To install MSGM, clone the repository and install the necessary dependencies:

```bash
git clone https://github.com/yourusername/MSGM.git
cd MSGM
pip install -r requirements.txt
```

## Training Models
To train the deep descriptors used in MSGM, follow the instructions provided in the Training Script.

Training Script

You can run TrainDescriptorNet.py to complete the model training. The pretrained model can be found at the path "ModelParameter/descriptor_model.pth".

This script includes data loading, model initialization, and training procedures necessary to obtain the deep descriptors for accurate whole slide image matching.

## Usage
We provide a one-click matching solution. Simply run the Demo_matching.py script to automatically complete the entire process, including loading the original images, preprocessing, matching, and storing the results. The path to the original image is "RawCase/HE_UC-1_1". The matching results, including visualizations, paired keypoints and time costs, can be found respectively at the paths "RawCase/HE_UC-1_1/DisplayMatchResult", "RawCase/HE_UC-1_1/MatchResult" and “RawCase/HE_UC-1_1/MatchTime”.

## License
This project is licensed under the Apache-2.0 License. 

## Acknowledgements
We would like to thank the contributors and the open-source community for their invaluable support.
