# Waste Container Detection — YOLOv8

<p align="left">
  <img src="https://img.shields.io/badge/Python-3.10+-3776AB?style=flat&logo=python&logoColor=white"/>
  <img src="https://img.shields.io/badge/YOLOv8-Ultralytics-FF6B35?style=flat"/>
  <img src="https://img.shields.io/badge/PyTorch-2.0+-EE4C2C?style=flat&logo=pytorch&logoColor=white"/>
  <img src="https://img.shields.io/badge/OpenCV-4.x-5C3EE8?style=flat&logo=opencv&logoColor=white"/>
  <img src="https://img.shields.io/badge/Dataset-Open_Images-4285F4?style=flat&logo=google&logoColor=white"/>
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat"/>
</p>

> End-to-end object detection pipeline that trains YOLOv8n on the Open Images waste container class, achieving **mAP@0.5 = 0.73** with real-time video inference support.

---

## Problem Statement

Waste management systems lack automated detection of overflow or misplaced containers. Manual monitoring is labour-intensive and error-prone. This project builds a production-ready computer vision pipeline — from dataset preparation through model training to real-time video inference — that can identify waste containers in images and video streams.

---

## Pipeline

```
Open Images Dataset (Waste Container class)
            │
            ▼
  ┌─────────────────────┐
  │  Dataset Preparation │  YAML config, train/val split
  └─────────────────────┘
            │
            ▼
  ┌─────────────────────┐
  │   YOLOv8n Training  │  50 epochs, imgsz=640, batch=16
  └─────────────────────┘
            │
            ▼
  ┌─────────────────────┐
  │  Model Evaluation   │  mAP@0.5, F1, Precision/Recall curves
  └─────────────────────┘
            │
            ▼
  ┌─────────────────────┐
  │   Video Inference   │  conf=0.5, bounding box overlay
  └─────────────────────┘
```

---

## Results

| Metric | Value |
|--------|-------|
| mAP@0.5 | **0.73** |
| F1 Score | **0.73** |
| Precision | **1.00** (at 0.92 confidence threshold) |
| Training Epochs | 50 |
| Input Size | 640 × 640 |

Full training plots and inference samples: [Google Drive Results](https://drive.google.com/drive/folders/1IVQTMe8PEdEVpj1uBONceOzVc8QjVzXU)

---

## Dataset

**Source:** [Open Images Dataset](https://storage.googleapis.com/openimages/web/index.html) — Waste Container class

**Prepared dataset (train/val split + YAML config):** [Google Drive](https://drive.google.com/drive/folders/1tf70blWnr-JqCh4zkpTNhgKwN3mzbLec)

The dataset was configured with a YAML file specifying class names and paths — plugged directly into the Ultralytics `model.train()` API.

---

## Tech Stack

| Component | Technology |
|-----------|-----------|
| Object Detection | YOLOv8n (Ultralytics) |
| Deep Learning Framework | PyTorch |
| Image Processing | OpenCV |
| Visualisation | Matplotlib |
| Language | Python 3.10+ |

---

## Features

- **Custom YAML dataset config** — train/val split prepared for Ultralytics API
- **YOLOv8n training** — lightweight nano model, 50 epochs, imgsz=640, batch=16
- **Evaluation plots** — precision/recall curves, F1 curve, confusion matrix
- **Video inference** — frame-by-frame detection with bounding box overlay at conf=0.5
- **Google Drive integration** — dataset and results hosted for reproducibility

---

## Installation

```bash
# 1. Clone the repository
git clone https://github.com/Cosmox999/waste-container-detection-yolov8.git
cd waste-container-detection-yolov8

# 2. Create and activate a virtual environment
python -m venv venv
venv\Scripts\activate        # Windows
# source venv/bin/activate   # macOS/Linux

# 3. Install dependencies
pip install -r requirements.txt
```

---

## Usage

1. Download the prepared dataset from the [Google Drive link](https://drive.google.com/drive/folders/1tf70blWnr-JqCh4zkpTNhgKwN3mzbLec)
2. Open [`notebooks/waste_container_detection_yolov8.ipynb`](notebooks/waste_container_detection_yolov8.ipynb)
3. Update the dataset path in the YAML config cell
4. Run all cells — training, evaluation, and video inference are fully sequential

---

## Project Structure

```
├── notebooks/
│   └── waste_container_detection_yolov8.ipynb   # Full pipeline: train → evaluate → infer
├── experiments/
│   └── assignment1_exploration.ipynb            # Early dataset exploration
├── requirements.txt
├── .gitignore
├── LICENSE
└── README.md
```

---

## Future Improvements

- **Multi-class detection** — extend to other waste categories (bins, bags, litter)
- **Transfer learning** — fine-tune YOLOv8m/l for higher mAP
- **Edge deployment** — export to ONNX/TensorRT for embedded systems
- **Real-time stream** — connect to IP camera feed via OpenCV VideoCapture

---

## Author

**Ganesh Pandurang Sonawane**
Indian Institute of Technology Bombay

[![GitHub](https://img.shields.io/badge/GitHub-Cosmox999-181717?style=flat&logo=github)](https://github.com/Cosmox999)
