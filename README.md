# Gesture Recognition with 2S-STGCN, Transformer & TCN

![Built With](https://img.shields.io/badge/Built%20With-Python%20%7C%20PyTorch%20%7C%20Deep%20Learning-blue)
![Language](https://img.shields.io/badge/Language-Python-orange)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)


## Project Overview

This project explores how **deep learning models** can be used to recognize human gestures for seamless **human–robot communication** in real-world settings (e.g., retail, healthcare, manufacturing).

Using the **NTU RGB+D 60** skeleton dataset, we developed three gesture recognition models:
- **2S-TCN** (Temporal CNN)
- **Transformer Encoder**
- **2S-STGCN** (Spatial-Temporal Graph Convolutional Network)

These models were evaluated to determine which is best for classifying workplace-relevant gestures such as waving, drinking, pointing, etc.

The project project was developed as part of the Deep Learning course at the **University of South Florida – Muma College of Business**.

---

## Motivation

Voice and touchscreen controls are limiting in noisy or dynamic environments.  
Gesture-based interaction is faster, more natural, and privacy-friendly.  
This system enables robots to understand intent from **skeleton-based motion**, without cameras or microphones.

---

## Dataset

- **Source**: [NTU RGB+D](https://rose1.ntu.edu.sg/dataset/actionRecognition/)
- **Modality**: Skeleton data only
- 25 joints per frame (x, y, z)
- 60 gesture/action classes
- 56,880 video samples
- Used 80% for training and 20% for validation

---

## Models

| Model        | Description                                      | Accuracy  |
|--------------|--------------------------------------------------|-----------|
| 2S-TCN       | Temporal CNN + Bone Stream                       | ~63%      |
| Transformer  | Attention-based encoder, no spatial bias         | ~65%      |
| 2S-STGCN     | Graph Conv + Temporal Conv + Bone Stream         | **~78%**  |

> Best performance achieved by 2S-STGCN due to joint + bone stream and spatiotemporal modeling.

---

## Confusion Matrix

- Misclassifications happened mostly between similar gestures (e.g., handshake vs hug).
- 2S-STGCN reduced these overlaps better than others.

---

## Business Value

- Enables **touchless, intuitive robot control** in industrial or public settings.
- Reduces hardware complexity (uses only skeleton sensors or vision models).
- Lowers training time and improves safety in automation workflows.

---

## Technologies Used

- Python, PyTorch, NumPy
- Skeleton-based GCNs
- Matplotlib, SciKit Learn

---

## File Structure
<pre>
Gesture-Recognition-Deep-Learning/
├── Demo/
│ └── Drink_Water.mp4
├── Report/
│ └── Team Project - Gesture Recognition.docx
├── 2sSTGCN.ipynb
├── 2sTCN.ipynb
├── Transformer_Encoder.ipynb
├── parse_skeleton.ipynb
└── README.md
</pre>
**File Descriptions**:
- `2sSTGCN.ipynb`: 2-stream Spatial-Temporal Graph Convolutional Network model
- `2sTCN.ipynb`: Two-Stream Temporal Convolutional Network model
- `Transformer_Encoder.ipynb`: Transformer Encoder model
- `parse_skeleton.ipynb`: Converts raw NTU skeleton files to NumPy arrays
- `README.md`: Project overview, models, results, and business implications
---

## Contributors

- Bhargav Rishi Medisetti  
- Chi Phuong Diep  
- Devansh Pavdighada  
(Muma College of Business – University of South Florida)

