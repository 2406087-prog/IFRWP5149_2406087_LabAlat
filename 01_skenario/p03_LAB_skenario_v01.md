Mahasiswa mengajukan peminjaman peralatan dengan memilih alat,
jumlah, dan rentang waktu. Sistem memeriksa ketersediaan. Jika
tersedia dan data lengkap, sistem menyimpan pengajuan berstatus
menunggu keputusan. Pada tampilan konfirmasi, mahasiswa dapat
memilih mencetak bukti pengajuan. Petugas mengelola data peralatan
serta menyetujui atau menolak pengajuan. Kepala laboratorium melihat
laporan peminjaman.
|  ID   |                                            Kebutuhan                                            |
|-------|-------------------------------------------------------------------------------------------------|
|LAB-R01|                         Mahasiswa dapat melihat ketersediaan peralatan                          |
|LAB-R02|                             Petugas dapat mengelola data peralatan                              |
|LAB-R03|Mahasiswa dapat mengajukan peminjaman; sistem memeriksa ketersediaan sebelum menyimpan pengajuan |
|LAB-R04|            Mahasiswa dapat mencetak bukti pada konfirmasi pengajuan jika memilihnya             |
|LAB-R05|                  Petugas dapat menetapkan persetujuan atau penolakan pengajuan                  |
|LAB-R06|                      Kepala laboratorium dapat melihat laporan peminjaman                       |

LAB-R01 dan LAB-R02 mempertahankan fungsi yang diperkenalkan pada
Pertemuan 2. Kebutuhan berikutnya menambah ruang lingkup analisis tanpa
mengubah arti kebutuhan lama Batas sistem dan aturan:
• Sistem mencatat dan menyediakan informasi; perpindahan fisik alat tidak
terjadi di dalam perangkat lunak.
• Pengguna telah terautentikasi dan memiliki hak akses sesuai peran.
• Pengajuan yang diterima sistem berstatus Menunggu keputusan, bukan
otomatis Disetujui.
• Pengajuan dengan peralatan tidak tersedia tidak disimpan sebagai
pengajuan berhasil.
• Pencetakan bukti tidak menjadi syarat keberhasilan pengajuan.
• Persetujuan petugas belum dimodelkan sebagai reservasi teknis stok.
• Pengambilan, pengembalian, kondisi alat, dan denda belum dianalisis
pada potongan model ini.
Kriteria penerimaan model: semua kebutuhan di atas mempunyai
representasi, include dan extend mempunyai alasan yang jelas, serta diagram
konsisten dengan deskripsinya.

Langkah 2 — Tentukan aktor
Simpan tabel ringkas berikut pada 01_skenario/P03_LAB_skenario_v01.md

|       Aktor       |                      Tujuanterhadapsistem                      |
|-------------------|----------------------------------------------------------------|
|     Mahasiswa     |Melihat ketersediaan, mengajukan peminjaman, dan mencetak bukti |
|Petugaslaboratorium|          Mengelola peralatan dan memproses keputusan           |
|Kepalalaboratorium |                   Melihat laporan peminjaman                   |

Langkah 3 — Susun katalog use case

|   ID   |       Nama use case      |         Peran dalam model       |
|--------|--------------------------|---------------------------------|
|LAB-UC01|Lihatketersediaanperalatan|     Fungsi utama mahasiswa      |
|LAB-UC02|   Keloladataperalatan    |      Fungsi utama petugas       |
|LAB-UC03|     Ajukanpeminjaman     |     Fungsi utama mahasiswa      |
|LAB-UC04|   Periksaketersediaan    |  Perilaku yang disertakan UC03  |
|LAB-UC05|   Cetakbuktipengajuan    |  Tambahan bersyarat pada UC03   |
|LAB-UC06|Proseskeputusanpeminjaman |      Fungsi utama petugas       |
|LAB-UC07|  Lihatlaporanpeminjaman  |Fungsi utama kepala laboratorium |

