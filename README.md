# 🗳️ Nepal Online Voting System — Full Stack Election Platform

<p>
  <img src="https://img.shields.io/badge/FRONTEND-REACT-61dafb?style=for-the-badge&logo=react&logoColor=black" alt="React" />
  <img src="https://img.shields.io/badge/BACKEND-NODE.JS-339933?style=for-the-badge&logo=node.js&logoColor=white" alt="Node.js" />
  <img src="https://img.shields.io/badge/API-EXPRESS-000000?style=for-the-badge&logo=express&logoColor=white" alt="Express" />
  <img src="https://img.shields.io/badge/DATABASE-MONGODB-47a248?style=for-the-badge&logo=mongodb&logoColor=white" alt="MongoDB" />
  <img src="https://img.shields.io/badge/AUTH-JWT%20%2B%20OTP-000000?style=for-the-badge&logo=jsonwebtokens&logoColor=white" alt="JWT" />
  <img src="https://img.shields.io/badge/DEPLOY-VERCEL-000000?style=for-the-badge&logo=vercel&logoColor=white" alt="Vercel" />
</p>

A full-stack, multi-portal digital election platform designed for **secure, transparent, and auditable voting workflows**. Built with React + Vite on the frontend and Node.js + Express + MongoDB on the backend.

---

## 📌 Table of Contents

- [About the Project](#-about-the-project)
- [Portals](#-portals)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Project Structure](#-project-structure)
- [Getting Started](#-getting-started)
- [Authentication & Security](#-authentication--security)
- [Role Access Rules](#-role-access-rules)
- [Future Enhancements](#-future-enhancements)
- [License](#-license)
- [Author](#-author)

---

## 📖 About the Project

The **Nepal Online Voting System (OVS)** is a production-ready style election platform with separate portals for Admins, Voters, and Political Parties. All election operations are backed by secure REST APIs and MongoDB, with strict role-based access control and full auditability.

---

## 🧭 Portals

| Portal | Role | Description |
|---|---|---|
| 👨‍💼 Admin | Election Manager | Create elections, manage voter/party registration, monitor live results |
| 🗳️ Voter | Registered Citizen | Verify identity, cast vote, view results |
| 🏛️ Party | Political Party | Manage profile, track campaign data and analytics |

---

## ✨ Features

### 👨‍💼 Admin Portal
- Full election lifecycle management (Create → Run → End → Results)
- Voter and party registration approval
- Live election stats and vote count monitoring
- Publish notifications and election updates
- Export election reports

### 🗳️ Voter Portal
- OTP-based identity verification
- Secure vote casting (one vote per election)
- Live result view after election ends

### 🏛️ Party Portal
- Party profile and candidate management
- Campaign performance analytics
- Notification center

### 🔒 Security
- JWT authentication across all portals
- OTP verification on login
- bcrypt password hashing
- Role-based URL route protection

---

## 🛠 Tech Stack

| Layer | Technology |
|---|---|
| Frontend Framework | React + Vite |
| Routing | React Router DOM |
| Styling | Tailwind CSS |
| HTTP Client | Axios |
| Backend Framework | Node.js + Express |
| Database | MongoDB (via Mongoose) |
| Authentication | JWT + OTP + bcrypt |
| Deployment | Vercel (frontend) |

---

## 📁 Project Structure

```text
OnlineVotingSystem-Frontend/
│
├── src/
│   ├── pages/
│   │   ├── admin/         # Admin portal pages
│   │   ├── voter/         # Voter portal pages
│   │   └── party/         # Party portal pages
│   ├── components/        # Shared UI components
│   ├── context/           # Auth context and role management
│   └── utils/             # Axios config, helpers
│
├── backend/
│   └── online-voting-backend/
│       ├── routes/        # API route definitions
│       ├── controllers/   # Route logic
│       ├── models/        # Mongoose models
│       ├── middleware/     # JWT auth middleware
│       └── server.js
│
├── public/
├── index.html
├── package.json
├── tailwind.config.js
├── vercel.json
└── vite.config.js
```

---

## 🚀 Getting Started

### Prerequisites

- Node.js (v18+)
- MongoDB (local or Atlas)

### Clone the Repository

```bash
git clone https://github.com/Ranshchettri/VotingSystem.git
cd VotingSystem
```

### Run Frontend

```bash
npm install
npm run dev
```

Runs at: `http://localhost:5173`

### Run Backend

```bash
cd backend/online-voting-backend
npm install
npm run dev
```

Runs at: `http://localhost:5000`

---

## ⚙️ Backend Environment

Create `backend/online-voting-backend/.env`:

```env
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
ADMIN_EMAIL=admin@example.com
ADMIN_PASSWORD=your_admin_password
SMTP_HOST=smtp.example.com
SMTP_PORT=587
SMTP_USER=your_email
SMTP_PASS=your_password
```

---

## 🔐 Authentication & Security

| Feature | Status |
|---|---|
| JWT token validation middleware | ✅ |
| OTP login flow | ✅ |
| bcrypt password hashing | ✅ |
| Role-based route guards (frontend) | ✅ |
| URL manipulation protection | ✅ |

### How JWT Works in this Project

- After OTP verification, server issues a signed JWT
- Token is stored in `localStorage` on the client
- All protected API calls send the token via `Authorization: Bearer <token>` header
- Backend middleware validates the token and extracts the role on every request

---

## 🛡️ Role Access Rules

| Role | Allowed Routes |
|---|---|
| Admin | `/admin/*` only |
| Voter | `/voter/*` only |
| Party | `/party/*` only |

Any attempt to access a route outside your role will safely redirect to the login page.

---

## 🧭 System Workflow

```
User → Landing Page → Select Role Portal
     → Login with Credentials + OTP
     → JWT Token Issued
     → Role Dashboard Loaded
     → API calls via Axios with JWT Header
     → MongoDB stores all critical data
```

---

## 🔮 Future Enhancements

- National-level deployment infrastructure
- Mobile app version (React Native)
- Biometric identity verification
- Blockchain vote integrity layer
- AI-based fraud detection system
- Full cloud deployment with auto-scaling

---

## 📄 License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.

---

## 👨‍💻 Author

**Ransh Chettri**

- GitHub: [Ranshchettri](https://github.com/Ranshchettri)
- LinkedIn: [ransh-chettri-852386315](https://www.linkedin.com/in/ransh-chettri-852386315)

⭐ If this project helps you, consider starring the repository.
