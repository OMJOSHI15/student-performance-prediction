# Student Performance Prediction System

A full-stack **machine learning web application** that predicts students' final academic performance and flags at-risk students early enough for intervention. Built with Python, Flask, and scikit-learn, with a web frontend and deployed on Vercel.

🔗 **Live Demo:** https://student-app-five-livid.vercel.app/

---

## Overview

The system analyzes key academic indicators — attendance, internal marks, assignment scores, and study hours — and produces two outputs:

- **Final Grade** — predicted via a **Linear Regression** model
- **Risk Category** (Safe / At Risk) — classified via a **Decision Tree** model

The goal is to replace slow, subjective, manual grade evaluation with fast, data-driven predictions that let educators identify and support struggling students *before* exams.

---

## Features

- Real-time prediction of final grades from student input
- Automatic Safe / At-Risk classification for early intervention
- Clean web interface for entering data and viewing results
- Trained models persisted with Joblib (no retraining per request)
- End-to-end pipeline: preprocessing → training → evaluation → serving

---

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Language | Python 3.x |
| ML | scikit-learn (LinearRegression, DecisionTreeClassifier) |
| Data | pandas |
| Backend | Flask (REST `/predict` endpoint) |
| Frontend | HTML / CSS |
| Model persistence | Joblib |
| Deployment | Vercel |

---

## Model Performance

**Linear Regression — Grade Prediction**

| Metric | Score |
|--------|-------|
| R² Score | 0.87 |
| MAE | 3.24 |
| RMSE | 4.12 |

**Decision Tree — Risk Classification**

| Metric | Score |
|--------|-------|
| Accuracy | 92% |
| Precision | 91% |
| Recall | 93% |
| F1-Score | 92% |

---

## Input Features

| Feature | Type | Range |
|---------|------|-------|
| Attendance (%) | Numeric | 0 – 100 |
| Internal Marks | Numeric | 0 – 30 |
| Assignment Marks | Numeric | 0 – 10 |
| Study Hours / Day | Numeric | 0 – 12 |

---

## How It Works

1. **Data preprocessing** — clean and prepare the dataset with pandas.
2. **Model training** — train Linear Regression (grades) and Decision Tree (risk) on a train/test split.
3. **Persistence** — serialize trained models with Joblib (`lr_model.pkl`, `dt_model.pkl`).
4. **Serving** — Flask backend loads the models and exposes a `/predict` route.
5. **Frontend** — the user enters student data; the app returns the predicted grade and risk category in real time.

---

## Testing

Validated with 42 test cases across unit, integration, and model-accuracy testing, reaching ~93% overall coverage.

---

## Future Scope

- Deep-learning models (e.g. LSTM) for multi-semester performance tracking
- Automated alerts to faculty when a student's risk level changes
- Multi-subject support with subject-wise dashboards
- Mobile application for student and faculty access

---

## Team

Academic group project — Department of Computer Engineering, DEPSTAR, CHARUSAT University.

- Om Joshi (24DCE052)
- Drashti Dedaniya (24DCE029)
- Krish Gajera (24DCE040)

Guided by Mr. Kashyap Patel.
