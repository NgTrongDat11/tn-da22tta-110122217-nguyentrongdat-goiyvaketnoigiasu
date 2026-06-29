<div align="center">

# LUMIN

### Hệ thống gợi ý và kết nối gia sư theo hướng kết hợp

[![Python](https://img.shields.io/badge/Python-3.12+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com)
[![React](https://img.shields.io/badge/React-19-61DAFB?style=for-the-badge&logo=react&logoColor=black)](https://react.dev)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-16-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)](https://postgresql.org)
[![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)](https://docker.com)

</div>

---

## Thông tin đồ án

| | |
|:---|:---|
| **Đề tài** | Hệ thống gợi ý và kết nối gia sư theo hướng kết hợp |
| **Sinh viên thực hiện** | Nguyễn Trọng Đạt |
| **MSSV** | 110122217 |
| **Lớp** | DA22TTA |
| **Giảng viên hướng dẫn** | ThS. Võ Thành C |
| **Trường** | Đại học Trà Vinh |

---

## Mục tiêu đồ án

Xây dựng hệ thống **Lumin** — nền tảng kết nối học viên với gia sư/lớp học, tích hợp trí tuệ nhân tạo (AI) để gợi ý gia sư phù hợp nhất với nhu cầu học tập của từng học viên.

### Tính năng chính

| Tính năng | Mô tả |
|:---|:---|
| **Gợi ý gia sư thông minh** | Sử dụng Google Gemini AI kết hợp thuật toán matching để đề xuất gia sư phù hợp |
| **Quản lý gia sư** | Đăng ký, xác minh trình độ, quản lý hồ sơ và lịch dạy |
| **Quản lý học viên** | Tạo nhu cầu học tập, xem gợi ý, gửi yêu cầu kết nối |
| **Quản lý lịch học** | Hỗ trợ lớp 1-1, lớp nhóm, theo dõi buổi học |
| **Thanh toán trực tuyến** | Tích hợp SePay cho thanh toán qua QR Banking |
| **Đánh giá gia sư** | Hệ thống đánh giá sau buổi học |
| **Nhắn tin trực tiếp** | Chat giữa học viên và gia sư |
| **Thông báo** | Hệ thống thông báo realtime |

---

## Công nghệ sử dụng

| Thành phần | Công nghệ | Phiên bản |
|:---|:---|:---|
| **Frontend** | React, TypeScript, Vite, TailwindCSS | 19, 6.0, 8.0, 4.3 |
| **Backend** | Python, FastAPI, SQLAlchemy (async), Alembic | 3.12+, 0.115+, 2.0+ |
| **Database** | PostgreSQL | 16 |
| **AI** | Google Gemini | gemini-2.5-flash |
| **Embedding** | Gemini Embedding | gemini-embedding-001 |
| **Storage** | Supabase Storage (S3-compatible) | — |
| **Payment** | SePay (QR Banking) | — |
| **Containerization** | Docker, Docker Compose | — |
| **Package Manager** | uv (Python), npm (Node.js) | — |

---

## Cấu trúc thư mục

```
tn-da22tta-110122217-nguyentrongdat-goiyvaketnoigiasu/
│
├── docs/                                           # Tài liệu đồ án
│   ├── KhoaLuan_NguyenTrongDat_110122217.docx      #   Quyển đồ án (.docx)
│   ├── KhoaLuan_NguyenTrongDat_110122217.pdf       #   Quyển đồ án (.pdf)
│   ├── NguyenTrongDat.pptx                         #   Slide bảo vệ
│   ├── TrongDatPoster.pdf                          #   Poster giới thiệu (A1)
│   └── HUONG_DAN_SU_DUNG.md                       #   Hướng dẫn sử dụng
│
├── src/                                            # Mã nguồn
│   ├── backend/                                    #   Backend API (FastAPI)
│   │   ├── app/                                    #     Application code
│   │   │   ├── api/v1/                             #       REST API endpoints
│   │   │   ├── core/                               #       Cấu hình, bảo mật
│   │   │   ├── db/                                 #       Database session
│   │   │   ├── models/                             #       SQLAlchemy models
│   │   │   ├── schemas/                            #       Pydantic schemas
│   │   │   ├── services/                           #       Business logic & AI
│   │   │   └── tests/                              #       Unit tests
│   │   ├── alembic/                                #     Database migrations
│   │   ├── .env.example                            #     Biến môi trường mẫu
│   │   └── pyproject.toml                          #     Python dependencies
│   │
│   ├── frontend/                                   #   Frontend (React + Vite)
│   │   ├── src/                                    #     Source code
│   │   │   ├── components/                         #       UI components
│   │   │   ├── pages/                              #       Page components
│   │   │   ├── services/                           #       API service layer
│   │   │   ├── hooks/                              #       Custom React hooks
│   │   │   └── utils/                              #       Utility functions
│   │   ├── package.json                            #     Node.js dependencies
│   │   └── vite.config.ts                          #     Vite configuration
│   │
│   ├── database/                                   #   Cơ sở dữ liệu
│   │   ├── schema.sql                              #     Database schema
│   │   ├── schema-powerdesigner.sql                #     Schema (PowerDesigner)
│   │   └── seed/                                   #     Dữ liệu demo
│   │
│   └── docker-compose.yml                          #   Docker Compose config
│
└── README.md                                       # Giới thiệu đồ án
```

---

## Hướng dẫn cài đặt & chạy chương trình

### Yêu cầu phần mềm

| Phần mềm | Phiên bản |
|:---|:---|
| [Python](https://python.org) | 3.12+ |
| [Node.js](https://nodejs.org) | 18+ |
| [Docker](https://docker.com) & Docker Compose | Mới nhất |
| [uv](https://docs.astral.sh/uv/) | Mới nhất |

### Bước 1: Clone repository

```bash
git clone https://github.com/NgTrongDat11/tn-da22tta-110122217-nguyentrongdat-goiyvaketnoigiasu.git
cd tn-da22tta-110122217-nguyentrongdat-goiyvaketnoigiasu
```

### Bước 2: Khởi động Database (PostgreSQL)

```bash
cd src
docker compose up -d
```

### Bước 3: Cấu hình & chạy Backend

```bash
cd src/backend
cp .env.example .env
# Chỉnh sửa file .env với thông tin cấu hình phù hợp
uv sync --extra dev
uv run uvicorn app.main:app --reload --port 8001
```

### Bước 4: Cài đặt & chạy Frontend

```bash
cd src/frontend
npm install
npm run dev
```

### Truy cập ứng dụng

| Dịch vụ | URL |
|:---|:---|
| **Ứng dụng web** | http://localhost:5173 |
| **API Docs (Swagger)** | http://localhost:8001/docs |
| **Health Check** | http://localhost:8001/api/v1/health |

> Xem hướng dẫn chi tiết hơn tại [docs/HUONG_DAN_SU_DUNG.md](docs/HUONG_DAN_SU_DUNG.md)

---

## Triển khai

| Thành phần | Phương thức triển khai |
|:---|:---|
| **Backend** | VPS với Docker hoặc trực tiếp bằng uvicorn |
| **Frontend** | Vercel (cấu hình `src/frontend/vercel.json`) |
| **Database** | PostgreSQL qua Docker Compose hoặc Supabase (cloud) |

---

## Liên hệ

| | |
|:---|:---|
| **Sinh viên** | Nguyễn Trọng Đạt |
| **MSSV** | 110122217 |
| **GitHub** | [NgTrongDat11](https://github.com/NgTrongDat11) |

---

<div align="center">

**© 2025 Nguyễn Trọng Đạt — Đại học Trà Vinh**

</div>
