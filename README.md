# 🚦 QueueLess — Intelligent Queue & Appointment Management System

<p align="center"><strong>Smart. Real-Time. Queue-Free.</strong></p>

<p align="center">A modern full-stack queue and appointment management platform that enables customers to join queues remotely, book appointments, track tokens in real time, and helps organizations efficiently manage their services and operations.</p>

---

# 📌 About the Project

**QueueLess** is an intelligent queue and appointment management system designed to reduce physical waiting time and improve the overall service experience.

The platform allows customers to:

- Join queues remotely
- Receive digital tokens
- Book appointments
- Track their queue position
- View estimated waiting time
- Monitor token status in real time
- Receive queue and appointment updates

Organizations can use QueueLess to manage:

- Organizations
- Branches
- Services
- Counters
- Staff
- Managers
- Customers
- Appointments
- Queue tokens
- Operational analytics

QueueLess follows a **role-based, multi-tenant architecture** so different organizations can manage their own branches, services, users, and queues.

---

# ❗ Problem Statement

Traditional queue systems require customers to physically visit a location and wait for their turn.

This can lead to:

- Long waiting times
- Crowded waiting areas
- Unpredictable service times
- Poor customer experience
- Inefficient counter utilization
- Difficulty managing appointments
- Lack of real-time queue information
- Manual queue management

QueueLess addresses these problems by converting a traditional physical queue into a digital, real-time queue management system.

---

# 💡 Solution

QueueLess allows customers to join a queue without physically standing in line.

### Traditional Queue

```text
Customer
   ↓
Visit Location
   ↓
Take Token
   ↓
Wait Physically
   ↓
Wait...
   ↓
Counter
   ↓
Service
```

### QueueLess

```text
Customer
   ↓
Select Service
   ↓
Join Queue Remotely
   ↓
Receive Digital Token
   ↓
Track Queue Online
   ↓
Receive Notification
   ↓
Arrive Near Turn
   ↓
Visit Counter
   ↓
Service Completed
```

---

# ✨ Key Features

## 👤 Customer

- 🔐 Customer registration and login
- 🏢 Browse available services
- 🎫 Digital queue token
- 📱 Remote queue joining
- 📅 Appointment booking
- ⏱️ Estimated waiting time
- 📊 Live queue position
- 🔔 Queue status updates
- 📝 Appointment history
- ❌ Appointment cancellation
- 📋 Token history
- 📱 Mobile-friendly dashboard

## 👨‍🔧 Staff / Operator

- View assigned counter
- View waiting customers
- Call next token
- Start service
- Complete service
- Hold token
- Skip token
- Mark no-show
- Update counter status
- Monitor queue activity

## 👨‍💼 Branch Manager

- Manage branch operations
- Manage counters
- Manage services
- Monitor staff
- Monitor appointments
- Monitor queue tokens
- View branch statistics
- Track operational activity

## 🛡️ Administrator

- Manage organization
- Manage branches
- Manage users
- Manage staff and managers
- Manage services
- Manage counters
- Manage appointments
- Monitor queues
- View analytics
- Manage permissions

## 👑 Super Administrator

- 🌐 Manage organizations
- 👥 Manage platform users
- 🔐 Manage roles and permissions
- 📊 Platform-wide analytics
- 📝 Audit logs
- ❤️ System health monitoring
- ⚙️ Global platform settings
- 🏢 Organization management
- 📈 Platform statistics

---

# 👥 User Roles

| Role | Responsibilities |
|---|---|
| 👑 Super Admin | Platform-wide administration |
| 🛡️ Admin | Organization administration |
| 👨‍💼 Manager | Branch management |
| 👨‍🔧 Staff | Queue and counter operations |
| 👤 Customer | Queue and appointment services |

---

# 🔄 Queue Workflow

