# System Architecture

## Overview

PASO follows a decoupled full-stack architecture designed for realtime communication, AI integration, and scalable messaging workflows.

The system consists of:

- Frontend Client
- Backend API Server
- Socket.io Realtime Server
- Machine Learning Service
- MongoDB Database
- Redis Adapter
- External Cloud Services

---

# High-Level Architecture

```txt
Frontend (React.js)
        ↓
Backend API (Express.js)
        ↓
MongoDB Database

Frontend ↔ Socket.io Server
                ↓
             Redis

Backend → ML Service (FastAPI)
Backend → Cloudinary
Backend → Brevo
Backend → Groq API
Backend → ZegoCloud
```

---

# Frontend Architecture

Frontend is built using:

- React.js
- Zustand
- Tailwind CSS
- DaisyUI
- Axios
- Socket.io Client

---

## Frontend Structure

```txt
frontend/src/
├── components/
├── constants/
├── lib/
├── pages/
├── store/
├── App.jsx
├── main.jsx
```

---

## Components

Contains reusable UI components.

### Examples

- ChatContainer
- MessageBubble
- Sidebar
- Navbar
- StatusViewer
- CreateGroupModal
- MessageInput

---

## Pages

Contains route-level pages.

### Examples

- LoginPage
- SignUpPage
- HomePage
- ProfilePage
- AdminDashboard
- SettingsPage

---

## Store

Global state management using Zustand.

### Stores

- useAuthStore
- useChatStore
- useCallStore
- useStatusStore
- useAdminStore
- useThemeStore

---

## Frontend Libraries

### axios.js

Centralized Axios configuration.

### utils.js

Frontend utility functions.

---

# Backend Architecture

Backend is built using:

- Node.js
- Express.js
- MongoDB
- Mongoose
- Socket.io

---

## Backend Structure

```txt
backend/src/
├── controllers/
├── middleware/
├── models/
├── routes/
├── services/
├── lib/
├── seeds/
```

---

# Realtime Communication Architecture

PASO uses Socket.io for:

- realtime messaging
- online presence
- typing indicators
- read receipts
- call signaling
- group calls

Redis adapter enables scalable multi-instance socket communication.

---

# Machine Learning Service

ML service is built using:

- FastAPI
- Python
- Scikit-learn

---

## ML Service Structure

```txt
ml-service/
├── app.py
├── toxic_model.pkl
├── spam_model.pkl
├── tfidf_vectorizer.pkl
├── requirements.txt
```

---

# ML Features

- toxic message detection
- spam detection
- message moderation analysis

The backend communicates with the ML service through HTTP API requests.

---

# Database Layer

Database:

```txt
MongoDB
```

Primary collections:

- users
- messages
- groups
- reports
- statuses

---

# Redis Layer

Redis is used for:

- Socket.io scaling
- pub/sub communication
- distributed realtime events

---

# External Services

## Cloudinary

Used for:
- image uploads
- media storage

---

## Brevo

Used for:
- email notifications
- password recovery workflows

---

## Groq API

Used for:
- AI chatbot integration

---

## ZegoCloud

Used for:
- voice calls
- video calls

---

# Deployment Architecture

## Frontend

```txt
Vercel
```

---

## Backend

```txt
Render
```

---

## ML Service

```txt
Render
```

---

# Core System Features

- realtime messaging
- group chat
- AI chatbot
- ML moderation
- admin analytics
- voice/video calling
- status system
- reporting system
- message reactions
- search system