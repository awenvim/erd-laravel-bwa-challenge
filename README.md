<p align="center">
    <a href="https://laravel.com" target="_blank">
        <img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400" alt="Laravel Logo">
    </a>
</p>

# 🧩 ERD Laravel — Car Wash Booking Challenge

Proyek ini dibuat untuk memenuhi challenge perancangan **Entity Relationship Diagram (ERD)** dan pembuatan **migrasi database** menggunakan Laravel 12.
Saat ini, proyek hanya berfokus pada desain struktur database dan belum memiliki fitur atau fungsi tambahan lainnya.

---

## 📌 Tujuan

* Mendesain ERD untuk sistem pemesanan cuci mobil.
* Membuat file migrasi Laravel untuk setiap entitas berikut:

  * `users`
  * `car_washes`
  * `services`
  * `bookings`
  * `booking_service` (pivot table)

---

## 📊 Struktur ERD

**Relasi antar entitas:**

* `users` memiliki banyak `bookings`
* `car_washes` memiliki banyak `bookings`
* `bookings` milik `users` dan `car_washes`
* `bookings` memiliki banyak `services` melalui `booking_service`
* `services` memiliki banyak `bookings` melalui `booking_service`

**Skema tabel singkat:**

| Tabel            | Kolom Utama                                                      |
| ---------------- | ---------------------------------------------------------------- |
| users            | id, name, email, password, phone                                 |
| car\_washes      | id, name, address, phone                                         |
| services         | id, name, description, price                                     |
| bookings         | id, user\_id, car\_wash\_id, booking\_date, total\_price, status |
| booking\_service | id, booking\_id, service\_id                                     |

---

## ⚙️ Cara Menjalankan Proyek (untuk pengujian migrasi)

1. Clone repository ini:

   ```bash
   git clone <url-repository>
   cd <nama-folder-repository>
   ```
2. Install dependencies dan buat file `.env`:

   ```bash
   composer install
   cp .env.example .env
   ```
3. Generate application key:

   ```bash
   php artisan key:generate
   ```
4. Jalankan migrasi database:

   ```bash
   php artisan migrate
   ```

---

## 📢 Catatan

Proyek ini hanya bertujuan untuk demonstrasi struktur database dan migrasi awal.
Belum ada implementasi logika bisnis, API, atau antarmuka pengguna.

