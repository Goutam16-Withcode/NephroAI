# 🩺 NephroAI — Real-Time Chronic Kidney Disease (CKD) Clinical Intelligence Platform

[![NephroAI](https://img.shields.io/badge/Platform-NephroAI%20v3.2-0284c7.svg?style=for-the-badge&logo=mediamarkt&logoColor=white)]()
[![Python](https://img.shields.io/badge/Python-3.9%2B-blue.svg?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![Streamlit](https://img.shields.io/badge/Streamlit-App-FF4B4B.svg?style=for-the-badge&logo=streamlit&logoColor=white)](https://streamlit.io)
[![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Machine%20Learning-F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white)](https://scikit-learn.org)
[![Accuracy](https://img.shields.io/badge/Model%20Accuracy-98.8%25-brightgreen.svg?style=for-the-badge)]()
[![AUC-ROC](https://img.shields.io/badge/AUC--ROC-0.96-success.svg?style=for-the-badge)]()
[![License](https://img.shields.io/badge/License-MIT-purple.svg?style=for-the-badge)]()

**NephroAI** is an advanced, machine learning-powered clinical decision support system designed for early screening, risk stratification, and diagnostic intelligence in Chronic Kidney Disease (CKD). Featuring a hospital-grade Streamlit web interface with real-time risk gauges, CKD-EPI eGFR staging, what-if scenario simulations, batch CSV scoring, benchmark analytics, and automated PDF medical report generation.

---

## 📌 Table of Contents
- [Executive Overview](#-executive-overview)
- [Key Features of NephroAI](#-key-features-of-nephroai)
- [Model Evaluation & Benchmarks](#-model-evaluation--benchmarks)
- [ROC Curve Analysis](#-roc-curve-analysis)
- [System Architecture](#-system-architecture)
- [Clinical Biomarkers & Features](#-clinical-biomarkers--features)
- [Installation & Quick Start](#-installation--quick-start)
- [Running NephroAI](#-running-nephroai)
- [Clinical PDF Report Export](#-clinical-pdf-report-export)
- [Medical Safety Disclaimer](#-medical-safety-disclaimer)

---

## 🔬 Executive Overview

Chronic Kidney Disease (CKD) impacts over 850 million people worldwide. Because kidney damage often progresses asymptomatically during its initial stages, early screening and clinical triage are vital to prevent progression to End-Stage Renal Disease (ESRD).

**NephroAI** addresses this challenge by combining:
1. **Multi-Algorithm Clinical Benchmarking**: Empirical evaluation across 7 supervised models (Random Forest, XGBoost, GBDT, Decision Tree, Logistic Regression, SVM, KNN).
2. **High-Accuracy Production Engine**: Deploying a **Random Forest Classifier** with **98.8% Accuracy** and **0.96 AUC-ROC** score.
3. **Diagnostic Intelligence Suite**: Integrating real-time eGFR (CKD-EPI) calculations, KDIGO stage mapping (G1 to G5), dynamic Plotly biomarker gauges, vital fingerprint radar charts, and explainable feature contributions.
4. **Hospital Workflow Integration**: Session triage registry, one-click patient presets, batch CSV screening, and downloadable formatted PDF clinical reports.

---

## 🌟 Key Features of NephroAI

- **⚡ 1-Click Patient Presets**: Instantly pre-populate typical profiles: *Healthy Adult*, *Borderline/At-Risk*, or *Severe CKD*.
- **🎯 Real-Time ML Risk Stratification**: Immediate diagnosis (*Low Risk / Negative* vs. *High Risk / Positive for CKD*) with prediction confidence percentage.
- **🧮 CKD-EPI eGFR & KDIGO Staging**: Automated calculation of Estimated Glomerular Filtration Rate and official 5-stage KDIGO classification.
- **📊 Interactive Vital Gauges & Radar**: Plotly visual gauges for Serum Creatinine, Blood Pressure, and Hemoglobin, plus a multi-axial vital radar fingerprint.
- **🚨 Automated Clinical Flags**: Triage warnings for Stage 1/2 Hypertension, Hyperglycemia, Azotemia, Anemia, and Proteinuria.
- **🔮 Interactive What-If Simulator**: Experiment with adjusting vitals (e.g. lowering Blood Pressure or Creatinine) to see simulated risk trajectory in real time.
- **📂 Batch CSV Screening**: Upload a roster of patients or generate synthetic cohorts for automated multi-patient risk screening and CSV export.
- **📈 Native Model Performance Auditing**: Direct in-app display of benchmark charts (`PE_kidney.jpeg` and `roc_kidney.jpeg`).
- **📄 Downloadable Clinical PDF Reports**: Generate official diagnostic summaries for patient records with clinical observations and doctor sign-off fields.

---

## 📊 Model Evaluation & Benchmarks

NephroAI was developed through rigorous cross-validation across 7 machine learning architectures. **Random Forest (RF)** exhibited superior generalization with minimal false-positive rates.

![Model Performance Evaluation](PE_kidney.jpeg)

| Model | Accuracy (%) | ROC Score (%) | AUC-ROC Area | Performance Rank |
| :--- | :---: | :---: | :---: | :---: |
| **Random Forest (RF)** ⭐ | **98.8%** | **98.2%** | **0.96** | **#1 (Production Engine)** |
| **XGBoost** | 96.2% | 94.6% | 0.95 | #2 |
| **GBDT (Gradient Boosted Trees)** | 96.2% | 94.6% | 0.95 | #3 |
| **Decision Tree (DT)** | 93.8% | 93.3% | 0.96 | #4 |
| **Logistic Regression (LR)** | 92.5% | 91.8% | 0.92 | #5 |
| **Support Vector Machine (SVM)** | 76.2% | 72.7% | 0.73 | #6 |
| **K-Nearest Neighbors (KNN)** | 57.5% | 57.4% | 0.57 | #7 |

---

## 📈 ROC Curve Analysis

Receiver Operating Characteristic (ROC) curves illustrate the diagnostic sensitivity (True Positive Rate) against (1 - Specificity) (False Positive Rate) across classification thresholds.

![ROC Curve Analysis](roc_kidney.jpeg)

- **Random Forest & Decision Tree** achieve a near-optimal curve with an **AUC of 0.96**, demonstrating robust sensitivity while maintaining very low false alarms.
- **XGBoost & GBDT** follow closely at **AUC = 0.95**.
- **Distance-based algorithms (KNN)** struggled due to mixed continuous and categorical distributions, highlighting the efficacy of tree-based ensembles for clinical tabular records.

---

## 🧬 Clinical Biomarkers & Features

NephroAI evaluates 24 clinical parameters grouped across three diagnostic pillars:

### 1. Patient Demographics & Urinalysis
- **Age**: Patient age in years (1 - 120)
- **Blood Pressure (`bp`)**: Resting blood pressure in mm/Hg
- **Specific Gravity (`sg`)**: Urine specific gravity (1.005, 1.010, 1.015, 1.020, 1.025)
- **Albumin (`al`)**: Proteinuria scale (0 to 5)
- **Sugar (`su`)**: Glycosuria scale (0 to 5)

### 2. Blood Chemistry & Renal Function
- **Blood Glucose Random (`bgr`)**: Serum glucose level (mg/dL)
- **Blood Urea (`bu`)**: Blood urea nitrogen marker (mg/dL)
- **Serum Creatinine (`sc`)**: Primary glomerular filtration marker (mg/dL)
- **Electrolytes (`sod`, `pot`)**: Sodium & Potassium levels (mEq/L)
- **Hemoglobin (`hemo`)**: Oxygen-carrying capacity (g/dL)
- **Bacteriuria (`ba`)**: Presence of bacteria (`present` / `notpresent`)

### 3. Hematology, Microscopy & Comorbidities
- **Packed Cell Volume (`pcv`)**, **White Blood Cell Count (`wc`)**, **Red Blood Cell Count (`rc`)**
- **Microscopy**: Urine Red Blood Cells (`normal`/`abnormal`), Pus Cells (`normal`/`abnormal`), Pus Cell Clumps
- **Comorbidities & History**: Hypertension (`htn`), Diabetes Mellitus (`dm`), Coronary Artery Disease (`cad`), Pedal Edema (`pe`), Anemia (`ane`), Appetite (`good`/`poor`)

---

## 📂 Project Structure

```
Kidney-Diesease-Prediction/
├── app.py                      # Production NephroAI Streamlit application
├── kindey.pkl                  # Serialized trained Random Forest ML model
├── PE_kidney.jpeg              # Benchmark performance evaluation bar chart
├── roc_kidney.jpeg             # ROC-AUC curves comparison plot
├── code_project.ipynb          # End-to-end data preprocessing, EDA & ML training
├── requirements.txt            # Python package dependencies
└── README.md                   # NephroAI platform documentation
```

---

## 🚀 Installation & Quick Start

### Prerequisites
- Python 3.9 or higher
- Git & virtual environment manager

### 1. Clone the Repository
```bash
git clone https://github.com/Goutam16-Withcode/Kidney-Diesease-Prediction.git
cd Kidney-Diesease-Prediction
```

### 2. Set Up Virtual Environment (Recommended)
```bash
# Windows
python -m venv venv
venv\Scripts\activate

# Linux / macOS
python3 -m venv venv
source venv/bin/activate
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

---

## 💻 Running NephroAI

Start the NephroAI application:
```bash
streamlit run app.py
```

The application will start immediately at:
🌐 **`http://localhost:8501`**

### Running the Analysis Notebook
To inspect the exploratory data analysis and model training:
```bash
jupyter notebook code_project.ipynb
```

---

## 📄 Clinical PDF Report Export

NephroAI compiles a multi-page medical PDF report for each assessed patient:
- **Parameters**: Patient Demographics, Vitals, Renal Function Markers, eGFR and KDIGO Staging, Diagnostic Classification, Confidence %, and Risk Flags.
- **One-Click Export**: Click **Download Official Medical Report (.PDF)** to export.

---

## ⚠️ Medical Safety Disclaimer

> **IMPORTANT**: NephroAI is an auxiliary clinical decision support and research system designed to assist qualified healthcare professionals. It **does not replace professional medical diagnosis, laboratory biopsy, or specialist nephrology consultation**. Always verify predictions with clinical laboratory tests.
