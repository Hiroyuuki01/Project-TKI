# Proyek Temu Kembali Informasi (TKI) — Penugasan UTS 2026/2027

Repositori ini memuat implementasi proyek penugasan Ujian Tengah Semester (UTS) mata kuliah **Temu Kembali Informasi (TKI)**, Program Studi Teknik Informatika, Fakultas Teknik, Universitas Muhammadiyah Malang. Proyek ini mencakup akuisisi, pengelolaan, ekstraksi informasi, serta analisis putusan peradilan dari **Direktori Putusan Mahkamah Agung RI** pada wilayah hukum **Pengadilan Negeri Banjarmasin** untuk perkara **Pidana Khusus (Narkotika dan Psikotropika)**.

---

##  Struktur Repositori

```text
Project-TKI/
├── Scrapping.ipynb                     # [TUGAS 3] Notebook Web Crawler (DrissionPage) & Ekstraksi Regex (VS Code & Colab)
├── Tugas4_Preprocessing_Indexing.ipynb # [TUGAS 4] Notebook Preprocessing, Inverted Index, TF-IDF & Okapi BM25
├── Hasil_Ekstraksi_Tugas3.csv          # [TUGAS 3] Tabel CSV hasil ekstraksi seluruh 77 putusan
├── Dataset overview tugas 2/
│   └── Narkotika.zip                   # [TUGAS 2] Arsip ZIP berisi dokumen putusan terpilih (*.pdf)
├── Overview tugas 2/
│   └── Overview.xlsx                   # [TUGAS 2] Tabel ringkasan data putusan format Microsoft Excel
├── PDF_Putusan/                        # [TUGAS 3] Koleksi 77 file PDF putusan pengadilan asli
├── TXT_Putusan/                        # [TUGAS 3] Koleksi 77 file teks putusan bersih tanpa noise watermark
└── README.md                           # Dokumentasi komprehensif proyek
```

---

##  BAGIAN I: TUGAS 2 — Akuisisi & Pengelolaan Dataset (SUBCPMK-2)

Pada penugasan ini, dilakukan akuisisi manual dan pengelolaan dokumen putusan peradilan narkotika dari Pengadilan Negeri Banjarmasin (rekomendasi tahun 2023–2025, bukan berstatus Berkekuatan Hukum Tetap).

* **Berkas ZIP Dataset**: Tersedia di folder [`Dataset overview tugas 2/Narkotika.zip`](Dataset%20overview%20tugas%202/Narkotika.zip).
* **Ringkasan Excel**: Tersedia di folder [`Overview tugas 2/Overview.xlsx`](Overview%20tugas%202/Overview.xlsx).

### Tabel Ringkasan Putusan Terpilih (Overview)

| No | Nomor Putusan | Lembaga Peradilan | Rangkuman Barang Bukti | Amar Putusan |
| :-: | :--- | :--- | :--- | :--- |
| **1** | `782/Pid.Sus/2025/PN Bjm` | PN Banjarmasin | 790 tablet obat farmasi putih polos, catatan kertas, plastik klip | Terbukti bersalah, pidana penjara 1 tahun 6 bulan dan denda |
| **2** | `864/Pid.Sus/2025/PN Bjm` | PN Banjarmasin | 1 paket sabu berat bersih 4,86 gram, HP Vivo biru, pipet kaca | Terbukti bersalah, pidana penjara 6 tahun dan denda Rp 1 Milyar |
| **3** | `801/Pid.Sus/2025/PN Bjm` | PN Banjarmasin | 15 butir pil ekstasi (XTC) bersih 6,66 gram, HP Oppo, kotak rokok | Terbukti bersalah, pidana penjara 6 tahun dan denda Rp 1 Milyar |
| **4** | `854/Pid.Sus/2025/PN Bjm` | PN Banjarmasin | 3 paket sabu bersih 3,68 gram, timbangan digital, HP Redmi | Terbukti bersalah, pidana penjara 5 tahun dan denda Rp 1 Milyar |
| **5** | `793/Pid.Sus/2025/PN Bjm` | PN Banjarmasin | 1 paket sabu bersih 5,07 gram, tisu, bungkus snack Gerry | Terbukti bersalah, pidana penjara 5 tahun dan denda Rp 1 Milyar |

---

##  BAGIAN II: TUGAS 3 — Web Crawler & Information Extraction (SUBCPMK-3)

Pada penugasan ini, dibangun sistem perayap web (*web crawler*) dan ekstraksi entitas terstruktur (*Information Extraction*) dengan spesifikasi:

1. **Kepatuhan Kebijakan `robots.txt`**:
   - Crawler memeriksa dan mematuhi etika perayapan direktori MA RI (`https://putusan3.mahkamahagung.go.id/robots.txt`).
   - Menerapkan *polite crawling* dengan jeda *Crawl-delay* minimal 3 detik antar-halaman.
