# 03-PRE-MCC — Latihan Java Pre-Mini Coding Challenge

Repository ini berisi kumpulan modul latihan Java sebagai persiapan Mini Coding Challenge (MCC), mulai dari dasar pemrograman hingga proyek aplikasi konsol berbasis OOP.

---

## Daftar Isi

- [Tujuan](#tujuan)
- [Prasyarat](#prasyarat)
- [Cara Install & Menjalankan](#cara-install--menjalankan)
- [Struktur Proyek](#struktur-proyek)
- [Modul & Fitur](#modul--fitur)
  - [1. Java Fundamental](#1-javafundamental)
  - [2. Java OOP](#2-javaoop)
  - [3. Exam Pre-MCC — Kasir JB Burgers](#3-exampremcc--kasir-jb-burgers)
  - [4. Exam Fix Pre-MCC — Toko Fashion Online](#4-examfixpremcc--toko-fashion-online)
  - [5. Exam Project Pre-MCC — Manajemen Data Penjualan](#5-examprojectpremcc--manajemen-data-penjualan)
- [Konsep OOP yang Diterapkan](#konsep-oop-yang-diterapkan)
- [Penulis](#penulis)

---

## Tujuan

Proyek ini dibuat sebagai bahan latihan dan evaluasi kemampuan pemrograman Java, mencakup:

- Implementasi logika matematika dari nol tanpa library bawaan
- Penerapan 4 pilar OOP: **Abstraksi, Enkapsulasi, Pewarisan, Polimorfisme**
- Membangun aplikasi konsol yang terstruktur dan interaktif
- Simulasi studi kasus nyata: kasir restoran, toko online, dan sistem manajemen data

---

## Prasyarat

| Kebutuhan | Versi Minimum |
|-----------|---------------|
| Java JDK  | 8+            |
| NetBeans IDE *(opsional)* | 8.x+ |

Proyek ini adalah **NetBeans Java SE Project** (`build.xml` sudah tersedia), namun bisa dikompilasi dan dijalankan dari IDE atau terminal mana pun.

---

## Cara Install & Menjalankan

### Menggunakan NetBeans IDE

1. Clone atau download repository ini.
2. Buka NetBeans, pilih **File > Open Project**.
3. Arahkan ke folder repository, lalu klik **Open**.
4. Pilih package/modul yang ingin dijalankan (lihat bagian [Struktur Proyek](#struktur-proyek)).
5. Klik kanan pada file `MainProgram.java` di package yang diinginkan, pilih **Run File**.

### Menggunakan Terminal (tanpa IDE)

```bash
# Clone repository
git clone https://github.com/jakabrajadenta/mii-pre-mcc.git
cd mii-pre-mcc

# Kompilasi semua source
javac -d build/classes src/**/*.java

# Jalankan modul tertentu (pilih salah satu):
java -cp build/classes javafundamental.MainDasar
java -cp build/classes javaoop.MainOOP
java -cp build/classes examfixpremcc.MainProgram
java -cp build/classes examprojectpremcc.MainProgram
```

> **Catatan:** Untuk `examprojectpremcc`, pastikan file `database.txt` berada di direktori kerja saat program dijalankan.

---

## Struktur Proyek

```
mii-pre-mcc/
├── src/
│   ├── javafundamental/        # Modul 1: Operasi matematika dasar
│   ├── javaoop/                # Modul 2: Konsep OOP (Shape/Square/Rectangle)
│   ├── exampremcc/             # Modul 3: Kasir restoran JB Burgers
│   ├── examfixpremcc/          # Modul 4: Toko fashion online
│   └── examprojectpremcc/      # Modul 5: Manajemen data penjualan (CRUD)
├── database.txt                # Penyimpanan data penjualan (file-based)
├── build.xml                   # Konfigurasi build NetBeans/Ant
└── nbproject/                  # Konfigurasi proyek NetBeans
```

---

## Modul & Fitur

### 1. `javafundamental`

**File:** `src/javafundamental/MainDasar.java`

Implementasi ulang operasi matematika dasar **tanpa menggunakan operator bawaan** (kecuali penjumlahan dan pengurangan), bertujuan melatih logika rekursif dan iteratif.

| Fungsi | Deskripsi |
|--------|-----------|
| `penjumlahan(a, b)` | Menjumlahkan dua bilangan bulat |
| `perkalian(a, b)` | Mengalikan dengan penjumlahan berulang |
| `faktorial(a)` | Menghitung n! menggunakan perkalian iteratif |
| `modulus(x, y)` | Mencari sisa bagi dengan pengurangan berulang |
| `modulbagi(p, q)` | Modulus untuk bilangan desimal |
| `perpangkatan(a, b)` | Menghitung a^b menggunakan perkalian berulang |

**Contoh Output:**
```
a + b = 5 + 6 = 11
a * b = 5 * 6 = 30
a! = 5! = 120
modulus (42 , 11) = 9
hasil pangkat = 81
```

---

### 2. `javaoop`

**File:** `src/javaoop/MainOOP.java`

Demonstrasi 4 pilar OOP menggunakan studi kasus geometri bangun datar.

**Hierarki Kelas:**
```
Shape (abstract)
├── Square     (Persegi)
└── Rectangle  (Persegi Panjang)
```

**Fitur:**
- Menghitung dan menampilkan **luas** dan **keliling** persegi dan persegi panjang
- Mendukung pembaruan dimensi setelah objek dibuat (`setS`, `setP`, `setLbr`)
- Menggunakan abstract class dan method overriding

**Contoh Output:**
```
PERSEGI
L =  5 * 5  = 25
L =  4 * 5  = 20

PERSEGI PANJANG
L =  8 * 5  = 40
L = 2*(8+5) = 26
```

---

### 3. `exampremcc` — Kasir JB Burgers

**File:** `src/exampremcc/MainProgram.java`

Simulasi program kasir restoran cepat saji **JB Burgers** dengan menu makanan dan minuman berlevel.

**Menu Makanan:**
| Kode | Produk | Level | Harga |
|------|--------|-------|-------|
| — | Chicken Burger | 1 / 2 / 3 | Rp 5.000 / 5.500 / 6.000 |
| — | Beef Burger | 1 / 2 / 3 | Rp 7.000 / 7.500 / 8.000 |
| — | FF Normal | 1 / 2 | Rp 1.000 / 1.500 |
| — | FF Large | 1 / 2 | Rp 2.000 / 2.500 |

**Menu Minuman:**
| Produk | Ukuran | Harga |
|--------|--------|-------|
| Cola Blood (Strawberry) | Normal / Large | Rp 2.000 / 3.000 |
| Cola Goold (Lemon) | Normal / Large | Rp 2.000 / 3.000 |
| Juice Orange | Normal / Large | Rp 4.000 / 5.000 |
| Juice Dragon Fruits | Normal / Large | Rp 5.000 / 6.000 |

**Hierarki Kelas:**
```
Meals (abstract)
├── Foods (abstract)
│   ├── Burger
│   └── Fries
└── Drinks (abstract)
    ├── Cola
    └── Juice
```

---

### 4. `examfixpremcc` — Toko Fashion Online

**File:** `src/examfixpremcc/MainProgram.java`

Aplikasi belanja fashion berbasis konsol dengan sistem akun dan keranjang belanja.

**Fitur Utama:**
- **Login System** — autentikasi username & password dengan maksimal 3 percobaan
- **Tampilan Profil** — nama, alamat, saldo, dan kota
- **Katalog Produk** — 14 item fashion dengan kode unik
- **Keranjang Belanja** — tambah item menggunakan kode produk
- **Cek Saldo Real-time** — saldo berkurang setiap item ditambahkan
- **Checkout** — ringkasan belanja + biaya ongkir Rp 10.000
- **Reset Cart** — kosongkan keranjang dan kembalikan saldo

**Katalog Produk:**
| Kode | Produk | Harga |
|------|--------|-------|
| TS01 | White T-Shirt | Rp 25.000 |
| TS02 | Black T-Shirt | Rp 25.000 |
| PL01 | Blue Polo Shirt | Rp 40.000 |
| PL02 | Grey Polo Shirt | Rp 40.000 |
| ST01 | Flower Shirt | Rp 80.000 |
| ST02 | Splash Shirt | Rp 60.000 |
| JS07 | Black Jeans | Rp 100.000 |
| JS08 | Navi Jeans | Rp 115.000 |
| SW03 | Brown-line Sweater | Rp 75.000 |
| SW04 | Vintage Sweater | Rp 90.000 |
| JK11 | Army Jacket | Rp 155.000 |
| JK12 | Parka Jacket | Rp 135.000 |
| SH21 | Sport Shoes | Rp 115.000 |
| SH22 | Casual Shoes | Rp 90.000 |

**Default akun (hardcoded):** `username: a` / `password: a`

**Hierarki Kelas:**
```
Operation (abstract)
└── OperationSystem
    └── MenuProgram
Account
Address
```

---

### 5. `examprojectpremcc` — Manajemen Data Penjualan

**File:** `src/examprojectpremcc/MainProgram.java`

Aplikasi CRUD data penjualan berbasis file teks, lengkap dengan sistem login admin.

**Fitur Utama:**

| Menu | Fungsi |
|------|--------|
| 1. Show Sales Data | Menampilkan seluruh data dari `database.txt` dalam format tabel |
| 2. Find Sales Data | Mencari data berdasarkan kata kunci (case-insensitive, multi-keyword) |
| 3. Add Sales Data | Menambahkan entri penjualan baru ke file |
| 4. Remove Sales Data | Menghapus baris data berdasarkan nomor urut |
| 5. Exit | Keluar dari program |

**Format Data (`database.txt`):**
```
x,Nama Costumer,Nomor Telepon,Negara,Item Dibeli
```

**Contoh isi database:**
```
x,Roni Sumantri,628219988,Indonesia,T-Shirt
x,Ayu Chaeyang,109954321,Korea,Jackets
x,Rose Pink,720256789,France,Shoes
```

**Detail Teknis:**
- Penyimpanan: file teks `database.txt` (append mode untuk penambahan data)
- Penghapusan: menulis ulang ke file sementara `tempDB.txt`, lalu mengganti file asli
- Pencarian: mendukung beberapa kata kunci sekaligus (dipisah spasi)
- Login: maks. 3 percobaan sebelum program terhenti otomatis

**Default akun (hardcoded):** `username: a` / `password: a`

**Hierarki Kelas:**
```
Operation (abstract interface)
└── OperationSystem (implementasi CRUD file I/O)
    └── MenuMain (menu utama & navigasi)
SistemAkun (model akun admin)
LoginSystem (autentikasi)
```

---

## Konsep OOP yang Diterapkan

| Konsep | Contoh dalam Proyek |
|--------|---------------------|
| **Abstraksi** | `Shape`, `Operation`, `Foods`, `Drinks` sebagai abstract class |
| **Enkapsulasi** | `private` fields dengan getter/setter di `Account`, `Square`, `Rectangle` |
| **Pewarisan** | `Square extends Shape`, `OperationSystem extends Operation`, `Burger extends Foods` |
| **Polimorfisme** | Method overriding `getL()`, `getK()`, `showL()`, `showK()` di subclass Shape |

---

## Penulis

**Jaka Brajadenta**
- GitHub: [@jakabrajadenta](https://github.com/jakabrajadenta)
- Dibuat sebagai bahan evaluasi Pre-MCC — 1 Maret 2021
