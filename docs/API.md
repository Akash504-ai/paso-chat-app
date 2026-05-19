# API Documentation

## Base URL

```txt
http://localhost:5001/api
```

---

# Authentication Routes

Base Route:

```txt
/api/auth
```

## Endpoints

| Method | Endpoint | Description |
|---|---|---|
| POST | `/signup` | Register new user |
| POST | `/login` | Login user |
| POST | `/logout` | Logout user |
| GET | `/check` | Check authenticated user |
| PUT | `/update-profile` | Update user profile |
| PUT | `/security-questions` | Setup security questions |
| POST | `/verify-security` | Verify security answers |
| POST | `/reset-password` | Reset password |
| POST | `/get-security-questions` | Get security questions |

---

# Message Routes

Base Route:

```txt
/api/messages
```

## Endpoints

| Method | Endpoint | Description |
|---|---|---|
| GET | `/users` | Get sidebar users |
| GET | `/search/:userId` | Search direct messages |
| GET | `/group/search/:groupId` | Search group messages |
| GET | `/:id` | Get direct messages |
| POST | `/send/:id` | Send direct message |
| GET | `/group/:groupId` | Get group messages |
| POST | `/group/send/:groupId` | Send group message |
| DELETE | `/:messageId/me` | Delete message for current user |
| DELETE | `/:messageId/everyone` | Delete message for everyone |
| PUT | `/mark-seen/:userId` | Mark messages as seen |
| PUT | `/chat-wallpaper` | Update chat wallpaper |
| DELETE | `/chat-wallpaper` | Remove chat wallpaper |
| POST | `/react/:messageId` | React to message |

---

# Group Routes

Base Route:

```txt
/api/groups
```

## Endpoints

| Method | Endpoint | Description |
|---|---|---|
| POST | `/create` | Create group |
| GET | `/my` | Get user groups |
| GET | `/:id` | Get group details |
| POST | `/:id/add-user` | Add user to group |
| POST | `/:id/remove-user` | Remove user from group |
| POST | `/:id/leave` | Leave group |
| PATCH | `/:id/update` | Update group |
| DELETE | `/:id` | Delete group |

---

# AI Routes

Base Route:

```txt
/api/ai
```

## Endpoints

| Method | Endpoint | Description |
|---|---|---|
| POST | `/chat` | Chat with AI assistant |

---

# Status Routes

Base Route:

```txt
/api/status
```

## Endpoints

| Method | Endpoint | Description |
|---|---|---|
| POST | `/` | Create status |
| GET | `/` | Get statuses |
| POST | `/:statusId/view` | View status |
| DELETE | `/:statusId` | Delete status |

---

# Report Routes

Base Route:

```txt
/api/reports
```

## User Endpoints

| Method | Endpoint | Description |
|---|---|---|
| POST | `/` | Create report |

---

## Admin Endpoints

| Method | Endpoint | Description |
|---|---|---|
| GET | `/` | Get all reports |
| PATCH | `/:id/status` | Update report status |
| PATCH | `/:id/delete-message` | Delete reported message |
| PATCH | `/:id/ban-user` | Ban reported user |
| DELETE | `/:id` | Delete report |

---

# Admin Routes

Base Route:

```txt
/api/admin
```

## Endpoints

| Method | Endpoint | Description |
|---|---|---|
| GET | `/users` | Get all users |
| PATCH | `/users/:id/ban` | Ban/unban user |
| DELETE | `/users/:id` | Delete user |
| GET | `/dashboard` | Get admin dashboard statistics |

---

# Authentication Middleware

Protected routes use:

```txt
protectRoute
```

Admin-only routes use:

```txt
isAdmin
```

---

# Features Covered by API

- authentication system
- profile management
- realtime messaging
- group chat
- AI chatbot
- status system
- moderation & reporting
- admin analytics
- message reactions
- search system
- chat wallpaper management