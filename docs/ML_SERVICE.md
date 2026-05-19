# ML Service Documentation

## Overview

PASO uses a separate FastAPI-based Machine Learning service for intelligent moderation and smart reply generation.

The ML service handles:

- toxic message detection
- spam detection
- smart reply suggestions

---

# Technology Stack

- FastAPI
- Python
- Scikit-learn
- Joblib
- Pydantic

---

# Service Entry Point

```txt
ml-service/app.py
```

---

# ML Models

## Toxic Detection Model

Files:

```txt
toxic_model.pkl
tfidf_vectorizer.pkl
```

Used for:
- toxic content analysis
- moderation scoring

---

## Spam Detection Model

Files:

```txt
spam_model.pkl
spam_vectorizer.pkl
```

Used for:
- spam detection
- suspicious message filtering

---

## Intent Detection Model

Files:

```txt
intent_model.pkl
intent_vectorizer.pkl
```

Used for:
- smart reply generation
- conversation intent prediction

---

# Smart Reply System

Supported intents:

- greeting
- question
- confirmation
- goodbye
- appreciation

Example smart replies:

```txt
Hi!
Hello!
Okay
Sure
Take care!
```

---

# API Endpoints

## Health Check

### Endpoint

```txt
GET /health
```

### Response

```json
{
  "status": "ML service running"
}
```

---

# Analyze Message Endpoint

## Endpoint

```txt
POST /analyze
```

---

## Request Body

```json
{
  "text": "Hello world"
}
```

---

## Response

```json
{
  "toxic_score": 0.01,
  "spam_score": 0.02,
  "smart_replies": [
    "Hi!",
    "Hello!"
  ]
}
```

---

# Moderation Flow

```txt
User Message
      ↓
Backend API
      ↓
ML Service
      ↓
Toxicity Analysis
Spam Analysis
Intent Prediction
      ↓
Moderation Result Returned
```

---

# Features Powered by ML Service

- realtime moderation
- spam prevention
- intelligent replies
- safer messaging environment

---

# CORS Configuration

The ML service currently allows all origins:

```python
allow_origins=["*"]
```

For production deployment, frontend origins should be restricted.

---

# Local Development

## Install Dependencies

```bash
pip install -r requirements.txt
```

---

## Run Service

```bash
uvicorn app:app --host 0.0.0.0 --port 8000 --reload
```

---

# Deployment

The ML service is deployed separately from the backend.

Deployment platform:

```txt
Render
```

---

# Future Improvements

- advanced NLP moderation
- multilingual moderation
- image moderation
- sentiment analysis
- AI-powered conversation safety
- contextual moderation