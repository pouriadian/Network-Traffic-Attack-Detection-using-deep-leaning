
#  NSL-KDD Network Intrusion Detection with Feature Selection and Deep Learning

## 📌 Overview
This project implements a **Network Intrusion Detection System (NIDS)** using the **NSL-KDD dataset**.  
It combines **feature engineering, feature selection, and deep learning models** (Conv1D CNN & LSTM) to detect network intrusions with **high accuracy**.

The main objectives are:
- Preprocess and transform raw network traffic data.
- Select the most important features using **RandomForest feature importance**.
- Train deep learning models (Conv1D CNN & LSTM) for intrusion detection.
- Achieve **>98% test accuracy** while maintaining model efficiency.

---

## 📊 Dataset
The **NSL-KDD** dataset is a well-known benchmark for intrusion detection.  
It contains normal and attack traffic records with **41 features** plus a label.

**Data sources:**
- [NSL-KDD Train Data](https://raw.githubusercontent.com/merteroglu/NSL-KDD-Network-Instrusion-Detection/master/NSL_KDD_Train.csv)  
- [NSL-KDD Test Data](https://raw.githubusercontent.com/merteroglu/NSL-KDD-Network-Instrusion-Detection/master/NSL_KDD_Test.csv)

**Label examples:**
- `normal`
- `neptune`, `satan`, `ipsweep`, `portsweep`, `smurf`, ...
- Binary conversion: `0 = attack`, `1 = normal`

---

## ⚙️ Features
### **1. Data Preprocessing**
- Standardization of numerical features (**StandardScaler**).
- One-hot encoding for categorical features (**OneHotEncoder**).
- Split into training, validation, and test sets.

### **2. Feature Selection**
- **RandomForestClassifier** is used to compute feature importance.
- Top **30 features** are selected to reduce dimensionality and improve training speed.

### **3. Models Implemented**
#### **CNN (Conv1D) Model**
- 4 convolutional layers with **BatchNormalization**.
- Fully connected dense layers with **Dropout** for regularization.
- Achieved **98.46% test accuracy**.

#### **LSTM Encoder-Decoder Model**
- Multi-layer LSTM encoder-decoder structure.
- Suitable for sequential feature learning.
- Achieved **~99% validation accuracy**.

---

## 📂 Project Structure
```

📦 NSL-KDD-Intrusion-Detection
┣ 📜 cnn\_nsl\_98.keras           # Saved CNN model weights
┣ 📜 LSTM\_nSL\_99.keras          # Saved LSTM model weights
┣ 📜 intrusion\_detection.py     # Main training & evaluation script
┣ 📜 README.md                  # Project documentation
┗ 📜 requirements.txt           # Python dependencies

````

---

## 🖥️ Installation & Usage
### **1. Clone the repository**
```bash
git clone https://github.com/yourusername/NSL-KDD-Intrusion-Detection.git
cd NSL-KDD-Intrusion-Detection
````

### **2. Install dependencies**

```bash
pip install -r requirements.txt
```

### **3. Run the project**

```bash
python intrusion_detection.py
```

---

## 📈 Results

| Model                | Test Accuracy | Notes                               |
| -------------------- | ------------- | ----------------------------------- |
| Conv1D CNN           | **98.46%**    | Fast and robust                     |
| LSTM Encoder-Decoder | **99%**       | High sequential learning capability |

---

## 🔍 Key Insights

* Feature selection drastically reduces training time while preserving accuracy.
* CNN handles spatial feature patterns well in intrusion detection.
* LSTM excels in capturing sequential dependencies in network data.

---

## 🛠 Technologies Used

* **Python 3.11**
* **Pandas, NumPy, Scikit-learn**
* **TensorFlow / Keras**
* **RandomForestClassifier**
* **NSL-KDD Dataset**

