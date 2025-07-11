# ECG-Beat-Classification-using-CNN

---

## 📚 Dataset

The dataset used in this project is the **MIT-BIH Arrhythmia Database**, comprising **112,647 ECG beat samples**. This dataset is a benchmark for ECG signal analysis and is publicly available via the [PhysioNet repository](https://www.physionet.org/physiobank/database/mitdb/).

> **Citation**  
Goldberger, A., Amaral, L., Glass, L., Hausdorff, J., Ivanov, P.C., Mark, R., Mietus, J.E., Moody, G.B., Peng, C.K. and Stanley, H.E., 2000. PhysioBank, PhysioToolkit, and PhysioNet: Components of a new research resource for complex physiologic signals. *Circulation*, 101(23), pp.e215–e220.  
RRID:SCR_007345

---

## 🧪 Experiments Overview

The `experiments_done` folder contains all major experiments conducted during the project, in the following order:

### 🔹 Baseline Models
1. **Pure CNN** – Convolutional Neural Network trained on the original imbalanced dataset.
2. **Pure DNN** – Deep Neural Network trained without any resampling.

### 🔹 Resampling Techniques
3. **Random Undersampling (RU)** – Downsamples the majority class to match minority class distribution.
4. **SMOTE** – Synthetic Minority Over-sampling Technique to balance class distribution.

### 🔹 Data Synthesis and Hybrid Methods
5. **GAN** – Generative Adversarial Network trained to generate synthetic ECG beats.
6. **SMOTE + RU** – Combined strategy to over- and under-sample for a fully balanced dataset.
7. **SMOTE + GAN** – Uses SMOTE first, followed by realistic synthetic data from GAN.
8. **Bootstrap + GAN** – Uses bootstrapped sampling before applying GAN-based augmentation.

---

## 🧠 Model Architecture

The **CNN model** used for classification consists of:
- 4 Convolutional layers  
- 4 MaxPooling layers  
- 2 Fully Connected layers  
- 1 Output layer

Both CNN and DNN models were evaluated using **Stratified 5-Fold Cross-Validation** to ensure class distribution was preserved across folds.

---

## 📊 Selected Results Summary

Below is a performance comparison of the **final selected experiments** (A, B, C):

| Dataset  | Resampling Strategy | Accuracy (%) | Precision (%) | Recall (%) | F1 Score (%) |
|----------|---------------------|--------------|----------------|-------------|---------------|
| A        | SMOTE + RU          | 98.98        | 98.98         | 98.98      | 98.98         |
| B        | SMOTE + GAN         | **99.35**    | **99.42**     | 99.25      | **99.33**     |
| C        | GAN only            | 99.13        | 99.42         | 98.75      | 99.08         |

> 📌 *Full experimental results for all 8 strategies are provided in the `experiments_done` folder.*

---

## 🧾 Summary

- The hybrid **SMOTE + GAN approach (Dataset B)** achieved the best overall performance.
- **GAN** generated data improved both realism and diversity in minority beat classes.
- CNN outperformed DNN in almost all setups, especially in highly imbalanced conditions.
- Comprehensive resampling and augmentation strategies yielded consistently high metrics (Accuracy, F1 > 98%).

---

## 👩‍💻 Author

**Lee Rong Xian**  
Bachelor of Computer Science (Bioinformatics), Universiti Teknologi Malaysia  
Class of 2025

---

## 📩 Contact

- 📧 Email: [your-email@example.com]
- 🌐 LinkedIn: [Your LinkedIn URL]

---

## 🛠 Technologies Used

- Python, NumPy, Pandas
- TensorFlow / Keras
- SciKit-learn
- Matplotlib, Seaborn
- PhysioNet's WFDB Toolkit

---

## ⭐ Acknowledgments

Special thanks to:
- PhysioNet and the MIT-BIH Arrhythmia Database team
- My supervisor and fellow researchers
- Open-source libraries that enabled this work
