a. Tujuan dan cakupan
Tugas ini MELANJUTKAN kasus SIA Pertemuan 4, bukan kasus baru.
Diagram acuannya adalah diagram SIA Pertemuan 4, dan kebutuhan
acuannya adalah SIA-R07 sampai SIA-R12 (lihat Jobsheet Pertemuan 4,
Tabel 4.6). Keterampilan baru pada tugas ini adalah penulisan skenario,
bukan perancangan kasus baru, sehingga mahasiswa tidak menambah use
case, aktor, atau kebutuhan di luar diagram SIA Pertemuan 4. Tidak ada
contoh jawaban SIA di dalam jobsheet ini.
Tabel 5.14 Indeks tugas skenario SIA
ID Nama use
case
Aktor Catatan pemetaan
SIA-UC07 Lihat
Kalender
Akademik
Civitas
Akademika
Ditulis satu kali atas nama Civitas
Akademika; berlaku untuk Mahasiswa
dan Dosen
SIA-UC08 Input Nilai
Mata Kuliah
Dosen Prasyarat: dosen pengampu mata
kuliah; alternatif: nilai di luar rentang
yang sah ditolak; direalisasikan SIACO01
SIA-UC09 Lihat KHS Mahasiswa Hanya nilai yang sudah dipublikasikan
yang ditampilkan; direalisasikan SIACO02
SIA-UC10 Kelola Data
Mahasiswa
Admin
Akademik
Skenario umum pengelolaan; langkah
bersama yang dirujuk UC11, UC12,
dan UC13
SIA-UC11 Tambah
Data
Mahasiswa
Admin
Akademik
Khusus dari UC10; perilaku pembeda:
data mahasiswa baru tersimpan
SIA-UC12 Ubah Data
Mahasiswa
Admin
Akademik
Khusus dari UC10; perilaku pembeda:
data mahasiswa berubah
SIA-UC13 Hapus Data
Mahasiswa
Admin
Akademik
Khusus dari UC10; perilaku pembeda:
data mahasiswa terhapus; syarat: tidak
ada data akademik aktif
b. Langkah-langkah
1) Langkah 1: Buka kembali diagram SIA Pertemuan 4 pada folder
04_model_analisis/P04/SIA hanya sebagai acuan. Jangan mengubah
isi diagram.
2) Langkah 2: Baca kembali kebutuhan SIA-R07 sampai SIA-R12 dan
katalog SIA-UC07 sampai SIA-UC13 pada jobsheet Pertemuan 4.
Tandai generalization aktor (Mahasiswa dan Dosen ke Civitas
Akademika) dan generalization use case (UC11, UC12, dan UC13 ke
UC10).
3) Langkah 3: Tulis tabel skenario untuk ketujuh use case pada Tabel
5.14 dengan struktur yang sama persis dengan Tabel 5.1: baris
Nama use case, Aktor, Tujuan, dan Deskripsi, kolom Kegiatan dan
Respon sistem, Skenario Normal, Skenario Alternative dengan
penomoran berlanjut, dan Skenario Akhir.

4) Langkah 4: Terapkan aturan generalization aktor pada UC07: tulis
satu tabel atas nama Civitas Akademika dengan catatan berlaku
untuk Mahasiswa dan Dosen.
5) Langkah 5: Terapkan aturan generalization use case: tulis skenario
umum UC10 sebagai perilaku bersama, lalu tulis tabel UC11, UC12,
dan UC13 yang masing-masing hanya memuat perilaku pembeda
dan merujuk ke skenario umum untuk langkah bersama.
6) Langkah 6: Sebutkan collaboration SIA-CO01 pada keterangan tabel
UC08 dan SIA-CO02 pada keterangan tabel UC09, tanpa langkah
kegiatan sendiri untuk collaboration.
7) Langkah 7: Periksa ketujuh tabel dengan checklist pada bagian C.4,
lalu simpan dalam satu dokumen LAB/
P05_<NIM>_LAB_skenario_v01.drawio pada folder 01_skenario.
c. Aturan khusus
• Pewarisan Civitas Akademika: Mahasiswa dan Dosen mewarisi Lihat
Kalender Akademik dari Civitas Akademika; asosiasi warisan tidak
digambar ulang dan skenario ditulis satu kali atas nama Civitas
Akademika.
• Nilai hanya dapat diinput oleh dosen pengampu mata kuliah tersebut.
• KHS hanya menampilkan nilai yang sudah dipublikasikan.
• Hapus Data Mahasiswa hanya untuk mahasiswa yang tidak memiliki
data akademik aktif.
• Diagram SIA Pertemuan 4 tidak diubah; produk tugas adalah
dokumen skenario, bukan diagram baru.
d. Penilaian
Penilaian tugas SIA memakai checklist pada bagian C.4 dan rubrik praktik
RPS. Checklist tersebut tidak disalin ulang pada bagian ini; periksa ketujuh
tabel SIA dengan butir yang sama, termasuk kelengkapan field, penomoran
berlanjut, pemisahan kolom, pemetaan include, extend, dan generalization,
serta kesamaan nama, ID, dan aktor dengan diagram SIA Pertemuan 4.