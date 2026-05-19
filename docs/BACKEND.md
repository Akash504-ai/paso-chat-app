# Backend Documentation

## Overview

The backend of PASO is built using Node.js, Express.js, MongoDB, and Socket.io.  
It handles authentication, real-time messaging, group management, AI integration, moderation workflows, admin operations, and status management.

---

# Backend Structure

```txt
backend/
├── src/
│   ├── controllers/
│   ├── lib/
│   ├── middleware/
│   ├── models/
│   ├── routes/
│   ├── seeds/
│   ├── services/
│   └── index.js
```

---

# Folder Structure

## controllers/

Contains request handling logic for API endpoints.

### Available Controllers

- `auth.controller.js`
- `message.controller.js`
- `group.controller.js`
- `ai.controller.js`
- `admin.controller.js`
- `report.controller.js`
- `status.controller.js`

---

## lib/

Contains reusable backend utilities and service integrations.

### Files

- `db.js` → MongoDB connection
- `socket.js` → Socket.io server configuration
- `cloudinary.js` → Cloudinary integration
- `redis.js` → Redis client setup
- `sendEmail.js` → Email service utilities
- `mlService.js` → ML moderation service communication
- `utils.js` → Common helper utilities

---

## middleware/

Contains custom Express middleware.

### Available Middleware

- `auth.middleware.js`
- `admin.middleware.js`
- `upload.middleware.js`
- `rateLimiter.js`

---

## models/

Contains Mongoose database schemas.

### Available Models

- `user.model.js`
- `message.model.js`
- `group.model.js`
- `report.model.js`
- `status.model.js`

---

## routes/

Contains Express route definitions.

### Available Routes

- `auth.route.js`
- `message.route.js`
- `group.routes.js`
- `ai.routes.js`
- `admin.routes.js`
- `report.routes.js`
- `status.routes.js`

---

## services/

Contains reusable business logic and external service logic.

### Available Services

- `ai.service.js`

---

## seeds/

Contains database seed scripts.

### Available Seeds

- `seedAIUser.js`

---

# Server Initialization Flow

The backend server starts from:

```txt
src/index.js
```

### Startup Process

1. Load environment variables using `dotenv`
2. Configure Express middleware
3. Enable CORS
4. Register API routes
5. Connect MongoDB database
6. Seed AI user
7. Initialize Socket.io server
8. Start HTTP server

---

# Registered API Routes

```txt
/api/auth
/api/messages
/api/groups
/api/ai
/api/status
/api/admin
/api/reports
```

---

# Core Technologies

- Node.js
- Express.js
- MongoDB
- Mongoose
- Socket.io
- Redis
- Cloudinary
- Groq API
- Brevo
- JWT Authentication

---

# Scripts

## Development

```bash
npm run dev
```

## Production

```bash
npm start
```

## Lint

```bash
npm run lint
```

---

# Environment Variables

Environment setup examples are available in:

```txt
backend/.env.example
```