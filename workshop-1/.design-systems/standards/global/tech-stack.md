# Tech Stack

This documents the technical stack for the Farm Company Equipment CRM Dashboard, reconciled to a Python/FastAPI backend.

## Framework & Runtime
- **Application Framework:** FastAPI
- **Language/Runtime:** Python
- **Package Manager:** uv

## Frontend
- **JavaScript Framework:** React, Next.js
- **CSS Framework:** Tailwind CSS
- **UI Components:** Material UI (MUI)

## Database & Storage
- **Database (dev / CI / production):** PostgreSQL
- **Database (tests / lightweight local):** SQLite — file-based or in-memory, zero setup, for fast isolated tests
- **ORM/Query Builder:** SQLAlchemy or SQLModel (Python ORM) — same models work on both engines
- **Migrations:** Alembic — set `render_as_batch=True` so `ALTER TABLE`-style changes also run on SQLite
- **Caching:** None for now

> **SQLite usage notes:** SQLite runs the same SQLAlchemy models and Alembic
> migrations as PostgreSQL. With FastAPI, pass
> `connect_args={"check_same_thread": False}` on the SQLite engine. Avoid (or
> guard per-dialect) Postgres-only types such as `JSONB` and array columns in
> shared models to prevent drift between the test database and production.

## Testing & Quality
- **Backend Tests:** pytest
- **End-to-End Tests:** Playwright
- **Linting/Formatting (frontend):** ESLint, Prettier

## Deployment & Infrastructure
- **Frontend Hosting:** Vercel (Next.js)
- **Backend Hosting:** Python-capable host (e.g., Railway or Render) for the long-running FastAPI API
- **CI/CD:** GitHub Actions

## Third-Party Services
- **Authentication:** Auth.js
- **Email:** Resend
- **Monitoring:** Sentry