<div align="center">
  <img src="https://upload.wikimedia.org/wikipedia/commons/2/27/PHP-logo.svg" width="100" alt="PHP Logo">
  <img src="https://www.svgrepo.com/show/353579/codeigniter.svg" width="100" alt="CodeIgniter 4 Logo">
</div>

# 📌 Laporan Tugas Praktikum 1-3

Dokumen ini merupakan laporan tugas untuk praktikum 1, 2, dan 3 pada mata kuliah Pemrograman Website 2. Setiap bagian praktikum membahas konsep fundamental hingga implementasi nyata menggunakan framework CodeIgniter 4.

Pada rangkaian praktikum ini, mahasiswa diajak untuk memahami konsep dasar framework, arsitektur MVC (Model-View-Controller), dan diharapkan dapat membangun aplikasi web sederhana dengan CodeIgniter 4. Seluruh tahapan, mulai dari instalasi, konfigurasi, pengembangan fitur CRUD, routing, hingga pemanfaatan View Layout dan View Cell, dijelaskan secara terperinci.

Laporan ini menyertakan screenshot dari hasil implementasi untuk mempermudah pemahaman dan sebagai bukti penyelesaian setiap tugas. Setelah menyelesaikan semua praktikum, mahasiswa diharapkan memiliki kemampuan untuk membangun aplikasi web yang terstruktur, efisien, dan modular.

## 🔗 Daftar Isi

