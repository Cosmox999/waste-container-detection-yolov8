# Waste Container Detection using YOLOv8

Object detection system for detecting waste containers using YOLOv8 and the Open Images dataset.

## Overview
This project trains a YOLOv8 model using the Ultralytics framework to detect waste containers in images and videos. The model is trained on a custom dataset derived from the Open Images dataset.

## Features
- Custom dataset preparation
- YOLOv8 training pipeline
- Real-time object detection
- Video inference support
- Bounding box visualization

## Dataset
Dataset used: Open Images – Waste Container class

Dataset Link:
https://drive.google.com/drive/folders/1tf70blWnr-JqCh4zkpTNhgKwN3mzbLec

## Results

Model Performance

mAP@0.5 : 0.73  
F1 Score : 0.73  
Precision : 1.00 (at 0.92 confidence)

Results:
https://drive.google.com/drive/folders/1IVQTMe8PEdEVpj1uBONceOzVc8QjVzXU

## Installation

Clone the repository

git clone https://github.com/YOUR_USERNAME/waste-container-detection-yolov8.git

Install dependencies

pip install ultralytics opencv-python numpy matplotlib

## Training

Run training using:

python train.py

## Inference

python detect.py

## Project Structure

notebooks/project.ipynb – main training notebook  
results/ – output predictions and evaluation  
images/ – sample detection outputs

## Tech Stack

Python  
YOLOv8 (Ultralytics)  
OpenCV  
PyTorch  

## Author

Ganesh Sonawane  
B.Tech Energy Science and Engineering  
IIT Bombay
