# Proyek-Akhir-Membangun-ETL-Pipeline-Sederhana
# Simple ETL Pipeline - Fashion Studio Data

Proyek ini adalah implementasi pipeline **ETL (Extract, Transform, Load)** sederhana menggunakan Python. Data dikumpulkan dari website simulasi toko online, dibersihkan menggunakan logika bisnis tertentu, dan disimpan ke dalam format terstruktur.

## 📌 Alur Kerja (Workflow)
Pipeline ini terdiri dari tiga tahap utama:
1.  **Extract**: Melakukan *web scraping* pada 50 halaman website [Fashion Studio](https://fashion-studio.dicoding.dev/) menggunakan `BeautifulSoup`.
2.  **Transform**: 
    * Konversi harga dari USD ($) ke IDR (asumsi kurs Rp16.000).
    * Pembersihan data dari produk yang tidak memiliki harga atau judul "Unknown".
    * Ekstraksi angka pada kolom *Rating* dan *Colors*.
    * Penghapusan data duplikat dan nilai kosong (*null*).
3.  **Load**: Menyimpan data hasil pemrosesan ke dalam file `products.csv`.

## 🛠️ Teknologi yang Digunakan
- **Bahasa Pemrograman**: Python 3.x
- **Library Utama**:
    - `Pandas`: Untuk manipulasi dan transformasi data.
    - `BeautifulSoup4` & `Requests`: Untuk proses web scraping.
    - `Pytest`: Untuk pengujian unit (unit testing).
    - `Coverage`: Untuk mengukur persentase pengujian kode.

## 📂 Struktur Folder
```text
.
├── tests/              # Folder berisi file unit testing
│   ├── test_extract.py
│   ├── test_transform.py
│   └── test_load.py
├── utils/              # Folder modul logika ETL
│   ├── extract.py
│   ├── transform.py
│   └── load.py
├── main.py             # File utama untuk menjalankan pipeline
├── requirements.txt    # Daftar library yang dibutuhkan
└── products.csv        # Hasil akhir dataset (output)

```

## ⚙️ Cara Instalasi & Penggunaan
### Clone Repositori

```Bash
git clone [https://github.com/mahmuda1004/Proyek-Akhir-Membangun-ETL-Pipeline-Sederhana.git](https://github.com/mahmuda1004/Proyek-Akhir-Membangun-ETL-Pipeline-Sederhana.git)
```
cd Proyek-Akhir-Membangun-ETL-Pipeline-Sederhana
Instalasi Library
Pastikan Python sudah terinstal di komputer Anda, lalu jalankan:

```
Bash
pip install -r requirements.txt
```
Jalankan Pipeline ETL
Eksekusi perintah berikut untuk memulai proses pengambilan hingga penyimpanan data:

```
Bash
python main.py
```
Menjalankan Pengujian (Testing)
Untuk memastikan semua fungsi (Extract, Transform, Load) berjalan normal, jalankan:

```
Bash
pytest tests/
```
Atau untuk melihat laporan cakupan tes (coverage):

Bash
coverage run -m pytest tests/
📊 Hasil Akhir
Data yang telah diproses akan disimpan dalam file products.csv dengan struktur kolom sebagai berikut:

title: Nama produk.

price: Harga dalam format Rupiah (IDR).

rating: Skor penilaian produk.

colors: Jumlah varian warna yang tersedia.

size: Ukuran produk.

gender: Kategori target (Men/Women/Unisex).

timestamp: Waktu saat data diambil.

Proyek ini dikembangkan sebagai bagian dari portofolio Data Engineering untuk menunjukkan kemampuan dalam pengolahan data menggunakan Python.
