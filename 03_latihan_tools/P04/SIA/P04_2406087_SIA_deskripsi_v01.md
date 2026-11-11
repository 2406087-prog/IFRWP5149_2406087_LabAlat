# Kebutuhan Sistem Informasi Akademik (SIA)

## 1. Tujuan Sistem
Mahasiswa dan dosen sama-sama merupakan Civitas Akademika yang dapat melihat kalender akademik. Dosen menginput nilai mata kuliah yang diampunya setelah masa perkuliahan berakhir. Mahasiswa melihat Kartu Hasil Studi (KHS) untuk semester yang nilainya sudah dipublikasikan. Admin Akademik mengelola data mahasiswa: menambah data mahasiswa baru, mengubah data mahasiswa, dan menghapus data mahasiswa. Dua use case utama, Input Nilai Mata Kuliah dan Lihat KHS, ditunjukkan realisasinya oleh collaboration yang bersesuaian.

## 2. Kebutuhan Sistem
- SIA-R01: Mahasiswa dapat melihat jadwal kuliah.
- SIA-R02: Admin akademik dapat mengelola jadwal kuliah.
- SIA-R03: Mahasiswa dapat mengajukan KRS.
- SIA-R04: Sistem memvalidasi KRS sebagai bagian dari pengajuan.
- SIA-R05: Mahasiswa dapat mengunduh bukti pengajuan jika memilihnya.
- SIA-R06: Dosen wali dapat menyetujui atau menolak KRS.

Ketentuan ini fiktif untuk praktikum. Batas SKS, aturan pembayaran, dan kewenangan institusi nyata tidak boleh ditambahkan tanpa sumber.
____________________________________________________________________________________________________________________
|     ID     |                      Kebutuhan tugas                                                                |
|____________|_____________________________________________________________________________________________________|
|   SIA-R01  | Mahasiswa dapat melihat jadwal kuliah                                                               |
|   SIA-R02  | Admin akademik dapat mengelola jadwal kuliah                                                        |  
|   SIA-R03  | Mahasiswa dapat mengajukan KRS                                                                      |
|   SIA-R04  | Sistem memvalidasi KRS sebagai bagian pengajuan                                                     |
|   SIA-R05  | Mahasiswa dapat mengunduh bukti jika memilihnya pada konfirmasi pengajuan                           |
|   SIA-R06  | Dosen wali dapat memproses persetujuan atau penolakan KRS                                           |
|   SIA-R07  | Mahasiswa dan Dosen, sebagai Civitas Akademika, dapat melihat kalender akademik.                    |
|   SIA-R08  | Dosen dapat menginput nilai mata kuliah yang diampunya.                                             |
|   SIA-R09  | Mahasiswa dapat melihat KHS untuk semester yang nilainya sudah dipublikasikan.                      |
|   SIA-R10  | Admin Akademik dapat mengelola data mahasiswa.                                                      |
|   SIA-R11  | Pengelolaan data mahasiswa terdiri dari tiga bentuk khusus: tambah, ubah, dan hapus data mahasiswa. |
|   SIA-R12  | Model menunjukkan collaboration yang merealisasikan Input Nilai Mata Kuliah dan Lihat KHS.          |
|____________|_____________________________________________________________________________________________________|

## 3. Asumsi & Batas Sistem
Pembayaran, pengisian nilai, dan implementasi basis data tidak termasuk dalam tugas ini.
Kode dimulai dari R03 agar kebutuhan jadwal SIA-R01 dan SIA-R02 dari Pertemuan 2 tetap mempunyai identitas berbeda.
Batas dan asumsi:
Batas sistem dan aturan
• Pengguna telah terautentikasi.
• Data mata kuliah, prasyarat, dan jadwal tersedia.
• Validasi gagal menyebabkan pengajuan belum berhasil tersimpan.
• Unduh bukti tidak menjadi syarat keberhasilan pengajuan.
• KRS tersimpan belum berarti disetujui.
• Pembayaran, pengisian nilai, dan implementasi basis data berada di luar tugas.
• Kode kebutuhan dimulai dari SIA-R07 agar SIA-R01 dan SIA-R02 (Pertemuan 2) serta SIA-R03 sampai SIA-R06 (Pertemuan 3) tetap mempunyai identitas berbeda.
• Pengguna telah terautentikasi dan memiliki hak akses sesuai peran.
• Kalender akademik pada tugas ini adalah agenda resmi institusi (awal semester, batas KRS, masa ujian, dan sejenisnya); jangan menyamakannya dengan jadwal kuliah pada Pertemuan 2
• Nilai hanya dapat diinput oleh dosen pengampu mata kuliah tersebut. Nilai yang diinput belum terpublikasi sebelum dinyatakan resmi oleh ketentuan tugas ini: KHS hanya menampilkan nilai yang sudah dipublikasikan.
• Hapus Data Mahasiswa hanya untuk mahasiswa yang tidak memiliki data akademik aktif. Ketentuan ini fiktif untuk latihan.
• Pengajuan KRS tetap digambar sebagai bagian diagram kumulatif dari Pertemuan 3. Pembayaran dan perancangan basis data berada di luar tugas ini.