# Plant-Disease-Classification
Multi-class plant disease detection across 38 categories using EfficientNetB3 transfer learning trained on 87,000+ leaf images. Achieves 99.78% validation accuracy.


# Plant Disease Classification with Transfer Learning

A plant disease detection model built as part of the **FarMate** graduation project — an AI-powered agricultural support platform designed to assist Egyptian farmers with crop management and disease diagnosis.

This model serves as the computer vision component of FarMate, enabling farmers to photograph a plant leaf and instantly receive a disease diagnosis across 38 categories and 14 crop species.

---

## About FarMate
FarMate is an agricultural support platform built to help Egyptian farmers diagnose crop diseases, access expert agricultural knowledge, and make better farming decisions using AI. This classification model is integrated into the platform to provide real-time image-based disease detection directly from a phone camera.

---

## Dataset
- **Source:** [New Plant Diseases Dataset — Kaggle](https://www.kaggle.com/datasets/vipoooool/new-plant-diseases-dataset)
- **Training samples:** 70,295 images
- **Validation samples:** 17,572 images
- **Classes:** 38 disease categories across 14 crop species
- **Balance:** Well balanced — 1,642 to 2,022 images per class

---

## Saved Model
The model was trained on Kaggle and saved as `plant.h5`. To reproduce the model, run the notebook on Kaggle with the dataset attached and GPU enabled. Training takes approximately 1.5 hours on a T4 GPU.

---

## Model Architecture
| Layer | Details |
|-------|---------|
| Base Model | EfficientNetB3 pretrained on ImageNet |
| Base Layers | Frozen — 385 layers |
| GlobalAveragePooling2D | Reduces spatial dimensions |
| Dense | 256 units, ReLU activation |
| Dropout | 30% |
| Output | 38 units, Softmax activation |

---

## Results

| Metric | Training | Validation |
|--------|----------|------------|
| Accuracy | 99.92% | 99.78% |
| Loss | 0.0148 | 0.0075 |

---

## Crops Covered
Apple, Blueberry, Cherry, Corn, Grape, Orange, Peach, Pepper, Potato, Raspberry, Soybean, Squash, Strawberry, Tomato

---

## Workflow
1. Exploratory data analysis — class distribution and sample visualization
2. Data loading using ImageDataGenerator
3. Transfer learning with EfficientNetB3 frozen base
4. Training for 5 epochs with Early Stopping
5. Evaluation on validation set
6. Prediction function for single image inference

---

## How to Run
This notebook is designed to run on Kaggle with the dataset attached directly.

1. Open the notebook on Kaggle
2. Attach the [New Plant Diseases Dataset](https://www.kaggle.com/datasets/vipoooool/new-plant-diseases-dataset)
3. Enable GPU accelerator
4. Run all cells

---

## Saved Model
The trained model is saved as `plant.h5` and included in this repository for direct inference without retraining.

---

## Part of FarMate Graduation Project
This repository is one component of the FarMate graduation project. The full platform includes:
- **Plant Disease Detection** — this repository
- **Agricultural Expert System** — domain-specific Q&A system covering 90+ crops
- **LLM Integration** — natural language understanding layer for farmer queries

---

## Libraries Used
- TensorFlow, Keras
- NumPy, Pandas
- Matplotlib, Seaborn
- Scikit-learn
- Pillow
