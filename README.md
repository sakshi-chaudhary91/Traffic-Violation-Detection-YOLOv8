# Traffic Violation Detection using YOLOv8

An object detection project built with **Ultralytics YOLOv8** and **PyTorch** on Kaggle (Tesla T4 GPU) to detect vehicles, pedestrians, traffic signals, and traffic/speed signs across **23 classes** for traffic violation monitoring.

## Dataset Overview
- **Dataset:** Traffic Violation Detection Dataset (`guisahanes/traffic-violation-detection-dataset`)
- **Splits:** 5,254 training images and 1,470 validation images in YOLO format
- **Classes (23):**
  - **Vehicles & Pedestrians:** `person`, `car`, `truck`, `bus`, `motorcycle`
  - **Traffic Lights:** `red light`, `green light`
  - **Traffic Signs & Speed Limits:** `stop sign`, `no entry`, `no overtaking`, `no left turn`, `no right turn`, `no stopping`, `no u-turn`, and speed limits (`20`, `30`, `40`, `50`, `60`, `70`, `80`, `100`, `120`)

## Workflow & Setup
1. **Environment & GPU Setup:** Configured Kaggle notebook with Tesla T4 GPU and installed `ultralytics`.
2. **Dataset Path Fix:** Generated `/kaggle/working/fixed_data.yaml` pointing cleanly to the Kaggle input dataset directory, `images/train`, and `images/val`.
3. **Baseline Training:** Trained `yolov8n.pt` (`imgsz=640`, `batch=16`, `epochs=20`) with Automatic Mixed Precision (AMP).
4. **Evaluation & Inference:** Validate best checkpoints (`best.pt`) using precision, recall, and mAP metrics, and run inference on sample traffic images.

## Project Structure
```text
Traffic-Violation-Detection-YOLOv8/
├── README.md
├── fixed_data.yaml          # Path-fixed dataset config for Kaggle
└── runs/
    └── traffic_yolov8n_baseline/
