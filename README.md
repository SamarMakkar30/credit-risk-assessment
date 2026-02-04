#Credit Risk Assessment — ML Inference System

A modular machine learning system designed to assess credit risk probability based on financial and demographic inputs.
This project focuses on production-style ML inference architecture, including API-based model serving, version control, and prediction observability.

🎯 Project Objective

To design and implement a deployable ML inference system rather than just training a model. The system demonstrates:

Separation of frontend, backend, and ML layers

Versioned model deployment

Structured prediction logging

Config-driven system design

🏗 System Architecture
User
  ↓
Frontend (React UI)
  ↓
FastAPI Backend (REST API)
  ↓
ML Model Inference
  ↓
Prediction Logging

Layer Responsibilities
Layer	Role
Frontend	Collects user inputs and displays risk results
Backend API	Handles requests, validation, logging, and model interaction
ML Layer	Loads active model and performs inference
Config Layer	Controls active model version
Logging Layer	Stores prediction data for monitoring and retraining
🤖 Machine Learning

Model Type: Gradient Boosting / XGBoost-based classifier

Feature Inputs: Financial history, credit profile, income indicators

Preprocessing pipeline ensures consistent transformation between training and inference

Model selection based on evaluation metrics (ROC-AUC, accuracy)

🔄 Model Versioning

Models are managed using configuration-based control:

models/
 ├── model_v1.pkl
 └── model_v2.pkl


model_config.yaml defines the active model, enabling safe updates and rollback without code changes.

📜 Prediction Logging

Each prediction request logs:

Input features

Predicted risk probability

Model version

Timestamp

Inference latency

This supports:

Performance monitoring

Auditing

Future retraining

📁 Project Structure
credit-risk-assessment/
├── backend/
│   ├── main.py
│   ├── routes/
│   ├── schemas/
│   └── services/
├── frontend/
├── models/
├── config/
│   └── model_config.yaml
├── logs/
├── requirements.txt
└── README.md

🚀 Running the Project
Install dependencies
pip install -r requirements.txt

Start backend
uvicorn backend.main:app --reload

Start frontend
cd frontend
npm install
npm start


Backend runs at:
http://localhost:8000

📊 Key Engineering Features

API-based ML model serving

Frontend–backend separation

Config-driven model version control

Structured logging for observability

Modular code organization

⚠️ Disclaimer

This system is developed for educational and research purposes.
It should not be used as a real financial decision-making system.

🛠 Tech Stack

Python, FastAPI, React, Scikit-learn, XGBoost, Joblib, REST APIs, Docker

📄 License

MIT License
