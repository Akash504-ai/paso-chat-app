# Setup Guide

## Prerequisites

Make sure the following tools are installed:

- Node.js
- npm
- Python 3.10+
- MongoDB
- Redis

---

# Clone Repository

```bash
git clone https://github.com/CodePlaygroundHub/paso-chat-app.git
cd paso-chat-app
```

---

# Backend Setup

## Navigate to Backend

```bash
cd backend
```

---

## Install Dependencies

```bash
npm install
```

---

## Configure Environment Variables

Create:

```txt
backend/.env
```

Copy values from:

```txt
backend/.env.example
```

---

## Start Backend Server

```bash
npm run dev
```

Backend runs on:

```txt
http://localhost:5001
```

---

# Frontend Setup

## Navigate to Frontend

```bash
cd frontend
```

---

## Install Dependencies

```bash
npm install
```

---

## Configure Environment Variables

Create:

```txt
frontend/.env
```

Copy values from:

```txt
frontend/.env.example
```

---

## Start Frontend

```bash
npm run dev
```

Frontend runs on:

```txt
http://localhost:5173
```

---

# ML Service Setup

## Navigate to ML Service

```bash
cd ml-service
```

---

## Install Python Dependencies

```bash
pip install -r requirements.txt
```

---

## Start ML Service

```bash
uvicorn app:app --host 0.0.0.0 --port 8000 --reload
```

ML service runs on:

```txt
http://localhost:8000
```

---

# ML Service Features

The FastAPI ML service provides:

- toxic message detection
- spam detection
- smart reply suggestions

---

# ML API Endpoint

## Analyze Message

```txt
POST /analyze
```

### Request Body

```json
{
  "text": "Hello world"
}
```

### Response

```json
{
  "toxic_score": 0.01,
  "spam_score": 0.02,
  "smart_replies": ["Hi!", "Hello!"]
}
```

---

# Frontend Technologies

- React.js
- Zustand
- Tailwind CSS
- DaisyUI
- Socket.io Client
- Axios
- Framer Motion

---

# Backend Technologies

- Node.js
- Express.js
- MongoDB
- Socket.io
- Redis
- JWT Authentication

---

# Python Dependencies

```txt
fastapi
uvicorn
scikit-learn
joblib
pydantic
```

---

# Production Deployment

## Frontend

Deployed on:

```txt
Vercel
```

---

## Backend

Deployed on:

```txt
Render
```

---

## ML Service

Deployed on:

```txt
Render
```

---

# Available Scripts

## Frontend

```bash
npm run dev
npm run build
npm run preview
npm run lint
```

---

## Backend

```bash
npm run dev
npm start
npm run lint
```

---

# Environment Example Files

```txt
frontend/.env.example
backend/.env.example
```