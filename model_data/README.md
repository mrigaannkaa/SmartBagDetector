# Model Weights Directory

This folder contains trained model weights for the bag detection system.

## Model Files

### Pre-trained YOLO Models
- `yolov8n.pt` - Nano version (fastest, smallest file size)
- `yolov8s.pt` - Small version (balanced speed and accuracy)
- `yolov8m.pt` - Medium version (higher accuracy)
- `yolov8l.pt` - Large version (highest accuracy, slower)

### Custom Trained Models
- `bag_detector_best.pt` - Best performing model on bag dataset
- `bag_detector_latest.pt` - Latest training checkpoint

## Download Instructions

Since model files are large (>25MB), they are not included in the repository.

### Option 1: Download Pre-trained Models
```bash
# Install ultralytics to download base models
pip install ultralytics

# Models will be automatically downloaded when first used
python -c "from ultralytics import YOLO; YOLO('yolov8n.pt')"
```

### Option 2: Train Your Own Model
```bash
# Train on the included dataset
yolo train model=yolov8n.pt data=../dataset/data.yaml epochs=100

# Trained model will be saved as runs/detect/train/weights/best.pt
# Copy it to this folder and rename to bag_detector_best.pt
```

## Usage in Application

The `bag_detector.py` application will automatically:
1. Look for custom trained models in this directory
2. Fall back to downloading pre-trained models if needed
3. Use the best available model for detection

## Model Performance

| Model | Size | Speed | Accuracy |
|-------|------|-------|----------|
| YOLOv8n | ~6MB | Fast | Good |
| YOLOv8s | ~22MB | Medium | Better |
| YOLOv8m | ~52MB | Slower | Very Good |
| Custom | ~6-22MB | Fast-Medium | Optimized for bags |

## File Structure
```
model_data/
├── README.md          # This file
├── yolov8n.pt         # Base nano model (auto-downloaded)
├── bag_detector_best.pt  # Custom trained model (if available)
└── training_logs/     # Training logs and metrics (if training)
```
from ultralytics import YOLO

# Load pre-trained model
model = YOLO('model_data/yolov11n.pt')

# Load custom trained model
model = YOLO('model_data/bag_detector_best.pt')
```

## Training Command:
```bash
yolo train model=yolov11n.pt data=dataset/data.yaml epochs=100 imgsz=640
```
