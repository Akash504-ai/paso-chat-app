# Frontend Documentation

## Overview

The PASO frontend is built using React.js and Vite with a modern realtime chat interface inspired by WhatsApp.

The frontend handles:

- authentication UI
- realtime messaging
- group chat
- AI chat
- voice/video calls
- admin dashboard
- status system
- realtime notifications

---

# Frontend Stack

- React.js
- Vite
- Zustand
- Tailwind CSS
- DaisyUI
- Socket.io Client
- Axios
- Framer Motion

---

# Frontend Structure

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

# Components

Reusable UI components are stored inside:

```txt
src/components/
```

---

## Major Components

### Chat Components

- ChatContainer
- ChatHeader
- MessageBubble
- MessageInput
- Sidebar

---

## Group Components

- CreateGroupModal
- GroupMembersModal
- AddMemberModal
- ChangeGroupInfoModal

---

## Status Components

- StatusViewer
- StatusSidebar
- StatusProgress
- AddStatusModal

---

## Calling Components

Located in:

```txt
components/call/
```

Used for:
- voice calls
- video calls
- call UI

---

## Admin Components

Located in:

```txt
components/admin/
```

Used for:
- admin dashboard
- moderation management
- analytics UI

---

# Pages

Application pages are located in:

```txt
src/pages/
```

---

## Available Pages

- LoginPage
- SignUpPage
- HomePage
- ProfilePage
- SettingsPage
- ForgotPassword
- GroupInfoPage
- AdminDashboard
- AdminUsers
- AdminReports

---

# Global State Management

PASO uses Zustand for state management.

Stores are located in:

```txt
src/store/
```

---

## Available Stores

| Store | Purpose |
|---|---|
| useAuthStore | Authentication state |
| useChatStore | Messaging state |
| useCallStore | Calling state |
| useStatusStore | Status system |
| useAdminStore | Admin panel |
| useThemeStore | Theme management |

---

# API Communication

Axios configuration is located in:

```txt
src/lib/axios.js
```

Used for:
- API requests
- authentication requests
- protected route communication

---

# Realtime Communication

Socket.io client is used for:

- realtime messaging
- online presence
- typing indicators
- call signaling
- read receipts

---

# UI System

PASO uses:

- Tailwind CSS
- DaisyUI

Features include:
- responsive design
- dynamic themes
- chat wallpapers
- modern messaging UI

---

# Routing

Frontend routing uses:

```txt
react-router-dom
```

Handles:
- protected routes
- admin routes
- authentication routing

---

# Calling System

Voice and video calls are powered using:

```txt
ZegoCloud
```

Supports:
- one-to-one calls
- group calls

---

# Frontend Features

- realtime chat
- group messaging
- AI assistant
- status stories
- reactions
- pinned messages
- reply system
- media sharing
- call system
- moderation system
- admin dashboard

---

# Frontend Environment Variables

Environment configuration:

```txt
frontend/.env
```

Example configuration:

```txt
frontend/.env.example
```

---

# Available Scripts

## Start Development Server

```bash
npm run dev
```

---

## Production Build

```bash
npm run build
```

---

## Preview Build

```bash
npm run preview
```

---

## Lint

```bash
npm run lint
```

---

# Production Deployment

Frontend deployment platform:

```txt
Vercel
```