🌊 AI-Based Flood Risk Prediction System

An **AI/ML-powered Flood Risk Prediction System** that analyzes environmental and geographical data to predict flood risk, explain the major contributing factors, visualize zone-wise risk, and provide interactive what-if simulations through a web dashboard.

---

## 📌 Project Overview

Floods can cause significant damage to life, property, agriculture, and infrastructure. Early identification of potentially risky conditions can help in better monitoring and preparedness.

This project uses **Machine Learning** to analyze factors such as:

* 🌧️ Rainfall
* 🌊 Water/River Level
* 💧 Humidity
* 🌡️ Temperature
* 💨 Wind Speed
* 🏔️ Elevation
* 📍 Location/Zone
* 📅 Date and Time
* 🌊 Previous Flood Status

The system predicts the **probability of flood risk** and converts it into an easy-to-understand risk category.

> **Note:** This project is an academic/prototype decision-support system and is not intended to replace official emergency warning systems.

---

# 🎯 Objectives

The main objectives of this project are:

1. Collect and analyze historical flood-related data.
2. Clean and preprocess environmental data.
3. Perform feature engineering and exploratory data analysis.
4. Train and compare multiple ML classification models.
5. Predict flood probability from environmental conditions.
6. Classify the prediction into different risk levels.
7. Explain the prediction using Explainable AI.
8. Provide zone-wise flood risk visualization.
9. Provide interactive what-if simulation.
10. Display alerts and predictions through a web dashboard.

---

# ✨ Key Features

## 1. 📊 Environmental Data Analysis

The system analyzes multiple environmental parameters:

```text
Rainfall
Water Level
Humidity
Temperature
Wind Speed
Elevation
Location
Date & Time
Previous Flood Status
```

---

## 2. 🧹 Data Preprocessing

Before training the ML model, raw data is cleaned by:

* Handling missing values
* Removing duplicate records
* Detecting incorrect values
* Selecting relevant features
* Converting data into ML-compatible format

Example:

```text
Humidity = 250%
```

Such an invalid value can be detected and corrected or removed during preprocessing.

---

## 3. ⚙️ Feature Engineering

Additional features can be created from existing environmental data.

Examples:

```text
Rainfall in last 24 hours
Rainfall in last 48 hours
Rainfall in last 7 days
Previous water level
Current water level
Water-level change
Rate of water-level increase
```

This helps the model understand environmental trends rather than only individual values.

---

## 4. 📈 Exploratory Data Analysis

EDA is performed to understand relationships and patterns in the dataset.

Example analyses:

* Rainfall vs Flood
* Water Level vs Flood
* Humidity vs Flood
* Feature correlation
* Rainfall trends
* Water-level trends

Visualization can be performed using charts and graphs.

---

# 🤖 Machine Learning

Multiple classification algorithms can be trained and compared.

### Models

* Logistic Regression
* Decision Tree
* Random Forest
* XGBoost

The final model is selected based on actual validation/test performance.

### Evaluation Metrics

The models can be evaluated using:

* Accuracy
* Precision
* Recall
* F1 Score
* Confusion Matrix
* ROC-AUC, where appropriate

> Model performance values should be reported from the actual dataset experiments rather than using sample/fabricated values.

---

# 🌊 Flood Risk Prediction

The user can enter current environmental conditions.

Example:

```text
Rainfall      = 120 mm
Water Level   = 5.4 m
Humidity      = 91%
Temperature   = 25°C
Wind Speed    = 16 km/h
```

The request follows this architecture:

```text
React Frontend
       ↓
    FastAPI
       ↓
   ML Model
       ↓
Prediction
```

Example output:

```text
Flood Probability = 87%
```

The percentage shown here is only an example; actual predictions depend on the trained model and input data.

---

# 🚦 Risk Classification

The predicted probability can be converted into project-defined risk categories.

Example:

| Probability | Risk Level  |
| ----------- | ----------- |
| 0–30%       | 🟢 Low      |
| 31–50%      | 🟡 Moderate |
| 51–75%      | 🟠 High     |
| 76–100%     | 🔴 Critical |

These thresholds are configurable and should be validated for the particular dataset and application.

---

# 🧠 Explainable AI

