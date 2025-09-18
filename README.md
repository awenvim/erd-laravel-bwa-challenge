<p align="center">
    <a href="https://laravel.com" target="_blank">
        <img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400" alt="Laravel Logo">
    </a>
</p>

# 🧩 ERD Laravel - Car Wash Booking Challenge

Proyek ini dibuat untuk memenuhi challenge perancangan **Entity Relationship Diagram (ERD)** dan pembuatan **migrasi database** menggunakan Laravel 12.  
Belum ada fitur atau fungsi lain yang diimplementasikan — hanya fokus pada desain struktur database.

## 📌 Tujuan

- Mendesain ERD untuk sistem pemesanan cuci mobil.
- Membuat file migrasi Laravel untuk setiap entitas berikut:
  - `users`
  - `car_washes`
  - `services`
  - `bookings`
  - `booking_service` (pivot table)

## 📊 Struktur ERD

**Relasi antar entitas:**
- `users` memiliki banyak `bookings`
- `car_washes` memiliki banyak `bookings`
- `bookings` milik `users` dan `car_washes`
- `bookings` memiliki banyak `services` melalui `booking_service`
- `services` memiliki banyak `bookings` melalui `booking_service`

**Skema tabel singkat:**

| Tabel             | Kolom Utama                                               |
|-------------------|-------------------------------------------------------------|
| users              | id, name, email, password, phone                            |
| car_washes         | id, name, address, phone                                    |
| services            | id, name, description, price                                |
| bookings            | id, user_id, car_wash_id, booking_date, total_price, status |
| booking_service     | id, booking_id, service_id                                 |

## ⚙️ Cara Menjalankan (untuk testing migrasi)

1. Clone repository ini
2. Install dependencies:

   ```bash
   composer install
