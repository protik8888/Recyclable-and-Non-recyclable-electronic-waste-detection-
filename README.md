# Recyclable-and-Non-recyclable-electronic-waste-detection-
# Real-Time E-Waste Classification with Image Processing



---

## Overview

Electronic waste is one of the fastest-growing waste streams in the world. Manual sorting of e-waste is slow, inefficient, and hazardous to workers. This project presents a real-time automated classification system using YOLOv8 that detects and categorizes e-waste components based on their recyclability from images of discarded electronics.

The model achieves up to 90% accuracy and is designed to be deployable in real recycling facilities to speed up sorting, reduce human error, and support sustainability goals.

---

## E-Waste Classes

The model classifies 5 categories of electronic components:

| Component | Recyclability | Reason |
|---|---|---|
| Lithium Battery | Non-Recyclable | Contains hazardous chemicals; requires special disposal |
| CRT Monitor | Non-Recyclable | Contains lead oxide (up to 20%); toxic and costly to process |
| Computer Mouse | Recyclable | Minimal hazardous materials; easily reusable |
| Printed Circuit Board | Recyclable | Reusable or copper-extractable if damaged |
| Mobile Phone | Recyclable | Valuable material recovery; economically beneficial |

---

## Dataset

- Platform: Roboflow (https://universe.roboflow.com/khobaer9999/green-computing-e-waste-njsej)
- Total Images: 1,382 across 5 classes (276–277 images per class, balanced at 20% each)
- Source: Images collected from various online sources and annotated using Roboflow

Preprocessing and Augmentation:
- Image size: 640x640 pixels
- Auto-orientation applied
- Dataset split: 85% training, 10% validation, 5% testing
- Augmentation: horizontal/vertical flipping, 90° rotations, random rotation between -15° and +15°, 3 outputs per training example

---

## Model Training

- Model: YOLOv8 (Ultralytics)
- Epochs: 100
- Batch Size: 16
- Optimizer: AdamW
- Learning Rate: 0.001 with cosine annealing
- Early Stopping: Patience of 10 epochs
- Hardware: NVIDIA GPU with CUDA acceleration

---

## Results

- Overall mAP@0.5: 0.840
- Overall Recall (all classes): 0.88

Class-wise Average Precision:

| Class | AP |
|---|---|
| Recyclable Mobile Phone | 0.972 |
| Recyclable Computer Mouse | 0.892 |
| Non-Recyclable CRT Monitor | 0.837 |
| Recyclable Printed Circuit Board | 0.792 |
| Non-Recyclable Lithium Battery | 0.708 |

---

## Project Structure

```
├── E_waste.ipynb       # Main training and evaluation notebook
└── README.md
```

---

## How to Run

1. Clone this repository
2. Install dependencies:
   ```bash
   pip install roboflow ultralytics
   ```
3. Open and run `E_waste.ipynb` in Google Colab or Jupyter Notebook
4. The notebook will download the dataset from Roboflow and begin training

---

## Team

| Name | Role |
|---|---|
| Abdullah Al Khobaer | Project Methodology, Workflow Design & Research Lead |
| Shadab Yasar | Team Member |
| SD Abon | Team Member |
| Nusrat Islam Choa | Team Member |

Supervisor: Dr. Md. Motaharul Islam
Institution: United International University, Dhaka, Bangladesh

---

## My Contribution (Abdullah Al Khobaer)

I was responsible for designing the overall project methodology and conducting the end-to-end project workflow — from defining the problem approach and planning the research structure to guiding how the different stages of the project were carried out.

---

## Research Paper

This project is based on the published research paper:

Real-Time E-Waste Classification with Image Processing to Identify Recyclable and Non-Recyclable Components in Discarded Electronics
Abdullah Al Khobaer, Shadab Yasar, Nusrat Islam Choa, Shaisab Das Abon, Md. Motaharul Islam

---

## License

This project is for academic and research purposes only.
