# Tugas Rutin 9 - Setup Laravel

**Nama:** Harun Rayp Aritonang
**NIM:** 4252550004
**Kelas:** PSIK 25A
**Kampus:** Universitas Negeri Medan

Project setup Laravel 13 dengan 3 route custom (`/`, `/about`, `/contact`), view Blade, data dinamis dari controller, dan koneksi database MySQL.

## Requirement
- PHP 8.3+
- Composer
- MySQL (Laragon)

## Langkah Install
1. Install Composer dan Laragon.
2. Buat project:
```bash
   composer create-project laravel/laravel TugasWeb-P9-LaravelSetup
   cd TugasWeb-P9-LaravelSetup
```
3. Buat database `laravel_p9` di phpMyAdmin.
4. Konfigurasi `.env`:
```env
   DB_CONNECTION=mysql
   DB_HOST=127.0.0.1
   DB_PORT=3306
   DB_DATABASE=laravel_p9
   DB_USERNAME=root
   DB_PASSWORD=
```
5. Jalankan migrasi:
```bash
   php artisan migrate
```
6. Jalankan server:
```bash
   php artisan serve
```
   Buka `http://127.0.0.1:8000`.

### Clone dari repo ini
```bash
git clone https://github.com/USERNAME/TugasWeb-P9-LaravelSetup.git
cd TugasWeb-P9-LaravelSetup
composer install
cp .env.example .env
php artisan key:generate
```
Lalu atur `.env` seperti langkah 4 dan jalankan `php artisan migrate`.

## Perintah Artisan yang Dipakai
```bash
php artisan make:controller PageController
php artisan make:model Mahasiswa -m
```

## Route
| URL | Keterangan |
|-----|------------|
| `/` | Home, menampilkan data dinamis (judul + hobi) |
| `/about` | Identitas mahasiswa |
| `/contact` | Email dan WhatsApp |
| `/hello/{nama}` | Bonus: route parameter |

## Struktur Folder
| Folder / File | Fungsi |
|---------------|--------|
| `app/Http/Controllers` | Logika controller (`PageController`) |
| `app/Models` | Model Eloquent (`Mahasiswa`) |
| `routes/web.php` | Definisi route web |
| `resources/views` | File Blade (tampilan) |
| `database/migrations` | Skema tabel database |
| `public/` | Entry point (`index.php`) dan aset publik |
| `config/` | File konfigurasi aplikasi |
| `.env` | Konfigurasi environment (tidak di-commit) |
| `vendor/` | Dependensi Composer |

## Bonus
- Styling dengan Tailwind CSS via CDN (tema neubrutalism)
- Route parameter `/hello/{nama}`

## Screenshot
### Welcome Page
![Welcome](screenshots/welcome.png)
### Home
![Home](screenshots/home.png)
### About
![About](screenshots/about.png)
### Contact
![Contact](screenshots/contact.png)
### Hello
![Hello](screenshots/hello.png)
### Database (phpMyAdmin)
![Database](screenshots/database.png)
