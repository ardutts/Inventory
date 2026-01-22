# Technical Test - Junior Fullstack Developer
## Sistem Inventaris Pro & Role Management (RBAC)

Project ini dikembangkan untuk memenuhi tugas seleksi teknis di **PT Multiartha Prima Sejahtera**. Aplikasi ini mengintegrasikan sistem manajemen stok barang dengan kontrol akses pengguna berbasis peran (Role-Based Access Control).

---

## 🛠️ Stack Teknologi
- **Backend**: Laravel 11
- **Database**: MySQL (Relational)
- **Authentication**: JWT (JSON Web Token)
- **Frontend**: Blade Templating & Tailwind CSS
- **Tools**: Composer, NPM, Git

---

## 🚀 Fitur Utama & Logika Bisnis
1. **Sistem Autentikasi JWT**:
   - Mengamankan seluruh endpoint menggunakan middleware.
   - Token-based authentication untuk menjaga integritas data pengguna.
2. **Role-Based Access Control (RBAC)**:
   - **Admin**: Akses penuh (Manajemen User & Produk).
   - **Seller**: Melihat produk dan melakukan transaksi penjualan.
   - **Pelanggan**: Hanya melihat daftar produk.
3. **Manajemen Inventaris**:
   - **Validation Logic**: Sistem secara otomatis menolak transaksi jika stok kurang dari jumlah permintaan (`Stock cannot be negative`).
4. **Manajemen User**:
   - Admin dapat mengubah peran pengguna (Admin/Seller/Pelanggan) dengan validasi role yang tersedia di database.

---

## 🏗️ Struktur Database (Relational)
Project ini menggunakan skema database relasional dengan integrasi *Foreign Key*:
- `roles` (id, name): Menyimpan data statis peran.
- `users` (id, name, email, password, **role_id**): Relasi *belongsTo* ke tabel roles.
- `products` (id, name, stock, price, created_at): Menyimpan data inventaris.

---

## ⚙️ Instruksi Instalasi & Setup Lokal

### 1. Persiapan
Pastikan Anda sudah menginstall PHP >= 8.2, Composer, dan MySQL.

### 2. Clone Repository
```bash
git clone [https://github.com/ardutts/inventory.git](https://github.com/ardutts/inventory.git)
cd inventaris-pro-test
3. Install Dependencies
Bash
composer install
npm install && npm run build
4. Konfigurasi Environment
Salin file .env.example ke .env dan atur koneksi database Anda:

Bash
cp .env.example .env
Sesuaikan bagian:

Cuplikan kode
DB_DATABASE=nama_db_lo
DB_USERNAME=root
DB_PASSWORD=
5. Setup Database & JWT
Jalankan perintah ini untuk generate key, migrasi tabel, dan mengisi data awal (seeding):

Bash
php artisan key:generate
php artisan jwt:secret
php artisan migrate --seed
6. Jalankan Server
Bash
php artisan serve
Akses aplikasi di: http://127.0.0.1:8000
