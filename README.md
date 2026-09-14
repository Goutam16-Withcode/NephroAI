# 🩺 NephroAI — Real-Time Chronic Kidney Disease (CKD) Clinical Intelligence Platform

[![Live Demo](https://img.shields.io/badge/Streamlit%20Cloud-Live%20Demo-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white)](https://goutam16-withcode-nephroai-app-tcvbsm.streamlit.app/)
[![GitHub](https://img.shields.io/badge/GitHub-Repository-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Goutam16-Withcode/Kidney-Diesease-Prediction)
[![Python](https://img.shields.io/badge/Python-3.9%2B-blue.svg?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Machine%20Learning-F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white)](https://scikit-learn.org)
[![Accuracy](https://img.shields.io/badge/Model%20Accuracy-98.8%25-brightgreen.svg?style=for-the-badge)]()
[![AUC-ROC](https://img.shields.io/badge/AUC--ROC-0.96-success.svg?style=for-the-badge)]()
[![License](https://img.shields.io/badge/License-MIT-purple.svg?style=for-the-badge)]()

---

> ### 🌐 **Live Cloud Application**
> **Launch NephroAI in your browser with zero installation:**  
> 🔗 **[https://goutam16-withcode-nephroai-app-tcvbsm.streamlit.app/](https://goutam16-withcode-nephroai-app-tcvbsm.streamlit.app/)**  
> *Fully interactive: 1-click clinical presets, CKD-EPI staging, real-time Plotly gauges, What-If simulator, and PDF clinical report downloads.*

---

## 📌 Table of Contents
- [Executive Overview](#-executive-overview)
- [Live Cloud Application](#-live-cloud-application)
- [Key Features of NephroAI](#-key-features-of-nephroai)
- [Model Evaluation & Benchmarks](#-model-evaluation--benchmarks)
- [ROC Curve Analysis](#-roc-curve-analysis)
- [Clinical Biomarkers & Features](#-clinical-biomarkers--features)
- [System Architecture](#-system-architecture)
- [Installation & Quick Start](#-installation--quick-start)
- [Programmatic API Usage](#-programmatic-api-usage)
- [Clinical PDF Report Export](#-clinical-pdf-report-export)
- [Medical Safety Disclaimer](#-medical-safety-disclaimer)

---

## 🔬 Executive Overview

Chronic Kidney Disease (CKD) affects over 850 million individuals worldwide. Because nephron destruction occurs asymptomatically in early phases, proactive screening and clinical triage are vital to prevent progression to End-Stage Renal Disease (ESRD) and dialysis.

**NephroAI** delivers:
1. **Multi-Model Empirical Benchmarking**: Rigorous evaluation across 7 supervised algorithms (Random Forest, XGBoost, GBDT, Decision Tree, Logistic Regression, SVM, KNN).
2. **State-of-the-Art Production Engine**: Deploys a **Random Forest Classifier** achieving **98.8% Accuracy** and **0.96 AUC-ROC** score.
3. **Diagnostic Intelligence Suite**: Real-time **CKD-EPI (2021) eGFR** computation, **KDIGO staging (G1 to G5)**, interactive Plotly vital gauges, radar vital fingerprinting, and explainable feature risk attribution.
4. **Clinical Workflow Tools**: 1-click clinical presets, what-if scenario simulator, cohort batch screening, session triage registry, and automated PDF medical summaries.

---

## 🌐 Live Cloud Application

The platform is deployed live on Streamlit Community Cloud:

👉 **[Launch NephroAI Live Web App](https://goutam16-withcode-nephroai-app-tcvbsm.streamlit.app/)**

### Highlights on the Cloud Instance:
- **Instant Testing**: Use the sidebar presets (**🟢 Healthy**, **🟡 Borderline**, **🔴 Severe CKD**) to test realistic clinical cases with 1 click.
- **Interactive Gauges**: Real-time radial meters for Blood Pressure, Serum Creatinine, and Hemoglobin.
- **What-If Simulation**: Adjust therapeutic sliders (e.g. lowering Blood Pressure or Creatinine) to observe projected eGFR recovery.
- **Instant PDF Export**: Generate and download an official diagnostic clinical report in seconds.

---

## 🌟 Key Features of NephroAI

| Feature | Description |
| :--- | :--- |
| **⚡ 1-Click Patient Presets** | Pre-populate realistic profiles: *Healthy Adult*, *Borderline/At-Risk*, or *Severe CKD*. |
| **🎯 Real-Time ML Stratification** | Immediate classification into *Low Risk (Negative)* or *High Risk (Positive for CKD)* with confidence probability. |
| **🧮 CKD-EPI eGFR & KDIGO Staging** | Computes estimated Glomerular Filtration Rate and categorizes into official stages (G1 to G5). |
| **📊 Interactive Vital Gauges & Radar** | Plotly visual meters for Serum Creatinine, BP, and Hemoglobin plus multi-axial vital radar fingerprint. |
| **🔍 Explainable AI (XAI)** | Dynamic relative diagnostic impact bar chart showing which biomarkers drove the risk score. |
| **🚨 Automated Clinical Flags** | Triage alert cards for Stage 1/2 Hypertension, Hyperglycemia, Azotemia, Anemia, and Proteinuria. |
| **🔮 What-If Scenario Simulator** | Test therapeutic interventions (e.g. glycemic or BP control) to project eGFR trajectory changes. |
| **📂 Batch Cohort Screening** | 1-click synthetic patient cohort scoring with risk distribution donut chart and downloadable CSV. |
| **🏥 Live Session Triage Registry** | Automatic logging of screened patients during the active session with CSV export. |
| **📄 Official Clinical PDF Export** | Downloadable hospital-grade summary with biomarker panels, eGFR, KDIGO staging, and physician signature block. |

---

## 📊 Model Evaluation & Benchmarks

NephroAI was trained and evaluated through stratified cross-validation across 7 machine learning models. **Random Forest (RF)** delivered the strongest diagnostic sensitivity with near-zero false alarms.

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

### 4. Run the Streamlit Dashboard Locally
```bash
streamlit run app.py
```
Open **`http://localhost:8501`** in your browser.

---

## 💻 Programmatic API Usage

You can also run inference directly in Python scripts:

```python
import pickle
import pandas as pd

# Load the production Random Forest model
with open('kindey.pkl', 'rb') as f:
    model = pickle.load(f)

# Patient clinical parameter dictionary
patient_sample = {
    'age': 52, 'blood_pressure': 90, 'specific_gravity': 1.015, 'albumin': 1, 'sugar': 1,
    'red_blood_cells': 1, 'pus_cell': 1, 'pus_cell_clumps': 0, 'bacteria': 0,
    'blood_glucose_random': 145.0, 'blood_urea': 44.0, 'serum_creatinine': 1.4,
    'sodium': 136.0, 'potassium': 4.5, 'haemoglobin': 12.1,
    'packed_cell_volume': 38.0, 'white_blood_cell_count': 8900.0,
    'red_blood_cell_count': 4.4, 'hypertension': 1,
    'diabetes_mellitus': 0, 'coronary_artery_disease': 0,
    'appetite': 0, 'peda_edema': 0, 'aanemia': 0
}

df = pd.DataFrame([patient_sample])
prediction = model.predict(df)[0]
confidence = model.predict_proba(df)[0][prediction] * 100

print("Diagnosis:", "Positive for CKD (High Risk)" if prediction == 0 else "Negative (Low Risk)")
print(f"Confidence: {confidence:.2f}%")
```

---

## 📄 Clinical PDF Report Export

NephroAI automatically compiles a formal medical PDF report for each assessed case using ReportLab:
- **Includes**: Clinic Header Ribbon, Patient ID, Clinical Timestamps, Measured Biomarker Panels, CKD-EPI eGFR, KDIGO Stage, Diagnostic Classification, Confidence %, Flagged Alerts, and Physician Sign-off field.
- **Export**: Click **Download Official Medical Report (.PDF)** to save a permanent record.

---

## ⚠️ Medical Safety Disclaimer

> **IMPORTANT**: NephroAI is an auxiliary clinical decision support and research system designed to assist qualified healthcare professionals. It **does not replace professional medical diagnosis, laboratory biopsy, or specialist nephrology consultation**. Always verify predictions with clinical laboratory tests.
