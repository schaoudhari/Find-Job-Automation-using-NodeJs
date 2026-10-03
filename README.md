# Job Application Automation — Full Stack

This archive contains the completed backend and frontend.

## Structure

- `backend/` — NestJS API, Firebase/Firestore, Apps Script/Sheets sync, job discovery, enrichment, deduplication, AI matching, Gmail draft creation, browser preparation, scheduler.
- `frontend/` — React + Vite + Material UI dashboard.

## Before first run

### Backend

1. Copy `.env.example` to `.env`.
2. Put your Firebase Admin service account at `backend/credentials/firebase.json`.
3. Add your existing Google Apps Script URL and Sheet ID.
4. Optionally configure OpenAI, Gmail OAuth, scheduler and source company lists.

Then:

```bash
cd backend
npm install
npm run build
npm run start:dev
```

API: `http://localhost:4000`

### Frontend

```bash
cd frontend
npm install
npm run dev
```

Dashboard: `http://localhost:5173`

Copy `frontend/.env.example` to `frontend/.env` if the API is not on `http://localhost:4000`.

## Important behavior

- Gmail integration creates drafts only; it never sends email.
- Browser automation prepares/fills forms but does not submit applications.
- Deterministic job filtering runs before AI matching.
- Firestore ingestion is duplicate-aware.
- The scheduler is disabled unless `JOB_SCHEDULER_ENABLED=true`.
- Firebase credentials and `.env` are intentionally excluded from the archive. Restore your own local credentials/configuration.

## Main API areas

- `/jobs`
- `/job-discovery`
- `/ai`
- `/email`
- `/applications`
- `/browser`
- `/automation`
- `/sheets`
- `/health`
