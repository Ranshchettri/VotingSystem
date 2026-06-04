# Nepal Online Voting System 🇳🇵  
 
Nepal Online Voting System is a full-stack, multi-portal election platform built for secure and transparent digital voting workflows.

This project includes separate experiences for:
- 👨‍💼 Admin (election control and monitoring)
- 🗳️ Voter (identity verification and voting)
- 🏛️ Party (profile, performance, and campaign data)

It is designed so that core election operations run through backend APIs and MongoDB, with role-based access control and auditable data flow.

## ✨ What This System Does

- Manage election lifecycle: create, run, end, results
- Register and manage voters and political parties
- Allow voter login with OTP + face verification step (demo flow)
- Track live election stats and party analytics
- Publish notifications and election updates across portals
- Export election reports for admin operations

## 🧱 Tech Stack

- **Frontend:** React + Vite + React Router + Axios
- **Backend:** Node.js + Express + Mongoose
- **Database:** MongoDB
- **Auth/Security:** JWT + OTP + bcrypt

## 🔐 Authentication & Security

### JWT Protection (Already Implemented) ✅
Yes, this project already uses JWT-based protection in backend and role-aware route guards in frontend.

### Why JWT helps
- Stateless auth token for secure API calls
- Fast role validation (`admin`, `voter`, `party`)
- Better route/API authorization control
- Easy expiration and session handling support

### Current implementation highlights
- JWT token validation middleware in backend
- OTP flow for admin/party/voter login
- bcrypt password hashing
- Role-based portal protection against URL manipulation

## 🛡️ Role Access Rules

- Admin can access only `/admin/*`
- Voter can access only `/voter/*`
- Party can access only `/party/*`
- Invalid role route access gets redirected safely

## 🗄️ Data Storage

- Election, voter, party, vote, analytics, and notification data are stored in **MongoDB**
- `localStorage` is used for session/token context only
- Party image data (logo, team photos, gallery) is currently stored as image data URLs in MongoDB party records

## 🧭 System Workflow (High Level)

1. User opens landing page and chooses role portal
2. Login starts with credential + OTP verification
3. JWT token issued after verification
4. User enters role dashboard
5. All critical data is fetched/saved through backend APIs
6. MongoDB remains the source of truth

## 🚀 Local Development

### Frontend
```bash
npm install
npm run dev
```

### Backend
```bash
cd backend/online-voting-backend
npm install
npm run dev
```

## ⚙️ Backend Environment

Set required values in `backend/online-voting-backend/.env`:
- `MONGO_URI`
- `JWT_SECRET`
- `ADMIN_EMAIL`
- `ADMIN_PASSWORD`
- SMTP fields (if email sending is enabled)

## 📁 Useful Docs

- `DIAGRAMS.md`
- `docs/SYSTEM_DIAGRAMS.md`

## 🧪 Build

```bash
npm run build
```

## 🔮 Future Enhancements

- National Level Implementation
- Mobile App Version
- Biometric Verification
- Blockchain Full Integration
- AI-based Fraud Detection
- Cloud Deployment

## 🎯 Project Goal

Deliver a production-ready style election platform architecture that can be scaled from local/demo operation to national-level digital governance workflows.
