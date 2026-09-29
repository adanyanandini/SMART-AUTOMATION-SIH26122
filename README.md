# InfraTrack — SIH26122

**Intelligent Data Capture & Schedule-Linking Layer for Infrastructure Project Management: Real-Time Actual Progress Tracking (Planning-to-Execution Bridge)**

InfraTrack is a simple full-stack web application designed to help infrastructure project teams monitor **planned schedules, actual progress, tasks, delays, and project execution** from a single dashboard.

The project addresses the gap between **project planning and real-world execution** by providing a centralized system where project managers can create projects, update progress, manage tasks, compare planned and actual dates, and generate execution reports.

---

## 🚧 Problem Statement

**Problem Statement ID:** SIH26122

**Title:** Intelligent Data Capture & Schedule-Linking Layer for Infrastructure Project Management: Real-Time Actual Progress Tracking (Planning-to-Execution Bridge)

**Theme:** Smart Automation

Infrastructure projects often face difficulties in tracking actual execution against the original plan. Information may be collected manually from different sources, making it difficult for project managers to identify delays and understand the current project status.

The proposed system provides a simple digital layer connecting:

```text
PROJECT PLAN
     ↓
SCHEDULE
     ↓
TASK EXECUTION
     ↓
ACTUAL PROGRESS
     ↓
REAL-TIME DASHBOARD
     ↓
REPORTS
```

---

# 🎯 Objectives

The main objectives of InfraTrack are:

* Track infrastructure projects digitally.
* Monitor actual progress against planned schedules.
* Identify delayed projects quickly.
* Manage project-level tasks.
* Record actual task completion dates.
* Provide a centralized project dashboard.
* Automatically refresh project information.
* Generate simple project reports.
* Reduce dependency on manual progress tracking.
* Create a foundation that can later be extended with AI, IoT, GPS and advanced analytics.

---

# ✨ Key Features

### 1. 📊 Real-Time Dashboard

The dashboard provides an overview of:

* Total projects
* Average project progress
* Delayed projects
* Completed tasks
* Total tasks
* Project progress bars
* Recent project activity

The dashboard automatically refreshes every **3 seconds**.

---

### 2. 🏗️ Project Management

Users can create new infrastructure projects by entering:

* Project name
* Location
* Project manager
* Planned start date
* Planned end date

Each project is stored in the backend.

---

### 3. 📈 Progress Tracking

Project managers can update the actual progress percentage from:

```text
0% → 100%
```

The system automatically updates the project status.

Example:

```text
0–49%     → Delayed
50–99%    → On Track
100%      → Completed
```

This is a simple demo rule and can later be replaced with schedule-based calculations.

---

### 4. 📋 Task Management

Each project can contain multiple tasks.

For example:

```text
City Flyover
│
├── Foundation
├── Pillars
├── Deck Slab
└── Road Finishing
```

Each task contains:

* Task name
* Planned date
* Actual completion date
* Status

---

### 5. 📅 Schedule Linking

The Schedule section compares:

| Project        | Task        | Planned Date | Actual Date | Status      |
| -------------- | ----------- | ------------ | ----------- | ----------- |
| City Flyover   | Foundation  | 20-09-2026   | 18-09-2026  | Completed   |
| City Flyover   | Pillars     | 15-10-2026   | —           | In Progress |
| Water Pipeline | Pipe Laying | 20-10-2026   | —           | In Progress |

This provides a basic **planning-to-execution bridge**.

---

### 6. ⚠️ Delay Monitoring

Projects can be identified as:

* On Track
* Delayed
* Completed

This makes it easier for project managers to identify projects requiring attention.

---

### 7. 🔄 Automatic Data Refresh

The frontend automatically communicates with the backend every few seconds.

```text
Frontend
   ↓
API Request
   ↓
Node.js Backend
   ↓
Project Data
   ↓
Frontend Update
```

This gives the application a real-time dashboard experience without requiring complex WebSocket infrastructure.

---

### 8. 📑 Reports

The Reports section provides a summary containing:

* Total projects
* Average progress
* Delayed projects
* Completed projects
* Completed tasks
* Total tasks

Users can also download the report as a `.txt` file.

---

### 9. 🔍 Project Search

Users can search projects using:

* Project name
* Location
* Project manager

This helps when multiple projects are being monitored.

---

### 10. 🗑️ Project Deletion

Projects can be deleted directly from the project management interface.

---

# 🛠️ Technology Stack

## Frontend

* HTML5
* CSS3
* JavaScript
* Responsive CSS

## Backend

* Node.js
* Express.js
* REST API

## Data Storage

* JSON-based storage

The JSON approach keeps the project simple and easy to understand for beginners.

For a production version, it can be replaced with:

* MySQL
* PostgreSQL
* MongoDB

---

# 📁 Project Structure

```text
InfraTrack_SIH26122/
│
├── package.json
├── server.js
├── README.md
│
├── data/
│   └── projects.json
│
└── public/
    ├── index.html
    ├── style.css
    └── app.js
```

### `server.js`

Contains the backend server and REST APIs.

### `public/index.html`

Contains the application interface.

### `public/style.css`

Contains the complete UI styling and responsive design.

### `public/app.js`

Contains frontend functionality and API communication.

### `data/projects.json`

Stores project information and tasks.

### `package.json`

Contains the Node.js project configuration and dependencies.

---

# 🔌 API Endpoints

### Get all projects

