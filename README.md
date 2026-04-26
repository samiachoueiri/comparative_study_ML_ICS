# CPS Attack Detection using Machine Learning

This repository contains the implementation, datasets, and supporting materials for a comparative study of machine learning techniques for detecting cyber-attacks in cyber-physical systems (CPS), with a focus on Modbus/TCP network traffic.

📄 Full paper: :contentReference[oaicite:0]{index=0}

---

## 📌 Project Overview

Cyber-physical systems (CPS) are critical to infrastructure such as energy, manufacturing, and transportation. With increasing IT/OT convergence, these systems are more vulnerable to cyber-attacks.

This project explores and compares multiple machine learning approaches for detecting malicious activity in CPS network traffic, including:

- Supervised learning (Random Forest, SVM, MLP)
- Deep learning (Recurrent Neural Networks)
- Unsupervised anomaly detection (Isolation Forest, DBSCAN, LOF)
- Reinforcement learning (DQN-based approach)

The goal is to evaluate trade-offs between:
- Accuracy
- Interpretability
- Computational cost
- Real-time applicability

---

## 📂 Repository Structure

. <br>
├── datasets/ # Raw and processed datasets <br>
├── figures/ # Plots, ROC curves, visualizations <br>
├── notebooks/ # Jupyter notebooks for experiments <br>
├── papers/ # Research papers and references <br>
├── term paper/ # Final report and documentation <br>
├── 1- Project Selection.docx <br>
├── 2- Feature Selection.docx <br>
├── 2- Feature Selection.pdf <br>
├── milestone presentation.pptx <br>
├── final presentation.pptx <br>
└── README.md


---

## ⚙️ Methodology

The project follows a two-stage workflow:

### 1. Offline Model Preparation
- Data preprocessing
- Feature extraction (e.g., packet size, inter-arrival time, Modbus features)
- Train models using different learning paradigms

### 2. Online Inference
- Apply trained models to unseen network traffic
- Detect anomalies or classify attacks in real time

*(See workflow diagram in the paper, Fig. 3)*

---

## 📊 Datasets

The study uses two main datasets:

### 🔹 Zenodo ICS Dataset
- CPS bottle-filling system
- Includes:
  - Modbus/TCP network traffic
  - System logs
  - Sensor readings
- Contains both faults and cyber-attacks

### 🔹 DataSense Dataset
- Large-scale IIoT environment
- Focus on diverse cyber-attacks:
  - DoS / DDoS
  - Man-in-the-middle
  - Brute force
  - Malware

---

## 🧠 Models Evaluated

### Supervised Learning
- Random Forest (best classical performance)
- Support Vector Machine (SVM)
- Multi-Layer Perceptron (MLP)

### Deep Learning
- Recurrent Neural Network (RNN)
- Captures temporal dependencies in traffic sequences
- Achieved highest overall performance

### Unsupervised Learning
- Isolation Forest
- DBSCAN
- Local Outlier Factor (LOF)

### Reinforcement Learning
- Deep Q-Network (DQN)
- Models detection as a sequential decision problem

---

## 📈 Key Results

- ✅ **RNN achieved the best performance** by leveraging temporal patterns  
- ✅ **Random Forest** performed best among classical models  
- ⚠️ Unsupervised methods performed significantly worse due to lack of labels  
- 🧪 Reinforcement learning showed promising but preliminary results  

---

## 🔍 Feature Engineering

Key features extracted from Modbus traffic include:

- Packet size statistics (min, max, mean)
- Inter-arrival time (IAT)
- Request/response counts

SHAP analysis shows that features like:
- `modbus_req`
- `pkt_size_mean`
- `iat_mean`

are the most influential.

---

## 🚀 How to Use

1. Clone the repository:
```bash
git clone https://github.com/your-username/cps-attack-detection.git
cd cps-attack-detection