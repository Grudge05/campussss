# 🎓 Campus Resource Optimizer

> **VIT Bhopal Hackathon — Problem Statement #05**  
> Smart Utilization of Shared Campus Infrastructure

---

## 📌 Problem Statement

Campus resources like labs, study rooms, and equipment are often **underutilized or poorly managed**. Students want to book or find available resources in real time but face confusion and inefficiency due to lack of a centralized system.

---

## 💡 Solution

**Campus Resource Optimizer** is a web-based platform that tracks, predicts, and optimizes campus resource usage in real time. Students can browse availability, make instant bookings, and view live utilization data — all from a single interface.

---

## ✨ Features

| Feature | Description |
|---|---|
| 📊 **Live Dashboard** | Real-time stats — total resources, available now, booked, and today's bookings |
| 🔍 **Browse & Search** | Filter resources by type (labs, rooms, equipment, sports) and search by name or location |
| 📅 **Booking System** | Book any resource by selecting a time slot; conflict detection prevents double-bookings |
| 📈 **Analytics** | Hourly usage chart, utilization by resource type, and availability timeline |
| 🗂️ **My Bookings** | View and cancel your upcoming reservations |
| 📋 **Usage Reports** | Admin-facing log of all bookings with CSV export |
| ⚙️ **Settings** | Notification preferences and account management |

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Frontend | HTML5, CSS3, Vanilla JavaScript |
| Styling | CSS Variables, Google Fonts (DM Sans + Space Mono) |
| Backend (original) | Python · Flask · Flask-CORS |
| Database (original) | Firebase Firestore |
| Deployment version | Fully self-contained single HTML file with in-memory JS database |

---

## 📁 Project Structure

```
campus-resource-optimizer/
│
├── campus_resource_optimizer.html   # ✅ Full standalone website (no server needed)
│
├── app2.py                          # Flask backend with Firebase integration
├── test.py                          # API test script
│
├── frontend1.html                   # Original frontend (connects to Flask API)
├── campus_resource_optimizer_ui.html # UI mockup / design reference
│
├── serviceAccountKey.json           # Firebase service account (keep private!)
│
└── README.md                        # This file
```

---

## 🚀 Running the Project

### Option 1 — Standalone (No Setup Required)

Just open `campus_resource_optimizer.html` in any modern browser. It includes a full in-memory database and works completely offline with no server or dependencies.

```bash
# Simply double-click the file, or:
open campus_resource_optimizer.html
```

### Option 2 — Full Stack (Flask + Firebase)

**Prerequisites:** Python 3.8+, pip, Firebase project

```bash
# 1. Install dependencies
pip install flask flask-cors firebase-admin

# 2. Place your serviceAccountKey.json in the project root

# 3. Start the Flask server
python app2.py
# Server runs on http://127.0.0.1:8000

# 4. Open frontend1.html in a browser
# (Update the API base URL in the JS to http://127.0.0.1:8000)
```

### Testing the API

```bash
python test.py
# Tests the /book endpoint with a sample booking
```

---

## 🗄️ API Endpoints (Flask Backend)

| Method | Endpoint | Description |
|---|---|---|
| `GET` | `/rooms` | Fetch all rooms from Firestore |
| `GET` | `/dashboard` | Get summary stats (total, available, occupied, bookings) |
| `POST` | `/book` | Book a room (with conflict check) |

**Book request body:**
```json
{
  "room_id": "A101",
  "user": "Aditya Kumar",
  "start_time": 10,
  "end_time": 12
}
```

---

## 🗃️ In-Memory Database (Standalone Version)

The standalone HTML file ships with a built-in JavaScript database containing:

- **13 resources** across labs, study rooms, equipment, and sports facilities
- **5 pre-loaded bookings** to demonstrate live dashboard data
- Full CRUD support — bookings persist for the duration of the browser session

---

## 📊 Resource Categories

| Type | Count | Examples |
|---|---|---|
| 🖥️ Computer Labs | 3 | Lab A, Lab B, Lab C |
| 📚 Study Rooms | 3 | Room 2B, 3A, 4C |
| 🔬 Equipment | 3 | 3D Printer, Laser Cutter, VR Headsets |
| 🏀 Sports | 4 | Basketball Court, Tennis, Badminton |

---

## 👥 Team

**Institution:** VIT Bhopal University  
**Event:** Vibe Hack 2026  
**Track:** Campus Tech / Smart Infrastructure

---

## 🔒 Security Note

> ⚠️ The `serviceAccountKey.json` file contains private Firebase credentials.  
> **Never commit this file to a public repository.**  
> Add it to `.gitignore` before pushing to GitHub.

```bash
# .gitignore
serviceAccountKey.json
```

---

## 📄 License

This project was built for educational and hackathon purposes at VIT Bhopal.
