# Automatic License Plate Recognition (ALPR) — YOLOv8 + PaddleOCR

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
pip install -r requirements.txt
