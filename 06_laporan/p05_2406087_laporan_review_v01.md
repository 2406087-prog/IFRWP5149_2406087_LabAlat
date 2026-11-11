# Laporan Review & Pengujian Jobsheet Pertemuan 5
**Mata Kuliah:** Praktikum Analisis dan Desain Berorientasi Objek  
**NIM / Nama:** 2406087 / Muhammad Dzikri Shiddiq Muttaqin  
**Tanggal:** 11 November 2026  
**Kode File:** P05_2406087_jobsheet_review_v01.md  

---

## A. Identitas Artefak dan Workspace Pertemuan 5

1. **Dokumen Skenario Studi Kasus Laboratorium (LAB):**
   * Workspace: `01_skenario/P05_2406087_LAB_skenario_v01.md` (Memuat 12 Tabel Skenario)
   * Diagram Acuan: `04_model_analisis/P04/LAB/P04_2406087_LAB_usecase_v01.drawio`

2. **Dokumen Skenario Tugas Akademik (SIA - Layanan Hasil Studi):**
   * Workspace: `01_skenario/P05_2406087_SIA_skenario_v01.md` (Memuat 7 Tabel Skenario)
   * Diagram Acuan: `04_model_analisis/P04/SIA/P04_2406087_SIA_usecase_v01.drawio`

---

## B. Pengujian dan Pemetaan Relasi Diagram ke Skenario

1. **Pemetaan Relasi `<<include>>`:**
   * Ditulis sebagai langkah rujukan wajib di dalam Skenario Normal tanpa menyalin ulang langkah detailnya.
   * *Contoh:* `LAB-UC03 Ajukan Peminjaman` memanggil `LAB-UC04 Periksa Ketersediaan` pada langkah 2.

2. **Pemetaan Relasi `<<extend>>`:**
   * Ditulis sebagai cabang bersyarat pada Skenario Alternative lengkap dengan condition `[mahasiswa memilih cetak]` dan extension point `Bukti pengajuan tersedia` yang merujuk ke `LAB-UC05 Cetak Bukti Pengajuan`.

3. **Penerapan Generalization Aktor:**
   * Skenario ditulis satu kali atas nama Aktor Umum (`Peminjam` untuk LAB dan `Civitas Akademika` untuk SIA) dengan catatan keterlakuan bagi aktor khusus (`Mahasiswa` / `Dosen`).

4. **Penerapan Generalization Use Case:**
   * Use case umum (`LAB-UC02` / `SIA-UC10`) memuat skenario langkah bersama, sedangkan use case khusus (Tambah, Ubah, Hapus) hanya memuat langkah pembeda.

5. **Pencatatan Collaboration:**
   * Collaboration `LAB-CO01`, `LAB-CO02`, `SIA-CO01`, dan `SIA-CO02` dicatat pada bagian keterangan tabel tanpa diberi penomoran langkah tersendiri.

---

## C. Lembar Checklist Verifikasi Skenario P05

| No | Indikator Pemeriksaan | Status | Catatan Penelusuran Review |
|:--:|:---|:---:|:---|
| 1 | Kelengkapan Field Tabel | ✓ | Seluruh 19 tabel memuat field lengkap dari Nama Use Case hingga Skenario Akhir. |
| 2 | Pemisahan Kolom & Penomoran | ✓ | Kolom `Kegiatan` berisi aksi aktor, `Respon sistem` berisi aksi sistem, penomoran berlanjut ke Skenario Alternative. |
| 3 | Konsistensi ID & Nama | ✓ | Seluruh ID (LAB-UC01 s.d. UC12 / SIA-UC07 s.d. UC13), Nama, Aktor, Condition, dan Extension Point sama persis dengan Diagram P04. |
| 4 | Kasus Khusus Kepala Lab | ✓ | `LAB-UC07 Lihat Laporan Peminjaman` berdiri sendiri tanpa relasi include/extend/generalization. |

---

## D. Catatan Perbaikan & Status Model
* **Kesesuaian Versi:** Berkas P04 tidak diubah dan dipertahankan sebagai acuan. Dokumen skenario disimpan di folder `01_skenario/` dengan format markdown/drawio sesuai SOP.
* **Status Model:** 12 Tabel Skenario LAB dan 7 Tabel Skenario SIA dinyatakan **Valid** dan siap dilanjutkan ke Activity Diagram.