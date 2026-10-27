# Getting Started

## Prerequisites

- Python 3.11+
- Node.js and npm
- Docker with Docker Compose
- `uv` or `pip`
- A Gemini API key, or a reachable Ollama installation

## 1. Database services

From the repository root:

```bash
docker compose up -d
```

This starts PostgreSQL on `5432`, pgAdmin on `5050`, and Adminer on `8088` using the development defaults in `docker-compose.yml`.

## 2. Backend

```bash
cd backend
cp .env.example .env
uv pip install -r requirements.txt
uv run uvicorn app:app --reload --port 8001
```

Configure at minimum:

```dotenv
JWT_SECRET=replace-with-a-long-random-value
DATABASE_URL=postgresql+asyncpg://postgres:password123@localhost:5432/cambo_ai
DEFAULT_PROVIDER=gemini
GEMINI_API_KEY=your-key
```

Swagger UI: <http://localhost:8001/docs>

## 3. User workspace

```bash
cd frontend
npm install
npm run dev
```

Open <http://localhost:5173>.

## 4. Admin portal

```bash
cd admin-site
npm install
npm run dev
```

Open <http://localhost:5174>.

## 5. Public website

```bash
cd public-sastra
npm install
npm run dev
```

Open <http://localhost:5175>.

## Validation

```bash
cd backend && uv run pytest -q
cd ../frontend && npm run build && npm run lint
cd ../admin-site && npm run build
cd ../public-sastra && npm run build
```

Do not deploy the development passwords, permissive settings, or local JSON data. Review [[Security and Privacy]] first.

