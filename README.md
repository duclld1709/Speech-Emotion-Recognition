![image](https://github.com/user-attachments/assets/49001d42-1b83-4cf9-85a8-36fb7adb674c)

# 🎙️ Custom CNN-based Emotion Recognition on EmoDB

This repository contains a custom Convolutional Neural Network (CNN) model for speech emotion recognition using the Berlin Database of Emotional Speech (**EmoDB**). Our model achieves an impressive **96% F1-Score** on the validation set.

---

## 📂 Dataset

- **Source**: [EmoDB on Kaggle](https://www.kaggle.com)  
- **Description**: The Berlin Database of Emotional Speech contains audio recordings of actors simulating 7 different emotions.
- **Feature Extraction**:  
  - Mel-frequency cepstral coefficients (**MFCC**)
  - First-order delta (velocity)
  - Second-order delta (acceleration)

**Data Distribution:**  
<table>
  <tr>
    <td><img src="https://github.com/user-attachments/assets/3cef5cf7-7adb-465d-bdf8-cff328ef6ff8" alt="Emotion Class Distribution" width="400"/></td>
    <td><img src="https://github.com/user-attachments/assets/9006f61f-aa34-4615-b35b-452ecc27d27d" alt="Audio Duration per Emotion" width="400"/></td>
  </tr>
</table>

---

## 🧩 Model Architecture

The custom CNN model consists of:
- **4 Convolutional Blocks**: Extract hierarchical features from input spectrograms.
- **Fully Connected Layer**: Maps features to the final **7 emotion classes** using a softmax activation.

**Architecture Overview:**  
![Model Diagram](https://github.com/user-attachments/assets/1629a19f-caa2-49bc-a3d7-ac273e811a8d)

---

## ⚙️ Experiment Setup

- **Platform**: Kaggle Notebook
- **Hardware**:  
  - GPU: NVIDIA Tesla P100 (16 GB VRAM)  
  - CPU: Intel Xeon @ 2.30GHz (2 cores)  
  - RAM: 13 GB

**Training Configuration:**
- Batch Size: **4**
- Epochs: **200**
- Validation Ratio: **15%**
- Test Ratio: **15%**
- Loss Function: `CrossEntropyLoss`
- Optimizer: `Adam` (`lr = 1e-4`)
- Learning Rate Scheduler: `ReduceLROnPlateau` (patience = 5, factor = 0.5)

---

## ✅ Results

- **Training Time**: ~6 minutes (~358.6 seconds) for 200 epochs.
- **Best Validation F1-Score**: **96%**

**Training Curves:**  
<table>
  <tr>
    <td><img src="https://github.com/user-attachments/assets/4db3141a-307d-4c45-bbc6-d7cc9e63f54e" alt="Loss Curve" width="400"/></td>
    <td><img src="https://github.com/user-attachments/assets/62b57262-e3d6-499f-864d-2e252a63860f" alt="F1 Score Curve" width="400"/></td>
  </tr>
</table> 

**Classification Report:**  
<img src="https://github.com/user-attachments/assets/1b0cbd7e-db6f-4b1e-b5fa-9d1b08d509c0" alt="Classification Report" width="600"/>

---

## 📄 Files in Repository

| File | Description |
|------|--------------|
| `.gitignore` | Standard Git ignore file |
| `EDA.ipynb` | Notebook for Exploratory Data Analysis |
| `LICENSE` | License file |
| `README.md` | Project documentation |
| `Train.ipynb` | Notebook for training the CNN model |

---

## 🚀 How to Run

1. Clone the repository  
   ```bash
   git clone https://github.com/duclld1709/Speech-Emotion-Recognition.git
   cd Speech-Emotion-Recognition
   ```
2. Open `EDA.ipynb` for data exploration.
3. Run `Train.ipynb` to train the model.
