# Capstone Fullstack Stack

Folder ini berisi copy dari `Backend-Capstone` dan `Frontend-Capstone` yang sudah disatukan ke dalam satu stack Docker Compose.

## Struktur

- `backend/`: copy dari backend FastAPI
- `frontend/`: copy dari frontend static dashboard
- `docker-compose.yml`: menjalankan dua container dalam satu stack
- `.env`: konfigurasi port dan lokasi database SQLite

## Akses Default

- Frontend: `http://localhost:8012`
- Backend API: `http://localhost:8010`
- Backend health check: `http://localhost:8010/health`
- Demo produk live: [https://db10-g003.my.id/](https://db10-g003.my.id/)

Frontend di-stack ini sudah diarahkan ke backend lokal lewat proxy Nginx `/api`, jadi tidak lagi memakai endpoint remote.

## Menjalankan di Docker Desktop Windows

### Prasyarat

- Docker Desktop sudah terpasang dan status engine `Running`
- Terminal berada di folder project ini

### Jalankan stack

```powershell
cd C:\Users\dawwi\Desktop\Dicoding\Capstone-Fullstack-Stack
docker compose up --build
```

### Jalankan di background

```powershell
docker compose up -d --build
```

### Hentikan stack

```powershell
docker compose down
```

### Lihat log

```powershell
docker compose logs -f
```

## Menjalankan di Linux

### Prasyarat

- Docker Engine sudah terpasang
- Docker Compose plugin tersedia
- User Anda bisa menjalankan `docker` tanpa masalah permission

### Jalankan stack

```bash
cd /path/to/Capstone-Fullstack-Stack
docker compose up --build
```

### Jalankan di background

```bash
docker compose up -d --build
```

### Hentikan stack

```bash
docker compose down
```

### Lihat log

```bash
docker compose logs -f
```

## Menjalankan dengan Podman

Project ini juga bisa dijalankan dengan Podman selama fitur compose tersedia di environment Anda.

### Opsi 1: `podman compose`

```bash
cd /path/to/Capstone-Fullstack-Stack
podman compose up --build
```

### Opsi 2: `podman-compose`

Jika sistem Anda memakai paket `podman-compose`, gunakan:

```bash
cd /path/to/Capstone-Fullstack-Stack
podman-compose up --build
```

### Jalankan di background

```bash
podman compose up -d --build
```

Atau jika memakai `podman-compose`:

```bash
podman-compose up -d --build
```

### Hentikan stack

```bash
podman compose down
```

Atau:

```bash
podman-compose down
```

## Konfigurasi Environment

File [.env](C:\Users\dawwi\Desktop\Dicoding\Capstone-Fullstack-Stack\.env) berisi konfigurasi utama:

```env
BACKEND_PORT=8010
FRONTEND_PORT=8012
DATABASE_URL=sqlite:////data/solar_telemetry.db
```

Jika ingin mengganti port, ubah nilai `BACKEND_PORT` dan `FRONTEND_PORT`, lalu jalankan ulang stack.
