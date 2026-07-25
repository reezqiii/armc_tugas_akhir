# ARMC — Access Request Management Control

Sistem manajemen hak akses pengguna berbasis web yang menerapkan metode **Role-Based Access Control (RBAC)** untuk mendigitalisasi proses pengajuan akun, persetujuan berjenjang, hingga pengelolaan pengguna pada sistem internal perusahaan.

Project ini dikembangkan sebagai **Proyek Akhir (Tugas Akhir)** Program Studi Teknik Informatika, Politeknik Negeri Batam, dengan judul:

**"Pengembangan Fitur Manajemen Hak Akses Pengguna Pada Sistem Internal Perusahaan Dengan Metode Role-Based Access Control (RBAC)"** — Studi Kasus PT. XYZ

## Deskripsi Umum

Sebelumnya, proses manajemen hak akses di perusahaan masih dilakukan secara manual melalui formulir kertas dan persetujuan berlapis, sehingga rawan menimbulkan kesalahan manusia (*human error*) dan pemberian akses yang berlebihan (*over-privilege*).

ARMC hadir sebagai solusi digital yang mengatur hak akses pengguna berdasarkan **peran (role)**, bukan secara individual, sehingga proses pemberian akses menjadi lebih terstruktur, efisien, transparan, dan aman.

## Aktor / Role Pengguna

| Role | Deskripsi |
|---|---|
| **Requestor** | Perwakilan departemen yang mengajukan permintaan pembuatan akun baru atau perubahan hak akses |
| **Head of Department Requestor** | Menyetujui/menolak request tingkat pertama (*first approval*) untuk stafnya |
| **Head of Department IT** | Memberikan verifikasi akhir (*final approval*) sebelum akun dieksekusi |
| **Administrator** | Mengeksekusi & mengelola akun, role, project, permission, department, dan position |

## Fitur Utama

- Autentikasi (login/logout) berbasis role
- Pengajuan request akun baru / perubahan hak akses (Requestor)
- Persetujuan berjenjang (Head of Department Requestor → Head of Department IT)
- Catatan penolakan pada setiap tahap approval
- Manajemen Akun Pengguna, Role, Project, Permission, Department, dan Position (Administrator)
- Reset password pengguna
- Export data akun pengguna ke Excel
- Audit log aktivitas untuk transparansi proses

## Tech Stack

| Layer | Teknologi |
|---|---|
| **Frontend** | [Next.js](https://nextjs.org/) (React) |
| **Backend** | [NestJS](https://nestjs.com/) (Node.js + TypeScript) |
| **Database** | [PostgreSQL](https://www.postgresql.org/) |
| **Containerization** | Docker |
| **CI/CD** | GitLab CI |

## Struktur Repository

```
armc_tugas_akhir/
├── armc-backend/     # REST API service (NestJS + PostgreSQL)
└── armc_frontend/    # Web application (Next.js)
```

## Installation & Setup Guide

### Prasyarat
- Node.js (LTS)
- PostgreSQL
- npm

### 1. Clone repository
```bash
git clone https://github.com/reezqiii/armc_tugas_akhir.git
cd armc_tugas_akhir
```

### 2. Setup Backend
```bash
cd armc-backend
npm install
```
Buat file `.env` di dalam folder `armc-backend` berisi konfigurasi database PostgreSQL dan variabel environment lain sesuai kebutuhan (lihat `.env.development` sebagai referensi format).

Jalankan backend:
```bash
npm run start:dev
```

### 3. Setup Frontend
```bash
cd ../armc_frontend
npm install
```
Buat file `.env` di dalam folder `armc_frontend` berisi variabel seperti URL API backend (lihat `.env.development` sebagai referensi format).

Jalankan frontend:
```bash
npm run dev
```

### 4. Akses Aplikasi
Buka browser dan akses `http://localhost:3000` (sesuaikan port jika berbeda).

## Pengujian

Sistem telah melalui **User Acceptance Testing (UAT)** dengan 42 skenario pengujian fungsional, dan seluruhnya dinyatakan **Pass**, membuktikan alur persetujuan dan manajemen akun berjalan sesuai spesifikasi.

## Metode Pengembangan

Project ini dikembangkan menggunakan metode **Agile (Scrum)**, dengan tahapan: Product Backlog → Sprint Planning → Sprint → Review, secara iteratif sesuai kebutuhan yang berkembang selama pengembangan.

## Kontributor / Pengembang

- **Rizqi Vela Syifa** — 3312301013 — Teknik Informatika, Politeknik Negeri Batam

## Lisensi

Project ini dibuat untuk keperluan akademik (Proyek Akhir/Tugas Akhir) dan studi kasus internal perusahaan (PT. XYZ — nama disamarkan).
