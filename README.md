# Hybrid-Deep-Learning-Cyclone-Eye-Detection-
Hybrid Deep Learning framework for tropical cyclone eye localization using satellite thermal imagery.
# Automated Cyclone Eye Localization Using Hybrid Deep Learning

## Overview
This project presents a hybrid deep learning framework for automatic localization of tropical cyclone eyes from satellite thermal imagery. The approach combines classical image processing techniques with a YOLOv8-based deep learning model to improve robustness under land–sea thermal interference.

## Dataset
- **Training:** Gonu cyclone satellite thermal images (30 images, augmented to 96)
- **Testing:** Hudhud cyclone satellite images (31 refined images)
- Images are preprocessed using a custom normalization strategy to enhance cyclone eye visibility.

## Preprocessing
- Custom **0–10 → 255 normalization** to generate a "White-Eye" signature.
- NaN/space regions mapped to 0.
- Classical pre-filters:
  - K-Means clustering
  - Hierarchical Otsu thresholding

## Methodology
Five comparative tasks were evaluated:
1. Otsu Thresholding (baseline)
2. K-Means Clustering (baseline)
3. Standalone YOLOv8 model
4. K-Means + YOLOv8 (hybrid)
5. Otsu + YOLOv8 (hybrid)

## Results
- Hybrid preprocessing improved cyclone eye localization accuracy by **15.4%** compared to standalone deep learning.
- Pre-filtering effectively removed land-based thermal interference, enabling better feature extraction.

## Tech Stack
Python, OpenCV, YOLOv8, TensorFlow, K-Means, Otsu Thresholding

## Usage
1. Run preprocessing scripts from `/preprocessing`
2. Train YOLOv8 using `/yolo_training/train.py`
3. Perform inference using `/yolo_training/infer.py`

## Future Work
- Temporal cyclone tracking
- Intensity estimation
- Integration with early warning systems

