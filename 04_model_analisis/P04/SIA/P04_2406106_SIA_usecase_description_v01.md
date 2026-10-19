# Use Case Description SIA — Pertemuan 4

## A. SIA-UC08 Input Nilai Mata Kuliah

**ID dan nama:** SIA-UC08 — Input Nilai Mata Kuliah

**Sumber kebutuhan:** SIA-R08

**Tujuan:** Memungkinkan dosen menginput nilai mahasiswa untuk mata kuliah yang diampunya.

**Aktor utama:** Dosen

**Pemicu:** Dosen memilih fungsi input nilai mata kuliah.

**Prasyarat:** Dosen telah login dan merupakan pengampu mata kuliah yang dipilih.

**Collaboration:** SIA-CO01 — Input Nilai Mata Kuliah

### Alur Utama

1. Dosen memilih menu Input Nilai Mata Kuliah.
2. Sistem menampilkan mata kuliah yang diampu dosen.
3. Dosen memilih mata kuliah dan mahasiswa.
4. Dosen memasukkan nilai mahasiswa.
5. Sistem memeriksa kelengkapan dan validitas nilai.
6. Dosen menyimpan nilai.
7. Sistem menyimpan nilai dan menampilkan konfirmasi.

### Alur Alternatif

- A1: Jika dosen bukan pengampu mata kuliah, sistem menolak input dan tidak menyimpan nilai.
- A2: Jika nilai di luar rentang yang sah, sistem menolak nilai dan meminta perbaikan.
- A3: Jika data belum lengkap, sistem meminta dosen melengkapi data.
- A4: Jika penyimpanan gagal, sistem menampilkan pesan kegagalan dan tidak menyatakan nilai berhasil disimpan.

**Pascakondisi berhasil:** Nilai tersimpan dan belum ditampilkan pada KHS sebelum dipublikasikan.

**Pascakondisi gagal:** Nilai tidak tersimpan atau tidak berubah.

## B. SIA-UC09 Lihat KHS

**ID dan nama:** SIA-UC09 — Lihat KHS

**Sumber kebutuhan:** SIA-R09

**Tujuan:** Memungkinkan mahasiswa melihat Kartu Hasil Studi berdasarkan semester yang dipilih.

**Aktor utama:** Mahasiswa

**Pemicu:** Mahasiswa memilih menu Lihat KHS.

**Prasyarat:** Mahasiswa telah login.

**Collaboration:** SIA-CO02 — Lihat KHS

### Alur Utama

1. Mahasiswa memilih menu Lihat KHS.
2. Sistem menampilkan pilihan semester.
3. Mahasiswa memilih semester.
4. Sistem mengambil data hasil studi yang tersedia.
5. Sistem menampilkan KHS yang hanya memuat nilai yang sudah dipublikasikan.

### Alur Alternatif

Jika belum ada nilai yang dipublikasikan, sistem menampilkan informasi bahwa nilai atau KHS belum tersedia.

**Pascakondisi berhasil:** KHS tampil dengan nilai yang telah dipublikasikan.

**Pascakondisi gagal:** KHS tidak ditampilkan jika data belum tersedia.