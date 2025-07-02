# YOLO Bag Detection Dataset

This folder contains a complete dataset for training YOLO models to detect different types of bags.

## Dataset Structure

```
dataset/
├── data.yaml          # YOLO configuration file
├── images/            # Training and validation images
│   ├── train/         # 80% of images for training
│   └── val/           # 20% of images for validation
└── labels/            # YOLO format annotations
    ├── train/         # Training labels
    └── val/           # Validation labels
```

## Dataset Statistics

- **Total Images**: 750+ labeled bag images
- **Training Split**: 80% (600+ images)
- **Validation Split**: 20% (150+ images)
- **Classes**: 3 bag types with detailed annotations
- **Format**: YOLO v5/v8 compatible

## Classes

| ID | Class Name | Description |
|----|------------|-------------|
| 0  | backpack   | Backpacks and rucksacks |
| 1  | handbag    | Purses and handbags |
| 2  | wallet     | Wallets and small bags |

## Label Format

YOLO format annotations with normalized coordinates:
```
class_id x_center y_center width height
```

Example:
```
0 0.5 0.4 0.3 0.5    # backpack centered in image
1 0.2 0.7 0.15 0.2   # handbag in lower left
2 0.8 0.3 0.1 0.08   # wallet in upper right
```

## Usage

### For Training
```bash
# Install YOLO
pip install ultralytics

# Train a model
yolo train model=yolov8n.pt data=data.yaml epochs=100 imgsz=640
```

### For Validation
```bash
# Validate model performance
yolo val model=best.pt data=data.yaml
```

## Data Quality

- High-resolution images (minimum 640x640)
- Diverse backgrounds and lighting conditions
- Multiple bag orientations and sizes
- Accurate bounding box annotations
- Consistent labeling across all images
5: messenger

## Current Status:
This demo uses simulated detection instead of real AI.

## To Add Real Dataset:
1. Use labelImg to annotate bag images
2. Export in YOLO format
3. Train model using YOLOv3/v4/v5
4. Replace simple_system.py with trained model
