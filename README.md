# 🚗 Vehicle Object Detection with YOLOv1 + ResNet

Object detection project developed for a university Deep Learning course.  
The model combines a **ResNet backbone** with a **YOLOv1** detection head, trained on a filtered subset of the **Vehicles-OpenImages (COCO)** dataset.

---

## 📌 Features

- YOLOv1-style detection model implemented in **PyTorch**
- **ResNet** backbone (pre-trained on ImageNet)
- Two training setups:
  - **Transfer Learning** (backbone frozen)
  - **Fine-Tuning** (selected layers unfrozen)
- Evaluation: confusion matrix, precision/recall/F1, qualitative predictions
- Fully reproducible on **Google Colab**

---

## 📂 Repository Structure

```
notebooks/
├── Yolov1Resnet_VehiclesDataset.ipynb
└── Fine_Tuning_Vehicles.ipynb

src/
├── dataset.py
├── model.py
├── loss.py
├── engine.py
└── utils.py

models/ # optional
images/examples/ # prediction samples
requirements.txt
```

---

## 🗂 Dataset

- **Vehicles-OpenImages.v1-416x416** (COCO format)  
- Classes used in this project: **car**, **truck**, **bus**, **motorcycle**  
- The fine-tuning notebook automatically filters and rebuilds the COCO annotations  

---

## 🧠 Model Architecture

- **Backbone:** ResNet (ImageNet)
- **Head:** YOLOv1 grid-based detection (S = 7, B = 2, C = 4)
- **Loss:** YOLOv1 Squared Error Loss
- **Input size:** 416×416

---

## 👨‍🎓 About

Project developed for the **Deep Learning course** of **Università Cattolica del Sacro Cuore** of **Milan**.

Author: **Giovanni Caminiti** and **Eleonora Farolfi**