| No  | Praktikum                                  | Link                                                     |
| --- | ------------------------------------------ | -------------------------------------------------------- |
| 1   | Praktikum 1: PHP Framework (CodeIgniter 4) | [Klik di sini](#praktikum-1-php-framework-codeigniter-4) |
| 2   | Praktikum 2: Framework Lanjutan (CRUD)     | [Klik di sini](#praktikum-2-framework-lanjutan-crud)     |
| 3   | Praktikum 3: View Layout dan View Cell     | [Klik di sini](#praktikum-3-view-layout-dan-view-cell)   |
| 4   | Praktikum 7: Relasi Tabel dan Query Builder| [Klik di sini](#praktikum-7-Relasi-Tabel-dan-Query-Builder) |

## 👤 Profil Mahasiswa

| Atribut         | Keterangan            |
| --------------- | --------------------- |
| **Nama**        | Faiz Maulana          |
| **NIM**         | 312310469             |
| **Kelas**       | TI.23.A.5             |
| **Mata Kuliah** | Pemrograman Website 2 |

---

# Praktikum 1: PHP Framework (CodeIgniter 4)

## 🎯 Tujuan Praktikum

- Memahami konsep dasar sebuah Framework.
- Mengenal arsitektur MVC.
- Membuat aplikasi sederhana menggunakan CodeIgniter 4.
- Mengimplementasikan routing dan controller.
- Mendesain tampilan dengan View dan Layout CSS.

---

## ⚙️ Langkah-Langkah Praktikum

### 📌 1. Persiapan

🔹 Mengaktifkan ekstensi PHP yang diperlukan di `php.ini`.
🔹 Melakukan restart pada Apache melalui XAMPP Control Panel.

📷 **Screenshot Konfigurasi PHP.ini:**

![alt text](<gambar/image-1.png>)

---

### 📌 2. Instalasi Codeigniter 4

🔹 Unduh Codeigniter 4 dari [situs resminya](https://codeigniter.com/download).
🔹 Ekstrak file ke dalam direktori `htdocs/lab11_ci/`.
🔹 Ganti nama folder menjadi `ci4`.
🔹 Buka `http://localhost/lab11_ci/ci4/public/` untuk verifikasi instalasi.

📷 **Screenshot Tampilan Codeigniter 4:**

![alt text](<gambar/ss 1.png>)

---

### 📌 3. Menjalankan CLI (Command Line Interface)

```bash
cd xampp/htdocs/lab11_ci/ci4/
php spark
```

📷 **Screenshot Hasil Perintah CLI:**

![alt text](<gambar/ss 2.png>)

---

### 📌 4. Mengaktifkan Mode Debugging

```bash
# Buka file .env dan ubah baris berikut:
CI_ENVIRONMENT = development
```

📷 **Screenshot Konfigurasi Debugging:**

![alt text](<gambar/Cuplikan layar 2025-03-14 014504.png>)

---

### 📌 5. Membuat Route Baru

Tambahkan kode berikut pada file `app/config/Routes.php`:

```php
$routes->get('/about', 'Page::about');
$routes->get('/contact', 'Page::contact');
$routes->get('/faqs', 'Page::faqs');
```

```bash
php spark routes
```

📷 **Screenshot Halaman Error:**

![alt text](<gambar/ss 5.png>)

---

### 📌 6. Membuat Controller Page

Buat file `Page.php` di direktori `app/Controllers/`:

```php
<?php
namespace App\Controllers;
class Page extends BaseController {
    public function about() { echo "Ini adalah halaman About"; }
    public function contact() { echo "Ini adalah halaman Contact"; }
    public function faqs() { echo "Ini adalah halaman FAQ"; }
}
```

📷 **Screenshot Tampilan Halaman About:**

![alt text](<gambar/ss 6.png>)

---

### 📌 7. Membuat View

Buat file `app/Views/about.php`:

```php
<!DOCTYPE html>
<html>
<head>
    <title><?= $title; ?></title>
</head>
<body>
    <h1><?= $title; ?></h1>
    <p><?= $content; ?></p>
</body>
</html>
```

📷 **Screenshot Tampilan View About:**

![alt text](<gambar/ss 7.png>)

---

### 📌 8. Membuat Layout Web dengan CSS

- Simpan file `style.css` di folder `public/`
- Buat `header.php` dan `footer.php` di `app/Views/template/`
- Modifikasi `about.php` untuk menggunakan `include`:

```php
<?= $this->include('template/header'); ?>
<h1><?= $title; ?></h1>
<p><?= $content; ?></p>
<?= $this->include('template/footer'); ?>
```

📷 **Screenshot :**

![alt text](<gambar/ss 8.png>)

### 📌 9. 🚀 Menambahkan Halaman Baru (Services & Artikel)

Untuk melengkapi website, halaman `Services` dan `Artikel` ditambahkan untuk menampilkan informasi relevan.

🛠 **Langkah 1: Menambahkan Route**
Tambahkan route baru di `app/Config/Routes.php`:

```php
$routes->get('/services', 'Page::services');
$routes->get('/artikel', 'Page::artikel');
```

📝 **Langkah 2: Membuat Method di Controller**
Tambahkan method `services()` dan `artikel()` di `app/Controllers/Page.php`:

```php
public function services() {
    return view('services', [
        'title' => '💼 Halaman Layanan',
        'content' => 'Kami menyediakan berbagai layanan, mulai dari konsultasi IT hingga pengembangan software.'
    ]);
}

public function artikel() {
    return view('artikel', [
        'title' => '📰 Halaman Artikel',
        'content' => 'Selamat datang di halaman artikel. Di sini Anda dapat membaca berbagai tulisan menarik.'
    ]);
}
```

🎨 **Langkah 3: Membuat View**
Buat file `app/Views/services.php` dan `app/Views/artikel.php`:

```php
// services.php
<?= $this->include('template/header'); ?>
<h1>🛠 <?= $title; ?></h1>
<p>📌 <?= $content; ?></p>
<?= $this->include('template/footer'); ?>

// artikel.php
<?= $this->include('template/header'); ?>
<h1>📰 <?= $title; ?></h1>
<p>📖 <?= $content; ?></p>
<?= $this->include('template/footer'); ?>
```

🌐 **Langkah 4: Mengakses Halaman**
Buka browser dan akses URL berikut:
`http://localhost:8080/services`
`http://localhost:8080/artikel`

📷 **Screenshot Halaman Services & Artikel:**

![alt text](<gambar/ss 9.png>)
![alt text](<gambar/ss 10.png>)

✅ **Kesimpulan Praktikum 1**

Dari praktikum ini, telah dipahami dasar-dasar penggunaan framework CodeIgniter 4, meliputi:
-   Struktur direktori dan konfigurasi awal.
-   Menjalankan aplikasi via Command Line Interface (CLI).
-   Pembuatan dan pengelolaan routing untuk halaman web.
-   Penggunaan Controller dan View untuk konten dinamis.
-   Implementasi layout dengan header dan footer.
-   Penambahan halaman baru (Services dan Artikel) untuk melengkapi website.

Praktikum ini memberikan wawasan mendalam tentang bagaimana CodeIgniter 4 menyederhanakan pengembangan aplikasi web. Framework ini menyediakan struktur yang rapi, efisien, dan fleksibel, yang sangat berguna untuk membangun aplikasi web secara lebih profesional. 🚀🔥

---

# Praktikum 2: Framework Lanjutan (CRUD)

## Tujuan

1. Mahasiswa mampu memahami konsep dasar Model.
2. Mahasiswa mampu memahami konsep dasar CRUD.
3. Mahasiswa mampu membuat program sederhana menggunakan Framework Codeigniter4.

## Langkah-langkah Praktikum

### 1. Membuat Database & Tabel

```sql
CREATE DATABASE lab_ci4;

CREATE TABLE artikel (
    id INT(11) auto_increment,
    judul VARCHAR(200) NOT NULL,
    isi TEXT,
    gambar VARCHAR(200),
    status TINYINT(1) DEFAULT 0,
    slug VARCHAR(200),
    PRIMARY KEY(id)
);
```

![alt text](<gambar/image.png>)

### 2. Konfigurasi Koneksi Database

Konfigurasi dilakukan pada file `.env`.

![alt text](<gambar/image-2.png>)

### 3. Membuat Model

Buat file `ArtikelModel.php` pada direktori `app/Models`.

```php
<?php
namespace App\Models;
use CodeIgniter\Model;

class ArtikelModel extends Model
{
    protected $table = 'artikel';
    protected $primaryKey = 'id';
    protected $useAutoIncrement = true;
    protected $allowedFields = ['judul', 'isi', 'status', 'slug', 'gambar'];
}
```

![alt text](<gambar/image-3.png>)

### 4. Membuat Controller

Buat Controller `Artikel.php` pada direktori `app/Controllers`.

```php
<?php
namespace App\Controllers;
use App\Models\ArtikelModel;

class Artikel extends BaseController
{
    public function index()
    {
        $title = 'Daftar Artikel';
        $model = new ArtikelModel();
        $artikel = $model->findAll();
        return view('artikel/index', compact('artikel', 'title'));
    }
}
```

![alt text](<gambar/image-4.png>)

### 5. Membuat View

Buat file `index.php` di dalam `app/views/artikel`.

```php
<?= $this->include('template/header'); ?>

<?php if($artikel): foreach($artikel as $row): ?>
<article class="entry">
    <h2><a href="<?= base_url('/artikel/' . $row['slug']);?>"><?= $row['judul']; ?></a></h2>
    <img src="<?= base_url('/gambar/' . $row['gambar']);?>" alt="<?= $row['judul']; ?>">
    <p><?= substr($row['isi'], 0, 200); ?></p>
</article>
<hr class="divider" />
<?php endforeach; else: ?>
<article class="entry">
    <h2>Belum ada data.</h2>
</article>
<?php endif; ?>

<?= $this->include('template/footer'); ?>
```

![alt text](<gambar/image-5.png>)

### 6. Menambahkan Data & Menampilkan Detail

Data ditambahkan ke database dan fungsi `view($slug)` dibuat di controller untuk menampilkan detail artikel.

![alt text](<gambar/ss 2.1.png>)
![alt text](<gambar/ss 2.2.png>)

### 7. Membuat Menu Admin (CRUD)

- Buat method `admin_index()`, `add()`, `edit()`, dan `delete()` pada Controller `Artikel`.
- Buat view untuk `admin_index`, `form_add`, dan `form_edit`.
- Tambahkan routing untuk semua fungsi admin.

![alt text](<gambar/ss 2.4.png>)
![alt text](<gambar/ss 2.5.png>)
![alt text](<gambar/ss 2.6.png>)

---

# Praktikum 3: View Layout dan View Cell

## Tujuan

1. Memahami konsep View Layout di CodeIgniter 4.
2. Menggunakan View Layout untuk membuat template.
3. Mengimplementasikan View Cell untuk komponen modular.

## Langkah-langkah Praktikum

### 1. Membuat Layout Utama

Buat file `main.php` di dalam `app/Views/layout/`.

```php
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title><?= $title ?? 'Website Saya' ?></title>
    <link rel="stylesheet" href="<?= base_url('/style.css');?>">
</head>
<body>
    <div id="container">
        <header>
            <h1>Layout Utama</h1>
        </header>
        <nav>
            <a href="<?= base_url('/');?>" class="active">Home</a>
            <a href="<?= base_url('/artikel');?>">Artikel</a>
            <a href="<?= base_url('/about');?>">About</a>
            <a href="<?= base_url('/contact');?>">Kontak</a>
        </nav>
        <section id="wrapper">
            <section id="main">
                <?= $this->renderSection('content') ?>
            </section>
            <aside id="sidebar">
                <?= view_cell('App\\Cells\\ArtikelTerkini::render') ?>
            </aside>
        </section>
        <footer>
            <p>&copy; 2024 - Universitas Pelita Bangsa</p>
        </footer>
    </div>
</body>
</html>
```


### 2. Modifikasi View

Ubah file view seperti `home.php` untuk menggunakan layout baru.

```php
<?= $this->extend('layout/main') ?>
<?= $this->section('content') ?>
    <h1><?= $title; ?></h1>
    <hr>
    <p><?= $content; ?></p>
<?= $this->endSection() ?>
```


### 3. Membuat View Cell

Buat class `ArtikelTerkini.php` di `app/Cells/` dan view `artikel_terkini.php` di `app/Views/components/`.


### 4. Modifikasi Database & Model

Tambahkan kolom `created_at` pada tabel `artikel` dan perbarui `allowedFields` di `ArtikelModel`.

```sql
ALTER TABLE artikel ADD COLUMN created_at DATETIME DEFAULT CURRENT_TIMESTAMP;
UPDATE artikel SET created_at = CURRENT_TIMESTAMP;
```


### 5. Hasil Akhir

Akses halaman home untuk melihat tampilan dengan layout dan view cell yang baru.

![alt text](<gambar/ss 3.1.png>)

---

## Pertanyaan dan Jawaban

### 1. Apa manfaat utama dari penggunaan View Layout dalam pengembangan aplikasi?

Manfaat utamanya adalah **Reusability** (penggunaan kembali kode) dan **Konsistensi**. Dengan layout, kita hanya perlu mendefinisikan struktur utama (header, footer, sidebar) satu kali dan menggunakannya di banyak halaman. Ini membuat kode lebih bersih dan pemeliharaan lebih mudah.

### 2. Jelaskan perbedaan antara View Cell dan View biasa.

| Fitur       | View Cell                                       | View Biasa                               |
|-------------|-------------------------------------------------|------------------------------------------|
| **Tujuan**  | Komponen UI kecil yang bisa digunakan kembali   | Menampilkan halaman penuh atau bagian besar |
| **Logika**  | Memiliki class sendiri untuk mengambil data     | Menerima data dari Controller            |
| **Contoh**  | Sidebar artikel terkini, widget, keranjang belanja | Halaman home, detail produk, halaman kontak |

### 3. Ubah View Cell agar hanya menampilkan post dengan kategori tertentu.

Untuk melakukan ini, kita bisa memodifikasi method render di class Cell untuk menerima parameter kategori, lalu menggunakannya untuk memfilter data dari model.

```php
// Panggilan di view
<?= view_cell('App\\Cells\\ArtikelTerkini::render', ['kategori' => 'tutorial']) ?>

// Modifikasi di class ArtikelTerkini
public function render(string $kategori = null)
{
    $model = new ArtikelModel();
    if ($kategori) {
        $model->where('kategori', $kategori);
    }
    $artikel = $model->orderBy('created_at', 'DESC')->limit(5)->findAll();
    return view('components/artikel_terkini', ['artikel' => $artikel]);
}
```

## Kesimpulan Akhir

Dalam rangkaian praktikum ini, saya telah berhasil mengimplementasikan konsep-konsep kunci dalam CodeIgniter 4, mulai dari dasar-dasar MVC, routing, hingga fitur-fitur lanjutan seperti CRUD, View Layout, dan View Cell. Penggunaan View Layout sangat membantu dalam menciptakan tampilan yang konsisten, sementara View Cell menyediakan cara yang efisien untuk mengelola komponen UI yang dapat digunakan kembali. Melalui praktikum ini, saya mendapatkan pemahaman yang lebih baik tentang cara membangun aplikasi web yang terstruktur, modular, dan mudah dikelola.