The system can use **SHAP (SHapley Additive exPlanations)** or feature-importance techniques to explain the prediction.

Instead of showing only:

```text
Flood Risk = 87%
```

the system can also show:

```text
Why is the risk high?

🌧️ Rainfall       → High contribution
🌊 Water Level    → High contribution
💧 Humidity       → Medium contribution
🌡️ Temperature   → Lower contribution
```

This helps users understand which input features contributed to the model's prediction.

---

# 🔮 What-If Simulation

The system provides an interactive simulation feature.

The user can change rainfall or other environmental parameters and observe how the model's predicted risk changes.

Example:

| Rainfall | Predicted Risk |
| -------: | -------------: |
|    80 mm |            45% |
|   100 mm |            62% |
|   120 mm |            78% |
|   140 mm |            89% |

These values are illustrative examples. Actual values are generated by the trained model.

### Example Question

> What happens to predicted flood risk if rainfall increases?

This makes the application interactive rather than only providing a single prediction.

---

# 🗺️ Zone-Wise Risk Mapping

If geographical data is available, the system can display flood risk for different zones.

Example:

```text
Zone A → 🟢 Low
Zone B → 🟡 Moderate
Zone C → 🔴 Critical
Zone D → 🟢 Low
Zone E → 🟠 High
Zone F → 🔴 Critical
```

The dashboard can highlight areas requiring priority monitoring based on predicted risk.

---

# 🚨 Alert System

When the predicted risk crosses a configured threshold, the system can generate an alert.

Example:

```text
🚨 FLOOD RISK ALERT

Zone C

Predicted Risk: Critical

Main contributing factors:
• Heavy rainfall
• Rising water level
```

For the academic prototype, alerts can be implemented through:

* Dashboard notifications
* Browser notifications
* Email notifications

The alert mechanism is intended for demonstration and monitoring purposes and does not replace official emergency alerts.

---

# 📊 Dashboard

The application provides a centralized dashboard containing:

* Current environmental conditions
* Flood probability
* Risk classification
* Rainfall trends
* Water-level trends
* Explainable AI results
* Zone-wise risk map
* What-if simulation
* Recent predictions
* Alerts

### Dashboard Concept

```text
┌─────────────────────────────────────────────┐
│ 🌊 AI FLOOD RISK PREDICTION SYSTEM          │
├─────────────────────────────────────────────┤
│                                             │
│ 🌧️ Rainfall       120 mm                   │
│ 🌊 Water Level    5.4 m                    │
│ 💧 Humidity       91%                      │
│ 🌡️ Temperature    25°C                    │
│                                             │
│        🔴 CRITICAL                         │
│        Probability: 87%                    │
│                                             │
│ 📈 Rainfall & Water-Level Trends            │
│                                             │
│ 🧠 WHY THIS PREDICTION?                     │
│ Rainfall       █████████                    │
│ Water Level    ████████                     │
│                                             │
│ 🗺️ ZONE-WISE RISK MAP                      │
│                                             │
│ 🚨 ALERTS                                   │
└─────────────────────────────────────────────┘
```

---

# 🔄 System Workflow

```text
                  DATA SOURCES
                       │
          ┌────────────┴────────────┐
          ↓                         ↓
   Historical Data             Current Data
          │                         │
          └────────────┬────────────┘
                       ↓
               DATA PREPROCESSING
                       ↓
              FEATURE ENGINEERING
                       ↓
                      EDA
                       ↓
               TRAIN ML MODELS
                       ↓
          ┌────────────────────────┐
          │ Random Forest /        │
          │ XGBoost / Other Models │
          └────────────┬───────────┘
                       ↓
                MODEL EVALUATION
                       ↓
                   BEST MODEL
                       ↓
              FLOOD PREDICTION
                       ↓
              RISK CLASSIFICATION
                       ↓
        ┌──────────────┼──────────────┐
        ↓              ↓              ↓
   Explainable     What-If       Zone-Wise
       AI          Simulation      Mapping
        │              │              │
        └──────────────┼──────────────┘
                       ↓
                  ALERT SYSTEM
                       ↓
                  WEB DASHBOARD
```

---

# 🏗️ Technology Architecture