```http
GET /api/projects
```

### Get a specific project

```http
GET /api/projects/:id
```

### Create project

```http
POST /api/projects
```

### Update project progress

```http
PATCH /api/projects/:id/progress
```

### Add task

```http
POST /api/projects/:id/tasks
```

### Update task

```http
PATCH /api/projects/:projectId/tasks/:taskId
```

### Delete project

```http
DELETE /api/projects/:id
```

### Get dashboard statistics

```http
GET /api/stats
```

### Check server status

```http
GET /api/health
```

---

# 🔄 Application Workflow

```text
                ┌──────────────────┐
                │  Project Manager  │
                └────────┬─────────┘
                         │
                         ▼
                ┌──────────────────┐
                │ Create Project   │
                └────────┬─────────┘
                         │
                         ▼
                ┌──────────────────┐
                │ Add Schedule &   │
                │ Tasks            │
                └────────┬─────────┘
                         │
                         ▼
                ┌──────────────────┐
                │ Record Actual    │
                │ Progress         │
                └────────┬─────────┘
                         │
                         ▼
                ┌──────────────────┐
                │ Node.js Backend  │
                └────────┬─────────┘
                         │
                         ▼
                ┌──────────────────┐
                │ JSON Data Store  │
                └────────┬─────────┘
                         │
                         ▼
                ┌──────────────────┐
                │ Live Dashboard   │
                └────────┬─────────┘
                         │
              ┌──────────┴──────────┐
              ▼                     ▼
       Delay Monitoring          Reports
```

---

# 🚀 Installation

## Prerequisites

Install:

* Node.js
* npm
* VS Code (recommended)

Check installation:

```bash
node -v
npm -v
```

---

## Install Dependencies

Open the project directory in the terminal:

```bash
npm install
```

---

## Start the Server

```bash
npm start
```

The application will run at:

```text
http://localhost:3000
```

Open this address in your browser.

---

# 🖥️ Example Use Case

Suppose a government infrastructure department is monitoring a **City Flyover Construction Project**.

The manager creates:

```text
Project:
City Flyover Construction

Location:
Hyderabad

Manager:
Ravi Kumar

Planned Start:
01-09-2026

Planned End:
20-12-2026
```

Tasks can then be added:

```text
Foundation
Pillars
Deck Slab
Road Finishing
```

The manager updates actual progress:

```text
Foundation → Completed
Pillars → In Progress
Deck Slab → Pending
```

The dashboard then shows the current project progress and status.

---

# 💡 Future Enhancements

The current project is designed as a simple working prototype. It can be expanded significantly for a production-level Smart Automation solution.

### 🤖 AI-Based Progress Detection

Use computer vision to analyze construction site images/videos and estimate actual physical progress.

```text
Site Image
     ↓
AI Computer Vision
     ↓
Construction Element Detection
     ↓
Estimated Progress
     ↓
Dashboard
```

### 📍 GPS-Based Location Tracking

Use GPS to associate project updates with specific construction locations.

### 📷 Image-Based Data Capture

Workers could upload site photographs as evidence of completed work.

### 📱 Mobile Application

A mobile application could allow field engineers to update progress directly from construction sites.

### 🗄️ Production Database

Replace JSON storage with:

```text
MySQL / PostgreSQL
```

### 🔐 Authentication

Add different user roles:

* Admin
* Project Manager
* Site Engineer
* Field Worker
* Government Officer

### 🔔 Notifications

Automatic notifications could be generated when:

* A project falls behind schedule.
* A task is overdue.
* Progress has not been updated.
* A milestone is completed.

### 📊 Advanced Analytics

Future versions could calculate:

* Schedule variance
* Cost variance
* Productivity
* Delay trends
* Project risk
* Estimated completion date

### 🌐 Multi-Project Monitoring

A centralized system could monitor hundreds of infrastructure projects across different locations.

---

# 🎓 SIH Relevance

InfraTrack directly addresses the **planning-to-execution bridge** described in SIH26122.

The prototype connects project planning information with actual execution data through:

```text
Planned Schedule
       +
Actual Progress
       +
Task Status
       +
Completion Dates
       ↓
Real-Time Project View
```

This provides a foundation for building a larger intelligent infrastructure monitoring platform.

---

# 🔒 Data and Security

The current prototype uses local JSON storage to keep the implementation simple.

For production deployment, recommended additions include:

* User authentication
* Password hashing
* Role-based access control
* HTTPS
* Database access controls
* API authentication
* Input validation
* Audit logs
* Secure file storage

---

# 📌 Project Status

**Current Version:** `1.0.0`

**Status:** Working prototype

**Theme:** Smart Automation

**Problem Statement:** SIH26122

**Application Type:** Full-Stack Web Application

---

# 👨‍💻 Contributors

Add your team members here:

```text
Team Name: YOUR_TEAM_NAME

Team Members:
1. Your Name
2. Member Name
3. Member Name
4. Member Name
5. Member Name
6. Member Name
```

---

# ⭐ Conclusion

**InfraTrack** provides a simple and functional foundation for real-time infrastructure project monitoring. It connects project schedules, tasks, actual progress and reporting in one application.

The current prototype focuses on simplicity and usability while providing a clear foundation for future integration of **AI, IoT, GPS, computer vision, databases, mobile applications and predictive analytics**.

> **InfraTrack — Connecting Infrastructure Planning with Real-World Execution.**