```text
                    ┌──────────────┐
                    │   CUSTOMER   │
                    └──────┬───────┘
                           │
                           ▼
                  ┌─────────────────┐
                  │ Select Service  │
                  └────────┬────────┘
                           │
                           ▼
                  ┌─────────────────┐
                  │   Join Queue   │
                  └────────┬────────┘
                           │
                           ▼
                  ┌─────────────────┐
                  │ Digital Token   │
                  │   Generated     │
                  └────────┬────────┘
                           │
                           ▼
                    ┌────────────┐
                    │  WAITING   │
                    └─────┬──────┘
                          │
                          ▼
                    ┌────────────┐
                    │   CALLED   │
                    └─────┬──────┘
                          │
                          ▼
                    ┌────────────┐
                    │ IN_SERVICE │
                    └─────┬──────┘
                          │
                          ▼
                    ┌────────────┐
                    │ COMPLETED  │
                    └────────────┘
```

Additional states:

```text
HOLD
CANCELLED
SKIPPED
NO_SHOW
```

---

# 🏗️ System Architecture

```text
                         ┌───────────────────┐
                         │     CUSTOMER      │
                         └─────────┬─────────┘
                                   │
                                   ▼
                    ┌──────────────────────────┐
                    │     REACT FRONTEND       │
                    │ React + TypeScript       │
                    │ Vite + Tailwind CSS      │
                    └────────────┬─────────────┘
                                 │
                          REST / WebSocket
                                 │
                                 ▼
                    ┌──────────────────────────┐
                    │     NESTJS BACKEND       │
                    │ REST API                 │
                    │ Authentication           │
                    │ Business Logic           │
                    │ Role Management          │
                    └────────────┬─────────────┘
                                 │
                    ┌────────────┴────────────┐
                    │                         │
                    ▼                         ▼
          ┌──────────────────┐       ┌──────────────────┐
          │   PostgreSQL     │       │      Redis       │
          │ Primary Database │       │ Cache / Queue    │
          │ Persistent Data  │       │ Rate Limiting    │
          └──────────────────┘       └────────┬─────────┘
                                               │
                                               ▼
                                      ┌──────────────────┐
                                      │     Socket.IO    │
                                      │ Real-Time Events │
                                      └──────────────────┘
```

---

# 🛠️ Technology Stack

| Technology | Purpose |
|---|---|
| React | User interface |
| TypeScript | Type-safe development |
| Vite | Frontend build tool |
| Tailwind CSS | UI styling |
| NestJS | Backend framework |
| REST API | Client-server communication |
| JWT | Authentication |
| PostgreSQL | Primary database |
| Redis | Caching and performance |
| Socket.IO | Real-time communication |
| Git | Version control |
| GitHub | Repository and collaboration |
| Docker | Containerized deployment |

---

# 🗄️ Database Architecture

```text
                    ORGANIZATION
                         │
              ┌──────────┴──────────┐
              │                     │
              ▼                     ▼
           BRANCHES               USERS
              │
       ┌──────┴──────┐
       │             │
       ▼             ▼
   COUNTERS       SERVICES
       │             │
       └──────┬──────┘
              │
              ▼
        QUEUE TOKENS
              │
              ▼
         APPOINTMENTS
```

Core tables:

- `appointments`
- `counters`
- `queue_tokens`
- `services`

---

# ⚡ Real-Time Queue Management

QueueLess is designed to provide real-time queue updates.

```text
Customer Token: A101

        WAITING
           │
           ▼
         CALLED
           │
           ▼
       IN_SERVICE
           │
           ▼
        COMPLETED
```

When a staff member changes a token status, the customer interface can receive the updated status through real-time communication without repeatedly refreshing the page.

---

# 🔐 Security

QueueLess uses multiple security layers.

### Authentication

- JWT-based authentication
- Secure login
- Protected routes
- Role-based authentication

### Authorization

```text
Super Admin
     │
     ▼
   Admin
     │
     ▼
  Manager
     │
     ▼
   Staff

Customer
     │
     └── Customer-only access
```

Additional security:

- Role-based access control
- Database permissions
- Multi-tenant organization isolation
- Protected management routes
- Audit logging
- Rate limiting support
- Environment-based secrets

