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
- Vehicle classes vary depending on the experimental setup (4 or 5 classes)
- The fine-tuning notebook automatically filters and rebuilds the COCO annotations  

---

## 🔬 Experimental Setups

This repository includes two different experimental configurations:

- **Transfer Learning (5 classes)**  
  The model is trained on a extended subset of vehicle categories  
  (**car, truck, bus, motorcycle, ambulance**) with a frozen ResNet backbone.  
  This setup is used as a baseline.

- **Fine-Tuning (4 classes)**  
  The model is fine-tuned on an restricted subset of vehicle categories,  
  excluding **ambulance**.  

The two setups are not meant to be directly compared, as they differ in the number of target classes.

---

## 🧠 Model Architecture

- **Backbone:** ResNet (ImageNet)
- **Head:** YOLOv1 grid-based detection (S = 7, B = 2, C = 4 or 5 depending on the setup)
- **Loss:** YOLOv1 Squared Error Loss
- **Input size:** 416×416

---

## 👨‍🎓 About

Project developed for the **Deep Learning course** of **Università Cattolica del Sacro Cuore** of **Milan**.

Author: **Giovanni Caminiti** and **Eleonora Farolfi**

