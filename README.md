# 📃 Laporan Praktikum Web - CodeIgniter 4

Laporan ini berisi dokumentasi hasil pengerjaan Praktikum 1 sampai Praktikum 3 untuk mata kuliah **Pemrograman Website 2**. Praktikum difokuskan pada pemahaman framework CodeIgniter 4, konsep MVC (Model, View, Controller), serta pembuatan fitur dasar website seperti routing, layout, dan fitur CRUD.

---

## 🔗 Navigasi

| No | Praktikum                            | Link                                          |
| -- | ------------------------------------ | --------------------------------------------- |
| 1  | Praktikum 1: Pengenalan CodeIgniter  | [Lihat](#praktikum-1-pengenalan-codeigniter)  |
| 2  | Praktikum 2: CRUD dengan CodeIgniter | [Lihat](#praktikum-2-crud-dengan-codeigniter) |
| 3  | Praktikum 3: View Layout & View Cell | [Lihat](#praktikum-3-view-layout--view-cell)  |

## 👨‍🎓 Biodata

| Atribut         | Data                  |
| --------------- | --------------------- |
| **Nama**        | Faiz Maulana          |
| **NIM**         | 312310469             |
| **Kelas**       | TI.23.A.5             |
| **Mata Kuliah** | Pemrograman Website 2 |

---

# Praktikum 1: Pengenalan CodeIgniter

## Tujuan

* Memahami dasar penggunaan framework PHP.
* Mengetahui konsep MVC pada CodeIgniter.
* Membuat routing dan controller sederhana.
* Menghubungkan tampilan menggunakan View dan Template.

## Langkah Praktikum

### Konfigurasi Awal & Instalasi

* Mengaktifkan modul PHP di `php.ini`.
* Ekstrak CodeIgniter ke direktori `htdocs/lab11_ci/ci4/`.

📷 **Screenshot Konfigurasi PHP.ini:**&#x20;

📷 **Screenshot Tampilan Codeigniter 4:**&#x20;

### Menjalankan Spark CLI & Mode Debug

```bash
php spark
```

📷 **Screenshot CLI:**&#x20;

📷 **Screenshot Debug Mode:**&#x20;

### Routing dan Controller

* Menambahkan routing `/about`, `/contact`, dan `/faqs`.
* Membuat controller `Page.php`.

📷 **Screenshot Routing & Error Page:** &#x20;

📷 **Screenshot About Page:**&#x20;

### View dan Template

* Membuat file view seperti `about.php`.

📷 **Screenshot Tampilan View:**&#x20;

* Membuat file `header.php`, `footer.php` dan menerapkan CSS.

📷 **Screenshot Template:**&#x20;

### Halaman Services & Artikel

* Menambah halaman `/services` dan `/artikel` dengan routing, controller, dan view.

📷 **Screenshot Halaman Services:**&#x20;

📷 **Screenshot Halaman Artikel:**&#x20;

---

# Praktikum 2: CRUD dengan CodeIgniter

## Tujuan

* Memahami penggunaan Model dalam CodeIgniter.
* Menerapkan fitur CRUD sederhana (Create, Read, Update, Delete).

## Langkah Praktikum

* Membuat database dan tabel `artikel`.
* Konfigurasi koneksi database melalui file `.env`.

📷 **Screenshot Database:** &#x20;

* Membuat Model `ArtikelModel.php`, Controller `Artikel.php`, dan view `index.php`.

📷 **Screenshot Model & Controller:** &#x20;

* Menampilkan daftar artikel dan detail artikel.

📷 **Screenshot View Artikel:**  &#x20;

* Menambahkan fitur admin: menampilkan, menambah, mengedit, dan menghapus artikel.

📷 **Screenshot Admin Panel:**   &#x20;

---

# Praktikum 3: View Layout & View Cell

## Tujuan

* Menggunakan layout utama untuk menyatukan tampilan.
* Memanfaatkan View Cell untuk komponen dinamis seperti sidebar.

## Langkah Praktikum

* Membuat `layout/main.php` sebagai layout dasar.

📷 **Screenshot Layout:**&#x20;

* Mengubah view agar mengikuti layout.

📷 **Screenshot Home Layout:**&#x20;

* Membuat class `ArtikelTerkini` dan view `artikel_terkini.php` untuk sidebar dinamis.

📷 **Screenshot View Cell:** &#x20;

* Menambahkan kolom `created_at` dan mengupdate data artikel.

📷 **Screenshot Update DB:** &#x20;

* Menampilkan 3 artikel terbaru di sidebar dan menyesuaikan controller.

📷 **Screenshot Home Controller:**&#x20;

* Menyesuaikan tampilan `artikel/index.php` dan `artikel/detail.php` dengan layout.

📷 **Screenshot View Index & Detail:** &#x20;

---

## ✅ Kesimpulan

Dari ketiga praktikum ini, saya memahami alur kerja CodeIgniter 4 mulai dari instalasi hingga pengembangan aplikasi CRUD dengan tampilan yang terstruktur. Penggunaan layout dan view cell sangat membantu menjaga konsistensi dan modularitas pada antarmuka aplikasi web.

Framework ini memberi kemudahan dalam pengembangan aplikasi yang skalabel dan terorganisir.