---

# 📱 Responsive Design

QueueLess is designed for:

- 💻 Desktop
- 📱 Mobile
- 📲 Tablet

Customers can track queues from mobile devices while staff and administrators can use dashboard interfaces for operational management.

---

# 📊 Dashboard

## Customer Dashboard

```text
┌──────────────────────────────┐
│       Customer Dashboard     │
├──────────────────────────────┤
│ Current Token                │
│ Estimated Wait               │
│ Queue Position               │
│                              │
│ Upcoming Appointments        │
│ Queue History                │
└──────────────────────────────┘
```

## Staff Dashboard

```text
┌──────────────────────────────┐
│        Staff Dashboard       │
├──────────────────────────────┤
│ Current Counter              │
│ Current Token                │
│ Waiting Queue                │
│                              │
│ [CALL NEXT]                  │
│ [START SERVICE]              │
│ [COMPLETE]                   │
└──────────────────────────────┘
```

## Admin Dashboard

```text
┌──────────────────────────────┐
│        Admin Dashboard       │
├──────────────────────────────┤
│ Active Queues                │
│ Appointments                 │
│ Counters                     │
│ Services                     │
│ Staff                        │
│ Analytics                    │
└──────────────────────────────┘
```

---

# 📂 Project Structure

```text
QueueLess/
│
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── hooks/
│   │   ├── services/
│   │   ├── contexts/
│   │   └── utils/
│   ├── public/
│   ├── package.json
│   └── vite.config.ts
│
├── backend/
│   ├── src/
│   │   ├── modules/
│   │   ├── controllers/
│   │   ├── services/
│   │   ├── guards/
│   │   ├── middleware/
│   │   └── main.ts
│   └── package.json
│
├── database/
│   ├── migrations/
│   └── seeds/
│
├── docs/
├── .env.example
├── .gitignore
├── docker-compose.yml
├── package.json
└── README.md
```

---

# ⚙️ Installation

## 1. Clone the Repository

```bash
git clone https://github.com/atul-dubey-2005/queueless-intelligent-mobile.git
```

## 2. Navigate to the Project

```bash
cd queueless-intelligent-mobile
```

## 3. Install Dependencies

```bash
npm install
```

If frontend and backend are separate applications:

```bash
cd frontend
npm install

cd ../backend
npm install
```

---

# 🔑 Environment Variables

Create a `.env` file based on `.env.example`.

```env
DATABASE_URL=your_postgresql_connection_string
JWT_SECRET=your_jwt_secret
REDIS_URL=your_redis_connection_string
PORT=3000
VITE_API_URL=http://localhost:3000
```

> ⚠️ Never commit real passwords, API keys, database credentials, or JWT secrets to GitHub.

---

# ▶️ Running the Project

## Start Frontend

```bash
cd frontend
npm run dev
```

Frontend:

```text
http://localhost:5173
```

## Start Backend

```bash
cd backend
npm run start:dev
```

Backend:

```text
http://localhost:3000
```

---

# 🐳 Docker

Start services:

```bash
docker compose up -d
```

Stop services:

```bash
docker compose down
```

---

# 🧪 Development

```bash
npm run dev
```

Production build:

```bash
npm run build
```

Preview production build:

```bash
npm run preview
```

---

# 🏥 Example Use Case

## Hospital Queue

A patient wants to consult a doctor.

### Step 1 — Select Service

```text
General Consultation
```

### Step 2 — Join Queue

```text
Token: G-024
```

### Step 3 — Track Queue

```text
Your Token: G-024
Currently Serving: G-019
People Ahead: 4
Estimated Wait: 25 Minutes
```

### Step 4 — Token Called

```text
🔔 Your token G-024 has been called.
Please proceed to Counter 3.
```

### Step 5 — Service

The patient visits the assigned counter.

### Step 6 — Completion

```text
G-024
Status: COMPLETED
```

---

# 🏫 Use Cases

## 🏥 Healthcare

