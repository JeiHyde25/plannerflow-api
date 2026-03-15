
# 🧠 PlannerFlow API

![MIT License](https://img.shields.io/badge/License-MIT-yellow.svg)  
![Python](https://img.shields.io/badge/Python-3.13-blue)  
![FastAPI](https://img.shields.io/badge/FastAPI-API-green)

PlannerFlow API is the backend service for **PlannerFlow**, an AI-powered productivity system that converts handwritten planner pages into structured digital schedules and calendar events.

The API receives planner images, processes them using **OpenAI Vision**, and returns structured planner data that can be edited, saved, and exported to calendar systems.

---

# 📌 Project Overview

Many professionals prefer planning their day using **physical planners**, but handwritten plans are disconnected from digital tools like calendars and reminders.

PlannerFlow bridges this gap by turning handwritten schedules into structured digital data.

Workflow:

Write planner → Scan planner → AI extraction → Review & edit → Export to calendar

This repository contains the **backend API responsible for**:

- Planner image processing
- AI extraction using OpenAI Vision
- Structured planner data validation
- Planner entry storage
- Calendar export generation

---

# 📁 Project Structure

plannerflow-api/
├── app/
│   ├── api/
│   │   └── routes/
│   ├── core/
│   │   └── config.py
│   ├── schemas/
│   │   └── planner_extraction.py
│   ├── services/
│   │   └── extraction_service.py
│   ├── models/
│   └── main.py
├── tests/
├── .gitignore
├── Dockerfile
├── README.md
├── requirements.in
├── requirements.txt
├── requirements-dev.in
├── requirements-dev.txt
└── setup-dev-env.sh

---

# 🔧 Features

- 📷 Planner image upload
- 🧠 AI-powered planner extraction using OpenAI Vision
- 🧾 Structured planner schedule parsing
- ✏️ Editable planner data
- 💾 Planner data persistence
- 📆 Export schedules as `.ics` calendar files
- 🔐 User authentication support (Supabase)
- 🧪 Extensible API architecture

---

# 🚀 Tech Stack

- Python 3.13
- FastAPI
- OpenAI Vision API
- PostgreSQL
- Supabase Auth
- Docker
- GitHub Actions

---

# 🛠️ Getting Started (Local)

## 1. Clone the repository

git clone https://github.com/JeiHyde25/plannerflow-api.git  
cd plannerflow-api

---

## 2. Install dependencies

Requires **Python 3.13+** and **pip-tools**

pip install pip-tools

pip-compile requirements.in  
pip-compile requirements-dev.in

pip install -r requirements.txt  
pip install -r requirements-dev.txt

Alternatively run:

./setup-dev-env.sh

---

## 3. Run the API

uvicorn app.main:app --reload

API will be available at:

http://localhost:8000

Interactive API docs:

http://localhost:8000/docs

---

# 📡 Example API Endpoints

### Health Check

GET /health

Response:

{
  "status": "ok"
}

---

### Planner Extraction

POST /planner/extract

Input:

- planner image

Output:

{
  "planner_date": "2026-03-15",
  "todos": [],
  "schedule_blocks": [
    {
      "start_time": "10:00",
      "end_time": "14:00",
      "title": "Work Block",
      "task_items": [
        {"text": "Send applications"},
        {"text": "Reply to emails"}
      ]
    }
  ]
}

---

# 🧪 Future Improvements

- Universal planner layout detection
- Google Calendar integration
- Planner analytics
- Recurring task detection
- Background extraction workers
- Improved handwriting recognition

---

# 📄 License

This project is licensed under the MIT License.

---

# 👤 Author

Harold Tago  
GitHub: https://github.com/JeiHyde25
