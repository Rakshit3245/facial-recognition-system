# Facial Recognition System

A complete, real-time **Facial Recognition System** built with **Django**, **PostgreSQL**, **OpenCV**, and **face_recognition**, designed for secure identity verification, surveillance, and access control. The system supports user registration and login via facial recognition and includes role-based access for admins and users.

---

## 🚀 Overview

This system provides a secure, scalable, and modular solution using facial biometrics for:
- Attendance tracking
- Access control (e.g., login/authentication)
- Time tracking (corporate/factory)
- Visitor management
- Real-time surveillance & watchlist monitoring

---

## 🔑 Core Features

### 👤 User Authentication (Face-Based)
- Register using face via webcam.
- Login with face recognition (no password).
- Role-based login: Admin & General User.

### 🕵️‍♂️ Real-Time Surveillance
- Live camera stream with automatic face detection.
- Watchlist recognition alerts.

### 📆 Attendance System
- Automatic check-in/check-out based on face.
- Ideal for corporate/school/factory attendance.

### 🧾 Access Control & Logging
- Role-based access: Admin/User
- Logs user activity, login times, and device info.

### 👥 Visitor Management
- One-time registration for visitors using facial scan.
- Entry logging with time and captured image.

### 🛠 Admin Dashboard
- Manage users, devices, logs, and settings.
- View analytics and system usage stats.

---

## 🏗 System Architecture
                     ┌──────────────────────────────┐
                     │        Client Browser        │
                     │ (HTML, JS, Bootstrap, Webcam)│
                     └────────────┬─────────────────┘
                                  │
                                  ▼
                     ┌──────────────────────────────┐
                     │    Django Web Application    │
                     │  (Views, Forms, Templates)   │
                     └────────────┬─────────────────┘
                                  │
        ┌─────────────────────────┼──────────────────────────┐
        ▼                         ▼                          ▼
┌────────────────┐      ┌─────────────────────┐     ┌────────────────────┐
│  Face Capture  │      │  Face Recognition   │     │    Role-Based      │
│  (OpenCV, JS)  │      │(face_recognition.py)│     │ Authentication &   │
│                │      │                     │     │ Authorization (RBAC)│
└────────────────┘      └─────────────────────┘     └────────────────────┘
         │                          │                          │
         └──────────────────────────┴──────────────┬──────────┘
                                                   ▼
                                      ┌────────────────────────────┐
                                      │   PostgreSQL Database      │
                                      │ (User, Face Embeddings,    │
                                      │  Attendance, Logs, etc.)   │
                                      └────────────────────────────┘

                     ┌──────────────────────────────────────────┐
                     │         Admin Dashboard Module           │
                     │  (Users, Attendance, Logs, Watchlist)    │
                     └──────────────────────────────────────────┘



---

---

## 🧰 Tech Stack

- **Frontend**: HTML5, CSS3, Bootstrap, Tailwind, JavaScript
- **Backend**: Django 4.x (Python 3.10+)
- **Database**: PostgreSQL
- **Facial Recognition**: `face_recognition`, `OpenCV`, `dlib`, `NumPy`
- **Real-Time Detection**: MediaPipe (optional)
- **Containerization** (optional): Docker-ready

---

## 🧪 Installation

### Prerequisites
- Python 3.10+
- pip / virtualenv
- PostgreSQL (or use SQLite for testing)
- Visual Studio C++ Build Tools (for Windows)
- Git

### Setup Instructions

```bash
# Clone the repo
git clone https://github.com/Rakshit3245/facial-recognition-system.git
cd facial-recognition-system

# Create virtual environment
python -m venv frs_venv
source frs_venv/bin/activate  # on Windows: frs_venv\Scripts\activate

# Install requirements
pip install -r requirements.txt

# Setup DB
python manage.py makemigrations
python manage.py migrate

# Run server
python manage.py runserver