2. **Pembersihan Noise & Watermark**:
   - Menghapus teks watermark vertikal Mahkamah Agung ber-font *Helvetica* yang secara default memecah teks pada naskah asli.
3. **Ekstraksi Entitas Cerdas (Regex Heuristics)**:
   - **Kolom Wajib**: `No Putusan`, `Lembaga Peradilan`, `Barang Bukti`, `Amar Putusan`.
   - **Kolom Nilai Tambah (Poin Plus)**: `Identitas Terdakwa`, `Tuntutan JPU`.
4. **Petunjuk Lingkungan Eksekusi Notebook (`Scrapping.ipynb`)**:
   -  **Dijalankan di VS Code (Komputer Lokal / Desktop)**:  
     Modul *Web Crawler* menggunakan library `DrissionPage` yang menghubungkan program langsung ke peramban Google Chrome nyata di komputer Anda. Hal ini diperlukan karena website Direktori Putusan Mahkamah Agung RI (`https://putusan3.mahkamahagung.go.id`) dilindungi sistem keamanan **Cloudflare Turnstile (Anti-Bot)** yang memerlukan peramban browser fisik agar terhindar dari *HTTP 403 Forbidden*.
5. **Koleksi Berkas Korpus**:
   - Folder PDF: [`PDF_Putusan/`](PDF_Putusan/) (77 berkas putusan)
   - Folder TXT: [`TXT_Putusan/`](TXT_Putusan/) (77 berkas teks bersih)
   - Tabel CSV: [`Hasil_Ekstraksi_Tugas3.csv`](Hasil_Ekstraksi_Tugas3.csv)

---

##  BAGIAN III: TUGAS 4 — Preprocessing, Indexing, & Pembobotan Teks (SUBCPMK-4)

Pada penugasan ini, dilakukan tahapan inti temu kembali informasi (*Information Retrieval*) pada seluruh bagian teks dari **77 dokumen putusan perkara Narkotika PN Banjarmasin**:

1. **Pipeline Preprocessing Teks Hukum**:
   - **Cleaning & Noise Removal**: Menghapus nomor halaman berulang, URL, dan sisa pecahan watermark MA.
   - **Case Folding**: Mengubah seluruh teks menjadi huruf kecil (*lowercase*).
   - **Tokenizing**: Memecah naskah putusan tebal menjadi unit token kata.
   - **Normalisasi Istilah Narkotika**: Menyeragamkan varian kata teknis hukum (`shabu` $\rightarrow$ `sabu`, `extacy` $\rightarrow$ `ekstasi`, `jpu` $\rightarrow$ `jaksa`, `uu` $\rightarrow$ `undang`).
   - **Stopword Removal**: Menghilangkan kata hubung umum Bahasa Indonesia serta kata struktural dokumen peradilan.
   - **Fast Cached Stemming**: Mengembalikan kata berimbuhan ke kata dasar dengan algoritma **Nazief-Adriani / Sastrawi** yang dioptimasi dengan kamus *cache* sehingga memproses seluruh naskah tebal korpus dalam hitungan detik.
2. **Pembangunan Inverted Index (Indeks Terbalik)**:
   - Memetakan setiap *term* kata dasar ke dalam *posting list* dokumen beserta frekuensi kata (*Term Frequency* / TF), frekuensi dokumen (*Document Frequency* / DF), dan *Inverse Document Frequency* (IDF).
   - Ekspor data: [`Inverted_Index_Tugas4.json`](Inverted_Index_Tugas4.json) dan [`Tabel_Inverted_Index_Tugas4.csv`](Tabel_Inverted_Index_Tugas4.csv).
3. **Teknik Pembobotan Teks (Weighting)**:
   - **Sublinear TF-IDF (Vector Space Model)**: Menggunakan pembobotan $w_{t,d} = (1 + \ln \text{tf}) \times \text{idf}$ disertai normalisasi L2 (*Cosine Similarity*).
   - **Okapi BM25**: Algoritma pembobotan probabilistik dengan penyesuaian panjang dokumen putusan ($k_1=1.5, b=0.75$).
4. **Mesin Pencari Putusan (Query Retrieval)**:
   - Menguji perankingan dokumen putusan menggunakan kueri kasus narkotika nyata (*permufakatan jahat, barang bukti timbangan/sabu, pasal 112 dan pasal 114*).
5. **Notebook Google Colaboratory**:
   - Dijalankan langsung melalui tautan: [Tugas4_Preprocessing_Indexing.ipynb](Tugas4_Preprocessing_Indexing.ipynb)

---

## Identitas Pengembang

* **Mahasiswa**: Muhammad Aulia Rahman (NIM: 202310370311005)

**Dosen Pengampu**: Galih W. W  
**Program Studi**: Teknik Informatika, Fakultas Teknik, Universitas Muhammadiyah Malang  
**Tahun Akademik**: Semester Ganjil 2026/2027
