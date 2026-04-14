# 🛒 AI-Powered Self-Checkout System for Retail Environments

## 📌 Overview

This project presents an **AI-based product identification system** for automated retail self-checkout environments. It evaluates and compares **traditional machine learning (ML)** and **deep learning (DL)** models for image-based product recognition under real-world conditions, including varying lighting scenarios.

The study is based on a **custom-built dataset** and investigates both **classification performance** and **deployment feasibility**.

---

## 🎯 Objectives

* Compare **traditional ML models (SVM, Random Forest)** with **deep learning (CNN, YOLOv5m, Faster R-CNN)**
* Evaluate **accuracy, inference speed, and computational efficiency**
* Analyze **impact of lighting conditions** on model performance
* Identify the most **practical model for real-time retail deployment**

---

## ❓ Research Questions

1. Can traditional ML models compete with deep learning models for product identification?
2. How do lighting conditions affect deep learning model performance in real-world environments?

---

## 📂 Dataset

* Custom dataset with **6 retail product classes**:

  * Red Boost
  * Blue Boost
  * Purple Boost
  * Pepsi
  * Quavers
  * Tuna Sandwich

* Dataset details:

  * **Original images:** 24
  * **After augmentation:** 744 images
  * **Train/Test split:** 600 / 144 (80/20)

### 🔧 Data Augmentation

Applied transformations:

* Rotation
* Zoom
* Width/height shift
* Shear
* Horizontal flip

This ensured robustness against:

* Camera angles
* Distance variation
* Real-world distortions

---

## 🧠 Models Implemented

### 🔹 Traditional Machine Learning

* Support Vector Machine (SVM)
* Random Forest (RF)

### 🔹 Deep Learning

* Transfer Learning CNN (MobileNetV2)
* YOLOv5m (Object Detection)
* Faster R-CNN (Object Detection)

---

## ⚙️ Methodology

1. Data Collection (real retail environment)
2. Exploratory Data Analysis (EDA)
3. Data Augmentation
4. Model Training
5. Performance Evaluation
6. Deployment Feasibility Analysis

---

## 📊 Key Results

### 📌 Classification Performance

| Model                   | Accuracy |
| ----------------------- | -------- |
| CNN (Transfer Learning) | **100%** |
| SVM                     | 84.03%   |
| Random Forest           | 83.33%   |

---

### ⚡ Inference Speed

| Model         | Latency     |
| ------------- | ----------- |
| SVM           | **2.56 ms** |
| Random Forest | 27.84 ms    |
| CNN           | 36.51 ms    |

* Real-time threshold: **33.3 ms**
* Only SVM consistently meets real-time requirements

---

### 🔍 Object Detection Performance

* **YOLOv5m**

  * Fast (~211.9 ms)
  * Struggles in low/dark lighting

* **Faster R-CNN**

  * Slower (~1211.7 ms)
  * More consistent across all lighting conditions

---

## 💡 Key Insights

* ✅ Traditional ML models are **computationally efficient**
* ❌ But lack **scalability and spatial understanding**
* ✅ CNN provides **perfect accuracy**
* ❌ But requires optimization for real-time use
* ⚖️ YOLOv5m vs Faster R-CNN trade-off:

  * Speed vs Robustness

---

## 🚀 Conclusion

* **CNN (Transfer Learning)** is best for real-world deployment due to robustness
* **SVM** is viable for small-scale, low-resource systems
* **YOLOv5m** is ideal for real-time applications with good lighting
* **Faster R-CNN** is better for accuracy-critical environments

---

## 🛠️ Tech Stack

* Python
* TensorFlow / Keras
* PyTorch
* Scikit-learn
* OpenCV
* NumPy / Pandas
* Matplotlib

---

## 🔮 Future Work

* Expand dataset with more product classes
* Improve CNN inference speed using:

  * TensorFlow Lite
  * Model quantization
* Explore transformer-based vision models
* Deploy on embedded retail hardware

---

## 📜 License

This project is for academic and research purposes.

---

## 👤 Author

**Abdullah Bin Omar Jawaid**
MSc Data Science
University of Salford
