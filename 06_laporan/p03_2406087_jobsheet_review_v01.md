# Laporan Review Jobsheet Pertemuan 3
**Mata Kuliah:** Praktikum Analisis dan Desain Berorientasi Objek  
**NIM / Nama:** 2406087 / Muhammad Dzikri Shiddiq Muttaqin
**Tanggal:** 14 Oktober 2026  
**Kode File:** P03_2406087_jobsheet_review_v01.md  

---

## A. Identitas Artefak dan Kasus
1. **Kasus Latihan Laboratorium (LAB):**
   * Workspace: `03_latihan_tools/P03/LAB/P03_2406087_LAB_usecase_v01.drawio`
   * Gambar Ekspor: `03_latihan_tools/P03/LAB/P03_2406087_LAB_usecase_v01.png`
   * Deskripsi: `03_latihan_tools/P03/LAB/P03_2406087_LAB_deskripsi_v01.md`
2. **Kasus Tugas Akademik (SIA):**
   * Workspace: `03_latihan_tools/P03/SIA/P03_2406087_SIA_usecase_v01.drawio`
   * Gambar Ekspor: `03_latihan_tools/P03/SIA/P03_2406087_SIA_usecase_v01.png`
   * Deskripsi: `03_latihan_tools/P03/SIA/P03_2406087_SIA_deskripsi_v01.md`

---

## B. Pengujian Konsistensi Model SIA

Pengujian dilakukan untuk memastikan konsistensi antara skenario, diagram UML, dan deskripsi use case pada 3 kondisi berikut:

### 1. Skenario 1: Validasi Berhasil & Mahasiswa Tidak Mengunduh Bukti
* **Jalur Alur:** `SIA-UC01 Ajukan KRS` -> `SIA-UC02 Validasi KRS` (Hasil: Valid) -> KRS Tersimpan (Status: Menunggu Persetujuan) -> Selesai.
* **Hasil Review:** Konsisten. Mahasiswa berhasil mengajukan KRS tanpa mengeksekusi use case `SIA-UC03 Unduh bukti pengajuan KRS`. Hal ini membuktikan bahwa relasi `<<extend>>` bersifat opsional dan tidak menggagalkan alur utama.

### 2. Skenario 2: Validasi Gagal
* **Jalur Alur:** `SIA-UC01 Ajukan KRS` -> `SIA-UC02 Validasi KRS` (Hasil: Gagal / Bentrok Jadwal / Prasyarat Belum Terpenuhi) -> Pesan Error Ditampilkan -> Alur Berakhir.
* **Hasil Review:** Konsisten. Pengajuan KRS tidak berhasil tersimpan ke sistem (Pascakondisi Gagal terpenuhi). Relasi `<<include>>` terbukti menjadi syarat mutlak sebelum penyimpanan pengajuan dilakukan.

### 3. Skenario 3: Validasi Berhasil & Mahasiswa Memilih Mengunduh Bukti
* **Jalur Alur:** `SIA-UC01 Ajukan KRS` -> `SIA-UC02 Validasi KRS` (Hasil: Valid) -> KRS Tersimpan -> Mencapai Extension Point di Langkah 6 -> Memanggil `SIA-UC03 Unduh bukti pengajuan KRS` -> File Bukti Terunduh.
* **Hasil Review:** Konsisten. Eksekusi `SIA-UC03` terbukti dipicu oleh kondisi `[mahasiswa memilih unduh]` pada extension point yang ditetapkan.

---

## C. Lembar Checklist Verifikasi Model

||No|Indikator| Pemeriksaan |  Status   | Catatan | Review |                                                                                              |
||--|---------|-------------|-----------|---------|--------|----------------------------------------------------------------------------------------------|
||1 | Setiap  |    aktor    | mempunyai |interaksi|  yang  |             jelas ✓ Mahasiswa & Dosen Wali terhubung dengan asosiasi yang tepat              |
||2 |   Use   |    case     |  berada   |   di    | dalam  |batas sistem (*system boundary*) ✓ Seluruh 4 elips use case berada di dalam batas sistem SIA  |
||3 | Relasi  |`<<include>>`| mengarah  |   ke    |perilaku|               yang disertakan ✓ Panah dari `SIA-UC01` mengarah ke `SIA-UC02`                 |
||4 | Relasi  |`<<extend>>` | mengarah  |   ke    |  use   |                  case dasar ✓ Panah dari `SIA-UC03` mengarah ke `SIA-UC01`                   |
||5 |Extension|    point    |  berada   |  pada   |  use   |              case dasar ✓ Extension point dituliskan pada langkah 6 `SIA-UC01`               |
||6 | Kondisi |   extend    | tercantum |  dalam  |diagram |                  dan deskripsi ✓ Diberi label `[mahasiswa memilih unduh]`                    |
||7 |Pengajuan|    tetap    | berhasil  |  tanpa  |perilaku|                        tambahan ✓ Terbukti pada Pengujian Skenario 1                         |
||8 |Prasyarat|  dibedakan  |   dari    |perilaku |include |                  ✓ Autentikasi menjadi prasyarat, validasi menjadi include                   |
||9 |  Alur   | alternatif  |menjelaskan|kegagalan|  dan   |                hasil akhirnya ✓ Dicantumkan pada alur alternatif langkah 4a                  |
||10| Diagram |     dan     | deskripsi | memakai |  nama  |         serta ID yang sama ✓ Menggunakan ID SIA-UC01 s.d. SIA-UC04 secara konsisten          |
||11| Sumber  |  `.drawio`  |    dan    |  hasil  | ekspor |                `.png` sesuai ✓ Berkas tersimpan dengan versi yang sama (v01)                 |


---

## D. Catatan Perbaikan & Riwayat Revisi
* **Perbaikan Notasi Diagram:** Memastikan garis asosiasi aktor menggunakan garis lurus tanpa kepala panah, serta membenarkan arah kepala panah terbuka pada relasi `<<include>>` dan `<<extend>>`.
* **Status Model:** Latihan Use Case Diagram Pertemuan 3 telah memenuhi seluruh standar kriteria penerimaan modul.