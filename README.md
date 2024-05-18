# MSGM: Whole Slide Image Matching

This repository contains the source code for MSGM, an open-source tool designed to match whole slide histopathology images (WSIs) to provide comprehensive information on homologous tissues, aiding in cancer diagnosis. (The methods and results described in this repository are based on ongoing research currently under peer review.)

## Overview

Accurately matching Giga-pixel WSIs is crucial for cancer diagnosis but challenging due to their large size. MSGM enhances accuracy by integrating traditional matching methods with learning-based approaches, even for large WSIs.

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
