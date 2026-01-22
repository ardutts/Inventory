Technical Test - Junior Fullstack Developer
Sistem Inventaris Pro & Role Management (RBAC)
Project ini dikembangkan untuk memenuhi tugas seleksi teknis di PT Multiartha Prima Sejahtera. Aplikasi ini mengintegrasikan sistem manajemen stok barang dengan kontrol akses pengguna berbasis peran (Role-Based Access Control) serta fitur monitoring aktivitas transaksi yang komprehensif.

🛠️ Stack Teknologi
Backend: Laravel 11

Database: MySQL (Relational)

Authentication: JWT (JSON Web Token)

Frontend: Blade Templating & Tailwind CSS

Reporting: DomPDF (Export Laporan PDF)

Tools: Composer, NPM, Git

🚀 Fitur Utama & Logika Bisnis
1. Keamanan & Akses (RBAC)
Sistem Autentikasi JWT: Mengamankan seluruh endpoint dan menjaga integritas data pengguna.

Role Management:

Admin: Kontrol penuh sistem, manajemen user, dan monitoring aktivitas global.

Seller: Manajemen stok etalase dan proses penjualan.

Pelanggan: Melakukan pembelian dan memantau riwayat pesanan.

Bulk Role Update: Fitur efisiensi bagi Admin untuk mengubah role banyak user sekaligus menggunakan checkbox (Bulk Action).

2. Manajemen Inventaris & Aktivitas
Dashboard Monitor: Admin dapat memantau secara real-time aktivitas Seller saat memasukkan produk ke etalase.

Smart Search: Fitur pencarian cepat di sisi Admin, Seller, maupun Pelanggan untuk mempermudah navigasi data barang.

Validation Logic: Sistem secara otomatis menolak transaksi jika stok kurang dari jumlah permintaan (Stock cannot be negative).

3. Transaksi & Riwayat (Audit Log)
Customer Journey: Pelanggan dapat melakukan pembelian barang secara langsung dan melihat Riwayat Pembelian pribadi.

Laporan Terintegrasi: Mencatat histori barang masuk (oleh Admin/Seller) dan barang keluar (terjual ke Customer).

Cetak Laporan PDF: Fitur ekspor laporan profesional yang mencakup:

Laporan Barang Masuk & Keluar.

Laporan Stok Inventaris saat ini.

Laporan Barang Terjual (Sales Report).

🏗️ Struktur Database (Relational)
Project ini menerapkan skema database relasional untuk menjamin konsistensi data:

roles: Master data peran pengguna.

users: Data pengguna dengan relasi role_id.

products: Data utama barang dan stok etalase.

transactions/histories: Mencatat log barang masuk, keluar, dan pembelian oleh customer.

⚙️ Instruksi Instalasi & Setup Lokal
1. Persiapan
Pastikan Anda sudah menginstall PHP >= 8.2, Composer, dan MySQL.

2. Clone Repository
Bash
git clone https://github.com/ardutts/inventory.git
cd inventory
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
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=tech_test
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
