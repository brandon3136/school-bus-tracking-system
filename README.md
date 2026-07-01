# SafeRoute School Bus Tracking System

SafeRoute is a full-stack school bus tracking platform designed for parents, drivers, and school administrators. It provides live bus location tracking, geofence-based arrival alerts, emergency notifications, and role-based dashboards in one unified system.

## Project Overview

This project consists of:

- A Next.js frontend for parents, drivers, and administrators
- An Express + TypeScript backend API
- A MySQL database schema for routes, buses, students, trips, alerts, and push subscriptions
- Real-time communication using Socket.IO for live bus updates
- Web push notifications for proximity alerts

## Features

- Real-time bus tracking on an interactive map
- Role-based dashboards for parents, drivers, and admins
- Route and bus management
- Student boarding and trip history
- Geofence-based arrival notifications
- Emergency alert reporting
- Web push notification support
- Secure authentication with JWT and cookie-based sessions

## Tech Stack

### Frontend

- Next.js 16
- React 19
- TypeScript
- Tailwind CSS
- Leaflet.js
- Socket.IO client
- Lucide icons

### Backend

- Node.js + Express
- TypeScript
- MySQL
- Socket.IO
- JWT authentication
- Web Push API
- Nodemailer

## Project Structure

```text
school-bus-tracking-system/
├── saferoute-backend/
│   ├── src/
│   │   ├── controllers/
│   │   ├── routes/
│   │   ├── services/
│   │   ├── socket/
│   │   └── types/
│   ├── schema.sql
│   └── package.json
├── school-bus-tracker/
│   ├── src/
│   │   ├── app/
│   │   ├── components/
│   │   ├── hooks/
│   │   └── lib/
│   └── package.json
└── render.yaml
```

## Prerequisites

Make sure you have the following installed:

- Node.js 20+
- npm or yarn
- MySQL 8+

## Backend Setup

1. Navigate to the backend folder:

```bash
cd saferoute-backend
```

2. Install dependencies:

```bash
npm install
```

3. Create a MySQL database and import the schema:

```bash
mysql -u root -p
```

Then run:

```sql
CREATE DATABASE saferoute;
USE saferoute;
SOURCE schema.sql;
```

4. Create a `.env` file in the backend folder with values similar to:

```env
PORT=4000
NODE_ENV=development
FRONTEND_URL=http://localhost:3000

DB_HOST=localhost
DB_PORT=3306
DB_USER=root
DB_PASSWORD=your_password
DB_NAME=saferoute

JWT_SECRET=your_jwt_secret
JWT_EXPIRES_IN=7d

SMTP_HOST=smtp.gmail.com
SMTP_PORT=587
SMTP_SECURE=false
SMTP_USER=your_email
SMTP_PASSWORD=your_app_password
EMAIL_FROM=your_email

VAPID_PUBLIC_KEY=your_vapid_public_key
VAPID_PRIVATE_KEY=your_vapid_private_key
VAPID_EMAIL=mailto:your_email
```

5. Start the backend:

```bash
npm run dev
```

The API will be available at:

```text
http://localhost:4000
```

## Frontend Setup

1. Navigate to the frontend folder:

```bash
cd school-bus-tracker
```

2. Install dependencies:

```bash
npm install
```

3. Start the app:

```bash
npm run dev
```

The frontend will be available at:

```text
http://localhost:3000
```

## Default Demo Accounts

The database seed data includes sample users:

- Admin: admin@school.tz
- Driver: driver@school.tz
- Parent: parent@school.tz

Default password for all seeded accounts:

```text
password123
```

## Deployment

This project includes a Render deployment configuration in [render.yaml](render.yaml). The backend is configured to run in Docker.

## Notes

- The backend exposes a health check endpoint at `/health`
- The main API routes are grouped under `/api`
- Real-time updates are handled through Socket.IO

## License

This project is for academic/final-year project use.
