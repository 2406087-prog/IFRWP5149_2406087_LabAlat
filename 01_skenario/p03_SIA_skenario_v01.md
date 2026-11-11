# Kebutuhan Sistem Informasi Akademik (SIA)

## 1. Tujuan Sistem
Sistem  digunakan untuk membantu mahasiswa mengajukan Kartu Rencana Studi (KRS) dan membantu dosen wali memproses keputusan pengajuan KRS.
Mahasiswa mengajukan KRS dengan memilih mata kuliah. Setiap pengajuan menjalankan validasi KRS yang memeriksa kelengkapan, prasyarat mata kuliah, dan benturan jadwal. Jika validasi berhasil, sistem menyimpan pengajuan berstatus menunggu persetujuan dosen wali. Pada konfirmasi penyimpanan, mahasiswa dapat memilih mengunduh bukti pengajuan. Dosen wali menyetujui atau menolak KRS dan memberikan catatan keputusan.
## 2. Kebutuhan Sistem
- SIA-R01: Mahasiswa dapat melihat jadwal kuliah.
- SIA-R02: Admin akademik dapat mengelola jadwal kuliah.
- SIA-R03: Mahasiswa dapat mengajukan KRS.
- SIA-R04: Sistem memvalidasi KRS sebagai bagian dari pengajuan.
- SIA-R05: Mahasiswa dapat mengunduh bukti pengajuan jika memilihnya.
- SIA-R06: Dosen wali dapat menyetujui atau menolak KRS.

Ketentuan ini fiktif untuk praktikum. Batas SKS, aturan pembayaran, dan kewenangan institusi nyata tidak boleh ditambahkan tanpa sumber.
____________________________________________________________________________________________
|     ID     |                      Kebutuhan tugas                                         |
|____________|______________________________________________________________________________|
|   SIA-R01  | Mahasiswa dapat melihat jadwal kuliah                                        |
|   SIA-R02  | Admin akademik dapat mengelola jadwal kuliah                                 |  
|   SIA-R03  | Mahasiswa dapat mengajukan KRS                                               |
|   SIA-R04  | Sistem memvalidasi KRS sebagai bagian pengajuan                              |
|   SIA-R05  | Mahasiswa dapat mengunduh bukti jika memilihnya pada konfirmasi pengajuan    |
|   SIA-R06  | Dosen wali dapat memproses persetujuan atau penolakan KRS                    |
|____________|______________________________________________________________________________|

## 3. Aturan dan Asumsi
- Pengguna telah login dan memiliki hak akses sesuai perannya.
- Data mata kuliah, prasyarat, dan jadwal tersedia.
- Jika validasi gagal, pengajuan tidak berhasil disimpan.
- Pengajuan yang berhasil disimpan berstatus menunggu persetujuan dosen wali.
- Pengunduhan bukti tidak wajib.
- KRS yang tersimpan belum tentu disetujui.

## 4. Batas Sistem
Pembayaran, pengisian nilai, dan implementasi basis data tidak termasuk dalam tugas ini.
Kode dimulai dari R03 agar kebutuhan jadwal SIA-R01 dan SIA-R02 dari Pertemuan 2 tetap mempunyai identitas berbeda.
Batas dan asumsi:
• Pengguna telah terautentikasi.
• Data mata kuliah, prasyarat, dan jadwal tersedia.
• Validasi gagal menyebabkan pengajuan belum berhasil tersimpan.
• Unduh bukti tidak menjadi syarat keberhasilan pengajuan.
• KRS tersimpan belum berarti disetujui.
• Pembayaran, pengisian nilai, dan implementasi basis data berada di luar tugas.
_________________________________________________________________________________________________________________________
|         Aktor         |                                    Tujuan terhadap sistem                                     |
|_______________________|_______________________________________________________________________________________________|
|Mahasiswa              | Melihat Jadwal, Mengajukan KRS, mengunduh bukti pengajuan KRS jika diinginkan.                |
|Dosen Wali             | Memproses pengajuan KRS atau menolak pengajuan.                                               |
|Admin Akademik         | Mengelola Jadwal Kuliah                                                                       |
|Sistem                 | Memvalidasi KRS Sebagai bagian dari pengajian                                                 |
|_______________________|_______________________________________________________________________________________________|
