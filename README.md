# Bhakti Q&A Website

A peaceful, spiritual Question-Answer platform built with React, Node.js, and PostgreSQL.

## Features
- **Glassmorphism UI**: Beautiful, calm aesthetic with bubble animations.
- **Q&A System**: Ask questions, give answers, and earn points.
- **Rewards Gallery**: Redeem points for devotional photos, audio, and videos.
- **Authentication**: Secure signup/login with JWT.
- **Admin Dashboard**: Manage questions, rewards, and users.

## Tech Stack
- **Frontend**: React, Tailwind CSS, Framer Motion, Lucide React
- **Backend**: Node.js, Express, Sequelize, PostgreSQL
- **Deployment**: Ready for Render (Monorepo structure)

## Setup Instructions

### Prerequisites
- Node.js installed
- PostgreSQL installed and running

### 1. Database Setup
Create a PostgreSQL database named `bhakti_qa` (or update `.env` with your own DB URL).

### 2. Server Setup
```bash
cd server
npm install
# Update .env file with your DB credentials
npm start
```
The server runs on port 5000. It will automatically create tables on first run.

### 3. Client Setup
```bash
cd client
npm install
npm run dev
```
The client runs on port 5173 (default Vite port).

## Deployment to Render
1. Create a new Web Service on Render.
2. Connect your repository.
3. Set **Build Command**: `cd client && npm install && npm run build && cd ../server && npm install`
4. Set **Start Command**: `cd server && npm start`
5. Add Environment Variables:
   - `DATABASE_URL`: Your Render PostgreSQL URL
   - `JWT_SECRET`: A secure random string
   - `NODE_ENV`: `production`

## Admin Access
To make a user an admin, you can manually update the `role` column in the `Users` table to `'admin'` using a DB tool like pgAdmin or DBeaver.
