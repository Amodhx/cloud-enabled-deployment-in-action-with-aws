# 🌩️ Cloud Enabled Deployment In Action with AWS & GCP

This repository demonstrates a **cloud-enabled microservices architecture** deployed with **AWS** and **GCP**.

It contains **four projects**:

- **course-service** (Spring Boot + MySQL + AWS/GCP integration)
- **student-service** (Spring Boot + MongoDB + AWS integration)
- **media-service** (Spring Boot + Local file storage, can be extended to AWS S3 / MinIO)
- **frontend-app** (React + TypeScript + MUI + Axios + Vite)

---

## 📂 Projects Overview

### 1. course-service
- **Entity:** `Course(id, name, duration)`
- **Endpoints:**
    - `GET /courses`
    - `GET /courses/{id}`
    - `POST /courses`
    - `DELETE /courses/{id}`
- **Default port:** `8081`
- **Database:** MySQL (Cloud-enabled with AWS RDS and GCP Cloud SQL)

### 2. student-service
- **Document:** `Student(registrationNumber, fullName, address, contact, email)`
- **Endpoints:**
    - `GET /students`
    - `GET /students/{id}`
    - `POST /students`
    - `DELETE /students/{id}`
- **Default port:** `8082`
- **Database:** MongoDB (Cloud-enabled with AWS DocumentDB)

### 3. media-service
- **Resource:** Files
- **Endpoints:**
    - `POST /files` (upload, multipart/form-data: file)
    - `GET /files` (list all files)
    - `GET /files/{id}` (fetch file)
    - `DELETE /files/{id}` (delete file)
- **Default port:** `8083`
- **Storage:** Local disk at `./data/media` (can be overridden with env var `MEDIA_STORAGE_DIR`).  
  Extendable to **AWS S3** or **MinIO**.

### 4. frontend-app
- **Stack:** React + TypeScript + MUI + Axios + Vite
- **Sections:** Courses, Students, Media
- **Scripts:**
    - `npm install`
    - `npm run dev` → Start Vite dev server
    - `npm run build` → Build production-ready app
    - `npm run preview` → Preview production build

---

## ⚙️ Build & Run

### Backend Services
At repo root:
```bash
mvn -q -e -DskipTests package
