# pcb-defect-detection-yolov12
Automated PCB defect detection using YOLOv12, with CLAHE and bilateral filtering preprocessing for improved detection of small, low-contrast defects. Achieves +2.43% mAP@50 over the YOLOv12n baseline.

# PCB Defect Detection using YOLOv12 with CLAHE and Bilateral Filtering

Final-year thesis project (Universiti Teknikal Malaysia Melaka) on automated PCB defect detection, combining an optimized image preprocessing pipeline with YOLOv12 to improve detection accuracy on small, low-contrast defects.

## Overview

Printed circuit board (PCB) defect inspection is traditionally manual, slow, and error-prone. This project builds an automated detection pipeline that:

- Applies **CLAHE (Contrast Limited Adaptive Histogram Equalization)** and **bilateral filtering** to enhance defect visibility while preserving edges
- Trains and compares **YOLOv8n, YOLOv11n, and YOLOv12n** on PCB defect datasets
- Benchmarks the optimized pipeline against a published YOLOv12n baseline (Yang et al.)

## Result
**+2.43% mAP@50** over YOLOv12n baseline.
**+4.94% mAP@50** over Yang et al.'s YOLOv12n baseline, using an apple-to-apple comparison on the same dataset split.

Preprocessing parameters were tuned via grid search:
- CLAHE: `clipLimit=3.0`, `tileGridSize=4×4`
- Bilateral filter: `d=15`, `σ_color=100`, `σ_space=100`

## Datasets

- [PKU-Market-PCB](https://robotics.pkusz.edu.cn/resources/dataset/)
- [norbertelter/pcb-defect-dataset](https://www.kaggle.com/datasets/norbertelter/pcb-defect-dataset) (Kaggle)

## Tech Stack

`Python` · `Ultralytics YOLO` · `OpenCV` · `Kaggle` · `Google Colab Pro (T4×2)`

## Method Summary

1. Preprocess raw PCB images with CLAHE + bilateral filtering
2. Train YOLOv8n, YOLOv11n, and YOLOv12n on both raw and preprocessed data
3. Evaluate using mAP@50 and recall across all variants
4. Run data leakage checks to ensure valid train/val/test splits
5. Compare best-performing configuration against published baseline

## Author

Wan Muhammad Afif — Computer Engineering, UTeM (2026)
[Portfolio]([https://Fyrehyer.github.io](https://github.com/FyreHyer)) · [LinkedIn](www.linkedin.com/in/fyrehyer)
