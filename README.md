# MSGM: Whole Slide Image Matching
This repository contains the source code for MSGM, an open-source tool designed to match whole slide histopathology images (WSIs) to provide comprehensive information on homologous tissues, aiding in cancer diagnosis. 

(We are working on the final version of the code and will upload the open source code by July 20, 2024 at the latest.)

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
The Training Script provides a step-by-step guide to train TDescNet for deep descriptor extraction. You can find the script in the scripts directory of the repository.

```bash
cd scripts
python training_script.py
```

This script includes data loading, model initialization, and training procedures necessary to obtain the deep descriptors for accurate whole slide image matching.

## Usage
Here's a quick example to get you started:

```bash
import msgm

# Load your whole slide images
image1 = msgm.load_wsi('path/to/your/image1.tif')
image2 = msgm.load_wsi('path/to/your/image2.tif')

# Perform matching
matches = msgm.match_images(image1, image2)

# Visualize the results
msgm.visualize_matches(image1, image2, matches)
```

## License
This project is licensed under the Apache-2.0 License. 

## Acknowledgements
We would like to thank the contributors and the open-source community for their invaluable support.
