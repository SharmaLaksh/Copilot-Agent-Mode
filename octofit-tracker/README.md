# OctoFit Tracker

A modern multi-tier fitness tracking application built with React 19 + Vite (frontend), Node.js + Express + TypeScript (backend), and MongoDB (database).

## Project Structure

```
octofit-tracker/
├── frontend/           # React 19 + Vite SPA
│   ├── src/
│   ├── package.json
│   ├── vite.config.js
│   └── .env
├── backend/            # Node.js + Express + TypeScript API
│   ├── src/
│   │   └── server.ts
│   ├── package.json
│   ├── tsconfig.json
│   └── .env
├── docker-compose.yml  # MongoDB setup
└── .gitignore
```

## Technology Stack

### Frontend
- **React 19** - UI framework
- **Vite** - Build tool and dev server
- **Node.js** - Runtime

### Backend
- **Node.js** - Runtime
- **Express.js** - Web framework
- **TypeScript** - Type-safe JavaScript
- **Mongoose** - MongoDB object modeling
- **CORS** - Cross-origin resource sharing

### Database
- **MongoDB** - NoSQL database

## Ports Configuration

| Service | Port | URL |
|---------|------|-----|
| Frontend (Vite) | 5173 | http://localhost:5173 |
| Backend API | 8000 | http://localhost:8000 |
| MongoDB | 27017 | mongodb://localhost:27017 |

## Prerequisites

- Node.js 16+ and npm
- Docker and Docker Compose (for MongoDB)

## Setup Instructions

### 1. Start MongoDB

From the `octofit-tracker` directory:

```bash
docker-compose up -d
```

Verify MongoDB is running:
```bash
docker-compose ps
```

### 2. Install and Run Frontend

```bash
cd frontend
npm install  # Already done
npm run dev
```

The frontend will start at **http://localhost:5173**

### 3. Install and Run Backend

```bash
cd backend
npm install  # Already done
npm run dev
```

The backend will start at **http://localhost:8000**

## Development Workflow

### Frontend Development
```bash
cd frontend
npm run dev      # Start dev server
npm run build    # Build for production
npm run preview  # Preview production build
```

### Backend Development
```bash
cd backend
npm run dev      # Start with nodemon (auto-reload)
npm run build    # Compile TypeScript
npm run start    # Run compiled code
```

## Environment Variables

### Frontend (.env)
```
VITE_API_URL=http://localhost:8000/api
```

### Backend (.env)
```
PORT=8000
MONGODB_URI=mongodb://localhost:27017/octofit-tracker
NODE_ENV=development
CORS_ORIGIN=http://localhost:5173
```

## API Health Check

Once both services are running, test the backend:

```bash
curl http://localhost:8000/api/health
```

Expected response:
```json
{
  "status": "ok",
  "message": "OctoFit Tracker Backend is running",
  "timestamp": "2024-06-08T..."
}
```

## Stopping Services

### Stop MongoDB
```bash
docker-compose down
```

### Stop Frontend/Backend
Press `Ctrl+C` in the respective terminal windows.

## Next Steps

1. Define Mongoose models for fitness data
2. Implement API routes and controllers
3. Create React components and pages
4. Add authentication (JWT)
5. Implement data persistence layer
6. Add error handling and logging
7. Deploy to production

## License

ISC
