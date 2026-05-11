# RISE HR Portal

A full-stack HR management portal built using the MERN stack.  
The application provides leave management workflows, shared calendar functionality, announcements feed, admin approvals, audit logging, and automated email notifications.

---

# Live Demo

[https://your-netlify-url.netlify.app](https://rise-hr-portal.netlify.app/)


---

# Features

## Authentication & Authorization
- JWT-based authentication
- Role-based access control (Admin / Member)
- Protected frontend and backend routes

---

## Leave Management
- Apply for leave
- Multiple leave types:
  - PTO
  - Half Day
  - Sick Leave
  - Planned Leave
  - Work From Home
- Leave overlap prevention
- Leave deduction engine
- Saturday half-day handling
- Sunday exclusion logic
- Admin approval/rejection workflow
- Rejection reason support

---

## Shared Calendar
- FullCalendar integration
- Approved leave visualization
- Leave event rendering
- Shared organizational visibility

---

## Admin Dashboard
- View pending leave requests
- Approve leave requests
- Reject leave requests
- Dashboard analytics cards
- Audit log access

---

## Announcements System
- Create announcements
- View organization-wide posts
- Reply to posts
- Nested discussions
- Reactions:
  - Love ❤️
  - Knowledge 💡

---

## Audit Logging
- Tracks:
  - Leave applications
  - Leave approvals
  - Leave rejections
- Immutable audit records
- Admin-only visibility

---

## Email Automation
- Cron-based automated digest emails
- Daily leave notifications
- Nodemailer integration

---

# Tech Stack

## Frontend
- React.js
- Vite
- TailwindCSS
- Axios
- React Router
- FullCalendar

## Backend
- Node.js
- Express.js
- MongoDB
- Mongoose
- JWT Authentication

## Deployment
- Frontend → Netlify
- Backend → Render
- Database → MongoDB Atlas

---

# Project Structure

## Frontend

```plaintext
client/
│
├── src/
│   ├── components/
│   ├── pages/
│   ├── services/
│   └── App.jsx
