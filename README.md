    # Meeting Action Items Tracker

A full-stack web app for turning meeting transcripts into actionable tasks. Paste a meeting transcript, get a structured list of action items (task, owner, due date) powered by an LLM, then manage them with tags, completion status, and transcript history.

---

## Deployed URLs

The frontend and backend were originally pushed to **separate GitHub repositories** and are **hosted separately**:

| App       | Deployed URL |
|----------|--------------|
| **Frontend** | [https://meeting-frontend-topaz.vercel.app](https://meeting-frontend-topaz.vercel.app/) |
| **Backend**  | [https://meeting-backend-khru.onrender.com](https://meeting-backend-khru.onrender.com) |

To use the live app, set the frontend’s API base URL (e.g. `VITE_API_URL`) to the backend URL above when building or in your hosting env vars.

---

## What This App Does

- **Paste a meeting transcript** (plain text).
- **Get a list of action items** — task, owner (if mentioned), due date (if found) — extracted via an LLM.
- **Edit, add, and delete** action items and **mark items as done**.
- **See a short history** of the last few transcripts.
- **Extras:** filters (open/done), tags, delete transcripts, and an Insights tab with aggregate stats.

---

## Repository Layout

This repo contains both the frontend and backend in one workspace:

```
Meeting tracker AI/
├── README.md          # This file (overview + links to sub-projects)
├── backend/           # Express API + Prisma + Groq LLM
│   └── README.md      # Backend setup, API reference, deployment
└── frontend/          # React app
    ├── README.md      # Frontend overview
    └── meeting/       # Vite + React app
        └── README.md  # Frontend setup, env, UI description
```

**Note:** Frontend and backend were initially developed and pushed as **separate GitHub repos** and are **deployed separately** (see [Deployed URLs](#deployed-urls) above). This parent folder is a combined view; for detailed setup and API docs, use the READMEs inside `backend/` and `frontend/` (or `frontend/meeting/`).

---

## Tech Stack

| Layer    | Stack |
|----------|--------|
| **Frontend** | React 19, TypeScript, Vite 7, Tailwind CSS 4 |
| **Backend**  | Node.js, Express 5, PostgreSQL (Prisma), Groq (Llama) for extraction |

---

## Quick Start (Local)

### 1. Backend

```bash
cd backend
npm install
# Create .env with DATABASE_URL, LLM_API_KEY, CORS_ORIGIN, PORT (see backend/.env.example)
npx prisma migrate deploy
npm run dev
```

Runs at `http://localhost:4000` by default. See [backend/README.md](backend/README.md) for full setup and API reference.

### 2. Frontend

```bash
cd frontend/meeting
npm install
# Optional: .env with VITE_API_URL=http://localhost:4000
npm run dev
```

Open [http://localhost:5173](http://localhost:5173). See [frontend/meeting/README.md](frontend/meeting/README.md) for env and UI details.

---

## Documentation

- **[backend/README.md](backend/README.md)** — Backend setup, environment variables, API reference, project structure.
- **[frontend/README.md](frontend/README.md)** — Frontend overview and structure.
- **[frontend/meeting/README.md](frontend/meeting/README.md)** — Frontend app setup, env, API contract, Workspace & Insights UI.

---

## License

ISC
