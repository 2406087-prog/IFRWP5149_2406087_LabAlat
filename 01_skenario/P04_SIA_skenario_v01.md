# Katalog Use Case Kumulatif SIA (Pertemuan 4)

| ID | Nama Use Case | Aktor Terkait | Peran dalam Model | Sumber Kebutuhan |
| :--- | :--- | :--- | :--- | :--- |
| **SIA-UC01** | Lihat Jadwal Kuliah | Civitas Akademika | Tetap dari P02; fungsi umum Civitas Akademika | SIA-R01 |
| **SIA-UC02** | Kelola Jadwal Kuliah | Admin Akademik | Tetap dari P02; fungsi utama Admin Akademik | SIA-R02 |
| **SIA-UC03** | Ajukan KRS | Mahasiswa | Tetap dari P03; menyertakan SIA-UC04 | SIA-R03 |
| **SIA-UC04** | Validasi KRS | Dosen Wali | Tetap dari P03; perilaku yang disertakan SIA-UC03 | SIA-R04 |
| **SIA-UC05** | Unduh Bukti Pengajuan KRS | Mahasiswa | Tetap dari P03; tambahan bersyarat pada SIA-UC03 («extend») | SIA-R05 |
| **SIA-UC06** | Proses Keputusan KRS | Dosen Wali | Tetap dari P03; fungsi utama Dosen Wali | SIA-R06 |
| **SIA-UC07** | Lihat Kalender Akademik | Civitas Akademika | Baru pada P04; fungsi umum Civitas Akademika | SIA-R07 |
| **SIA-UC08** | Input Nilai Mata Kuliah | Dosen | Baru pada P04; fungsi utama Dosen; direalisasikan SIA-CO01 | SIA-R08, SIA-R12 |
| **SIA-UC09** | Lihat KHS | Mahasiswa | Baru pada P04; fungsi utama Mahasiswa; direalisasikan SIA-CO02 | SIA-R09, SIA-R12 |
| **SIA-UC10** | Kelola Data Mahasiswa | Admin Akademik | Baru pada P04; use case UMUM bagi SIA-UC11, SIA-UC12, SIA-UC13 | SIA-R10, SIA-R11 |
| **SIA-UC11** | Tambah Data Mahasiswa | Admin Akademik | Baru pada P04; use case KHUSUS dari SIA-UC10 | SIA-R11 |
| **SIA-UC12** | Ubah Data Mahasiswa | Admin Akademik | Baru pada P04; use case KHUSUS dari SIA-UC10 | SIA-R11 |
| **SIA-UC13** | Hapus Data Mahasiswa | Admin Akademik | Baru pada P04; use case KHUSUS dari SIA-UC10 | SIA-R11 |

## Keputusan Generalization & Collaboration
* **Generalization Aktor**: Mahasiswa dan Dosen mewarisi fungsi Civitas Akademika (SIA-UC01 dan SIA-UC07).
* **Generalization Use Case**: SIA-UC11, SIA-UC12, dan SIA-UC13 mewarisi fungsi umum SIA-UC10.
* **Collaboration**: 
  * `SIA-CO01: Input Nilai Mata Kuliah` -> Merealisasikan `SIA-UC08`
  * `SIA-CO02: Lihat KHS` -> Merealisasikan `SIA-UC09`