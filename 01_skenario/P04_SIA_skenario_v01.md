# Skenario dan Katalog Use Case SIA — Pertemuan 4

## 1. Daftar Aktor

| Aktor | Peran |
|---|---|
| Civitas Akademika | Aktor umum yang dapat melihat kalender akademik. |
| Mahasiswa | Aktor khusus Civitas Akademika. |
| Dosen | Aktor khusus Civitas Akademika dan dapat menginput nilai mata kuliah yang diampunya. |
| Admin Akademik | Mengelola data mahasiswa. |
| Dosen Wali | Memproses keputusan KRS sesuai fungsi dari Pertemuan 3. |

## 2. Katalog Use Case

| ID | Nama Use Case | Status |
|---|---|---|
| SIA-UC01 | Lihat Jadwal Kuliah | Tetap dari Pertemuan 2 |
| SIA-UC02 | Kelola Jadwal Kuliah | Tetap dari Pertemuan 2 |
| SIA-UC03 | Ajukan KRS | Tetap dari Pertemuan 3 |
| SIA-UC04 | Validasi KRS | Tetap dari Pertemuan 3 |
| SIA-UC05 | Unduh Bukti Pengajuan KRS | Tetap dari Pertemuan 3 |
| SIA-UC06 | Proses Keputusan KRS | Tetap dari Pertemuan 3 |
| SIA-UC07 | Lihat Kalender Akademik | Baru |
| SIA-UC08 | Input Nilai Mata Kuliah | Baru |
| SIA-UC09 | Lihat KHS | Baru |
| SIA-UC10 | Kelola Data Mahasiswa | Baru, use case umum |
| SIA-UC11 | Tambah Data Mahasiswa | Baru, use case khusus |
| SIA-UC12 | Ubah Data Mahasiswa | Baru, use case khusus |
| SIA-UC13 | Hapus Data Mahasiswa | Baru, use case khusus |

## 3. Keputusan Generalization Aktor

Civitas Akademika menjadi aktor umum karena Mahasiswa dan Dosen sama-sama memiliki fungsi melihat kalender akademik. Mahasiswa dan Dosen menjadi aktor khusus yang mewarisi fungsi tersebut.

Arah panah generalization dibuat dari Mahasiswa menuju Civitas Akademika dan dari Dosen menuju Civitas Akademika.

## 4. Keputusan Generalization Use Case

SIA-UC10 Kelola Data Mahasiswa merupakan use case umum. SIA-UC11 Tambah Data Mahasiswa, SIA-UC12 Ubah Data Mahasiswa, dan SIA-UC13 Hapus Data Mahasiswa merupakan use case khusus yang mewarisi tujuan umum pengelolaan data mahasiswa.

## 5. Daftar Collaboration

| ID | Nama Collaboration | Use Case yang Direalisasikan |
|---|---|---|
| SIA-CO01 | Input Nilai Mata Kuliah | SIA-UC08 Input Nilai Mata Kuliah |
| SIA-CO02 | Lihat KHS | SIA-UC09 Lihat KHS |