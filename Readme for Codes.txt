# AI Powered Self-Checkout Systems in Retail Environments — Machine Learning Project

---

## File Overview

data_augmentation.ipynb

Generates augmented training images from raw product photos using Keras `ImageDataGenerator`, applying random rotations, flips, zooms, and shifts — producing 30 augmented variants per original image. It then automatically splits the augmented dataset into **train (80%)** and **test (20%)** folders for both the products and fruits datasets.

---

EDA_Analysis.ipynb

Performs exploratory data analysis on the training dataset by examining class distribution, image resolution statistics, and sample visualisations per class. It produces bar charts and histograms to surface any class imbalance or resolution inconsistencies before model training begins.

---

SVM.ipynb

Trains a **Support Vector Machine (SVM)** classifier on flattened, resized product images using an sklearn pipeline with PCA dimensionality reduction and standard scaling. Model performance is evaluated via accuracy score, classification report, and a confusion matrix, with the trained model saved using `joblib`.

---

RF.ipynb

Trains a **Random Forest** classifier on 64×64 pixel-flattened product images as a traditional ML baseline. Evaluation includes a full classification report and a seaborn-rendered confusion matrix, providing a comparison point against the deeper learning models.

---

pixel_based_cnn_analysis.ipynb

Builds and trains a **custom CNN from scratch** in PyTorch on raw pixel data at 224×224 resolution. The notebook includes dataset loading with a 15% validation split, training loop with loss/accuracy tracking, and a final evaluation against a held-out test set under challenging (bad) lighting conditions.

---

cnn_transfer_learning.ipynb

Fine-tunes a pretrained **MobileNetV2** backbone (ImageNet weights) with a custom classification head using TensorFlow/Keras. Training is done in two phases — first with frozen base layers, then with selective unfreezing — using brightness augmentation to simulate poor lighting environments that reflect real-world deployment conditions.

---

faster_rcnn.ipynb

Implements an **object detection** pipeline using Faster R-CNN (torchvision) trained on YOLO-format annotated product images converted to bounding-box tensors. The notebook covers dataset preparation, model fine-tuning with a custom detection head for 6 product classes plus background, and inference on validation images.

---

Yolov5m.ipynb

Trains a **YOLOv5m** object detection model on Google Colab using the Ultralytics YOLOv5 repository, with the dataset and `dataset.yaml` config loaded from Google Drive. Training runs for 30 epochs with early stopping, and the best weights are saved back to Drive; inference is then run on test images with bounding-box results exported.

---

benchmark_efficiency_latency.ipynb (Additional coding)

Benchmarks and compares **inference latency and memory usage** across all trained models (SVM, Random Forest, MobileNetV2 CNN). It measures per-sample prediction time with warm-up runs for JIT stability, tracks peak memory with `tracemalloc`, and visualises the results as comparative bar charts to support model selection for deployment.

---

