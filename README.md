# Traffic Violation Detection using YOLOv8

Real-time traffic violation, vehicle, pedestrian, traffic signal, and sign detection built with **Ultralytics YOLOv8n** and **PyTorch** on Kaggle (Tesla T4 GPU) across **23 classes**.

## Model & Training Summary
- **Base Model:** `yolov8n.pt` (fine-tuned for 20 epochs, `imgsz=640`, `batch=16`, AMP enabled) 
- **Dataset:** Traffic Violation Detection Dataset (`5,254` train images, `1,470` validation images, 23 classes)   
- **Validation Performance (`best.pt`):**
  - **Precision:** `0.886`
  - **Recall:** `0.863`
  - **mAP50:** `0.913`
  - **mAP50-95:** `0.782`
  - **Inference Speed (Tesla T4):** `~3.9 ms` per image (validation) / `~7.6 ms` (single-image sample run)   

## Classes (23)
- **Vehicles & Pedestrians:** `person`, `car`, `truck`, `bus`, `motorcycle`  
- **Traffic Lights:** `red light`, `green light`
- **Traffic Signs & Speed Limits:** `stop sign`, `no entry`, `no overtaking`, `no left turn`, `no right turn`, `no stopping`, `no u-turn`, and speed limits (`20`, `30`, `40`, `50`, `60`, `70`, `80`, `100`, `120`)

## Highlights & Observations
- Strongest performance seen on traffic and speed limit signs (e.g., `stop sign` at `0.995` mAP50, `speed limit 100` at `0.992` mAP50).
- Larger vehicles and signals (`truck`, `bus`, `motorcycle`, `red light`) show room for further gains with longer training or a larger YOLO variant.

## Repository Structure
```text
Traffic-Violation-Detection-YOLOv8/ 
├── README.md
├── fixed_data.yaml
├── weights/
│   └── best.pt
└── assets/
    ├── results.png
    └── confusion_matrix.png
