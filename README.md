# Analisis Kesejahteraan Rakyat Kabupaten Tapanuli Utara

Pengolahan dan visualisasi data **SUSENAS 2023–2025** dengan Python

## Overview

Proyek ini mengolah data publikasi **Kesejahteraan Rakyat Kabupaten Tapanuli Utara** yang bersumber dari **Survei Sosial Ekonomi Nasional (SUSENAS)** periode 2023–2025. Data awal berupa tabel publikasi dalam satu file Excel dengan beberapa worksheet. Tabel-tabel tersebut dibersihkan (baris judul, kolom tahun, tipe data), digabungkan menjadi dataset final yang rapi, lalu divisualisasikan untuk melihat perkembangan indikator kesejahteraan dari tahun ke tahun, terutama menurut jenis kelamin.

### Tujuan

1. Membersihkan dan menstandarkan tabel publikasi SUSENAS yang formatnya belum siap analisis.
2. Menghasilkan dataset final yang terstruktur dalam satu file Excel.
3. Memvisualisasikan perkembangan indikator kesejahteraan rakyat Kabupaten Tapanuli Utara tahun 2023–2025.

## Dataset

- **Sumber:** Survei Sosial Ekonomi Nasional (SUSENAS), publikasi Kesejahteraan Rakyat Kabupaten Tapanuli Utara
- **Wilayah:** Kabupaten Tapanuli Utara
- **Periode:** 2023, 2024, 2025
- **File input:** `dataset_kesejahteraan_rakyat_taput_2023_2024_2025.xlsx`
- **File output:** `dataset_final_taput.xlsx`

### Worksheet yang diolah

| Dataset | Indikator |
|---|---|
| Partisipasi Sekolah | Tidak/belum sekolah, masih sekolah, tidak sekolah lagi |
| Pendidikan Tertinggi | Tidak memiliki ijazah SD, SD/sederajat, SMP/sederajat, SMA/ke atas |
| Angka Kesakitan | Persentase penduduk yang sakit |
| Kepemilikan Bangunan | Milik sendiri, bukan milik sendiri |
| Sumber Air | Air kemasan/leding, sumur/mata air, lainnya |
| Teknologi Informasi | Menggunakan HP, menggunakan internet |
| Jenis Aset | Kepemilikan aset rumah tangga |
| Pengeluaran | Komposisi pengeluaran makanan dan bukan makanan menurut kelompok pengeluaran (40% terbawah, 40% menengah, 20% teratas) |

## Data Processing Pipeline

| Step | Description |
|---|---|
| 1. Import library | Pandas, NumPy, Matplotlib |
| 2. Upload & read | Memuat file Excel dan membaca seluruh worksheet ke dalam dictionary |
| 3. Data understanding | Cek `head()`, `info()`, dan jumlah missing value di setiap worksheet |
| 4. Data cleaning | Mengisi kolom `Tahun` dengan forward fill, menghapus baris judul yang ikut terbaca sebagai data, menyeragamkan nama kolom, dan menghapus baris kosong |
| 5. Data transformation | Mengubah kolom angka menjadi numerik (`pd.to_numeric`), lalu verifikasi tipe data dan missing value |
| 6. Descriptive statistics | `describe()` untuk setiap dataset |
| 7. Export | Menyimpan 8 dataset bersih ke `dataset_final_taput.xlsx` |
| 8. EDA & visualisasi | Memuat dataset final dan membuat 15 grafik |

### Dataset Final (`dataset_final_taput.xlsx`)

| Sheet | Isi |
|---|---|
| Partisipasi Sekolah | Partisipasi sekolah menurut karakteristik dan tahun |
| Pendidikan | Pendidikan tertinggi yang ditamatkan |
| Kesakitan | Angka kesakitan |
| Rumah | Status kepemilikan rumah |
| Air | Sumber air utama |
| Teknologi | Penggunaan HP dan internet |
| Aset | Kepemilikan aset |
| Pengeluaran | Komposisi pengeluaran rumah tangga |

## Visualisasi

| No. | Visualisasi | Jumlah grafik |
|---|---|---:|
| 1 | Tingkat partisipasi sekolah menurut jenis kelamin (tidak/belum sekolah, masih sekolah, tidak sekolah lagi) | 3 |
| 2 | Tingkat pendidikan tertinggi menurut jenis kelamin (tanpa ijazah SD, SD, SMP, SMA ke atas) | 4 |
| 3 | Angka kesakitan menurut jenis kelamin | 1 |
| 4 | Status kepemilikan rumah menurut jenis kelamin | 1 |
| 5 | Sumber air utama rumah tangga (air kemasan/leding, sumur/mata air, lainnya) | 3 |
| 6 | Penggunaan HP dan internet menurut jenis kelamin | 1 |
| 7 | Kepemilikan aset rumah tangga menurut jenis aset | 1 |
| 8 | Komposisi pengeluaran rumah tangga menurut kelompok pengeluaran | 1 |

Grafik dibuat dengan Matplotlib (garis dan batang bertema hangat, dengan label persentase pada setiap titik).

## Cara Menjalankan

1. Buka `notebook/Pengolahan_Data_SUSENAS.ipynb` di Google Colab.
2. Unggah file `dataset_kesejahteraan_rakyat_taput_2023_2024_2025.xlsx` saat sel Upload Data dijalankan.
3. Jalankan seluruh sel secara berurutan.

Untuk menjalankan di lokal, hapus sel `google.colab` dan pasang library:

```bash
pip install pandas numpy matplotlib openpyxl
```

## Tools

- **Bahasa:** Python
- **Pengolahan data:** Pandas, NumPy, OpenPyXL
- **Visualisasi:** Matplotlib
- **Lingkungan:** Google Colab, Jupyter Notebook
