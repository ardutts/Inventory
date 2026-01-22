# Inventaris Pro - Sistem Manajemen Stok & User

Project ini dikembangkan sebagai bagian dari tes praktik seleksi Web Developer di **PT Multiartha Prima Sejahtera**. Aplikasi ini berfokus pada efisiensi pengelolaan stok barang dan kontrol akses pengguna.

## 🚀 Fitur Utama
- **Dashboard Overview**: Ringkasan data sistem.
- **Manajemen Inventaris**: Pengelolaan stok dengan validasi otomatis (mencegah stok minus).
- **Manajemen User (ACL)**: Pengaturan role (Admin, Seller, User) dengan fitur perubahan massal (Bulk Action).
- **Responsive UI**: Menggunakan Tailwind CSS untuk tampilan yang optimal di berbagai perangkat.

## 🛠️ Cara Instalasi & Setup Lokal

### Prasyarat
- PHP >= 8.2
- Composer
- MySQL 
- Node.js & NPM 

### Langkah-langkah
1. **Clone Repository**
   ```bash
   git clone [https://github.com/username-anda/inventaris-pro.git](https://github.com/ardutts/inventory)
   cd inventory

2. **Install Depencies**
    composer install
    npm install && npm run build

3. Konfigurasi Environment Salin file .env.example menjadi .env
   cp .env.example .env


4. Generate App Key
   php artisan key:generate

5. Migrate & Seed Menjalankan migrasi tabel dan mengisi data awal (role & admin default).
   php artisan migrate --seed

6. Jalankan Server
   php artisan serve

6. Akun Login Default (Testing)
  Email: aryadutasatriaa@gmail.com

  Password: password123
   

   
