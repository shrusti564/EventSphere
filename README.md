# Event-Booking-System

# 🎟️ Event Booking System

A full-stack web application that enables seamless event management, ticket booking, and real-time updates for both **Admins** and **Students**.

🚀 **Live Demo:** https://event-booking-system-otjq.onrender.com  

---

## 📌 Overview

The **Event Booking System** is designed to simplify event organization and participation. It allows administrators to create and manage events while enabling students to explore, book, and track their event participation.

The system ensures:
- Smooth ticket booking experience
- Real-time updates
- Secure authentication
- Smart event cancellation with notifications

---

## ✨ Key Features

### 👨‍💼 Admin Features
- Create, edit, and delete events
- Upload event posters
- Manage ticket availability
- Cancel events even after bookings
- QR-based check-in system
- View analytics (tickets sold, events, etc.)

---

### 🧑‍🎓 Student Features
- Browse upcoming events
- Filter/search events by category
- Book tickets (1 per user)
- View booking history
- QR code for event entry
- Real-time dashboard updates
- Automatic updates when event is cancelled

---

### 📧 Smart Notification System
- Email notifications sent when:
  - Event is cancelled
- Ensures users stay informed instantly

---

### 🔒 Authentication & Security
- JWT-based authentication
- Role-based access control (Admin / Student)
- Protected routes for secure operations

---

## 🏗️ Tech Stack

### 🔹 Frontend
- HTML5
- CSS3
- JavaScript (Vanilla JS)
- Responsive UI

### 🔹 Backend
- Node.js
- Express.js

### 🔹 Database
- MongoDB (Mongoose)

### 🔹 Other Tools
- Multer (file uploads)
- Nodemailer (email notifications)
- QRCode (ticket verification)
- JWT (authentication)

---

## 🧠 System Architecture
Frontend (HTML/CSS/JS)
↓
REST API (Express.js)
↓
MongoDB Database


---

## ⚙️ How It Works

### 1. Event Creation
Admin creates event → stored in database → displayed to students

### 2. Booking Flow
Student selects event → booking created → QR code generated

### 3. Event Cancellation
Admin cancels event →
- Event status updated
- Students notified via email
- Dashboard reflects cancellation

### 4. QR Check-in
Admin scans QR →
- Validates ticket
- Marks entry status



---
## 🛠️ Setup & Run Locally

### Prerequisites
- Node.js (LTS) and npm
- A MongoDB database (free MongoDB Atlas cluster, or local MongoDB)
- A Gmail account with an App Password (for email notifications)

### 1. Clone the repository
```bash
git clone https://github.com/shrusti564/EventSphere.git
cd EventSphere
```

### 2. Install dependencies
```bash
cd backend
npm install
```

### 3. Create the `.env` file
Create a file named `.env` inside the `backend` folder with the following:

```
MONGO_URI=your_mongodb_connection_string
PORT=5000
JWT_SECRET=your_random_secret
EMAIL_USER=your_gmail_address
EMAIL_PASS=your_gmail_app_password
```

- `MONGO_URI`: connection string from MongoDB Atlas (include a database name before the `?`)
- `JWT_SECRET`: any long random string. Generate one with:
  `node -e "console.log(require('crypto').randomBytes(32).toString('hex'))"`
- `EMAIL_PASS`: a 16-character Gmail App Password (no spaces), not your normal password

### 4. Start the server
```bash
node server.js
```
You should see `Server running on 5000` and `MongoDB Connected`.

### 5. Open the app
Go to http://localhost:5000

### Creating an Admin account
Registration always creates a **Student**. To make an admin:
1. Register a new account with an `@msrit.edu` email.
2. In MongoDB Atlas, open the `users` collection and change that user's `role` to `Admin`.
3. Log out and log in again.

> Note: the `.env` file is private and is not included in this repository.