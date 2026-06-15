# Tarkeswor Dentist - Deployment Guide

## Quick Start (Railway.app - Recommended)

1. Go to [railway.app](https://railway.app) and sign up/login
2. Create a new project → Deploy from GitHub / Upload folder
3. Upload this entire folder
4. Add a PostgreSQL plugin from Railway dashboard
5. Railway auto-sets DATABASE_URL from the plugin
6. Set `PORT` environment variable (Railway sets it automatically)
7. Set the start command: `node dist/index.mjs`
8. Deploy! Your site will be live in minutes.

## Manual Server Deployment (VPS / Render / Fly.io)

### Requirements
- Node.js 18+
- PostgreSQL database

### Environment Variables
Create a `.env` file (or set in your hosting dashboard):
```
DATABASE_URL=postgresql://user:password@host:5432/dbname
PORT=3000
```

### Setup
```bash
npm install
node dist/index.mjs
```

The server starts on the port specified in `PORT` (default: 8080).
Visit: `http://localhost:PORT/`

## Admin Panel
- URL: `http://your-domain/admin.html`
- Password: `123456`

## What's Included

```
├── dist/              # Pre-built API server (Express + all routes)
├── public/            # Pre-built frontend (HTML, CSS, JS, images)
│   ├── index.html     # Main website
│   ├── admin.html     # Admin panel
│   ├── appointment.html
│   ├── team.html
│   ├── service.html
│   ├── blog.html
│   └── ...
├── package.json
└── DEPLOY.md
```

## Database Schema
The app auto-creates tables and seeds default dental content on first run.

## Vercel Deployment (Frontend Only)
For Vercel, deploy only the `public/` folder:
1. Upload the `public/` folder to Vercel
2. Set the root directory to `public`
3. Note: API features (booking, dynamic content) require the full server

## Support
- Admin Password: `123456`
- WhatsApp number can be changed in Admin → Site Settings → WhatsApp Number
