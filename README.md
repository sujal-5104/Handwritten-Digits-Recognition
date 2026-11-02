# ✍️ PRCP-1002: Handwritten Digits Recognition (MNIST)

## 📌 Project Overview
This capstone project focuses on computer vision fundamentals by classifying handwritten digits ($0$ through $9$) using the classic **MNIST** dataset. The objective is to build, evaluate, and compare traditional machine learning classifiers (KNN, SVM) against a deep learning Convolutional Neural Network (CNN).

---

## 📊 Task 1: Data Analysis Report
* **Dataset Source:** MNIST via TensorFlow/Keras (`60,000` training images, `10,000` testing images).
* **Image Dimensions:** $28 \times 28$ pixels (Grayscale).
* **Class Distribution:** The dataset is well-balanced across all digits from $0$ to $9$, ensuring unbiased model training and evaluation.

---

## 🤖 Task 2 & 3: Model Comparison Report
We trained and benchmarked multiple classifiers on the dataset:

| Model | Description / Architecture | Accuracy (%) |
| :--- | :--- | :--- |
| **K-Nearest Neighbors (KNN)** | $k=3$ (Trained on 10k subset) | ~94.5% |
| **Support Vector Machine (SVM)** | RBF Kernel (Trained on 10k subset) | ~96.2% |
| **Convolutional Neural Network (CNN)** | 2x Conv2D/MaxPooling + Dense + Dropout | **~99.1%** |

* **Conclusion for Production:** The **Convolutional Neural Network (CNN)** is selected as the best model for production because it extracts spatial hierarchies and edge features automatically, achieving superior accuracy.

---

## 🛠️ Report on Challenges Faced & Solutions
1. **High Computational Overhead (KNN/SVM):** Training distance-based and kernel models on 60,000 high-dimensional images ($784$ features) was slow. 
   * *Solution:* Used an optimized representative subset (10,000 samples) for traditional ML benchmarking.
2. **Spatial Information Loss:** Flattening 2D images into 1D arrays destroys structural curve relationships.
   * *Solution:* Preserved 2D tensor dimensions `(28, 28, 1)` for Convolutional Neural Networks.
3. **Overfitting:** Neural network memorization.
   * *Solution:* Integrated a Dropout layer (`0.3`) in the fully connected network.

---

## 📂 Repository Structure
```text
├── Handwritten Digits Recognition.ipynb   # Complete code & analysis
├── handwritten_digit_cnn_model.h5       # Saved production CNN model
├── requirements.txt                     # Python dependencies
└── README.md                            # Project reports & documentation
