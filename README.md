# 💧 AquaSense AI
### Smart Water Intelligence Platform

An AI-powered water intelligence platform for **water demand forecasting, unusual consumption detection, and data-driven water consumption analysis**.

![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![Machine Learning](https://img.shields.io/badge/Machine%20Learning-Scikit--learn-orange)
![Backend](https://img.shields.io/badge/Backend-FastAPI-green)
![Frontend](https://img.shields.io/badge/Frontend-HTML%20%7C%20CSS%20%7C%20JavaScript-blue)
![Status](https://img.shields.io/badge/Status-Developed-success)

---

## Overview

AquaSense AI is a machine learning-based water intelligence platform designed to analyze historical water consumption patterns, forecast demand, and identify unusual consumption behavior.

The platform combines machine learning models with an interactive web dashboard to make water consumption data easier to understand and monitor.

## Key Features

- **Water Demand Forecasting:** Predicts water consumption using a Random Forest Regressor.
- **Anomaly Detection:** Identifies unusual consumption patterns using Isolation Forest.
- **Interactive Dashboard:** Displays consumption trends, model predictions and anomaly statistics.
- **Data Analytics:** Visualizes monthly consumption, prediction errors and anomaly distribution.
- **Report Generation:** Downloads prediction, anomaly and model performance reports in CSV format.
- **API Integration:** Connects the frontend dashboard to machine learning results through FastAPI.

## Technologies Used

| Category | Technologies |
|---|---|
| Programming | Python |
| Machine Learning | Scikit-learn |
| Data Processing | Pandas, NumPy |
| Forecasting | Random Forest Regressor |
| Anomaly Detection | Isolation Forest |
| Backend | FastAPI |
| Frontend | HTML, CSS, JavaScript |
| Visualization | Plotly |
| Model Storage | Joblib |
| Development | Jupyter Notebook, VS Code / JupyterLab |

## Machine Learning Models

### 1. Demand Forecasting – Random Forest Regressor

The forecasting model learns water consumption patterns using historical consumption and engineered time-based features.

**Evaluation Results**

| Metric | Result |
|---|---:|
| Mean Absolute Error (MAE) | 182.19 |
| Root Mean Squared Error (RMSE) | 250.99 |
| R² Score | 0.949 |
| Training Records | 36,691 |
| Testing Records | 9,173 |

The R² score indicates that approximately 94.9% of the variation in the test-set consumption values is explained by the model.

### 2. Anomaly Detection – Isolation Forest V3

Isolation Forest identifies unusual water consumption observations that differ from normal patterns.

**Detection Results**

| Metric | Result |
|---|---:|
| Testing Records | 9,173 |
| Detected Anomalies | 263 |
| Normal Records | 8,910 |
| Anomaly Percentage | 2.867% |

**Note:** An anomaly indicates unusual consumption behavior. It does not independently confirm a physical water leak. The dataset does not contain ground-truth leak labels.

## Dataset

The project uses historical hourly water consumption data obtained from Zenodo.

- Source: [Zenodo – Water Consumption Dataset](https://zenodo.org/records/11045013)
- Location: Germany
- Period: January 2016 – April 2021
- Original Records: 46,032
- Features include date, time, consumption, temperature, rainfall and sunshine.

Data preprocessing and feature engineering were performed before model training.

## Project Structure

```text
AquaSense-AI/
│
├── Backend/
│   ├── main.py
│   └── requirements.txt
│
├── Frontend/
│   ├── index.html
│   ├── style.css
│   └── script.js
│
├── app/
│   └── app.py
│
├── dataset/
│   ├── AquaSense_Cleaned_Data.csv
│   ├── AquaSense_Feature_Engineered.csv
│   └── waterconsumption_noNaN_fixedTimechange (1).csv
│
├── models/
│   ├── AquaSense_Demand_Forecasting_Model.pkl
│   ├── AquaSense_Anomaly_Detection_Model_V3.pkl
│   ├── AquaSense_Anomaly_Features_V1.pkl
│   ├── AquaSense_Isolation_Forest_V1.pkl
│   └── AquaSense_Model_Features.pkl
│
├── notebooks/
│   ├── 01_AquaSense_Data_Analysis.ipynb
│   ├── 02_AquaSense_Data_Preprocessing..ipynb
│   ├── 03_AquaSense_Exploratory_Data_Analysis.ipynb
│   ├── 04_AquaSense_Demand_Forecasting.ipynb
│   ├── 05_AquaSense_Anomaly_Detection.ipynb
│   └── 06_AquaSense_Model_Integration.ipynb
│
├── reports/
│   ├── AquaSense_Anomaly_Detection_Results.csv
│   └── AquaSense_Integrated_Model_Results.csv
│
├── .gitignore
├── .gitattributes
└── README.md
```

## Installation and Setup

### 1. Clone the repository

```bash
git clone https://github.com/Git-Dipali/AquaSense-AI.git
cd AquaSense-AI
```

### 2. Set up Git LFS

The trained machine learning models are stored using Git Large File Storage.

```bash
git lfs install
git lfs pull
```

### 3. Create and activate the environment

```bash
conda create -n aquasense python=3.10
conda activate aquasense
```

### 4. Install backend dependencies

```bash
cd Backend
pip install -r requirements.txt
```

### 5. Start the FastAPI backend

```bash
python -m uvicorn main:app --reload
```

Backend URL:

`http://127.0.0.1:8000`

API documentation:

`http://127.0.0.1:8000/docs`

### 6. Launch the frontend

Open `Frontend/index.html` in your browser.

Keep the FastAPI backend running while using the dashboard.

## API Endpoints

| Endpoint | Description |
|---|---|
| `/` | API welcome endpoint |
| `/api/health` | Backend and model health |
| `/api/dashboard-summary` | Dashboard summary statistics |
| `/api/consumption-trends` | Monthly consumption trends |
| `/api/anomaly-records` | Anomaly detection records |
| `/api/prediction-records` | Forecasting evaluation records |

## Future Scope

- Integration with IoT-based smart water meters.
- Real-time water consumption monitoring.
- Automated alerts for unusual consumption patterns.
- Integration with smart city water management systems.
- Extended forecasting capabilities using updated observations.

## Project Objective

To develop an intelligent water monitoring platform that uses machine learning and data analytics to support better understanding of water consumption patterns and more informed water resource management.

---

## Author

**sonali yadav**

**Project:** AquaSense AI – Smart Water Intelligence Platform

---

*Developed as a machine learning project focused on intelligent water consumption analysis.*
