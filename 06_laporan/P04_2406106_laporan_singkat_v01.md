### Pertemuan 4

USE CASE DIAGRAM LANJUTAN: GENERALIZATION DAN COLLABORATION

A. Tujuan Pembelajaran

Setelah melaksanakan praktikum Pertemuan 4, mahasiswa diharapkan mampu:

Mengidentifikasi aktor umum dan aktor khusus dari skenario yang diberikan.

Membuat hierarki generalization aktor dengan arah panah yang benar.

Menyusun generalization use case yang memuat satu use case umum dan beberapa use case khusus.

Mengidentifikasi collaboration yang merealisasikan use case tertentu.

Menghubungkan collaboration dengan use case menggunakan relasi realization.

Mengembangkan diagram secara kumulatif tanpa mengubah fungsi dari Pertemuan 3.

B. Teori atau Prinsip Dasar Praktikum

1. Pengembangan Use Case Diagram

Pertemuan 4 merupakan kelanjutan dari pemodelan Pertemuan 3. Diagram sebelumnya tetap dipertahankan dan dilengkapi dengan fungsi baru. Pada tugas SIA, fungsi baru berkaitan dengan kalender akademik, input nilai mata kuliah, Kartu Hasil Studi (KHS), dan pengelolaan data mahasiswa.

2. Generalization

Generalization menggambarkan hubungan antara elemen umum dengan elemen yang lebih khusus. Pada aktor, Mahasiswa dan Dosen merupakan aktor khusus dari Civitas Akademika. Relasi digambarkan menggunakan garis utuh dengan segitiga kosong yang menunjuk ke aktor umum.

Pada use case, Tambah Data Mahasiswa, Ubah Data Mahasiswa, dan Hapus Data Mahasiswa merupakan bentuk khusus dari Kelola Data Mahasiswa.

3. Collaboration dan Realization

Collaboration menggambarkan elemen-elemen yang bekerja sama untuk mewujudkan perilaku tertentu. Pada diagram, collaboration ditampilkan sebagai elips bergaris putus-putus.

Realization menghubungkan collaboration dengan use case yang direalisasikannya. Relasi ini digambarkan menggunakan garis putus-putus dengan segitiga kosong yang mengarah dari collaboration ke use case. Nama collaboration harus sama persis dengan nama use case yang direalisasikan.

C. Prosedur dan Mekanisme Praktik

1. Studi Kasus

Pada Pertemuan 4, SIA dikembangkan untuk menyediakan layanan hasil studi. Mahasiswa dan Dosen merupakan Civitas Akademika yang dapat melihat kalender akademik. Dosen dapat menginput nilai untuk mata kuliah yang diampunya setelah masa perkuliahan berakhir. Mahasiswa dapat melihat KHS untuk semester yang nilainya sudah dipublikasikan. Admin Akademik bertugas mengelola data mahasiswa melalui proses tambah, ubah, dan hapus data.

2. Kebutuhan Sistem

ID

Kebutuhan

SIA-R07

Mahasiswa dan Dosen sebagai Civitas Akademika dapat melihat kalender akademik.

SIA-R08

Dosen dapat menginput nilai mata kuliah yang diampunya.

SIA-R09

Mahasiswa dapat melihat KHS untuk semester yang nilainya sudah dipublikasikan.

SIA-R10

Admin Akademik dapat mengelola data mahasiswa.

SIA-R11

Pengelolaan data mahasiswa terdiri atas tambah, ubah, dan hapus data mahasiswa.

SIA-R12

Model menunjukkan collaboration yang merealisasikan Input Nilai Mata Kuliah dan Lihat KHS.

Pengguna harus terautentikasi dan memiliki hak akses sesuai perannya. Kalender akademik merupakan agenda resmi institusi dan berbeda dari jadwal kuliah. Nilai hanya dapat diinput oleh dosen pengampu, sedangkan KHS hanya menampilkan nilai yang telah dipublikasikan. Penghapusan data mahasiswa hanya diperbolehkan apabila mahasiswa tidak memiliki data akademik aktif.

3. Identifikasi Aktor dan Use Case

Aktor yang digunakan adalah:

Aktor

Peran

Civitas Akademika

Aktor umum yang dapat melihat kalender akademik.

Mahasiswa

Aktor khusus Civitas Akademika yang dapat melihat KHS.

Dosen

Aktor khusus Civitas Akademika yang dapat menginput nilai mata kuliah yang diampunya.

Admin Akademik

Mengelola data mahasiswa.

Dosen Wali

