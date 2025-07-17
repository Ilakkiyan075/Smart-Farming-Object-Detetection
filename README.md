# 🌾 Smart Farming: Object Detection System using YOLOv8

An end-to-end deep learning project to enhance agricultural productivity using computer vision. This system detects key elements in farm environments such as **crops**, **weeds**, **pests**, and **fruits ready for harvest** using real-time object detection.

---

## 🚀 Features

- 🔍 Detect multiple farm elements (crop, weed, pest, fruit) using YOLOv8
- 🎯 High-accuracy custom-trained model on annotated agricultural dataset
- 📷 Real-time inference on webcam/drone footage
- 💻 Streamlit-based web app for easy interaction
- ⚙️ Easily extendable to more classes and inputs (videos, drones, IoT)

---

## 🧠 Problem Statement

Manual monitoring of crops and plant health is labor-intensive and time-consuming. This project automates field monitoring through object detection techniques to:
- Identify crop maturity
- Detect weeds or diseased plants
- Track pests or animals
- Highlight fruits ready for harvest

---

## 🗂️ Project Structure

smart-farming-detection/
│
├── data/
│ ├── train/images/
│ ├── train/labels/
│ ├── val/images/
│ └── val/labels/
│
├── yolo_config/
│ └── smartfarm.yaml
│
├── runs/
│
├── app/
│ └── streamlit_app.py
│
├── assets/
│ └── sample_output.gif
│
├── requirements.txt
├── README.md
└── LICENSE



---

## 📦 Dataset

### Option A: Public Dataset (Used)
- [PlantDoc](https://github.com/pratikkayal/PlantDoc-Dataset) – disease & pest images
- [Roboflow Universe](https://universe.roboflow.com) – fruits, weeds, insects

### Option B: Custom Dataset (Optional)
- Captured via drone/webcam
- Annotated using:
  - [LabelImg](https://github.com/tzutalin/labelImg)
  - [Roboflow Annotate](https://roboflow.com)

---

## ⚙️ Model Architecture: YOLOv8

- Framework: [Ultralytics YOLOv8](https://github.com/ultralytics/ultralytics)
- Model: `yolov8n.pt` (Nano version for fast training)
- Classes: `['crop', 'weed', 'pest', 'fruit']`

### Training Command
```bash
yolo task=detect mode=train model=yolov8n.pt data=yolo_config/smartfarm.yaml epochs=50 imgsz=640
