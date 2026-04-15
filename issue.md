# Planning Aplikasi Backend (ElysiaJS + Drizzle + MySQL)

Dokumen ini berisi high-level requirement untuk membangun aplikasi backend. 

## 1. Setup & Konfigurasi
- Pastikan project berjalan lancar menggunakan `bun run dev`.
- Konfigurasikan koneksi database MySQL menggunakan `drizzle-orm` dan `mysql2`.
- Buat file `.env` untuk menyimpan konfigurasi koneksi database (URL, username, password, dll).
- Lakukan setup Drizzle Kit (`drizzle.config.ts`) untuk mempermudah proses migrasi database.

## 2. Struktur Database (Schema)
- Definisikan tabel-tabel utama yang diperlukan di file schema (misalnya di folder `src/db/schema.ts`).
- Simpan konfigurasi database MySQL sehingga instance Drizzle siap di-inject ke berbagai endpoint. 
- Buat script npm/bun untuk menjalankan `drizzle-kit generate` dan `drizzle-kit push`/`migrate`.

## 3. Pembuatan API Endpoints (ElysiaJS)
- Buat instance aplikasi ElysiaJS.
- Definisikan routes API (RESTful) untuk entitas utama. Minimal mencakup operasi CRUD:
  - **GET**: Mengambil data.
  - **POST**: Menyimpan data baru.
  - **PUT/PATCH**: Memodifikasi data yang ada.
  - **DELETE**: Menghapus data.
- Hubungkan setiap endpoint tersebut dengan fungsi database (Drizzle Queries) untuk membaca/menulis ke MySQL.

## 4. Struktur Folder & Kode
- Buat pemisahan kode secara logis (contoh: `src/routes`, `src/controllers`, `src/db`).
- Gunakan tipe data TypeScript yang disediakan/dihasilkan oleh ElysiaJS maupun Drizzle agar semuanya *type-safe*.

---
**Catatan untuk Developer/AI Model:** 
- Silakan jabarkan detail schema database berdasarkan kebutuhan spesifik nantinya.
- Jangan terlalu banyak boilerplate, jaga agar kode tetap simpel dan mudah dibaca.
