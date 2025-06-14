# A Deep Learning-Based Approach for IR Drop Hotspot Detection in VLSI Design

##  Dataset

We use the **CircuitNet-N14 IR Drop dataset**, available at:

 [https://github.com/ehdtjr1121/CircuitNet](https://github.com/ehdtjr1121/CircuitNet)

Due to size and license constraints, the dataset is **not included** in this repository.  
However, a few **sample `.npy` files** are provided in `data/raw/` and `data/processed/` to demonstrate the format.

This project specifically uses the **IR Drop subset** from CircuitNet, as proposed in:

> **Zhao, Heng, et al.**  
> “CircuitNet: An Open-Source Dataset for Machine Learning Applications in Electronic Design Automation (EDA).”  
> *arXiv preprint* arXiv:2006.11397 (2020).  
>  [View on arXiv](https://arxiv.org/abs/2006.11397)

---

##  Introduction

In advanced **VLSI** (Very-Large-Scale Integration) circuits, **IR drop** refers to the voltage loss caused by resistance in the power delivery network.  
Excessive IR drop can lead to **logic failures**, **timing violations**, and **performance degradation**.

This project explores a **deep learning-based solution** using a Fully Convolutional Network (FCN) — specifically, a **U-Net architecture** — to **predict IR drop hotspots** based on layout features.

---

##  Highlights

- Preprocessed the CircuitNet IR drop dataset  
- Trained on **1000 samples**, tested on **500 samples**
- Evaluated using:
  -  **ROC AUC**
  -  **Precision-Recall**
  -  **F1 Score**
  -  **Confusion Matrix**
- Visualized predicted IR drop maps and classification masks

---

##  Model Architecture

- **U-Net** model for pixel-wise classification
- **Input:** 256×256 grayscale IR drop feature maps  
- **Output:** Binary mask of IR drop hotspots (threshold = 0.5)  
- **Loss Function:** Binary Cross-Entropy  
- **Optimizer:** Adam

---

## Evaluation Metrics

| Metric     | Value    |
|------------|----------|
| **ROC AUC**  | 0.9991   |
| **F1 Score** | 0.9983   |

###  Visual Results:

- ROC Curve: ![ROC Curve](./results/roc_curve.png)
- Precision-Recall Curve: ![PR Curve](./results/precision_recall_curve.png)
- Confusion Matrix: `conf_matrix.png`
- IR Drop Heatmaps: Stored under `results/visualized/`

---

##  Repository Structure
├── data/
│ ├── raw/ # Sample raw feature files (from CircuitNet)
│ └── processed/ # Preprocessed feature and label files
│
├── notebooks/
│ └── IR_DROP_PREDICTION.ipynb # Main notebook with training, testing, and results
│
├── results/
│ ├── roc_curve.png
│ ├── precision_recall_curve.png
│ ├── conf_matrix.png
│ └── visualized/ # Heatmaps of predicted IR drop


---

## Author

This project was completed as part of an **internship** exploring the intersection of **AI and VLSI Design**.

---

## Contact

If you have any questions or are interested in collaborating, feel free to reach out!

> Created by **NAGAVALLI S**





