# Dataset Putusan Pengadilan Narkotika dan Psikotropika (PN Banjarmasin)

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC_BY_4.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
[![Domain: Information Retrieval](https://img.shields.io/badge/Domain-Information_Retrieval-blue.svg)](https://id.wikipedia.org/wiki/Temu_kembali_informasi)
[![Jurisdiction: Indonesia](https://img.shields.io/badge/Jurisdiction-Mahkamah_Agung_RI-red.svg)](https://putusan3.mahkamahagung.go.id/)
[![Documents: 5 PDFs](https://img.shields.io/badge/Dataset_Size-5_Putusan-green.svg)](#struktur-repositori)

Dataset ini berisi kumpulan dokumen putusan pengadilan tingkat pertama dari **Pengadilan Negeri Banjarmasin** untuk perkara **Pidana Khusus**, dengan klasifikasi kejahatan **Narkotika dan Psikotropika**. Dataset ini dikembangkan dan dikelola sebagai bagian dari pemenuhan **Tugas 2 (SUBCPMK-2)** mata kuliah **Temu Kembali Informasi (TKI)**, Program Studi Teknik Informatika, Fakultas Teknik, Universitas Muhammadiyah Malang.

Dokumen peradilan ini bersifat terbuka untuk umum (*public legal records*) dan bebas hak kekayaan intelektual (HaKI).

---

## Karakteristik & Metadata Dataset

| Parameter | Keterangan |
| :--- | :--- |
| **Sumber Data** | Direktori Putusan Mahkamah Agung RI (`https://putusan3.mahkamahagung.go.id/`) |
| **Lembaga Peradilan** | Pengadilan Negeri Banjarmasin |
| **Klasifikasi Perkara** | Pidana Khusus — Narkotika dan Psikotropika |
| **Tahun Putusan** | 2025 (Sesuai rekomendasi rentang 2023 - 2025) |
| **Status Hukum** | Bukan berstatus Berkekuatan Hukum Tetap (BHT) saat naskah tingkat pertama diterbitkan |
| **Total Dokumen** | 5 Dokumen Putusan Lengkap Terpilih |
| **Format Berkas** | PDF Asli (`Narkotika.zip`), Teks Bersih (`TXT_Putusan`), dan Excel (`Overview.xlsx`) |

---

## Struktur Repositori

Struktur direktori ini disusun persis mengikuti ketentuan format pada panduan penugasan:

```text
Dataset-Narkotika_<NIM1>_<NIM2>/
├── Dataset/
│   └── Narkotika.zip          # Arsip ZIP berisi 5 dokumen putusan pengadilan (*.pdf)
├── Overview/
│   └── Overview.xlsx          # Tabel ringkasan 5 data putusan (No, No Putusan, Lembaga, BB, Amar)
├── PDF_Putusan/               # Salinan berkas 5 PDF asli (Putusan_01.pdf s.d. Putusan_05.pdf)
├── TXT_Putusan/               # Salinan berkas 5 TXT hasil ekstraksi bersih tanpa watermark
├── Overview_Tugas2.csv        # Tabel ringkasan format CSV UTF-8
└── README.md                  # Dokumentasi resmi dataset
```

---

## Ringkasan 5 Dokumen Putusan Terpilih

| No | No Putusan | Lembaga Peradilan | Rangkuman Barang Bukti | Amar Putusan |
| :-: | :--- | :--- | :--- | :--- |
| 1 | `782/Pid.Sus/2025/PN Bjm` | PN Banjarmasin | 790 tablet obat farmasi putih polos, catatan kertas, plastik | Menyatakan terdakwa terbukti bersalah, pidana penjara 1 tahun 6 bulan dan denda |
| 2 | `864/Pid.Sus/2025/PN Bjm` | PN Banjarmasin | 1 paket sabu berat bersih 4,86 gram, 1 HP Vivo biru, pipet kaca | Menyatakan terdakwa terbukti bersalah, pidana penjara 6 tahun dan denda 1 Milyar |
| 3 | `801/Pid.Sus/2025/PN Bjm` | PN Banjarmasin | 15 butir pil ekstasi (XTC) berat bersih 6,66 gram, HP Oppo, kotak rokok | Menyatakan terdakwa terbukti bersalah, pidana penjara 6 tahun dan denda 1 Milyar |
| 4 | `854/Pid.Sus/2025/PN Bjm` | PN Banjarmasin | 3 paket sabu berat bersih 3,68 gram, timbangan digital, HP Redmi | Menyatakan terdakwa terbukti bersalah, pidana penjara 5 tahun dan denda 1 Milyar |
| 5 | `793/Pid.Sus/2025/PN Bjm` | PN Banjarmasin | 1 paket sabu berat bersih 5,07 gram, tisu, bungkus snack Gerry | Menyatakan terdakwa terbukti bersalah, pidana penjara 5 tahun dan denda 1 Milyar |

*Catatan: Seluruh data lengkap dan verbatim dapat dilihat pada file `Overview/Overview.xlsx`.*

---

## Identitas Kelompok

* **Anggota 1**: [Nama Mahasiswa 1] (NIM: [NIM 1])
* **Anggota 2**: [Nama Mahasiswa 2] (NIM: [NIM 2])

**Mata Kuliah**: Temu Kembali Informasi (TKI)  
**Program Studi**: Teknik Informatika, Fakultas Teknik, Universitas Muhammadiyah Malang  
**Tahun Akademik**: Semester Ganjil 2026/2027

