# Task Manager API

REST API for managing users and tasks built with **Node.js**, **Express**, and **MongoDB (Mongoose)**. Uses **JWT** authentication and includes email helpers (Mailgun).

## Tech

- Express API server (`app.js`)
- MongoDB via Mongoose (`db/mongoose.js`)
- JWT auth middleware (`middlewares/`)
- File upload tooling (`multer`, `sharp`) where used by routes/controllers
- Email notifications via Mailgun (`emails/account.js`)

## Prerequisites

- Node.js (LTS recommended)
- MongoDB connection string
- (Optional) Mailgun API key + domain for emails

## Setup

1. Install dependencies:

```bash
npm install
```

2. Create a `.env` file in this folder (same level as `app.js`) with:

| Variable | Purpose |
|----------|---------|
| `PORT` | Port to listen on (required by `app.js`) |
| `MONGOOSE` | MongoDB connection URI used by `db/mongoose.js` |
| `JWT_SECRET` | JWT signing/verification secret |
| `MAILAPI` | Mailgun API key (optional; required to send emails) |
| `MAILDOMAIN` | Mailgun domain (optional; required to send emails) |

3. Start the server:

```bash
npm start
```

API routes are mounted under:

- `/user`
- `/task`

## Project layout

| Path | Role |
|------|------|
| `app.js` | Express app entry and route mounting |
| `db/mongoose.js` | MongoDB connection |
| `routes/` | Route definitions |
| `controllers/` | Route handlers |
| `models/` | Mongoose models |
| `middlewares/` | Auth and request middleware |
| `emails/account.js` | Mailgun email helpers |
| `utils/` | Shared helpers (uploads, async wrappers, etc.) |
