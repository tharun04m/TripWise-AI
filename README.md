# TripWise AI

An India-focused budget travel recommendation and itinerary planning prototype. It uses a FastAPI REST API, SQLAlchemy database models, and a React/Vite interface.

## What it does

- Recommends curated destinations from a budget, duration, travel style, transport and stay preference.
- Shows transparent estimates for transport, accommodation, food, activities and miscellaneous costs.
- Generates a rule-based day-wise itinerary without needing a paid AI API.
- Exposes interactive API documentation at `/docs`.

All costs, travel suggestions, and activities are curated sample estimates, not live prices, availability, schedules, bookings, or safety information.

## Run locally (PowerShell)

```powershell
Copy-Item .env.example .env
python -m venv .venv
.\.venv\Scripts\Activate.ps1
pip install -r backend\requirements.txt
uvicorn app.main:app --app-dir backend --reload
```

In a second terminal:

```powershell
cd frontend
npm install
npm run dev
```

Open the frontend URL shown by Vite (normally `http://localhost:5173`). API docs are at `http://127.0.0.1:8000/docs`.

## MySQL

The project defaults to SQLite so it is runnable immediately. Create `tripwise_db` in MySQL, install `pymysql` (already included), and set `DATABASE_URL` in `.env` to the MySQL example in `.env.example`.

To populate a database explicitly, run:

```powershell
python scripts\seed_database.py
```

## Recommendation scoring

Score = budget fit (50%) + travel-style match (30%) + duration suitability (20%). It is explanatory only, not scientifically validated.
