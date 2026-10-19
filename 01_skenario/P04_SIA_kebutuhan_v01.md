# Kebutuhan Sistem Informasi Akademik (SIA) — Pertemuan 4

## 1. Skenario

Sistem Informasi Akademik menyediakan layanan kalender akademik, input nilai mata kuliah, melihat Kartu Hasil Studi (KHS), serta pengelolaan data mahasiswa. Mahasiswa dan dosen dapat melihat kalender akademik. Dosen menginput nilai mata kuliah yang diampunya, sedangkan mahasiswa melihat KHS untuk semester yang nilainya sudah dipublikasikan. Admin Akademik mengelola data mahasiswa melalui fungsi tambah, ubah, dan hapus data.

## 2. Daftar Kebutuhan

| ID | Kebutuhan |
|---|---|
| SIA-R07 | Mahasiswa dan Dosen sebagai Civitas Akademika dapat melihat kalender akademik. |
| SIA-R08 | Dosen dapat menginput nilai mata kuliah yang diampunya. |
| SIA-R09 | Mahasiswa dapat melihat KHS untuk semester yang nilainya sudah dipublikasikan. |
| SIA-R10 | Admin Akademik dapat mengelola data mahasiswa. |
| SIA-R11 | Pengelolaan data mahasiswa terdiri dari tambah, ubah, dan hapus data mahasiswa. |
| SIA-R12 | Model menunjukkan collaboration yang merealisasikan Input Nilai Mata Kuliah dan Lihat KHS. |

## 3. Batas dan Asumsi

1. Pengguna telah login dan memiliki hak akses sesuai perannya.
2. Kalender akademik merupakan agenda resmi institusi, bukan jadwal kuliah.
3. Nilai hanya dapat diinput oleh dosen pengampu mata kuliah tersebut.
4. KHS hanya menampilkan nilai yang sudah dipublikasikan.
5. Penghapusan data mahasiswa hanya diperbolehkan jika mahasiswa tidak memiliki data akademik aktif.
6. Fungsi jadwal kuliah dan pengajuan KRS dari Pertemuan 2 dan Pertemuan 3 tetap dipertahankan.
7. Pembayaran dan perancangan basis data tidak termasuk dalam tugas ini.

## 4. Hasil Pemeriksaan

- Situasi A: Mahasiswa tetap dapat melihat kalender akademik karena mewarisi fungsi Civitas Akademika.
- Situasi B: Input nilai oleh dosen yang bukan pengampu harus ditolak dan tidak boleh disimpan.
- Situasi C: Penghapusan mahasiswa yang masih memiliki data akademik aktif harus ditolak.