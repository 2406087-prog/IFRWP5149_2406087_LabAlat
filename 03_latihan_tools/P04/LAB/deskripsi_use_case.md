# Deskripsi Use Case LAB-UC11: Catat Pengembalian Peralatan

| Elemen | Keterangan |
| :--- | :--- |
| **ID dan Nama** | LAB-UC11: Catat Pengembalian Peralatan |
| **Sumber Kebutuhan** | LAB-R09 dan LAB-R10 |
| **Tujuan** | Pengembalian tercatat dan status peminjaman serta kondisi peralatan terbarui |
| **Aktor Utama** | Petugas Laboratorium |
| **Pemicu** | Petugas memilih fungsi pencatatan pengembalian dan menentukan peminjaman yang akan dikembalikan |
| **Prasyarat** | Petugas telah terautentikasi; peminjaman terpilih berstatus Dipinjam |
| **Pascakondisi Berhasil** | Pengembalian tercatat dengan tanggal kembali dan kondisi peralatan; status peminjaman menjadi Selesai |
| **Pascakondisi Gagal** | Tidak ada pengembalian baru yang tercatat; status peminjaman tidak berubah |
| **Include** | LAB-UC12: Periksa Kondisi Peralatan |
| **Collaboration** | LAB-CO02: Catat Pengembalian Peralatan |

### Alur Utama (Main Flow)
| Langkah | Tindakan Petugas | Respons Sistem |
| :---: | :--- | :--- |
| **1** | Memilih peminjaman yang akan dikembalikan | Menampilkan data peminjaman terpilih dan statusnya |
| **2** | Mengonfirmasi alat yang kembali dan jumlahnya | Menampung konfirmasi petugas |
| **3** | *(Tidak ada)* | Memeriksa status peminjaman harus Dipinjam |
| **4** | *(Tidak ada)* | Menjalankan LAB-UC12: memeriksa dan mencatat kondisi peralatan |
| **5** | Menyimpan pencatatan pengembalian | Menyimpan tanggal kembali dan kondisi; mengubah status peminjaman menjadi Selesai |
| **6** | Melihat konfirmasi | Menampilkan ringkasan pengembalian |

### Alur Alternatif / Pengecualian
* **A1: Status bukan Dipinjam (Langkah 3)**: Sistem menolak pencatatan dan menampilkan status peminjaman saat ini. Pascakondisi gagal berlaku; tidak ada data yang disimpan.
* **A2: Kondisi Rusak Ringan atau Rusak Berat (Langkah 4)**: Sistem tetap menyimpan pencatatan, menandai kondisi tersebut pada data peralatan, dan pengembalian tetap tercatat.
* **A3: Jumlah alat yang kembali tidak sesuai (Langkah 2)**: Sistem meminta petugas memeriksa kembali isian sebelum penyimpanan; pencatatan tidak disimpan sampai jumlah sesuai.