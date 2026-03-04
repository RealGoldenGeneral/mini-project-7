# **Mini Project 7 — Blood Cell Detection with YOLO26**

**Course:** COMP 9130 — Applied Artificial Intelligence  
**Project:** Object Detection in Medical Imaging  
**Group:** 2  

**Team Members:**  
- Aristide Kanamugire  
- Nicky Cheng  

**GitHub Repository:**  
https://github.com/RealGoldenGeneral/mini-project-7  

---

## Project Overview

This project presents the development of an object detection system designed to identify and localize blood cells in microscopic blood smear images. The model detects three clinically significant cell types:

- Red Blood Cells (RBC)  
- White Blood Cells (WBC)  
- Platelets  

Automated blood cell detection plays an essential role in Complete Blood Count (CBC) analysis. In high-throughput pathology laboratories, thousands of samples are processed daily, making manual review both time-consuming and resource-intensive. An accurate AI-assisted detection system can help prioritize abnormal samples, reduce turnaround time, and support pathologists while not replacing clinical expertise.

---

## Dataset

**Dataset:** Blood Cell Count and Detection (BCCD)  
**Source:** Roboflow Universe  

- **Detection Classes:** RBC, WBC, Platelets  
- **Images:** ~364 annotated blood smear images  
- **Format:** YOLO annotation format  
- **Splits:** Predefined train/validation/test sets  

The dataset includes bounding box annotations for each labeled cell instance.

### Dataset Structure

```bash
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
```

---

## Environment Setup

### Requirements

- Python 3.9+  
- Google Colab (GPU runtime recommended)  
- NVIDIA T4 GPU or equivalent  

### Install Dependencies

```bash
pip install ultralytics opencv-python matplotlib pyyaml
```

---

##  How to Run the Project

1. Upload the dataset ZIP file (`complete blood cell count.v1i.yolov8.zip`) to Google Colab.  
2. Unzip the dataset.  
3. *(Recommended)* Rename the extracted folder to avoid path-related issues:

```bash
mv "complete blood cell count.v1i.yolov8" blood_cell_yolo
```

4. Open the provided Jupyter notebook.  
5. Run all cells sequentially:
   - Dataset loading  
   - Model training  
   - Evaluation  
   - Visualization  

When executed in order, the notebook runs end-to-end without errors.

---

##  Model Details

- **Architecture:** YOLO26s  
- **Framework:** Ultralytics  
- **Pretrained Weights:** COCO  
- **Epochs:** 25  
- **Image Size:** 640  
- **Batch Size:** 16  

Transfer learning is applied to adapt a general-purpose object detection model to the medical imaging domain.

---

## Results Summary

Validation performance after 25 training epochs:

- **mAP@50:** 0.948  
- **mAP@50–95:** 0.721  
- **Precision:** 0.921  
- **Recall:** 0.892  

### Per-Class mAP@50

- **RBC:** 0.970  
- **WBC:** 0.960  
- **Platelets:** 0.912  

The model achieves the highest performance on RBC detection, largely due to class dominance and consistent visual patterns. Platelet detection remains comparatively more challenging because of the smaller object size and class imbalance.

---

## Team Contributions

### Aristide Kanamugire
- Dataset handling and preprocessing  
- YOLO model training and evaluation  
- Notebook implementation and experimentation  

### Nicky Cheng
- Experimental design and hyperparameter analysis  
- Results interpretation  
- Documentation and report refinement  

---

This project demonstrates the effectiveness of modern object detection techniques in medical imaging and highlights the potential of AI-assisted systems in supporting clinical workflows.