- Doctor appointments
- OPD queues
- Diagnostic centers
- Pharmacy queues

## 🏫 Education

- College offices
- Admission counters
- Examination departments
- Student services

## 🏛️ Government

- Citizen service centers
- Document verification
- Certificate applications
- Government counters

## 🏦 Banking

- Customer service
- Account services
- Loan departments
- Document verification

## 🏢 Corporate

- Employee help desks
- Visitor management
- Service desks
- Internal support centers

---

# 📝 API Concept

## Authentication

```text
POST   /auth/login
POST   /auth/register
POST   /auth/logout
```

## Services

```text
GET    /services
POST   /services
PUT    /services/:id
DELETE /services/:id
```

## Queue

```text
GET    /queue
POST   /queue/join
GET    /queue/:id
PUT    /queue/:id
```

## Appointments

```text
GET    /appointments
POST   /appointments
GET    /appointments/:id
PUT    /appointments/:id
DELETE /appointments/:id
```

## Counters

```text
GET    /counters
POST   /counters
PUT    /counters/:id
```

---

# 📈 Scalability

```text
                  Load Balancer
                       │
             ┌─────────┴─────────┐
             │                   │
        Backend 1           Backend 2
             │                   │
             └─────────┬─────────┘
                       │
                  Redis Layer
                       │
                       ▼
                  PostgreSQL
```

The backend can be scaled horizontally as traffic increases. Redis can be used for caching, rate limiting, and real-time coordination, while PostgreSQL remains the primary source of persistent data.

---

# 🔮 Future Enhancements

- 🤖 AI-based queue time prediction
- 📱 Dedicated Android and iOS applications
- 🔔 Push, SMS, email, and WhatsApp notifications
- 📊 Advanced analytics and reports
- 🧠 Intelligent counter allocation
- 🌍 Multi-language support
- 📍 Branch/location discovery
- 📅 Advanced appointment scheduling

---

# 🎯 Project Goals

QueueLess aims to:

- ⏱️ Reduce unnecessary waiting time
- 😊 Improve customer experience
- 👨‍💼 Improve staff productivity
- 📱 Provide remote queue access
- 🔔 Provide real-time updates
- 📅 Simplify appointment management
- 📊 Improve operational visibility
- 🏢 Support multiple organizations
- 🔐 Provide secure role-based access
- 🚀 Provide a scalable architecture

---

# 🤝 Contributing

Contributions are welcome.

### 1. Fork the repository

### 2. Clone your fork

```bash
git clone https://github.com/your-username/queueless-intelligent-mobile.git
```

### 3. Create a feature branch

```bash
git checkout -b feature/new-feature
```

### 4. Make your changes

```bash
git add .
git commit -m "Add new feature"
```

### 5. Push the branch

```bash
git push origin feature/new-feature
```

### 6. Create a Pull Request

Open a Pull Request on GitHub and describe the changes made.

---

# 🐛 Bug Reports

If you find a bug, create a GitHub Issue with:

- Description of the issue
- Steps to reproduce
- Expected behavior
- Actual behavior
- Screenshots if applicable
- Browser/device information

---

# 💡 Feature Requests

Feature suggestions are welcome. Include:

- Feature description
- Problem it solves
- Expected behavior
- Possible implementation approach

---

# 🔒 Security

If you discover a security vulnerability, please avoid publicly posting sensitive information in an issue. Contact the project owner privately with details about the vulnerability.

---

# 📜 License

This project is developed for educational and project purposes.

---

# 👨‍💻 Author

## Atul Dubey

GitHub: https://github.com/atul-dubey-2005

---

# ⭐ Support

If you find **QueueLess** useful or interesting, consider giving the repository a ⭐ on GitHub.

---

<p align="center">
  <strong>QueueLess — Smart Queue Management for a Better Service Experience 🚦</strong>
</p>

<p align="center">
  Built with ❤️ using React, TypeScript, NestJS, PostgreSQL, Redis & Socket.IO.
</p>
