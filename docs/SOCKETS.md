# Socket.io Documentation

## Overview

PASO uses Socket.io for real-time communication including:

- realtime messaging
- online/offline presence
- typing indicators
- message seen status
- one-to-one calling
- group calling
- realtime group communication

Socket server configuration is located in:

```txt
backend/src/lib/socket.js
```

---

# Socket Server Setup

The Socket.io server is initialized using:

```js
const io = new Server(server, {
  cors: {
    origin: [
      "https://chat-app-sooty-mu.vercel.app",
      "http://localhost:5173",
    ],
    credentials: true,
  },
});
```

Redis adapter is used for scalable realtime communication across instances.

---

# Redis Adapter

Socket.io Redis adapter configuration:

```js
io.adapter(createAdapter(pubClient, subClient));
```

This enables:
- horizontal scalability
- multi-server socket synchronization
- distributed realtime events

---

# User Socket Mapping

PASO maintains active user socket connections using:

```js
const userSocketMap = {};
```

Each user can have:
- multiple active sockets
- multiple browser tabs/devices

---

# Online User System

When users connect:
- their socket is registered
- they join their personal room
- online status is updated

Online users are broadcast using:

```js
io.emit("getOnlineUsers", Object.keys(userSocketMap));
```

---

# Rooms System

## Personal Rooms

Each user joins:

```txt
socket.join(userId)
```

Used for:
- direct messaging
- private realtime events
- personal notifications

---

## Group Rooms

Users automatically join their groups:

```js
socket.join(group._id.toString());
```

Used for:
- group messaging
- group calls
- realtime group events

---

# Typing Indicators

## Events

### Client Emit

```txt
typing
stopTyping
```

### Server Emit

```txt
typing
stopTyping
```

Used for realtime typing status.

---

# Message Seen System

## Events

### Client Emit

```txt
messageSeen
groupMessageSeen
```

### Server Emit

```txt
messageStatusUpdateBulk
groupMessageSeen
```

Used for:
- seen status synchronization
- realtime read receipts

---

# One-to-One Calling System

## Active Call Tracking

```js
const activeCalls = new Set();
```

Used to:
- prevent duplicate calls
- handle busy users

---

## Calling Events

### Client Emit

```txt
call:invite
call:accept
call:reject
call:end
```

### Server Emit

```txt
call:incoming
call:accepted
call:rejected
call:ended
call:busy
```

---

# Group Calling System

## Active Group Calls

```js
const activeGroupCalls = new Map();
```

Tracks active group call rooms.

---

## Group Call Events

### Client Emit

```txt
group:call:start
group:call:end
```

### Server Emit

```txt
group:call:incoming
group:call:ended
group:call:already-active
```

---

# Presence Management

On connection:
- user marked online

On disconnect:
- socket removed
- last seen updated
- online status removed if no active sockets remain

---

# Socket Connection Flow

```txt
Client Connect
    ↓
Authenticate User
    ↓
Register Socket
    ↓
Join Personal Room
    ↓
Join Group Rooms
    ↓
Broadcast Online Users
    ↓
Handle Realtime Events
```

---

# Core Features Powered by Socket.io

- realtime messaging
- group messaging
- typing indicators
- online presence
- read receipts
- voice/video call signaling
- group call synchronization
- realtime moderation updates