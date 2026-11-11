# 🚶 WalkGuardian – AI-Based Object Detection System

### Intelligent Object Detection using YOLOv11 Nano

WalkGuardian is an AI-based object detection project developed using the YOLOv11 Nano architecture. The project focuses on detecting and identifying objects in visual environments using computer vision and deep learning techniques.

The system uses a custom annotated dataset exported from Roboflow and is designed as an object detection solution.

---

## 🎯 Project Overview

- **Project Name:** WalkGuardian
- **Model Architecture:** YOLOv11 Nano
- **Task:** Object Detection
- **Dataset Platform:** Roboflow
- **Annotation Format:** YOLO
- **Framework:** Ultralytics YOLO

## 🧠 Model Performance

The following metrics were reported in the Roboflow model evaluation:

| Metric | Result |
|---|---:|
| mAP@50 | 70.1% |
| Precision | 57.2% |
| Recall | 78.7% |
| F1 Score | 66.2% |

## 📂 Dataset Structure

```text
WalkGuardian/
│
├── train/
│   ├── images/
│   └── labels/
│
├── valid/
│   ├── images/
│   └── labels/
│
├── test/
│   ├── images/
│   └── labels/
│
├── data.yaml
├── README.dataset.txt
├── README.roboflow.txt
└── README.md
```

## ⚙️ Technologies Used

- Python
- YOLOv11 Nano
- Ultralytics
- Roboflow
- Computer Vision
- Deep Learning

## 🚀 Installation

Install the required Python package:

```bash
pip install ultralytics
```

## 🏋️ Model Training

To train the YOLOv11 Nano model using the dataset:

```python
from ultralytics import YOLO

model = YOLO("yolo11n.pt")

model.train(
    data="data.yaml",
    epochs=100,
    imgsz=640
)
```

## 🔍 Model Validation

```python
from ultralytics import YOLO

model = YOLO("runs/detect/train/weights/best.pt")

metrics = model.val(data="data.yaml")
```

## 📸 Object Detection

```python
from ultralytics import YOLO

model = YOLO("runs/detect/train/weights/best.pt")

results = model.predict(
    source="test/images",
    save=True
