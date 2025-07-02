# Smart Bag Detector

A professional computer vision system for bag detection using YOLO architecture, featuring a complete dataset and modern user interface.


##  Features

- **YOLO 11 Detection**: Advanced neural network for accurate bag recognition
- **Modern UI**: Clean, professional interface with real-time statistics
- **Complete Dataset**: 750+ labeled images ready for training
- **Real-time Processing**: Smooth 30 FPS camera detection
- **Smart Analysis**: Detailed detection results with confidence scores
- **Training Ready**: Full YOLO dataset structure for custom models

##

**Easy Launch:**
```bash
# Double-click to run:
START_DETECTOR.bat

# Or manually:
python bag_detector.py
```

**Requirements:**
```bash
pip install -r requirements.txt
```

## Project Structure

```
SmartBagRecommender/
├── bag_detector.py              # Main YOLO detection application
├── START_DETECTOR.bat          # Easy launcher for Windows
├── requirements.txt            # Python dependencies
├── dataset/                    # Complete YOLO dataset
│   ├── data.yaml              # Dataset configuration
│   ├── images/                # Training & validation images
│   │   ├── train/             # Training images (80%)
│   │   └── val/               # Validation images (20%)
│   └── labels/                # YOLO format annotations
│       ├── train/             # Training labels
│       └── val/               # Validation labels
├── model_data/                # Model weights directory
├── figures/                   # Demo images and documentation
└── font/                      # UI fonts
```

##  Dataset Information

### **Dataset Statistics:**
- **Total Images**: 750+ high-quality bag images
- **Training Set**: 80% of dataset with annotations
- **Validation Set**: 20% of dataset with annotations
- **Classes**: 3 bag types (backpack, handbag, wallet)
- **Format**: YOLO v5/v8/v11 compatible
- **Annotations**: Bounding box labels for all objects

### **Label Format:**
```
# YOLO format: class x_center y_center width height
0 0.5 0.5 0.3 0.4  # backpack at center
1 0.3 0.7 0.2 0.3  # handbag in lower left
2 0.8 0.2 0.15 0.1 # wallet in upper right
```

###  **Classes:**
- **0**: Backpack
- **1**: Handbag  
- **2**: Wallet

**Training Configuration:**
- **Base Model**: YOLOv8n (nano) - fast and efficient
- **Image Size**: 640x640 pixels
- **Batch Size**: 16 (adjust based on GPU memory)
- **Epochs**: 100+ recommended for best results
- **Classes**: 3 bag types with detailed annotations

##  UI Features

- **Real-time Detection**: Live camera feed with YOLO processing
- **Professional Design**: Clean, modern interface with intuitive controls
- **Detection Statistics**: Confidence scores and performance monitoring
- **Visual Feedback**: Clear bounding boxes and object labels
- **Status Indicators**: Real-time system status and detection results



##  Performance

- **Detection Speed**: 30 FPS real-time processing
- **Model Size**: Lightweight (~6-20MB depending on YOLO variant)
- **Accuracy**: High precision with proper training data
- **Supported Objects**: Backpacks, handbags, wallets with bounding boxes




MIT License - Feel free to use for educational and research purposes.


---


