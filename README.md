<!-- # Automatic License Plate Recognition (ALPR) — YOLOv8 + PaddleOCR

This repo detects license plates in video frames with YOLOv8 and reads the text using PaddleOCR.
Built during my internship at One Network. I annotated ~3000 images in Roboflow; the final model was trained on a GPU.

## Pipeline
1) Detect `license-plate` boxes with a fine-tuned YOLOv8 model  
2) Crop each plate region  
3) Run PaddleOCR to read text  
4) Save results to CSV

## Training
I trained locally for 20 epochs to validate the pipeline.  
Final 100-epoch training was performed by my supervisor on a GPU using my annotated dataset.  
The training cell remains in `notebooks/alpr.ipynb` for reference, but is off by default.

## Model Weights
Download the trained weights and place the file at `weights/best.pt`.  
- Option A: GitHub Releases (recommended) — upload your `.pt` and link it here.  
- Option B: Google Drive — share a link and put it here.

## Requirements
Python 3.10+ recommended.
```bash
pip install -r requirements.txt -->

# Automatic License Plate Recognition (ALPR) — YOLOv8 + PaddleOCR

This project implements an **Automatic License Plate Recognition (ALPR) system** using:
- [YOLOv8](https://github.com/ultralytics/ultralytics) for license plate detection  
- [PaddleOCR](https://github.com/PaddlePaddle/PaddleOCR) for optical character recognition  
- [OpenCV](https://opencv.org/) and [CVZone](https://github.com/cvzone/cvzone) for visualization  

The system detects vehicles and their license plates in **real-time video streams**, draws bounding boxes around the detected plates, and overlays the extracted text directly on the video feed.

---

## 🚀 Features
- **Custom-trained YOLOv8 model** on ~3000 motorway images for robust plate detection  
- **Live video inference** with bounding boxes and text overlays  
- **OCR integration** with PaddleOCR for multilingual text reading  
- **Lightweight pipeline** that runs on video streams frame by frame  
- Fully reproducible with the released weights  

---

## 📸 Dataset & Training
- Annotated **~3000 motorway images** manually in Roboflow (license plates + vehicles).  
- Conducted experiments with **20-epoch training** locally to validate the pipeline.  
- Final **100-epoch training** performed on GPU with the full dataset for higher accuracy.  
- Model saved as: best.pt


The training reference remains in `notebooks/alpr.ipynb` (training cell provided but not run by default).

---

## 📦 Model Weights

The trained weights are available in the **[Releases](../../releases)** section.  

1. Go to the [Releases](../../releases) page of this repository.  
2. Download `best.pt`.  
3. Place the file inside the `weights/` folder:
weights/best.pt


⚠️ **Note on stability**:  
The release was published as a **stable release** . While the model works reliably on many motorway cases, it is still being improved and is not fully production-grade.

---

## 📂 Repository Structure

```plaintext
.
├── weights/
│   ├── best.pt        # Downloaded model weights (from Releases)
│   └── .gitkeep       # Keeps folder tracked in Git
├── notebooks/
│   └── alpr.ipynb     # Main notebook (detection + OCR pipeline)
├── requirements.txt
└── README.md



---

## ⚙️ Installation

1. Clone this repository:
  
2. Create a virtual environment (recommended):
```bash
    python -m venv venv
    source venv/bin/activate  # Linux/Mac
    venv\Scripts\activate     # Windows

3. Install dependencies:
 ```bash
    pip install -r requirements.txt

  
4. Download the model weights from Releases and place in weights/best.pt

