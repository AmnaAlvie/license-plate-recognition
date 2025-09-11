

# Automatic License Plate Recognition (ALPR) — YOLOv8 + PaddleOCR

An ALPR system that detects and reads license plates from traffic footage using a custom-trained YOLOv8 model and PaddleOCR. Built during my internship at One Network.

## 📸 Sample Output

![ALPR Detection Example](sample_output/image.png)

The system detects license plates and vehicles in real-time, overlaying extracted text on the video feed with confidence scores.

## � Features

- **Real-time detection** of license plates and vehicles
- **OCR text extraction** with PaddleOCR
- **CSV logging** with timestamps and coordinates
- **Video processing** (MP4, AVI, MOV formats)
- **Automatic fallback** to YOLOv8n if custom weights not found

## 📦 Dataset & Training

- **3000+ annotated images** from motorway footage (Roboflow)
- **Local training**: 20 epochs for validation
- **Final training**: 100 epochs on GPU
- **Classes**: `['license-plate', 'vehicle']`

---

## � Repository Structure

```
license-plate-recognition/
├── weights/best.pt          # Custom YOLOv8 model weights (download from releases)
├── notebooks/alpr.ipynb     # Main Jupyter notebook
├── assets/                  # Place your video files here
├── results/                 # Auto-generated CSV detection results
├── sample_output/image.png  # Example detection
└── requirements.txt         # Dependencies
```

## ⚙️ Quick Start

### 1. Setup
```bash
git clone https://github.com/AmnaAlvie/license-plate-recognition.git
cd license-plate-recognition
pip install -r requirements.txt
```

### 2. Download Model Weights
- Download `best.pt` from [Releases](../../releases) 
- Place in `weights/best.pt`

### 3. Add Your Video
- Place video file in `assets/` folder
- Update `video_path` in notebook config cell

### 4. Run Detection
```python
# In notebooks/alpr.ipynb first cell:
weights_path = "weights/best.pt"
video_path = "assets/your_video.mp4"
conf_thresh = 0.5

# Run all cells to start detection
```

## 🎮 Controls
- **Press 't'**: Stop processing
- **Ctrl+C**: Emergency stop
- Results auto-save to `results/` folder

## � Output Format

CSV file with columns: `timestamp, frame_number, plate_text, confidence, bbox_x1, bbox_y1, bbox_x2, bbox_y2`

---


## 🚨 Troubleshooting

**Model weights not found:**
- Download `best.pt` from Releases and place in `weights/` folder
- System will offer YOLOv8n fallback for general object detection

**Video file not found:**
- System provides interactive options: alternative file path, or exit
- Ensure video file is in supported format (MP4, AVI, MOV)


## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

---

**Note**: This system was developed for educational and research purposes. For production deployment, additional validation and optimization may be required.
