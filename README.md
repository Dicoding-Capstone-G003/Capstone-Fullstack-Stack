# Capstone Fullstack Stack

Folder ini berisi copy dari `Backend-Capstone` dan `Frontend-Capstone` yang sudah disatukan ke dalam satu stack Docker Compose.

## Struktur

- `backend/`: copy dari backend FastAPI
- `frontend/`: copy dari frontend static dashboard
- `docker-compose.yml`: menjalankan dua container dalam satu stack
- `.env`: konfigurasi port dan lokasi database SQLite

## Menjalankan

```powershell
docker compose up --build
```

## Akses

- Frontend: `http://localhost:8012`
- Backend API: `http://localhost:8010`
- Health check backend: `http://localhost:8010/health`

Frontend di-stack ini sudah diarahkan ke backend lokal lewat proxy Nginx `/api`, jadi tidak lagi memakai endpoint remote.
