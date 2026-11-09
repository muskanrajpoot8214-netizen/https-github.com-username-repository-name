# BookEase — Month 3 Industry Project

A full-stack accommodation booking project based on the supplied Month 3 internship brief.

## Quick start (Windows PowerShell)

### Requirements
Install Node.js 18+ and MongoDB Community Server (or create a MongoDB Atlas database).

### 1. Start backend
```powershell
cd backend
Copy-Item .env.example .env
```
Open `backend/.env` and set a unique `JWT_SECRET` (32+ random characters) and your MongoDB URI. Then:
```powershell
npm install
npm run seed
npm run dev
```
Backend health check: `http://localhost:5000/api/health`

Demo admin account created by seed:
- Email: `admin@bookease.test`
- Password: `ChangeMe123!`
Change this password and remove/disable the demo account before any public deployment.

### 2. Start frontend (new PowerShell window)
```powershell
cd frontend
Copy-Item .env.example .env
npm install
npm run dev
```
Open the Vite URL shown (normally `http://localhost:5173`).

### 3. Use the app
Register a guest account, select dates, select a property and confirm a reservation. The frontend loads real listings from the API (seed script inserts six). Use My bookings to view saved bookings.

## Project layout
- `frontend/` React + Vite + React Router + Axios UI.
- `backend/` Express REST API, MongoDB/Mongoose, auth, business logic.
- `docs/` architecture, database/API and security documentation.
- `postman/BookEase.postman_collection.json` API request collection.

## Important commands
```powershell
# backend
npm run dev
npm run seed
# frontend
npm run dev
npm run build
```

## Testing the API
Import `postman/BookEase.postman_collection.json` into Postman. Run health, register/login, list properties and booking calls. Set `token` and `propertyId` collection variables from responses.

## Deliverables & honest scope
Included: system architecture, database schemas, REST API design, React UI, Express backend, JWT authentication, bcrypt hashing, role/ownership middleware, booking date/capacity/overlap checks, seed data, Postman collection, README and security policy.

Still required before production: add automated integration tests and verify them against your own MongoDB; add a transaction/locking mechanism for booking race conditions; real payment, email verification, password reset, provider/admin dashboards, cloud image storage, monitoring, backups and deploy to a hosting provider. No real payment or live hotel inventory is connected.
