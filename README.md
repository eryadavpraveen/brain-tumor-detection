# 🧠 Brain Tumor Detection using YOLO

A deep learning project for detecting brain tumors from MRI images using YOLO (You Only Look Once) object detection.

# 📌 Project Overview

This project trains a custom YOLO model to detect tumor regions in brain MRI scans.

- 📷 Input: Brain MRI images

- 🎯 Output: Bounding box around tumor

- 🧠 Model: YOLO (Ultralytics)

- 🔍 Task: Object Detection

# 🗂 Project Structure
```bash
brain-tumor-detection/
│── dataset/
│   ├── images/
│   ├── labels/
│── runs/
│── train.py
│── predict.py
│── data.yaml
│── requirements.txt
│── README.md
```
# 📊 Dataset

Dataset contains annotated brain MRI images in YOLO format.

Each image has a corresponding .txt label file:
```bash
class_id x_center y_center width height
```
You can use datasets from:
- Kaggle Brain MRI Dataset
- Custom annotated dataset

⚠️ Dataset is not uploaded due to GitHub size limits.


