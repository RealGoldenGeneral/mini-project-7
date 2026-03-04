Mini Project 7 — Blood Cell Detection with YOLO26

Course: COMP 9130 — Applied Artificial Intelligence
Project: Object Detection in Medical Imaging
Group: 2

Team Members:

Aristide Kanamugire

Nicky Cheng

GitHub Repository:
https://github.com/RealGoldenGeneral/mini-project-7

📌 Project Overview

This project develops an object detection system for identifying and localizing blood cells in microscopic blood smear images. The model detects three clinically relevant cell types:

Red Blood Cells (RBC)

White Blood Cells (WBC)

Platelets

Automated blood cell detection is a critical component of complete blood count (CBC) analysis. In high-volume pathology labs, thousands of samples are processed daily, and manual review is time-consuming. An accurate AI-assisted system can help prioritize abnormal samples, reduce turnaround time, and support pathologists without replacing clinical judgment.

📂 Dataset

Dataset: Blood Cell Count and Detection (BCCD)
Source: Roboflow Universe
Detection Classes: RBC, WBC, Platelets
Images: ~364 annotated blood smear images

The dataset is provided in YOLO format and includes predefined train / validation / test splits with bounding box annotations.

Dataset Structure

blood_cell_yolo/
├── train/
│   ├── images/
│   └── labels/
├── valid/
│   ├── images/
│   └── labels/
├── test/
│   ├── images/
│   └── labels/
└── data.yaml

⚙️ Environment Setup
Requirements

Python 3.9+

Google Colab (GPU runtime recommended)

NVIDIA T4 GPU or equivalent

Install Dependencies
pip install ultralytics opencv-python matplotlib pyyaml
▶️ How to Run the Project

Upload the dataset ZIP file (complete blood cell count.v1i.yolov8.zip) to Google Colab

Unzip the dataset

(Recommended) Rename the extracted folder to avoid path issues:

mv "complete blood cell count.v1i.yolov8" blood_cell_yolo

Open the provided Jupyter notebook

Run all cells sequentially:

Dataset loading

Model training

Evaluation

Visualization

All code runs end-to-end without errors when executed in order.

🧠 Model Details

Architecture: YOLO26s

Framework: Ultralytics

Pretrained Weights: COCO

Epochs: 25

Image Size: 640

Batch Size: 16

Transfer learning is used to adapt a general object detector to the medical imaging domain.

📊 Results Summary

Validation performance after 25 epochs:

mAP@50: 0.948

mAP@50–95: 0.721

Precision: 0.921

Recall: 0.892

Per-class mAP@50:

RBC: 0.970

WBC: 0.960

Platelets: 0.912

The model performs best on RBC due to class dominance and clear visual patterns, while platelet detection remains more challenging due to small object size and class imbalance.

👥 Team Contributions

Aristide Kanamugire

Dataset handling and preprocessing

YOLO training and evaluation

Notebook implementation and experiments

Nicky Cheng

Experimental design and hyperparameter analysis

Results interpretation

Documentation and report refinement
