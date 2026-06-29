# Hướng dẫn sử dụng chương trình Lumin

## Yêu cầu hệ thống

| Phần mềm | Phiên bản tối thiểu |
|---|---|
| Python | 3.12+ |
| Node.js | 18+ |
| Docker & Docker Compose | Mới nhất |
| PostgreSQL | 16 (qua Docker) |
| uv (Python package manager) | Mới nhất |

## 1. Cài đặt và chạy bằng Docker (Khuyến nghị)

### Bước 1: Clone repository

```bash
git clone https://github.com/NgTrongDat11/tn-da22tta-110122217-nguyentrongdat-goiyvaketnoigiasu.git
cd tn-da22tta-110122217-nguyentrongdat-goiyvaketnoigiasu
```

### Bước 2: Khởi động PostgreSQL

```bash
cd src
docker compose up -d
```

Chờ container healthy (khoảng 10 giây), kiểm tra:

```bash
docker compose ps
```

### Bước 3: Cấu hình Backend

```bash
cd src/backend
cp .env.example .env
```

Mở file `.env` và cấu hình các biến môi trường:
- `DATABASE_URL`: Connection string PostgreSQL
- `JWT_SECRET_KEY`: Khóa bí mật JWT (tối thiểu 32 ký tự)
- `GEMINI_API_KEY`: API key Google Gemini (nếu muốn bật AI)
- Các biến S3/Supabase Storage (nếu cần upload file)
- Các biến SePay (nếu cần thanh toán)

### Bước 4: Chạy Backend

```bash
cd src/backend
uv sync --extra dev
uv run uvicorn app.main:app --reload --port 8001
```

Kiểm tra backend hoạt động: truy cập `http://localhost:8001/docs` để xem Swagger UI.

### Bước 5: Chạy Frontend

```bash
cd src/frontend
npm install
npm run dev
```

Truy cập ứng dụng tại: `http://localhost:5173`

## 2. Tài khoản demo

Sau khi khởi tạo database, có thể import dữ liệu demo:

```bash
psql -U postgres -d lumin -f src/database/seed/extra_demo_accounts.sql
```

## 3. API Documentation

- Swagger UI: `http://localhost:8001/docs`
- ReDoc: `http://localhost:8001/redoc`
- Health check: `GET /api/v1/health`

## 4. Kiểm tra (Testing)

### Backend

```bash
cd src/backend
$env:PYTHONPATH = "."   # Windows PowerShell
uv run pytest
```

### Frontend

```bash
cd src/frontend
npm run build
```

## 5. Triển khai Production

### Backend (VPS / Cloud)

1. Cài đặt Python 3.12+, uv, PostgreSQL
2. Clone repo và cấu hình `.env` với thông tin production
3. Chạy migration: `uv run alembic upgrade head`
4. Chạy server: `uv run uvicorn app.main:app --host 0.0.0.0 --port 8000`

### Frontend (Vercel)

1. Import project từ GitHub, chọn thư mục `src/frontend`
2. Cấu hình rewrites trong `vercel.json` với domain backend thật
3. Deploy
