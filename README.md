# RISE HR Portal

A full-stack HR management portal built using the MERN stack that centralizes leave management, shared calendars, announcements, audit logging, and admin workflows into a single platform.

---

# Live Demo

https://rise-hr-portal.netlify.app/

---

# Features

## Authentication & Authorization
- JWT-based authentication
- Role-based access control (Admin / Member)
- Protected routes
- Admin-only APIs and pages

---

## Leave Management System
- Apply for leave
- Multiple leave types:
  - PTO
  - Half Day
  - Sick Leave
  - Planned Leave
  - Work From Home
- Leave approval/rejection workflow
- Overlapping leave prevention
- Leave deduction engine
- Saturday half-day deduction logic
- Sunday skip logic
- Holiday exclusion logic

---

## Shared Calendar
- FullCalendar integration
- Approved leave visualization
- Employee leave events
- Calendar event rendering

---

## Admin Dashboard
- View pending leave requests
- Approve leave requests
- Reject leave requests
- Admin-only controls
- Dashboard analytics cards

---

## Announcements Feed
- Create announcements
- View announcements feed
- Reply system
- Nested replies
- Reaction system:
  - ❤️ Love
  - 💡 Knowledge

---

## Audit Logging
- Immutable audit logs
- Tracks:
  - Leave applications
  - Leave approvals
  - Leave rejections
- Admin-only audit log access

---

## Automation
- Daily digest email automation
- Cron job scheduling using node-cron
- Email notifications using Nodemailer

---

# Tech Stack

## Frontend
- React.js
- Vite
- TailwindCSS
- Axios
- React Router DOM
- FullCalendar

## Backend
- Node.js
- Express.js
- MongoDB
- Mongoose
- JWT Authentication

## Deployment
- Frontend: Netlify
- Backend: Render
- Database: MongoDB Atlas

---

# System Architecture

```plaintext
React Frontend
      ↓
Express REST APIs
      ↓
MongoDB Atlas
```

---

# Folder Structure

## Frontend

```plaintext
client/
│
├── src/
│   ├── components/
│   ├── pages/
│   ├── services/
│   └── App.jsx
```

---

## Backend

```plaintext
server/
│
├── controllers/
├── middlewares/
├── models/
├── routes/
├── utils/
├── cron/
└── server.js
```

---

# Database Models

## User
- name
- email
- role
- team

## LeaveRequest
- leaveType
- startDate
- endDate
- deductedDays
- status

## Announcement
- title
- body
- authorId

## Reply
- announcementId
- body
- authorId

## Reaction
- targetId
- targetType
- reaction

## AuditLog
- actorId
- actionType
- target
- reason

---

# Core Business Logic

## Leave Deduction Rules

### Sundays
- Deduct 0 days

### Saturdays
- Full day leave → 0.5 deduction
- Half day leave → 0.25 deduction

### Holidays
- Deduct 0 days

### Multi-Day Leaves
- Per-day computation
- Holiday and Sunday skipping

---

# API Endpoints

## Auth

### Login
```http
POST /api/auth/login
```

---

## Leave APIs

### Apply Leave
```http
POST /api/leave
```

### Get My Leaves
```http
GET /api/leave/my-leaves
```

### Get Pending Leaves
```http
GET /api/leave/pending
```

### Approve Leave
```http
PUT /api/leave/approve/:id
```

### Reject Leave
```http
PUT /api/leave/reject/:id
```

---

## Calendar APIs

### Get Calendar Events
```http
GET /api/calendar
```

---

## Announcement APIs

### Create Announcement
```http
POST /api/announcement
```

### Get Announcements
```http
GET /api/announcement
```

### Create Reply
```http
POST /api/announcement/reply
```

### Get Replies
```http
GET /api/announcement/reply/:id
```

### React to Post/Reply
```http
POST /api/announcement/react
```

---

## Audit APIs

### Get Audit Logs
```http
GET /api/audit
```

---

# Local Setup Instructions

# 1. Clone Repository

```bash
git clone https://github.com/yourusername/rise-hr-portal.git
```

---

# 2. Frontend Setup

```bash
cd client
npm install
npm run dev
```

Frontend runs on:
```plaintext
http://localhost:5173
```

---

# 3. Backend Setup

```bash
cd server
npm install
npm run dev
```

Backend runs on:
```plaintext
http://localhost:5000
```

---

# Environment Variables

## Backend `.env`

```env
PORT=5000

MONGO_URI=your_mongodb_uri

JWT_SECRET=your_secret

EMAIL_USER=your_email

EMAIL_PASS=your_password

CLIENT_URL=http://localhost:5173
```

---

# Deployment

## Frontend
Deployed on Netlify.

## Backend
Deployed on Render.

## Database
Hosted on MongoDB Atlas.

---

# Learning Outcomes

This project helped in understanding:
- REST API architecture
- Role-based access control
- Full-stack application development
- MongoDB schema design
- Workflow automation
- Cron jobs
- Authentication systems
- Deployment pipelines
- Production-grade backend design

---

# Author

Tushar Bhakat

- IIT Guwahati
- MERN Stack Developer
- Backend & Full Stack Engineering Enthusiast