```text
                 USER
                   │
                   ↓
          React + Tailwind CSS
                   │
                   ↓
                REST API
                   │
                   ↓
                FastAPI
                   │
                   ↓
             Python ML Model
                   │
        ┌──────────┴──────────┐
        ↓                     ↓
  Scikit-learn             XGBoost
        │
        ↓
   Prediction
        │
        ↓
       SHAP
        │
        ↓
 Explainability
        │
        ↓
    Dashboard
```

---

# 🛠️ Tech Stack

| Layer                | Technology           |
| -------------------- | -------------------- |
| Frontend             | React.js             |
| Styling              | Tailwind CSS         |
| Backend              | FastAPI              |
| Programming Language | Python               |
| Machine Learning     | Scikit-learn         |
| Boosting Model       | XGBoost              |
| Explainable AI       | SHAP                 |
| Database             | MongoDB / PostgreSQL |
| Maps                 | Leaflet              |
| Map Data             | OpenStreetMap        |
| API Communication    | REST API             |
| Version Control      | Git & GitHub         |

---

# 📁 Project Structure

```text
AI-Flood-Risk-Prediction/
│
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── services/
│   │   └── App.jsx
│   ├── package.json
│   └── README.md
│
├── backend/
│   ├── app/
│   │   ├── main.py
│   │   ├── routes/
│   │   ├── models/
│   │   ├── services/
│   │   └── schemas/
│   ├── requirements.txt
│   └── .env.example
│
├── ml/
│   ├── data/
│   ├── notebooks/
│   ├── preprocessing/
│   ├── training/
│   ├── evaluation/
│   └── models/
│
├── docs/
│   ├── architecture/
│   ├── screenshots/
│   └── project-report/
│
├── .gitignore
├── README.md
└── LICENSE
```

---

# 🚀 Installation & Setup

## 1. Clone the Repository

```bash
git clone https://github.com/your-username/AI-Flood-Risk-Prediction.git
```

```bash
cd AI-Flood-Risk-Prediction
```

---

## 2. Backend Setup

Create a Python virtual environment:

```bash
python -m venv venv
```

### Windows

```bash
venv\Scripts\activate
```

### Linux/macOS

```bash
source venv/bin/activate
```

Install dependencies:

```bash
pip install -r backend/requirements.txt
```

Start FastAPI:

```bash
uvicorn backend.app.main:app --reload
```

Backend will run on:

```text
http://127.0.0.1:8000
```

---

# 💻 Frontend Setup

Move into the frontend directory:

```bash
cd frontend
```

Install packages:

```bash
npm install
```

Start the development server:

```bash
npm run dev
```

The frontend will be available at the URL shown by Vite.

---

# 🔌 Example API

### Predict Flood Risk

```http
POST /predict
```

Example request:

```json
{
  "rainfall": 120,
  "water_level": 5.4,
  "humidity": 91,
  "temperature": 25,
  "wind_speed": 16,
  "elevation": 120
}
```

Example response:

```json
{
  "flood_probability": 0.87,
  "risk_level": "CRITICAL"
}
```

The exact API fields and response depend on the implemented backend.

---

# 📚 Dataset

The project can initially use historical/public flood and environmental datasets.

Possible data sources include:

* Historical rainfall data
* River/water-level observations
* Weather observations
* Geographic/elevation data
* Historical flood records

Later versions can integrate live weather or water-level APIs.

---

# 📊 Model Training Pipeline

```text
Raw Dataset
     ↓
Data Cleaning
     ↓
Missing Value Handling
     ↓
Feature Selection
     ↓
Feature Engineering
     ↓
Train/Test Split
     ↓
Model Training
     ↓
Model Evaluation
     ↓
Model Selection
     ↓
Model Saving
     ↓
FastAPI Integration
```

A trained model can be saved and loaded by the backend for prediction.

---

# 🔐 Environment Variables

Create a `.env` file for configuration.

Example:

```env
DATABASE_URL=your_database_url
MODEL_PATH=path_to_model
API_KEY=your_api_key
```

Do not upload sensitive API keys or credentials to GitHub.

Use:

```text
.env
```

in `.gitignore`.

Provide:

```text
.env.example
```

for other developers.

---

# 🧪 Testing

Testing can be perfo