Tetap dipertahankan untuk proses keputusan KRS dari Pertemuan 3.

Katalog use case gabungan adalah:

ID

Nama Use Case

Status

SIA-UC01

Lihat Jadwal Kuliah

Tetap dari Pertemuan 2

SIA-UC02

Kelola Jadwal Kuliah

Tetap dari Pertemuan 2

SIA-UC03

Ajukan KRS

Tetap dari Pertemuan 3

SIA-UC04

Validasi KRS

Tetap dari Pertemuan 3

SIA-UC05

Unduh Bukti Pengajuan KRS

Tetap dari Pertemuan 3

SIA-UC06

Proses Keputusan KRS

Tetap dari Pertemuan 3

SIA-UC07

Lihat Kalender Akademik

Baru

SIA-UC08

Input Nilai Mata Kuliah

Baru

SIA-UC09

Lihat KHS

Baru

SIA-UC10

Kelola Data Mahasiswa

Baru, use case umum

SIA-UC11

Tambah Data Mahasiswa

Baru, use case khusus

SIA-UC12

Ubah Data Mahasiswa

Baru, use case khusus

SIA-UC13

Hapus Data Mahasiswa

Baru, use case khusus

4. Penetapan Generalization Aktor

Aktor Mahasiswa dan Dosen dihubungkan menuju aktor umum Civitas Akademika menggunakan relasi generalization. Segitiga kosong mengarah ke Civitas Akademika.

UC07 Lihat Kalender Akademik dihubungkan satu kali dengan Civitas Akademika. Mahasiswa dan Dosen tidak diberi asosiasi langsung tambahan ke UC07 karena fungsi tersebut diwarisi dari aktor umum.

5. Penetapan Generalization Use Case

UC10 Kelola Data Mahasiswa menjadi use case umum. Tiga use case khususnya adalah:

SIA-UC11 — Tambah Data Mahasiswa: menambahkan data mahasiswa baru.

SIA-UC12 — Ubah Data Mahasiswa: mengubah informasi mahasiswa yang sudah terdaftar.

SIA-UC13 — Hapus Data Mahasiswa: menghapus data mahasiswa sesuai aturan tugas.

Setiap use case khusus dihubungkan dengan panah generalization yang mengarah ke UC10. Admin Akademik dihubungkan dengan UC10 sebagai aktor yang menjalankan pengelolaan data mahasiswa.

6. Penetapan Collaboration

Dua collaboration ditetapkan sebagai berikut:

ID Collaboration

Nama Collaboration

Use Case yang Direalisasikan

SIA-CO01

Input Nilai Mata Kuliah

SIA-UC08 Input Nilai Mata Kuliah

SIA-CO02

Lihat KHS

SIA-UC09 Lihat KHS

Nama collaboration sama persis dengan nama use case yang direalisasikannya. Hubungan keduanya menggunakan relasi realization, bukan include atau extend. Collaboration tidak dihubungkan secara langsung dengan aktor.

7. Penyusunan Use Case Description

SIA-UC08 — Input Nilai Mata Kuliah

Elemen

Deskripsi

ID dan nama

SIA-UC08 — Input Nilai Mata Kuliah

Sumber kebutuhan

SIA-R08

Tujuan

Memasukkan nilai mahasiswa pada mata kuliah yang diampu.

Aktor utama

Dosen

Aktor pendukung

Tidak ditetapkan pada skenario.

Pemicu

Dosen memilih menu Input Nilai Mata Kuliah.

Prasyarat

Dosen telah login dan merupakan pengampu mata kuliah terkait.

Generalization

Tidak menjadi bagian dari hierarki generalization pada tugas ini.

Collaboration

SIA-CO01 — Input Nilai Mata Kuliah

Pascakondisi berhasil

Nilai tersimpan; nilai baru tampil pada KHS setelah dipublikasikan.

Pascakondisi gagal

Nilai tidak tersimpan atau tidak mengalami perubahan.

Aturan bisnis

Nilai di luar rentang yang sah ditolak.

Alur utama:

Dosen membuka menu Input Nilai Mata Kuliah.

Sistem menampilkan daftar mata kuliah yang diampu.

Dosen memilih mata kuliah dan mahasiswa.

Dosen memasukkan nilai.

Sistem memeriksa kelengkapan dan validitas nilai.

Dosen mengonfirmasi penyimpanan.

Sistem menyimpan nilai dan menampilkan konfirmasi.

Alur alternatif:

Jika dosen bukan pengampu mata kuliah, sistem menolak proses input.

