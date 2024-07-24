# MSGM: Whole Slide Image Matching

Tittle: MSGM: An Advanced Deep Multi-Size Guiding Matching Network for Whole Slide Histopathology Images Addressing Staining Variation and Low Visibility Challenges.

This repository contains the source code for MSGM, an open-source tool designed to match whole slide histopathology images (WSIs) to provide comprehensive information on homologous tissues, aiding in cancer diagnosis. 

(To successfully upload to GitHub, we utilized segmented compression, uploading a total of 22 files.)

## Overview
Accurately matching giga-pixel WSIs is crucial for cancer diagnosis but challenging due to their size. MSGM integrates traditional and learning-based methods to enhance accuracy, even for large WSIs. Our matching error is generally less than 200 micrometers compared to manually annotated gold standards, demonstrating potential to assist pathologists in routine diagnostics.

## Features
- **High Accuracy**: Achieves high-accuracy matching using multi-size guiding methods.
- **Advanced Descriptors**: Utilizes TDescNet for training deep descriptors (C64 and C256) and 3D-ring descriptors to handle staining variation and low visibility.
- **Progressive Matching**: Employs C64, C256, and 3D-ring descriptors for refined local matching with geometric consistency.
- **Performance**: Matches 4096×4096 pixel WSIs with an average error of 123.48 μm and a 93.02% success rate.

## Platform
MSGM is computed on a 64-bit Windows 10 system with Python, utilizing a 12th Gen Intel Core i9-12900K CPU running at 3.9 GHz with 32.0 GB of RAM, and an Nvidia GeForce GTX 1080Ti with 11 GB of memory.

## Training Models
To train the deep descriptors used in MSGM, follow the instructions provided in the Training Script.

Training Script

You can run TrainDescriptorNet.py to complete the model training. The pretrained model can be found at the path "ModelParameter/descriptor_model.pth".

This script includes data loading, model initialization, and training procedures necessary to obtain the deep descriptors for accurate whole slide image matching.

## Usage
We provide a one-click matching solution. Simply run the Demo_matching.py script to automatically complete the entire process, including loading the original images, preprocessing, matching, and storing the results. The path to the original image is "RawCase/HE_UC-1_1". The matching results, including visualizations, paired keypoints and time costs, can be found respectively at the paths "RawCase/HE_UC-1_1/DisplayMatchResult", "RawCase/HE_UC-1_1/MatchResult" and “RawCase/HE_UC-1_1/MatchTime”.

## Reference

```bibtex
@article{li2024msgm,
  title={MSGM: An Advanced Deep Multi-Size Guiding Matching Network for Whole Slide Histopathology Images Addressing Staining Variation and Low Visibility Challenges},
  author={Li, Xiaoxiao and Li, Zhengxiong and Hu, Taobo and Long, Mengping and Ma, Xiao and Huang, Jin and Liu, Yiqiang and Yalikun, Yaxiaer and Liu, Sheng and Wang, Du and others},
  journal={IEEE Journal of Biomedical and Health Informatics},
  year={2024},
  publisher={IEEE}
}

Li X, Li Z, Hu T, et al. MSGM: An Advanced Deep Multi-Size Guiding Matching Network for Whole Slide Histopathology Images
Addressing Staining Variation and Low Visibility Challenges[J]. IEEE Journal of Biomedical and Health Informatics, 2024.
```

## License
This project is licensed under the Apache-2.0 License. 

## Acknowledgements
We would like to thank the contributors and the open-source community for their invaluable support.

