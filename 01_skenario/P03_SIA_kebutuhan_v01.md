# P03 — Kebutuhan Sistem Informasi Akademik (SIA)

## 1. Skenario
Mahasiswa mengajukan KRS dengan memilih mata kuliah. Setiap pengajuan menjalankan validasi KRS yang memeriksa kelengkapan, prasyarat mata kuliah, dan benturan jadwal. Jika validasi berhasil, sistem menyimpan pengajuan berstatus menunggu persetujuan dosen wali. Pada konfirmasi penyimpanan, mahasiswa dapat memilih mengunduh bukti pengajuan. Dosen wali menyetujui atau menolak KRS dan memberikan catatan keputusan.

## 2. Kebutuhan fungsional pada tugas praktik Pertemuan 3
| ID | Kebutuhan |
|---|---|
| SIA-R03 | Mahasiswa dapat mengajukan KRS. |
| SIA-R04 | Sistem memvalidasi KRS sebagai bagian dari proses pengajuan. |
| SIA-R05 | Mahasiswa dapat mengunduh bukti jika memilihnya pada konfirmasi pengajuan. |
| SIA-R06 | Dosen Wali dapat memproses persetujuan atau penolakan KRS dan memberikan catatan keputusan. |

Catatan: SIA-R01 (Mahasiswa melihat jadwal kuliah) dan SIA-R02 (Admin Akademik mengelola jadwal kuliah) merupakan fungsi jadwal dari Pertemuan 2. Diagram tugas praktik KRS ini berfokus pada kebutuhan SIA-R03 sampai SIA-R06. Jangan menambahkan Admin Akademik ke fungsi KRS hanya karena aktor itu ada pada tugas jadwal Pertemuan 2.

## 3. Aktor
| Aktor | Tujuan |
|---|---|
| Mahasiswa | Mengajukan KRS dan, jika dipilih, mengunduh bukti pengajuan. |
| Dosen Wali | Menyetujui atau menolak KRS serta memberikan catatan keputusan. |

## 4. Batas sistem, aturan, dan asumsi
- Pengguna telah terautentikasi.
- Data mata kuliah, prasyarat, dan jadwal tersedia.
- Validasi gagal menyebabkan pengajuan belum berhasil tersimpan.
- Mengunduh bukti bukan syarat keberhasilan pengajuan.
- KRS yang tersimpan belum berarti telah disetujui.
- Pembayaran, pengisian nilai, dan implementasi basis data berada di luar ruang lingkup tugas ini.
- Pengajuan yang lolos validasi disimpan dengan status “Menunggu persetujuan dosen wali”.

## 5. Katalog use case
| ID | Nama use case | Aktor/relasi | Sumber kebutuhan |
|---|---|---|---|
| SIA-UC03 | Ajukan KRS | Mahasiswa | SIA-R03, SIA-R04, SIA-R05 |
| SIA-UC04 | Validasi KRS | Dipanggil oleh SIA-UC03 melalui «include» | SIA-R04 |
| SIA-UC05 | Unduh Bukti Pengajuan KRS | Mahasiswa; perluasan opsional SIA-UC03 | SIA-R05 |
| SIA-UC06 | Proses Keputusan KRS | Dosen Wali | SIA-R06 |

## 6. Keputusan relasi
### SIA-UC03 «include» SIA-UC04
Validasi merupakan bagian yang selalu dilakukan saat pengajuan mencapai tahap pemeriksaan. Panah putus-putus berlabel «include» diarahkan dari **Ajukan KRS** ke **Validasi KRS**.

### SIA-UC05 «extend» SIA-UC03
Unduh bukti merupakan perilaku opsional. Panah putus-putus berlabel «extend» diarahkan dari **Unduh Bukti Pengajuan KRS** ke **Ajukan KRS**.
- Extension point pada SIA-UC03: **Konfirmasi pengajuan tersimpan**.
- Kondisi: **[mahasiswa memilih unduh bukti]**.
- Pengajuan tetap berhasil walaupun mahasiswa tidak mengunduh bukti.
