# AI Architecture

## Overview

The AI Job Market Intelligence Platform incorporates Artificial Intelligence and Machine Learning to transform raw job postings into actionable career insights.

Rather than using AI for a single prediction task, the platform integrates multiple AI modules, each solving a different real-world problem.

The AI layer operates independently from the core application, allowing models to be developed, updated, and deployed without affecting the backend services.

---

# AI Objectives

The AI layer aims to:

- Extract structured information from unstructured job descriptions.
- Predict salary ranges.
- Recommend relevant technical skills.
- Identify skill gaps.
- Forecast future job market demand.
- Generate personalized career recommendations.

---

# AI Pipeline

Raw Job Data

↓

Data Cleaning

↓

Text Preprocessing

↓

Feature Engineering

↓

Machine Learning / NLP Models

↓

Predictions

↓

REST API

↓

Frontend Dashboard

---

# AI Modules

## 1. Skill Extraction

### Objective

Extract technical skills from job descriptions.

Example

Input

"We are looking for a Python developer with FastAPI, Docker and PostgreSQL experience."

Output

- Python
- FastAPI
- Docker
- PostgreSQL

Technology

- spaCy
- Sentence Transformers

---

## 2. Salary Prediction

### Objective

Predict expected salary using:

- Skills
- Experience
- Location
- Job Title

Input

Software Engineer

Python

Delhi

2 Years Experience

↓

Output

₹12 LPA

Possible Models

- Random Forest
- XGBoost
- Gradient Boosting

---

## 3. Skill Gap Analysis

### Objective

Compare a user's current skills with market demand.

Input

Current Skills

↓

Required Market Skills

↓

Missing Skills

↓

Recommended Learning Path

---

## 4. Career Recommendation

### Objective

Recommend possible career paths.

Example

Current Skills

- Python
- SQL

↓

Recommended

- Backend Developer
- Data Analyst
- AI Engineer

---

## 5. Job Demand Forecasting

### Objective

Predict future demand for skills and job roles.

Example

Current Trend

↓

Historical Data

↓

Forecast

↓

Future Skill Demand

Possible Models

- Prophet
- ARIMA
- LSTM

---

# Data Flow

Job Description

↓

Cleaning

↓

Skill Extraction

↓

Database

↓

Analytics

↓

Machine Learning

↓

Predictions

↓

Dashboard

---

# Machine Learning Workflow

Training Data

↓

Preprocessing

↓

Feature Engineering

↓

Model Training

↓

Evaluation

↓

Model Storage

↓

Prediction API

---

# Model Evaluation

Evaluation metrics depend on the task.

Regression

- MAE
- RMSE
- R² Score

Classification

- Accuracy
- Precision
- Recall
- F1 Score

Forecasting

- RMSE
- MAE
- MAPE

---

# Model Storage

Trained models will be stored separately from the backend application.

Example

ml/models/

- salary_model.pkl
- skill_model.pkl
- forecasting_model.pkl

---

# Future AI Features

Future releases may include:

- Resume Parser
- AI Resume Scoring
- Interview Question Generator
- AI Career Coach
- Learning Path Generator
- Company Recommendation Engine
- AI Chat Assistant

---

# AI Design Principles

The AI layer should be:

- Modular
- Explainable
- Scalable
- Replaceable
- Independent of the backend