# Inventory Management System

A full-stack inventory management application with a FastAPI backend, PostgreSQL database, and Vue 3 frontend.

## Features

- User registration and JWT login/logout
- Product CRUD with SKU uniqueness
- Category CRUD with product relationship protection
- Dashboard statistics for products, categories, units, low stock, and inventory value
- Docker Compose setup for PostgreSQL, backend, and frontend

## Tech stack

| Layer | Technology |
| --- | --- |
| Backend | FastAPI, SQLAlchemy 2, Alembic, Pydantic, JWT |
| Database | PostgreSQL |
| Frontend | Vue 3, Vite, Pinia, Vue Router, Tailwind CSS |
| Runtime | Docker Compose |

## Project structure

```text
backend/
  app/
    api/routes/
    core/
    db/
    models/
    schemas/
  alembic/
frontend/
  src/
    api/
    layouts/
    router/
    stores/
    views/
docker-compose.yml
.env.example
```

## Run with Docker

1. Copy the example environment file:

   ```powershell
   Copy-Item .env.example .env
   ```

2. Start the application:

   ```powershell
   docker compose up --build
   ```

3. Open:

   - Frontend: http://localhost:5173
   - Backend API docs: http://localhost:8000/docs
   - PostgreSQL: localhost:5433 by default, configurable with `POSTGRES_PORT`

4. Create a user through the API:

   ```powershell
   curl -X POST http://localhost:8000/api/auth/register `
     -H "Content-Type: application/json" `
     -d "{\"email\":\"admin@example.com\",\"full_name\":\"Admin User\",\"password\":\"password123\"}"
   ```

Then sign in from the frontend with `admin@example.com` and `password123`.

## Backend development

From `backend\`:

```powershell
pip install -e .[dev]
alembic upgrade head
fastapi dev app/main.py
```

Required environment variables:

- `DATABASE_URL`
- `JWT_SECRET_KEY`

## Frontend development

From `frontend\`:

```powershell
npm install
npm run dev
```

Set `VITE_API_BASE_URL` if the API is not running at `http://localhost:8000`.

## API endpoints

- `POST /api/auth/register`
- `POST /api/auth/login`
- `GET /api/auth/me`
- `GET|POST /api/categories`
- `GET|PUT|DELETE /api/categories/{id}`
- `GET|POST /api/products`
- `GET|PUT|DELETE /api/products/{id}`
- `GET /api/dashboard/stats`

## Project checklist

- [x] Scaffold project folders and top-level configuration
- [x] Implement backend settings, database, models, migrations, auth, and REST APIs
- [x] Implement frontend routing, state management, login, dashboard, products, and categories
- [x] Add Dockerfiles and Docker Compose
- [x] Add setup and usage documentation
