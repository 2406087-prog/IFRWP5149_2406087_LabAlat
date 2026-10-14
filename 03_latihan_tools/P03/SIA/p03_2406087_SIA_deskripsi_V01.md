Tabel Elemen Use Case Description:
|       Elemen       |                             Isi                             |
|--------------------|-------------------------------------------------------------|
|     IDdanNama      |                     SIA-UC01 Ajukan KRS                     |
|  SumberKebutuhan   |                  SIA-R03, SIA-R04, SIA-R05                  |
|       Tujuan       |   Menyimpan pengajuan KRS berstatus Menunggu Persetujuan    |
|     AktorUtama     |                          Mahasiswa                          |
|       Pemicu       |            Mahasiswa memilih menu pengajuan KRS             |
|     Prasyarat      |Mahasiswa terautentikasi; data mata kuliah & jadwal tersedia |
|PascakondisiBerhasil| Pengajuan KRS tersimpan dengan status Menunggu Persetujuan  |
| PascakondisiGagal  |                Pengajuan KRS tidak tersimpan                |
|      Include       |                    SIA-UC02 Validasi KRS                    |
|   ExtensionPoint   |          Bukti pengajuan tersedia, pada langkah 6           |
|       Extend       |           SIA-UC03 jika [mahasiswa memilih unduh]           |

Tabel Alur Utama:
|Langkah|       TindakanAktor        |                      Respond sitem                      l
|-------|----------------------------|---------------------------------------------------------|
|   1   |   MembukmenupengajuanKRS   |       Menampilkan formulir pemilihan mata kuliah        |
|   2   |     Memilihmatakuliah      |              Menampung pilihan mata kuliah              |
|   3   |    MengirimpengajuanKRS    |               Memeriksa kelengkapan data                |
|   4   |             -              |            Menjalankan SIA-UC02 Validasi KRS            |
|   5   |             -              |Jika valid, menyimpan KRS berstatus Menunggu Persetujuan |
|   6   |Melihatkonfirmasipenyimpanan|     Menampilkan status konfirmasi (extension point)     |
|   7   |      Mengakhiriproses      |               Menutup formulir pengajuan                |

Alur Alternatif / Pengecualian
4a. Validasi Gagal: Jika validasi pada SIA-U menyatakan data tidak lengkap, melanggar prasyarat, atau bentrok jadwal, sistem menampilkan pesan kesalahan dan proses berakhir tanpa menyimpan pengajuan.
6a. Unduh Bukti: Pada langkah 6, jika mahasiswa memilih mengunduh bukti, sistem menjalankan SIA-UC03 Unduh bukti pengajuan KRS

<!-- deskripsi skenario -->
Mahasiswa mengajukan KRS dengan memilih mata kuliah. Setiap pengajuan menjalankan validasi KRS yang memeriksa kelengkapan, prasyarat mata kuliah, dan benturan jadwal. Jika validasi berhasil, sistem menyimpan pengajuan berstatus menunggu persetujuan dosen wali. Pada konfirmasi penyimpanan, mahasiswa dapat memilih mengunduh bukti pengajuan. Dosen wali menyetujui atau menolak KRS dan memberikan catatan keputusan.

<!-- tabel kebutuhan -->
 ID Kebutuhan 
SIA-R03  Mahasiswa dapat mengajukan KRS 
SIA-R04 Sistem memvalidasi KRS sebagai bagian pengajuan 
 SIA-R05  Mahasiswa dapat mengunduh bukti jika memilihnya pada konfirmasi pengajuan 
 SIA-R06  Dosen wali dapat memproses persetujuan atau penolakan KRS 

<!-- batas sistem dan aturan -->
Batas sistem dan aturan:
* Pengguna telah terautentikasi.
* Data mata kuliah, prasyarat, dan jadwal tersedia.
* Validasi gagal menyebabkan pengajuan belum berhasil tersimpan.
* Unduh bukti tidak menjadi syarat keberhasilan pengajuan.
* KRS tersimpan belum berarti disetujui.
* Pembayaran, pengisian nilai, dan implementasi basis data berada di luar tugas.

<!-- tabel aktor -->
| Aktor | Tujuan |
|---|---|
| Mahasiswa | Mengajukan KRS dan mengunduh bukti pengajuan |
| Dosen Wali | Memproses keputusan (persetujuan/penolakan) KRS |

<!-- tabel katalog use case -->
| ID | Name Use Case | Peran Dalam Model |
|---|---|---|
| SIA-UC01  Ajukan KRS  Fungsi utama mahasiswa 
| SIA-UC02  Validasi KRS  Perilaku yang disertakan UC01 
| SIA-UC03  Unduh bukti pengajuan KRS  Tambahan bersyarat pada UC01 
| SIA-UC04  Proses keputusan KRS  Fungsi utama dosen wali 

<!-- relasi include -->
SIA-UC01 <<include>> SIA-UC02
Alasan: Validasi KRS (kelengkapan, prasyarat, dan benturan jadwal) wajib dilakukan pada setiap pengajuan KRS.

<!-- relasi extend -->
SIA-UC03 <<extend>> SIA-UC01
Extension point: Bukti pengajuan tersedia
Kondisi: [mahasiswa memilih unduh]
Alasan: Pengajuan KRS tetap berhasil tersimpan meskipun mahasiswa tidak mengunduh bukti.