Jika nilai berada di luar rentang yang sah atau data belum lengkap, sistem meminta perbaikan.

Jika penyimpanan gagal, sistem menampilkan informasi kegagalan dan nilai tidak dianggap berhasil tersimpan.

SIA-UC09 — Lihat KHS

Elemen

Deskripsi

ID dan nama

SIA-UC09 — Lihat KHS

Sumber kebutuhan

SIA-R09

Tujuan

Menampilkan Kartu Hasil Studi mahasiswa.

Aktor utama

Mahasiswa

Pemicu

Mahasiswa memilih menu Lihat KHS.

Prasyarat

Mahasiswa telah login.

Generalization

Tidak menjadi bagian dari hierarki generalization use case.

Collaboration

SIA-CO02 — Lihat KHS

Pascakondisi berhasil

KHS menampilkan nilai yang sudah dipublikasikan.

Pascakondisi gagal

KHS tidak dapat ditampilkan atau belum tersedia.

Alur utama:

Mahasiswa membuka menu Lihat KHS.

Sistem menampilkan pilihan semester.

Mahasiswa memilih semester.

Sistem mengambil data hasil studi yang tersedia.

Sistem menampilkan KHS dengan nilai yang sudah dipublikasikan.

Alur alternatif: Jika belum ada nilai yang dipublikasikan untuk semester tersebut, sistem menampilkan informasi bahwa KHS belum tersedia.

8. Pembuatan Diagram

Diagram Pertemuan 3 disalin menggunakan fitur File → Save As agar berkas asli tetap dipertahankan. Setelah itu, elemen Pertemuan 4 ditambahkan secara bertahap, yaitu aktor umum dan khusus, use case layanan hasil studi, use case pengelolaan data mahasiswa, serta collaboration dan relasi realization.

Berkas sumber disimpan pada folder 04_model_analisis/P04/SIA/ menggunakan nama P04_<NIM>_SIA_usecase_v01.drawio. Diagram kemudian diekspor ke PNG dengan nama dasar dan versi yang sama.

[Sisipkan Gambar 4.1 — Use Case Diagram SIA Pertemuan 4 di sini]

Keterangan: Diagram kumulatif SIA yang mempertahankan fungsi jadwal kuliah dan KRS serta menambahkan layanan hasil studi, generalization, collaboration, dan realization.

9. Uji Konsistensi, Review, dan Revisi

Pemeriksaan dilakukan terhadap tiga situasi berikut.

Mahasiswa melihat kalender akademik tanpa asosiasi langsung ke UC07. Hal ini benar karena Mahasiswa mewarisi fungsi aktor umum Civitas Akademika melalui relasi generalization.

Dosen yang bukan pengampu mencoba menginput nilai. Sistem harus menolak proses input karena tidak memenuhi prasyarat use case.

Admin Akademik menghapus mahasiswa yang masih memiliki data akademik aktif. Sistem harus menolak penghapusan berdasarkan aturan tugas.

Pemeriksaan juga mencakup arah panah generalization dan realization, kesamaan nama collaboration dengan use case, keberadaan seluruh use case lama, serta kesesuaian antara kebutuhan, katalog, diagram, dan deskripsi.

D. Hasil Praktikum Pertemuan 4

Hasil praktikum berupa diagram use case kumulatif SIA yang mencakup fungsi dari Pertemuan 2, Pertemuan 3, dan Pertemuan 4. Diagram mempertahankan UC01 sampai UC06 beserta relasi sebelumnya dan menambahkan UC07 sampai UC13.

Generalization aktor menunjukkan hubungan Mahasiswa dan Dosen terhadap Civitas Akademika. Generalization use case menunjukkan hubungan UC11, UC12, dan UC13 terhadap UC10. Sementara itu, SIA-CO01 merealisasikan UC08 dan SIA-CO02 merealisasikan UC09 melalui relasi realization.

Hasil akhir perlu diperiksa kembali agar seluruh elemen memiliki ID dan nama yang konsisten, berkas sumber dapat dibuka kembali dan disunting, serta gambar PNG sesuai dengan diagram terakhir.

E. Referensi

Institut Teknologi Garut. (2026). Jobsheet Praktikum Analisis dan Desain Berorientasi Objek — Pertemuan 4: Use Case Diagram Lanjutan: Generalization dan Collaboration.

Object Management Group. (2017). OMG Unified Modeling Language, Version 2.5.1.

Dokumentasi draw.io/diagrams.net mengenai diagram UML, penyimpanan diagram, dan ekspor berkas.