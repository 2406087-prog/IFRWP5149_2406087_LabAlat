# Laporan Review & Pengujian Jobsheet Pertemuan 4
**Mata Kuliah:** Praktikum Analisis dan Desain Berorientasi Objek  
**NIM / Nama:** 2406087 / Muhammad Dzikri Shiddiq Muttaqin  
**Tanggal:** 11 November 2026  
**Kode File:** P04_2406087_jobsheet_review_v01.md  

---

## A. Identitas Artefak dan Workspace Pertemuan 4

1. **Studi Kasus Laboratorium (LAB):**
   * Berkas Skenario & Kebutuhan: `01_skenario/P04_LAB_kebutuhan_v01.md`[cite: 22, 24]
   * Workspace Diagram: `04_model_analisis/P04/LAB/P04_2406087_LAB_usecase_v01.drawio`
   * Gambar Ekspor: `04_model_analisis/P04/LAB/P04_2406087_LAB_usecase_v01.png`
   * Deskripsi Use Case: `04_model_analisis/P04/LAB/P04_2406087_LAB_UC11_deskripsi_v01.md`[cite: 27, 28]

2. **Tugas Praktik Akademik (SIA - Layanan Hasil Studi):**
   * Berkas Skenario & Kebutuhan: `01_skenario/P04_SIA_kebutuhan_v01.md`[cite: 22, 34]
   * Workspace Diagram: `04_model_analisis/P04/SIA/P04_2406087_SIA_usecase_v01.drawio`[cite: 22, 35]
   * Gambar Ekspor: `04_model_analisis/P04/SIA/P04_2406087_SIA_usecase_v01.png`[cite: 22, 35]

---

## B. Pengujian Konsistensi dan Situasi Kasus SIA (Hasil Studi)

Pengujian konsistensi dilakukan berdasarkan 3 situasi pemodelan yang disyaratkan pada Jobsheet P04[cite: 36]:

### 1. Situasi A: Pewarisan Akses Lihat Kalender Akademik
* **Kondisi:** Mahasiswa melihat kalender akademik tanpa adanya garis asosiasi langsung dari aktor `Mahasiswa` ke `SIA-UC07 Lihat Kalender Akademik`[cite: 36].
* **Hasil Review:** **Sesuai & Valid.** Aktor `Mahasiswa` dan `Dosen` merupakan bentuk khusus (*specialized*) dari aktor umum `Civitas Akademika`[cite: 34]. Asosiasi digambar satu kali dari `Civitas Akademika` ke `SIA-UC07`[cite: 35]. Berdasarkan aturan UML 2.5.1, `Mahasiswa` otomatis mewarisi seluruh kemampuan interaksi aktor umumnya[cite: 16, 17, 36].

### 2. Situasi B: Pembatasan Hak Akses Input Nilai
* **Kondisi:** Dosen yang bukan merupakan pengampu mata kuliah mencoba menginput nilai perkuliahan[cite: 36].
* **Hasil Review:** **Sesuai & Valid.** Sistem menolak akses input nilai[cite: 34, 36]. Berdasarkan prasyarat dan alur alternatif deskripsi use case `Input Nilai Mata Kuliah`, autentikasi dan status pengampu diverifikasi sebelum form pengisian nilai terbuka[cite: 34, 36].

### 3. Situasi C: Baturan Hapus Data Mahasiswa Aktif
* **Kondisi:** Admin Akademik mencoba menghapus data mahasiswa yang masih memiliki record akademik aktif[cite: 36].
* **Hasil Review:** **Sesuai & Valid.** Berdasarkan aturan bisnis `SIA-R11` dan kriteria penghapusan, aksi ditolak oleh sistem dan data mahasiswa tidak terhapus (Pascakondisi Gagal berlaku)[cite: 34].

---

## C. Checklist Verifikasi Model Pertemuan 4

| No | Indikator Modul | Pemeriksaan | Status | Catatan Review |
|:--:|:---|:---|:---:|:---|
| 1 | Integritas Artefak P03 | Seluruh elemen Pertemuan 3 tetap ada dan tidak diubah namanya | ✓ | LAB-UC01 s.d. LAB-UC07 dan relasi include/extend Pertemuan 3 dipertahankan utuh[cite: 15, 26, 36] |
| 2 | Aktor Kepala Lab | Kepala Lab hanya terhubung 1 asosiasi ke LAB-UC07 | ✓ | Tidak ada relasi include/extend/generalization pada LAB-UC07[cite: 32, 36] |
| 3 | Generalization Aktor | Aktor khusus terhubung ke aktor umum dengan panah segitiga kosong | ✓ | Ujung segitiga kosong menunjuk ke `Peminjam` (LAB)[cite: 17, 26, 37] dan `Civitas Akademika` (SIA)[cite: 34, 35] |
| 4 | Penghilangan Garis Ganda | Tidak ada asosiasi warisan yang digambar ulang dari aktor khusus | ✓ | Garis asosiasi ke UC01 & UC03 cukup digambar dari `Peminjam`[cite: 16, 17, 26, 36] |
| 5 | Generalization Use Case | Use case khusus (Tambah, Ubah, Hapus) mengarah ke UC Umum | ✓ | Tiga panah segitiga kosong dari UC khusus menunjuk ke `Kelola Data`[cite: 18, 26, 30, 37] |
| 6 | Collaboration & Realization | Collaboration digambar sebagai elips garis putus-putus | ✓ | Namanya sama persis dengan UC (`Ajukan Peminjaman` & `Catat Pengembalian`)[cite: 19, 27, 31, 37] |
| 7 | Relasi Realization | Realization digambar dari Collaboration menuju Use Case | ✓ | Menggunakan garis putus-putus berujung segitiga kosong[cite: 19, 20, 31, 37] |
| 8 | Bebas Garis Aktor-Collaboration | Tidak ada garis asosiasi langsung dari aktor ke Collaboration | ✓ | Aktor hanya berinteraksi langsung dengan Use Case[cite: 19] |
| 9 | Konsistensi Penamaan & Versi | Nama/ID pada diagram, katalog, dan deskripsi sama persis | ✓ | Menggunakan versi konsisten `v01` pada `.drawio` dan `.png`[cite: 22, 37] |

---

## D. Summary Perubahan Model (Kumulatif P03 -> P04)

1. **Perubahan Garis Asosiasi:** Asosiasi ke `Lihat Ketersediaan` (LAB-UC01) dan `Ajukan Peminjaman` (LAB-UC03) yang pada P03 digambar dari Mahasiswa, dipindahkan menjadi satu garis dari `Peminjam`[cite: 26, 27].
2. **Penambahan Fitur Pengembalian:** Penambahan `LAB-UC11 Catat Pengembalian Peralatan` yang menyertakan (`<<include>>`) `LAB-UC12 Periksa Kondisi Peralatan`[cite: 26, 31].
3. **Penambahan Collaboration:** Menambahkan `LAB-CO01` dan `LAB-CO02` untuk menunjukkan perwujudan/realisasi dua use case utama[cite: 23, 27, 31].