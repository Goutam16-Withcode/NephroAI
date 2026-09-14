# 🏥 Chronic Kidney Disease (CKD) Prediction & Clinical Risk Intelligence

[![Python](https://img.shields.io/badge/Python-3.9%2B-blue.svg?logo=python&logoColor=white)](https://python.org)
[![Streamlit](https://img.shields.io/badge/Streamlit-App-FF4B4B.svg?logo=streamlit&logoColor=white)](https://streamlit.io)
[![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Machine%20Learning-F7931E.svg?logo=scikit-learn&logoColor=white)](https://scikit-learn.org)
[![Accuracy](https://img.shields.io/badge/Best%20Model%20Accuracy-98.8%25-brightgreen.svg)]()
[![AUC-ROC](https://img.shields.io/badge/AUC--ROC-0.96-success.svg)]()
[![License](https://img.shields.io/badge/License-MIT-purple.svg)]()

An advanced machine learning-powered clinical decision support system designed to screen, assess, and predict the risk of Chronic Kidney Disease (CKD). Featuring an interactive, hospital-grade Streamlit web application with real-time risk gauges, model benchmark analytics, clinical flags, and downloadable patient PDF reports.

---

## 📌 Table of Contents
- [Executive Overview](#-executive-overview)
- [Key Features](#-key-features)
- [Model Evaluation & Benchmarks](#-model-evaluation--benchmarks)
- [ROC Analysis](#-roc-analysis)
- [System Architecture](#-system-architecture)
- [Clinical Biomarkers & Features](#-clinical-biomarkers--features)
- [Quick Start & Installation](#-quick-start--installation)
- [Running the Application](#-running-the-application)
- [Clinical PDF Report Generation](#-clinical-pdf-report-generation)
- [Disclaimer](#-clinical-disclaimer)

---

## 🔬 Executive Overview

Chronic Kidney Disease (CKD) often progresses silently without pronounced symptoms until advanced stages. Early diagnosis and intervention significantly improve patient prognosis and prevent renal failure.

This project delivers:
1. **Multi-Model Machine Learning Benchmark**: Evaluates 7 distinct algorithms (Random Forest, XGBoost, GBDT, Decision Tree, Logistic Regression, SVM, KNN) on clinical patient records.
2. **Production Ensemble Model**: Deploys a **Random Forest Classifier** reaching **98.8% Accuracy** and **0.96 AUC-ROC** score.
3. **Interactive Clinical UI**: Built with Streamlit, custom medical typography, dynamic interactive Plotly gauges, fast one-click patient presets, and automated clinical flag detections.
4. **Automated Diagnostic Reporting**: Generates formatted PDF medical summaries on the fly with ReportLab.

---

## 🌟 Key Features

- **⚡ Fast-Track Patient Presets**: Pre-populate vitals for Healthy baseline, Borderline/At-Risk, or Severe CKD cases with a single click.
- **🎯 Real-Time Risk Stratification**: Immediate classification into *Low Risk (Negative)* or *High Risk (Positive for CKD)* along with prediction confidence probability.
- **📊 Interactive Vital Gauges**: Plotly radial indicators for Serum Creatinine, Blood Pressure, and Hemoglobin with color-coded safety, borderline, and danger zones.
- **🚨 Automated Clinical Flags**: Instant triage warnings for Hypertension ($\ge$ 140 mm/Hg), Hyperglycemia ($\ge$ 200 mg/dL), Elevated Creatinine (> 1.2 mg/dL), and Anemia (< 12 g/dL).
- **📈 Embedded Model Performance Analytics**: Direct visual audit of accuracy and ROC benchmarks right inside the dashboard.
- **📑 Downloadable PDF Clinical Summary**: Instant PDF generation detailing patient vitals, clinical risk category, and diagnostic observations.

---

## 📊 Model Evaluation & Benchmarks

We evaluated 7 machine learning architectures using stratified cross-validation and standard test splits. **Random Forest (RF)** exhibited superior generalization with minimal false-positive rates.

![Model Performance Evaluation](PE_kidney.jpeg)

| Model | Accuracy (%) | ROC Score (%) | AUC-ROC Area | Performance Rank |
| :--- | :---: | :---: | :---: | :---: |
| **Random Forest (RF)** ⭐ | **98.8%** | **98.2%** | **0.96** | **#1 (Selected Model)** |
| **XGBoost** | 96.2% | 94.6% | 0.95 | #2 |
| **GBDT (Gradient Boosted Trees)** | 96.2% | 94.6% | 0.95 | #3 |
| **Decision Tree (DT)** | 93.8% | 93.3% | 0.96 | #4 |
| **Logistic Regression (LR)** | 92.5% | 91.8% | 0.92 | #5 |
| **Support Vector Machine (SVM)** | 76.2% | 72.7% | 0.73 | #6 |
| **K-Nearest Neighbors (KNN)** | 57.5% | 57.4% | 0.57 | #7 |

---

## 📈 ROC Analysis

Receiver Operating Characteristic (ROC) curves illustrate the diagnostic sensitivity (True Positive Rate) against (1 - Specificity) (False Positive Rate) across classification thresholds.

![ROC Curve Analysis](roc_kidney.jpeg)

- **Random Forest & Decision Tree** achieve a near-optimal curve with an **AUC of 0.96**, demonstrating robust sensitivity while maintaining very low false alarms.
- **XGBoost & GBDT** follow closely at **AUC = 0.95**.
- **Distance-based algorithms (KNN)** struggled due to mixed continuous and categorical distributions, highlighting the efficacy of tree-based ensembles for clinical tabular records.

---

## 🧬 Clinical Biomarkers & Features

The model evaluates 24 clinical parameters grouped across three diagnostic pillars:

### 1. Patient Demographics & Urinalysis
- **Age**: Age in years (1 - 120)
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
├── app.py                      # Production Streamlit clinical web app
├── kindey.pkl                  # Serialized trained Random Forest ML model
├── PE_kidney.jpeg              # Benchmark performance evaluation bar chart
├── roc_kidney.jpeg             # ROC-AUC curves comparison plot
├── code_project.ipynb          # End-to-end data preprocessing, EDA & ML training
├── requirements.txt            # Python package dependencies
└── README.md                   # Comprehensive project documentation
```

---

## 🚀 Quick Start & Installation

### Prerequisites
- Python 3.9+ installed
- Recommended: A virtual environment (`venv` or `conda`)

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

## 💻 Running the Application

Launch the Streamlit web dashboard:
```bash
streamlit run app.py
```

The application will start immediately at:
🌐 **`http://localhost:8501`**

### Exploring the Jupyter Notebook
To inspect the exploratory data analysis, data imputation, and model training:
```bash
jupyter notebook code_project.ipynb
```

---

## 📄 Clinical PDF Report Generation

The application automatically compiles an official PDF report for each assessed case using ReportLab.
- **Includes**: Clinical timestamps, Patient Demographics, Vitals, Renal Function Markers, Diagnostic Classification, Confidence %, and Risk Flags.
- **One-Click Export**: Click **Download Clinical Report (.PDF)** after running an assessment to save a local record.

---

## ⚠️ Clinical Disclaimer

> **IMPORTANT**: This application is a machine learning research prototype designed to assist healthcare professionals in screening and triage. It is **not a substitute for definitive medical diagnosis, laboratory biopsy, or professional nephrology consultation**. Always verify predictions with clinical laboratory tests.
