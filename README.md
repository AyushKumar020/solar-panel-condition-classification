#  SolarGuard AI
### Intelligent Solar Panel Surface Defect Detection using Deep Learning

<div align="center">

![Python](https://img.shields.io/badge/Python-3.10-blue?logo=python)
![PyTorch](https://img.shields.io/badge/PyTorch-Deep%20Learning-red?logo=pytorch)
![YOLOv8](https://img.shields.io/badge/YOLOv8-Classification-green)
![OpenCV](https://img.shields.io/badge/OpenCV-Computer%20Vision-blue?logo=opencv)
![ONNX](https://img.shields.io/badge/ONNX-Edge%20Deployment-orange)
![License](https://img.shields.io/badge/License-MIT-green)

**AI-powered Computer Vision System for Automated Solar Panel Surface Inspection**

</div>

---

#  Overview

SolarGuard AI is a deep learning-based computer vision system that automatically analyzes solar panel images and classifies their surface condition into one of six operational categories.

The model is designed for autonomous solar panel cleaning robots and intelligent maintenance systems, enabling real-time inspection without requiring cloud connectivity.

Instead of cleaning every solar panel indiscriminately, the system determines the appropriate action for each panel, improving operational efficiency while preventing damage to already faulty panels.

---
#  Industry Project

This project was developed as part of an **AI & Robotics Internship at Eythor Private Limited**, a company specializing in intelligent robotics solutions for large-scale solar power plants.

The project contributes to **Eyto**, an Autonomous Solar Panel Cleaning Robot, where the objective is to enable intelligent decision-making through computer vision. The developed deep learning model classifies the surface condition of solar panels, allowing the robot to determine whether a panel should be cleaned, inspected, or skipped.

**Company:** Eythor Private Limited  
**Product:** Eyto – Automated Solar Panel Cleaning Robot  
**Project Type:** Industry Internship Project

---

#  Features

✅ Detects **6 different solar panel conditions**

- Clean
- Dusty
- Bird Droppings
- Snow Covered
- Physical Damage
- Electrical Damage

✅ YOLOv8 Nano Classification Model

✅ Real-time Inference

✅ Edge AI Ready (ONNX Export)

✅ Lightweight Model for Embedded Deployment

✅ Suitable for Autonomous Cleaning Robots

---

#  Problem Statement

Solar panels lose efficiency due to:

- Dust accumulation
- Bird droppings
- Snow coverage
- Physical damage
- Electrical faults

Traditional cleaning systems clean every panel regardless of its condition, leading to unnecessary wear and increased maintenance costs.

This project introduces an intelligent vision system capable of identifying the surface condition of each panel and recommending the correct maintenance action.

---

#  Model Architecture

| Property | Value |
|------------|----------------|
| Model | YOLOv8 Nano Classification |
| Framework | Ultralytics YOLOv8 |
| Input Size | 224 × 224 RGB |
| Output | 6-Class Classification |
| Transfer Learning | Yes |
| Deployment | PyTorch + ONNX |

---

#  Dataset

Dataset Used:

**Solar Panel Images – Clean and Faulty**
- Source: https://www.kaggle.com/datasets/pythonafroz/solar-panel-images
- Total Images: **792**
- Image Type: RGB
- Classes: **6**

Dataset Split

- Training: **80%**
- Validation: **10%**
- Testing: **10%**

---

#  Classes

| Class | Robot Action |
|------------|----------------------------|
| Clean | No  Action |
| Dusty | Clean Panel |
| Bird-drop | Clean Panel |
| Snow-Covered | Remove Snow |
| Physical-Damage | Flag for Inspection |
| Electrical-Damage | Stop the Robot & Alert |

---

#  Data Augmentation

The model uses several augmentation techniques during training:

- Random Rotation
- Brightness Adjustment
- Saturation Jitter
- Hue Shift
- Horizontal Flip

These augmentations improve robustness under varying outdoor conditions.

---

#  Training Configuration

| Parameter | Value |
|------------|---------|
| Epochs | 60 |
| Batch Size | 32 |
| Optimizer | Default YOLOv8 |
| Learning Rate | 0.001 |
| Image Size | 224 |
| GPU | Kaggle T4 |

Training Time:

Approximately **10–15 minutes** on Kaggle GPU.

---

#  Performance

Expected Performance

- Top-1 Accuracy: **75–90%**
- Top-5 Accuracy: **95%+**

> Actual accuracy depends on dataset balance and training configuration.

---

#  Inference Pipeline

```text
Solar Panel Image
        │
        ▼
Image Preprocessing
        │
        ▼
YOLOv8 Classification Model
        │
        ▼
Surface Condition Prediction
        │
        ▼
Robot Decision System
        │
        ├── Clean
        ├── Remove Snow
        ├── No Action
        └── Maintenance Alert
```

---

#  Installation

```bash
git clone https://github.com/yourusername/solar-panel-defect-detection.git

cd solar-panel-defect-detection

pip install -r requirements.txt
```

---

#  Run Inference

```python
from ultralytics import YOLO

model = YOLO("surface_defect_best.pt")

result = model.predict("panel.jpg")

print(result[0].probs)
```

---

#  Project Structure

```text
SolarGuard-AI
│
├── dataset/
│
├── models/
│
├── notebooks/
│
├── exports/
│      ├── surface_defect_best.pt
│      └── surface_defect.onnx
│
├── inference/
│
├── training/
│
├── requirements.txt
│
└── README.md
```

---

#  Applications

- Autonomous Solar Cleaning Robots
- Smart Solar Farms
- Industrial Solar Inspection
- Predictive Maintenance
- Renewable Energy Monitoring
- Edge AI Systems
- Embedded Vision Applications

---

#  Edge Deployment

The trained model can be exported to:

- PyTorch (.pt)
- ONNX
- STM32N6 Neural-ART
- NVIDIA Jetson
- Raspberry Pi
- Embedded AI Devices

---

#  Future Improvements

- Increase dataset to 2,000+ images
- Add water stains and algae detection
- Confidence-based prediction filtering
- Multi-frame temporal prediction
- Continuous Learning Pipeline
- Robot-camera fine tuning

---

#  Tech Stack

- Python
- PyTorch
- Ultralytics YOLOv8
- OpenCV
- NumPy
- ONNX
- Kaggle GPU

---

#  Project Integration

This model serves as the **Surface Defect Detection Module** of the autonomous solar panel cleaning robot.

### Workflow

```text
RGB Camera
      │
      ▼
YOLOv8 Classification Model
      │
      ▼
Panel Condition Classification
      │
      ▼
Decision Engine
      │
 ┌────┼─────────────┐
 │    │             │
 ▼    ▼             ▼
Clean Skip     Maintenance Alert
```

---

#  Demo

<p align="center">
  <img src="assets/WhatsApp Image 2026-06-26 at 11.46.42 AM.jpeg" width="700">
</p>

<p align="center">
  <img src="assets/WhatsApp Image 2026-06-26 at 11.46.43 AM (1).jpeg" width="700">
</p>

<p align="center">
  <img src="assets/WhatsApp Image 2026-06-26 at 11.46.43 AM (2).jpeg" width="700">
</p>

<p align="center">
  <img src="assets/WhatsApp Image 2026-06-26 at 11.46.43 AM (3).jpeg" width="700">
</p>

<p align="center">
  <img src="assets/WhatsApp Image 2026-06-26 at 11.46.43 AM (4).jpeg" width="700">
</p>

<p align="center">
  <img src="assets/WhatsApp Image 2026-06-26 at 11.46.43 AM.jpeg" width="700">
</p>




---

#  Contributing

Contributions are welcome!

Feel free to fork the repository and submit pull requests.

---

#  License

This project is licensed under the MIT License.

---

#  Author

**Ayush Kumar**

**Avi Jayant**

**Devanshu Kumar**


B.Tech Computer Science Engineering

Deep Learning • Computer Vision • Edge AI • Machine Learning

---
