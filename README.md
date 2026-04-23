# Batik Sesa Bojonegoro — Business Management App

> A comprehensive cross-platform business management application for Batik Sesa Bojonegoro — featuring financial tracking, fabric and raw material inventory, employee payroll, and transaction management.

---

## Table of Contents

- [English Version](#english-version)
  - [Overview](#overview)
  - [Features](#features)
  - [Tech Stack](#tech-stack)
  - [Project Structure](#project-structure)
  - [Getting Started](#getting-started)
  - [Configuration](#configuration)
  - [Application Flow](#application-flow)
- [Versi Indonesia](#versi-indonesia)
  - [Gambaran Umum](#gambaran-umum)
  - [Fitur Utama](#fitur-utama)
  - [Teknologi yang Digunakan](#teknologi-yang-digunakan)
  - [Struktur Proyek](#struktur-proyek)
  - [Cara Memulai](#cara-memulai)
  - [Konfigurasi](#konfigurasi)
  - [Alur Aplikasi](#alur-aplikasi)

---

## English Version

### Overview

**Batik Sesa Bojonegoro App** is a Flutter-based mobile and desktop business management system designed specifically to handle the daily operations of a Batik business. The app provides a complete financial and operational management solution, including income (penerimaan) tracking, fabric (kain) and raw material inventory, employee management, and payroll.

The application is backed by **Firebase Realtime Database**, uses **Flutter Riverpod** for reactive state management, and supports multiple platforms: Android, iOS, Web, Windows, macOS, and Linux — with a responsive UI that adapts to various screen sizes.

### Features

#### Dashboard
- Real-time financial overview showing total income (penerimaan) and total transactions.
- Monthly transaction growth calculation and comparison.
- Quick menu navigation (Raw Materials, Fabric List, Necessities, Employees).
- Recent transaction timeline with quick actions (View detail, Edit, Delete).

#### Penerimaan (Revenue / Income)
- Record product sales and transactions with quantity, unit, price, and total amount.
- Detailed bottom sheet views for transaction details.
- Full CRUD capabilities for financial records.
- Real-time data syncing from Firebase.

#### Inventori Kain & Bahan Baku (Fabric & Material Inventory)
- Comprehensive fabric catalog with categories (Katun, Sutra, Dobby, Rayon).
- Advanced filtering by search query, category, width, and measurement unit.
- Manage raw materials (Bahan Baku) and general necessities (Daftar Keperluan).
- Automated database seeding for default fabric price lists.

#### Karyawan & Gaji (Employee & Payroll Management)
- Manage employee roster with search and status filtering (active/inactive).
- Record and track employee salaries (Gaji) and compensations.
- Real-time data streams for seamless HR management.

#### Settings & Security
- App-wide PIN-based security lock with enable/disable toggles.
- Secure PIN change and reset functionality (Default PIN: `123456`).
- Encrypted local state storage.

### Tech Stack

| Layer | Technology |
|---|---|
| Framework | Flutter (Dart SDK ^3.8.1) |
| State Management | Flutter Riverpod 2.6.1 |
| Backend / Database | Firebase Realtime Database 12.0.0 |
| Core Backend | Firebase Core 4.0.0 |
| Local Storage | Shared Preferences 2.5.3 |
| Navigation | Persistent Bottom Nav Bar 6.2.1 |
| UI / Components | Month Picker Dialog 6.3.0, Loading Animation Widget 1.3.0 |
| Internationalization | Intl 0.20.2 |
| Icons | Heroicons 0.11.0, Iconsax 0.0.8, Cupertino Icons |
| Security | Crypto 3.0.6 |

### Project Structure

```text
batik-sesa-bojonegoro-app/
├── lib/
│   ├── main.dart                         # App entry point
│   ├── firebase_options.dart             # Firebase configuration file
│   ├── core/
│   │   ├── model/                        # Data models (Penerimaan, Kain, Karyawan, Gaji, dll)
│   │   ├── provider/                     # Riverpod providers for state management
│   │   └── repository/                   # Firebase CRUD repositories
│   ├── screens/                          # UI Screens
│   │   ├── dashboard/                    # Dashboard, Add/Edit Penerimaan
│   │   ├── ...                           # Other feature screens
│   └── widgets/                          # Reusable UI components
├── assets/
│   ├── img/logo-app.png
│   ├── icon/icon_app.png
│   └── font/Sriwedari.ttf
├── android/ ios/ web/ windows/ macos/ linux/
├── pubspec.yaml
└── firebase.json
```

### Getting Started

#### Prerequisites
- Flutter SDK >= 3.8.1
- Dart SDK ^3.8.1
- A Firebase project with Realtime Database enabled

#### Installation
1. **Clone the repository**
   ```bash
   git clone https://github.com/your-username/batik-sesa-bojonegoro-app.git
   cd batik-sesa-bojonegoro-app
   ```
2. **Install dependencies**
   ```bash
   flutter pub get
   ```
3. **Run the app**
   ```bash
   flutter run
   ```

### Configuration

#### Firebase Database Rules
Ensure your Firebase Realtime Database rules allow read/write access for your environment:
```json
{
  "rules": {
    ".read": true,
    ".write": true
  }
}
```
*(Note: Secure these rules properly before moving to production).*

#### PIN Security
- Default PIN: `123456`
- Users can activate, change, or reset the PIN via the Quick Settings menu on the Dashboard.

### Application Flow

```text
App Launch
    └── PIN Screen (if enabled)
            └── Main App (Bottom Navigation)
                    ├── Dashboard
                    │     ├── Settings (Top Right Menu -> Manage PIN)
                    │     ├── Add Penerimaan (Revenue)
                    │     ├── Detail / Edit / Delete Penerimaan
                    │     └── Quick Menus (Bahan Baku, Kain, Keperluan, Karyawan)
                    ├── Daftar Kain (Fabric Inventory)
                    │     └── Filter by Category / Unit / Search
                    ├── Bahan Baku / Keperluan
                    └── Karyawan (Employees)
                          └── Employee Management & Payroll (Gaji)
```

---

## Versi Indonesia

### Gambaran Umum

**Batik Sesa Bojonegoro App** adalah aplikasi manajemen bisnis berbasis Flutter yang dirancang khusus untuk menangani operasional harian usaha Batik Sesa Bojonegoro. Aplikasi ini menyediakan solusi manajemen operasional dan keuangan yang lengkap, mencakup pencatatan pemasukan (penerimaan), manajemen inventaris kain dan bahan baku, hingga pengelolaan data dan gaji karyawan.

Aplikasi ini didukung oleh **Firebase Realtime Database**, menggunakan **Flutter Riverpod** untuk *state management* yang reaktif, dan mendukung berbagai platform: Android, iOS, Web, Windows, macOS, dan Linux — dengan antarmuka yang responsif untuk berbagai ukuran layar.

### Fitur Utama

#### Dashboard
- Ringkasan keuangan *real-time* yang menampilkan total penerimaan dan total transaksi.
- Perhitungan pertumbuhan transaksi (persentase) dibandingkan bulan sebelumnya.
- Menu Cepat (Bahan Baku, Daftar Kain, Daftar Keperluan, Karyawan).
- Timeline penerimaan terakhir dengan aksi cepat (Lihat Detail, Edit, Hapus).

#### Penerimaan (Pemasukan)
- Catat transaksi penjualan dengan informasi kuantitas, satuan, harga, dan total.
- Tampilan *bottom sheet* informatif untuk melihat detail setiap transaksi.
- Fitur lengkap CRUD (Tambah, Baca, Perbarui, Hapus) untuk data keuangan.
- Sinkronisasi data seketika (*real-time*) dengan Firebase.

#### Inventori Kain & Bahan Baku
- Katalog kain yang lengkap beserta kategorinya (Katun, Sutra, Dobby, Rayon).
- Pencarian dan filter cerdas berdasarkan kategori, lebar kain, dan satuan.
- Pengelolaan bahan baku penunjang dan daftar keperluan produksi.
- *Seeding* data otomatis untuk memasukkan daftar harga kain bawaan ke *database*.

#### Karyawan & Gaji
- Kelola daftar karyawan dengan fitur pencarian dan filter status (aktif/non-aktif).
- Catat dan pantau pembayaran gaji / honor karyawan.
- Pembaruan data otomatis (*stream*) untuk mempermudah HR.

#### Pengaturan & Keamanan
- Sistem keamanan berbasis PIN untuk membatasi akses aplikasi.
- Fitur pengaturan PIN lengkap (Aktifkan/Nonaktifkan, Ubah PIN, Reset PIN).
- **PIN Default: 123456**.

### Teknologi yang Digunakan

| Lapisan | Teknologi |
|---|---|
| Framework | Flutter (Dart SDK ^3.8.1) |
| State Management | Flutter Riverpod 2.6.1 |
| Backend / Database | Firebase Realtime Database 12.0.0 |
| Core Backend | Firebase Core 4.0.0 |
| Penyimpanan Lokal | Shared Preferences 2.5.3 |
| Navigasi | Persistent Bottom Nav Bar 6.2.1 |
| UI / Komponen | Month Picker Dialog 6.3.0, Loading Animation Widget 1.3.0 |
| Internasionalisasi | Intl 0.20.2 |
| Ikon | Heroicons 0.11.0, Iconsax 0.0.8, Cupertino Icons |
| Keamanan & Kriptografi | Crypto 3.0.6 |

### Struktur Proyek

```text
batik-sesa-bojonegoro-app/
├── lib/
│   ├── main.dart                         # Titik masuk aplikasi
│   ├── firebase_options.dart             # Konfigurasi proyek Firebase
│   ├── core/
│   │   ├── model/                        # Model data (Penerimaan, Kain, Karyawan, Gaji, dll)
│   │   ├── provider/                     # Riverpod providers untuk state management
│   │   └── repository/                   # Repository CRUD Firebase
│   ├── screens/                          # Layar antarmuka (UI)
│   │   ├── dashboard/                    # Dashboard, Tambah/Edit Penerimaan
│   │   ├── ...                           # Layar fitur lainnya
│   └── widgets/                          # Komponen UI yang dapat digunakan kembali
├── assets/
│   ├── img/logo-app.png
│   ├── icon/icon_app.png
│   └── font/Sriwedari.ttf
├── android/ ios/ web/ windows/ macos/ linux/
├── pubspec.yaml
└── firebase.json
```

### Cara Memulai

#### Prasyarat
- Flutter SDK >= 3.8.1
- Dart SDK ^3.8.1
- Proyek Firebase dengan fitur Realtime Database yang sudah diaktifkan

#### Instalasi
1. **Clone repositori**
   ```bash
   git clone https://github.com/your-username/batik-sesa-bojonegoro-app.git
   cd batik-sesa-bojonegoro-app
   ```
2. **Install dependensi**
   ```bash
   flutter pub get
   ```
3. **Jalankan aplikasi**
   ```bash
   flutter run
   ```

### Konfigurasi

#### Aturan Firebase Database
Pastikan aturan (*rules*) Firebase Realtime Database Anda mengizinkan operasi baca/tulis:
```json
{
  "rules": {
    ".read": true,
    ".write": true
  }
}
```
*(Catatan: Amankan aturan ini sebelum aplikasi dirilis ke tahap produksi).*

#### Keamanan PIN
- PIN Default: `123456`
- Pengguna dapat mengaktifkan, mengubah, atau mereset PIN melalui menu Pengaturan di pojok kanan atas Dashboard.
