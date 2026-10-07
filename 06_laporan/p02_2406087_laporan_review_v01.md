# Laporan Review Notasi Use Case Diagram (SIA)

## Tabel Analisis Temuan Kesalahan dan Perbaikan

| No. | Temuan Kesalahan | Perbaikan yang Diperlukan | Alasan (Sesuai Standar UML) |
| :---: | :--- | :--- | :--- |
| 1* | Aktor Mahasiswa diletakkan di dalam batas sistem (*System Boundary*). | Pindahkan aktor **Mahasiswa** ke luar batas sistem (di sisi kiri). | Aktor merupakan entitas eksternal yang berinteraksi dengan sistem, sehingga posisinya harus berada di luar batas sistem. |
| 2 | Fungsi **Lihat jadwal kuliah** digambar menggunakan bentuk persegi panjang/kotak. | Ubah bentuk **Lihat jadwal kuliah** dari persegi panjang menjadi bentuk elips (*ellipse*). | Menurut standar UML, fungsi/aksi (*use case*) wajib digambarkan dengan simbol elips, bukan kotak. |
| 3| Aktor **Mahasiswa** terhubung dengan *use case* **Kelola jadwal kuliah**. | Hapus garis tersebut dan hubungkan **Mahasiswa** hanya ke *use case* **Lihat jadwal kuliah**. | Sesuai skenario, Mahasiswa hanya berhak melihat jadwal, sedangkan pengelolaan jadwal adalah wewenang penuh Admin akademik. |
| 4 | Judul pada batas sistem (*System Boundary*) menggunakan nama sistem laboratorium. | Ubah judul batas sistem menjadi **Sistem Informasi Akademik**. | Nama sistem pada diagram harus konsisten dengan konteks dan skenario kasus yang sedang digarap (SIA). |
> Garis asosiasi (*Association*) pada *Use Case Diagram* hanya menggambarkan **keterlibatan/partisipasi aktor** dalam suatu fungsi (*use case*). Asosiasi tidak menunjukkan urutan kronologis, langkah demi langkah, ataupun aliran data antar-fungsi. Urutan alur proses kegiatan digambarkan pada jenis diagram lain seperti *Activity Diagram* atau *Sequence Diagram*.