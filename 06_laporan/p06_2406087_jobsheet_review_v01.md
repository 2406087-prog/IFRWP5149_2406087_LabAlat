# Laporan Review & Pengujian Jobsheet Pertemuan 6
**Mata Kuliah:** Praktikum Analisis dan Desain Berorientasi Objek  
**NIM / Nama:** 2406087 / Muhammad Dzikri Shiddiq Muttaqin  
**Tanggal:** 11 November 2026  
**Kode File:** P06_2406087_jobsheet_review_v01.md  

---

## A. Identitas Artefak dan Workspace Pertemuan 6

1. **Workspace Activity Diagram Studi Kasus Laboratorium (LAB):**
   * `04_model_analisis/P06/LAB/P06_2406087_LAB_activity_lihat_ketersediaan_v01.drawio` & `.png` (LAB-UC01)
   * `04_model_analisis/P06/LAB/P06_2406087_LAB_activity_kelola_data_v01.drawio` & `.png` (LAB-UC02, UC08, UC09, UC10)
   * `04_model_analisis/P06/LAB/P06_2406087_LAB_activity_peminjaman_v01.drawio` & `.png` (LAB-UC03, include UC04, extend UC05)
   * `04_model_analisis/P06/LAB/P06_2406087_LAB_activity_cetak_bukti_v01.drawio` & `.png` (LAB-UC05)
   * `04_model_analisis/P06/LAB/P06_2406087_LAB_activity_keputusan_v01.drawio` & `.png` (LAB-UC06)
   * `04_model_analisis/P06/LAB/P06_2406087_LAB_activity_pengembalian_v01.drawio` & `.png` (LAB-UC11, include UC12)
   * `04_model_analisis/P06/LAB/P06_2406087_LAB_activity_laporan_v01.drawio` & `.png` (LAB-UC07)

2. **Workspace Activity Diagram Tugas Akademik (SIA):**
   * `04_model_analisis/P06/SIA/P06_2406087_SIA_activity_v01.drawio` & `.png` (Input Nilai s.d. Lihat KHS)

---

## B. Pengujian dan Penelusuran Activity Diagram P06

1. **Kontinuitas & Guard Decision:**
   * Setiap diagram memiliki tepat 1 *Initial Node* dan minimal 1 *Activity Final Node*.
   * Cabang *Decision* dilengkapi *guard* dalam kurung siku `[...]` yang saling lepas dan menutup seluruh kemungkinan (misal `[baik dan lengkap]` dan `[rusak atau tidak lengkap]`).

2. **Penggunaan Swimlane (Partisi Aktivitas):**
   * Aksi aktor manusia berada di *swimlane* aktor terkait, aksi sistem berada di *swimlane* Sistem. Aktor `Kepala Laboratorium` hanya muncul pada Activity Laporan.

3. **Penerapan Fork & Join:**
   * **LAB (Pengembalian):** Membagi proses paralel `Periksa Kondisi Peralatan` dan `Periksa kelengkapan aksesori peralatan` (unsur proses baru), disatukan kembali oleh *Join*.
   * **SIA (Hasil Studi):** Membagi proses paralel `Menerbitkan KHS` dan `Mengirim pemberitahuan hasil studi`, disatukan oleh *Join* sebelum `Melihat KHS`.

4. **Integrasi Include, Extend, dan Varian Pengelolaan:**
   * Use Case *Include* menjadi *action* wajib pada alur utama.
   * Use Case *Extend* menjadi cabang bersyarat `[ya, memilih cetak]`.
   * Varian Kelola Data dilipat menjadi 3 cabang (`[tambah]`, `[ubah]`, `[hapus]`) di dalam satu diagram.

---

## C. Lembar Checklist Verifikasi Activity Diagram P06

| No | Indikator Modul | Status | Catatan Review |
|:--:|:---|:---:|:---|
| 1 | Node Awal & Akhir | ✓ | Tepat 1 *Initial Node*, tidak ada *action* yang terputus dari alur. |
| 2 | Guard Decision | ✓ | Semua alur keluar dari *Decision* memiliki label *guard* yang sah. |
| 3 | Pasangan Fork & Join | ✓ | Seluruh proses paralel disatukan oleh *Join* (bukan *Merge*). |
| 4 | Keterlacakan Skenario | ✓ | Nama *action* dan urutan alur sama persis dengan tabel skenario P05. |
| 5 | Kelengkapan File LAB & SIA | ✓ | 7 file diagram LAB + 1 file diagram SIA lengkap beserta ekspor `.png` versi `v01`. |

---

## D. Catatan Revisi & Status Pekerjaan
* **Status Perbaikan:** Seluruh diagram `P06` telah lulus uji kelayakan checklist.
* **Status Akhir Proyek:** Tugas Praktikum Pertemuan 1 sampai 6 telah selesai dikerjakan dan siap diarsipkan (`.zip`) untuk diunggah ke LMS.