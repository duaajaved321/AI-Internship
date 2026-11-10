# AI Internship Portfolio

A curated index of my AI internship projects, documenting practical work across healthcare data processing, clinical NLP, Generative AI, machine learning, APIs, and deployment.

This repository acts as a central portfolio: each project remains in its own repository, and the links below take you directly to its source code, notebooks, documentation, and implementation details.

## Project Areas

- [Python & Healthcare Data Processing](#1-python--healthcare-data-processing)
- [SQL & Healthcare Analytics](#2-sql--healthcare-analytics)
- [Healthcare Applications & APIs](#3-healthcare-applications--apis)
- [Clinical NLP & Generative AI](#4-clinical-nlp--generative-ai)
- [Machine Learning & Model Evaluation](#5-machine-learning--model-evaluation)
- [Backend, Deployment & Model Serving](#6-backend-deployment--model-serving)

---

## 1. Python & Healthcare Data Processing

### [Privacy-Conscious Patient Data Processor with Basic Python](https://github.com/duaajaved321/Privacy-Conscious-Patient-Data-Processor-with-Basic-Python)
Process synthetic patient records from CSV files. The script validates fields, separates valid and invalid records, masks selected personal information, and exports cleaned data.

**Technologies:** Python, CSV, regular expressions, file handling, exception handling, data validation.

## 2. SQL & Healthcare Analytics

### [SQL-Based Healthcare Analytics AI Pipeline](https://github.com/duaajaved321/SQL-Based-Healthcare-Analytics-AI-Pipeline)
Explore a relational hospital database using SQL and Python. The project joins healthcare tables, performs exploratory analysis, engineers features, and prepares data for further machine-learning work.

**Technologies:** SQL, SQLite, Python, Pandas, NumPy, Matplotlib, Seaborn, scikit-learn.

## 3. Healthcare Applications & APIs

### [Healthcare CSV Upload and Patient Summary Dashboard with Streamlit](https://github.com/duaajaved321/Healthcare-CSV-Upload-and-Patient-Summary-Dashboard-with-Streamlit)
A multi-page dashboard for uploading healthcare CSV files, selecting patient and measurement columns, filtering records, viewing patient histories, and exploring summary statistics and time-series charts.

**Technologies:** Python, Streamlit, Pandas, NumPy, data visualization.

### [Patient Vitals API](https://github.com/duaajaved321/Patient_Vitals_API)
A REST API for validating, storing, retrieving, and summarizing patient vital-sign records. It uses structured request validation and a SQLite database.

**Technologies:** Python, FastAPI, Pydantic, SQLite, Uvicorn, pytest, HTTPX.

## 4. Clinical NLP & Generative AI

### [Regex Keyword Matching Data Extractor](https://github.com/duaajaved321/Regex-Keyword-Matching-Data-Extractor)
Extract structured information from clinical notes, including note identifiers, age, symptoms, diagnoses, and medication mentions. Combines regular expressions and keyword/context matching with similarity-based techniques, then exports structured results.

**Technologies:** Python, regex, Pandas, NumPy, NLTK, Gensim/Word2Vec, scikit-learn, cosine similarity.

### [Medical Jargon Translator — Streamlit & LLM API](https://github.com/duaajaved321/Medical-Jargon-Translator-Streamlit-LLM-API-)
A Streamlit application that uses an LLM API to rewrite clinical notes in patient-friendly language while preserving important details such as medication names, doses, measurements, dates, and uncertainty.

**Technologies:** Python, Streamlit, Gemini API, OpenAI SDK compatibility, python-dotenv, prompt engineering, API error handling.

### [Smart Medical Note Assistant](https://github.com/duaajaved321/Smart-Medical-Note-Assistant)
Convert unstructured practitioner notes into structured SOAP-style documentation using Gemini. The application validates structured output, handles API retries, and supports JSON downloads.

**Technologies:** Python, Streamlit, Gemini API, OpenAI-compatible SDK, Pydantic, Tenacity, prompt engineering, JSON.

## 5. Machine Learning & Model Evaluation

### [Regression and Classification](https://github.com/duaajaved321/Regression-and-Classification)
Explore regression and classification using a chronic kidney disease dataset. Includes preprocessing pipelines, model evaluation, visualizations, and cross-validation.

**Technologies:** Python, Pandas, NumPy, scikit-learn, Matplotlib, ucimlrepo.

### [Hospital Readmission Prediction — Decision Tree and Random Forest](https://github.com/duaajaved321/Hospital-Readmission-Prediction-Decision-Tree-and-Random-Forest-)
Predict hospital readmission using Decision Tree and Random Forest models. Covers data cleaning, patient-level splitting, categorical encoding, model comparison, evaluation metrics, confusion matrices, and feature importance.

**Technologies:** Python, Pandas, NumPy, scikit-learn, Matplotlib, Seaborn, Joblib.

### [Diabetes Readmission Prediction — End-to-End ML Pipeline](https://github.com/duaajaved321/Diabetes-Readmission-Prediction-End-to-End-ML-Pipeline)
Build a machine-learning pipeline for predicting 30-day readmission using the Diabetes 130-US Hospitals dataset. Includes target engineering, patient-level splitting to reduce leakage, preprocessing, cross-validation, evaluation, and model serialization.

**Technologies:** Python, Pandas, NumPy, scikit-learn, Matplotlib, Joblib, ML pipelines, feature engineering.

### [Comparing Two Medical Risk Classifiers](https://github.com/duaajaved321/Comparing-Two-Medical-Risk-Classifiers)
Compare Logistic Regression and Decision Tree classifiers on a chronic kidney disease dataset. Includes feature analysis, leakage-aware preprocessing, cross-validation, and classification metrics.

**Technologies:** Python, Pandas, NumPy, scikit-learn, SciPy, Matplotlib, ucimlrepo.

### [Multiclass Classification Using One-vs-Rest and One-vs-One](https://github.com/duaajaved321/Multiclass-Classification-Using-One-vs-Rest-and-One-vs-One)
Compare One-vs-Rest and One-vs-One strategies for multiclass classification. Covers exploratory analysis, preprocessing of numeric and categorical features, and macro, micro, and weighted evaluation metrics.

**Technologies:** Python, Pandas, NumPy, scikit-learn, SciPy, Matplotlib, Seaborn.

### [MLP for Tabular Health Prediction](https://github.com/duaajaved321/MLP-for-Tabular-Health-Prediction)
Train a PyTorch multilayer perceptron on tabular diabetes-risk data and compare its performance with a Random Forest baseline. Includes preprocessing, training, learning curves, and evaluation.

**Technologies:** Python, PyTorch, Pandas, NumPy, scikit-learn, neural networks, model evaluation.

## 6. Backend, Deployment & Model Serving

### [Building a Local FastAPI Application](https://github.com/duaajaved321/Building-a-Local-FastAPI-Application)
A starter REST API demonstrating route creation, patient record handling, request validation, and interactive API documentation.

**Technologies:** Python, FastAPI, Uvicorn, Pydantic, REST APIs, Swagger UI.

### [Dockerizing a FastAPI Application](https://github.com/duaajaved321/Dockerizing-a-FastAPI-Application)
Containerize a FastAPI patient-vitals service with Docker and Docker Compose. Includes validation, SQLite persistence, automated tests, a health check, and a non-root container user.

**Technologies:** Python, FastAPI, Pydantic, SQLite, Docker, Docker Compose, pytest, HTTPX.

### [ML Model Served via FastAPI with Automatic Logging](https://github.com/duaajaved321/ML-Model-Served-via-FastAPI-with-Automatic-Logging)
Serve a trained machine-learning pipeline through a FastAPI prediction endpoint. The service validates inputs and records prediction activity in SQLite without storing raw patient answers.

**Technologies:** Python, FastAPI, scikit-learn, Pydantic, SQLite, Uvicorn, pytest, Joblib.

---

## Skills & Tools Covered

- **Programming and data:** Python, Pandas, NumPy, CSV processing, SQL, SQLite
- **Machine learning:** scikit-learn, PyTorch, classification, regression, feature engineering, cross-validation, model evaluation
- **Clinical NLP and GenAI:** regular expressions, NLTK, Word2Vec, Gemini API, prompt engineering, structured LLM outputs
- **Applications and APIs:** Streamlit, FastAPI, REST APIs, Pydantic, Uvicorn
- **Deployment and testing:** Docker, Docker Compose, pytest, HTTPX, model serialization, logging
- **Visualization:** Matplotlib, Seaborn, Streamlit charts

## Notes

- Each linked repository contains its own implementation and project-specific documentation.
- These are learning and engineering projects, not clinically validated medical devices or sources of medical advice.
- Patient examples and records used in these projects are synthetic or drawn from public datasets, as described in the individual repositories. Do not upload private or identifiable patient information.