Lihat ketersediaan menyediakan informasi untuk pengguna, sedangkan
Periksa ketersediaan memvalidasi alat, jumlah, dan rentang waktu dalam
pengajuan. Kedua fungsi tidak disamakan hanya karena memakai kata
“ketersediaan”

Langkah 4 — Tetapkan relasi
Tuliskan dua keputusan pemodelan:
LAB-UC03 «include» LAB-UC04
Alasan: pemeriksaan menjadi bagian validasi pengajuan.

LAB-UC05 «extend» LAB-UC03
Extension point: Bukti pengajuan tersedia.
Kondisi: [mahasiswa memilih cetak].
Alasan: pengajuan tetap berhasil tanpa pencetakan.

Simpan alasan tersebut pada jobsheet. Kondisi extend harus muncul pula
dalam deskripsi, bukan hanya pada diagram.

Langkah 5 — Tulis use case description utama
Gunakan contoh berikut sebagai model penulisan.

|       Elemen       |                   LAB-UC03—Ajukanpeminjaman                   |
|--------------------|---------------------------------------------------------------|
|       Tujuan       |       Menghasilkan pengajuan peminjaman yang tersimpan        |
|     Aktorutama     |                           Mahasiswa                           |
|  Sumberkebutuhan   |                      LAB-R03 dan LAB-R04                      |
|  PemicuMahasiswa   |              memilih fungsi pengajuan peminjaman              |
|     Prasyarat      |    Mahasiswa telah terautentikasi; data peralatan tersedia    |
|Pascakondisiberhasil|Pengajuan tersimpan dengan nomor dan status Menunggu keputusan |
| Pascakondisigagal  |       Tidak ada pengajuan baru yang berhasil tersimpan        |
|      Include       |                LAB-UC04 — Periksa ketersediaan                |
|   Extensionpoint   |           Bukti pengajuan tersedia, pada langkah 6            |
|       Extend       |            LAB-UC05 jika [mahasiswa memilih cetak]            |

Alur utama:

|Langkah|Tindakanmahasiswa|                          Responssistem                          |
|-------|-----------------|-----------------------------------------------------------------|
|   1   |     Membuka     |                 pengajuan Menampilkan formulir                  |
|   2   |     Memilih     |             alat, jumlah,rentang waktu, dan tujuan              |
|   3   |    Mengirim     |              pengajuan Memeriksa kelengkapan data               |
|   4   |        —        |                      Menjalankan LAB-UC04                       |
|   5   |        —        |      Jika tersedia, menyimpan pengajuandan memberikan nomo      |
|   6   |     Melihat     |konfirmasi Menampilkan nomor dan status;mencapai extension point |
|   7   |   Mengakhiri    |               pengajuan Menutup proses pengajuan                |

Langkah 6 — Gambar batas sistem dan elemen
Buka kakas yang digunakan pada Pertemuan 2.
a. Buat diagram baru.
b. Tambahkan batas sistem berjudul lengkap.
c. Letakkan tiga aktor di luar batas.
d. Letakkan tujuh use case di dalam batas.
e. Gunakan ID pada metadata atau katalog; nama fungsi pada elips tetap
mudah dibaca.

|   ID   |       Nama usecase       I  Perandalammodel                I
|--------|--------------------------|---------------------------------|
|LAB-UC01|Lihatketersediaanperalatan|     Fungsi utama mahasiswa      |
|LAB-UC02|   Keloladataperalatan    |      Fungsi utama petugas       |
|LAB-UC03|     Ajukanpeminjaman     |     Fungsi utama mahasiswa      |
|LAB-UC04|   Periksaketersediaan    |  Perilaku yang disertakan UC03  |
|LAB-UC05|   Cetakbuktipengajuan    |  Tambahan bersyarat pada UC03   |
|LAB-UC06|Proseskeputusanpeminjaman |      Fungsi utama petugas       |
|LAB-UC07|  Lihatlaporanpeminjaman  |Fungsi utama kepala laboratorium |

