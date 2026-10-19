# Use Case Description — Sistem Informasi Akademik (P03)

Dokumen ini mendeskripsikan empat use case yang diminta dalam tugas praktik Pertemuan 3.

## SIA-UC03 — Ajukan KRS

| Elemen | Deskripsi |
|---|---|
| ID dan nama | SIA-UC03 — Ajukan KRS |
| Sumber kebutuhan | SIA-R03, SIA-R04, SIA-R05 |
| Tujuan | Menyimpan pengajuan KRS dengan status Menunggu persetujuan dosen wali. |
| Aktor utama | Mahasiswa |
| Aktor pendukung | Dosen Wali memproses keputusan setelah pengajuan tersimpan. |
| Pemicu | Mahasiswa memilih fungsi Ajukan KRS. |
| Prasyarat | Mahasiswa telah terautentikasi; data mata kuliah, prasyarat, dan jadwal tersedia. |
| Relasi include | SIA-UC04 — Validasi KRS |
| Extension point | Konfirmasi pengajuan tersimpan. |
| Relasi extend | SIA-UC05 — Unduh Bukti Pengajuan KRS jika [mahasiswa memilih unduh bukti]. |
| Pascakondisi berhasil | Pengajuan tersimpan dengan nomor pengajuan dan status Menunggu persetujuan dosen wali. |
| Pascakondisi gagal | Tidak ada pengajuan baru yang dinyatakan berhasil tersimpan. |
| Aturan bisnis/asumsi | Pengajuan tersimpan belum berarti disetujui; unduh bukti bersifat opsional. |

### Alur utama
| Langkah | Tindakan Mahasiswa | Respons Sistem |
|---|---|---|
| 1 | Membuka fungsi Ajukan KRS. | Menampilkan formulir pengajuan. |
| 2 | Memilih mata kuliah yang akan diambil. | Menampung pilihan mata kuliah. |
| 3 | Mengirim pengajuan KRS. | Memeriksa kelengkapan data. |
| 4 | — | Menjalankan SIA-UC04 Validasi KRS. |
| 5 | — | Jika valid, menyimpan pengajuan dan membuat nomor pengajuan dengan status Menunggu persetujuan dosen wali. |
| 6 | Melihat konfirmasi. | Menampilkan nomor pengajuan dan status; mencapai extension point. |
| 7 | Tidak memilih unduh bukti atau mengakhiri proses. | Pengajuan tetap berhasil tersimpan. |

### Alur alternatif/pengecualian
- **A1 — Data tidak lengkap (langkah 3):** sistem menunjukkan data yang belum lengkap; pengajuan belum berhasil disimpan.
- **A2 — Prasyarat tidak terpenuhi (langkah 4):** sistem menampilkan hasil validasi gagal; pengajuan tidak disimpan sebagai pengajuan berhasil.
- **A3 — Benturan jadwal (langkah 4):** sistem memberi tahu adanya benturan; pengajuan belum berhasil disimpan.
- **A4 — Mahasiswa memilih unduh bukti (langkah 6):** SIA-UC05 dijalankan. Status persetujuan KRS tidak berubah.
- **A5 — Bukti gagal diunduh:** pengajuan tetap tersimpan; sistem memberi tahu bahwa unduhan gagal.

## SIA-UC04 — Validasi KRS

| Elemen | Deskripsi |
|---|---|
| ID dan nama | SIA-UC04 — Validasi KRS |
| Sumber kebutuhan | SIA-R04 |
| Tujuan | Memeriksa kelengkapan, prasyarat mata kuliah, dan benturan jadwal sebelum pengajuan disimpan. |
| Aktor utama | Tidak ada aktor manusia yang memulai langsung; use case dipanggil oleh SIA-UC03. |
| Pemicu | SIA-UC03 meminta validasi pengajuan KRS. |
| Prasyarat | Mahasiswa telah memilih mata kuliah dan mengirim pengajuan. |
| Pascakondisi berhasil | Sistem mengembalikan hasil validasi berhasil ke SIA-UC03. |
| Pascakondisi gagal | Sistem mengembalikan hasil validasi gagal; pengajuan tidak disimpan sebagai pengajuan berhasil. |
| Aturan bisnis/asumsi | Validasi dilakukan pada setiap pengajuan yang mencapai tahap pemeriksaan. |

### Alur utama
1. Sistem menerima data pengajuan dari SIA-UC03.
2. Sistem memeriksa kelengkapan data.
3. Sistem memeriksa prasyarat setiap mata kuliah.
4. Sistem memeriksa benturan jadwal.
5. Jika semua pemeriksaan lolos, sistem mengembalikan hasil validasi berhasil kepada SIA-UC03.

### Alur alternatif/pengecualian
- Jika data tidak lengkap, sistem mengembalikan hasil tidak valid.
- Jika prasyarat tidak terpenuhi, sistem mengembalikan hasil tidak valid.
- Jika ditemukan benturan jadwal, sistem mengembalikan hasil tidak valid.
- Untuk setiap kegagalan, pengajuan tidak dinyatakan berhasil tersimpan.

## SIA-UC05 — Unduh Bukti Pengajuan KRS

| Elemen | Deskripsi |
|---|---|
| ID dan nama | SIA-UC05 — Unduh Bukti Pengajuan KRS |
| Sumber kebutuhan | SIA-R05 |
| Tujuan | Menyediakan bukti untuk pengajuan KRS yang telah tersimpan. |
| Aktor utama | Mahasiswa |
| Pemicu | Mahasiswa memilih unduh bukti pada konfirmasi pengajuan. |
| Prasyarat | Pengajuan KRS berhasil tersimpan dan konfirmasi ditampilkan. |
| Pascakondisi berhasil | Bukti pengajuan tersedia untuk diunduh. |
| Pascakondisi gagal | Pengajuan tetap tersimpan, tetapi bukti belum berhasil diunduh. |
| Aturan bisnis/asumsi | Use case opsional; tidak menentukan keberhasilan pengajuan. |

### Alur utama
1. Sistem menampilkan konfirmasi pengajuan yang telah tersimpan.
2. Mahasiswa memilih opsi unduh bukti.
3. Sistem menyiapkan bukti pengajuan.
4. Sistem menyediakan berkas bukti untuk diunduh.

### Alur alternatif/pengecualian
- Jika mahasiswa tidak memilih unduh bukti, use case ini tidak dijalankan dan pengajuan tetap berhasil.
- Jika bukti gagal disiapkan atau diunduh, sistem memberi tahu mahasiswa; status pengajuan tidak berubah.

## SIA-UC06 — Proses Keputusan KRS

| Elemen | Deskripsi |
|---|---|
| ID dan nama | SIA-UC06 — Proses Keputusan KRS |
| Sumber kebutuhan | SIA-R06 |
| Tujuan | Memungkinkan Dosen Wali menyetujui atau menolak KRS dan memberikan catatan keputusan. |
| Aktor utama | Dosen Wali |
| Pemicu | Dosen Wali membuka pengajuan KRS yang menunggu keputusan. |
| Prasyarat | Dosen Wali telah terautentikasi dan tersedia pengajuan berstatus Menunggu persetujuan dosen wali. |
| Pascakondisi berhasil | Keputusan tersimpan sebagai Disetujui atau Ditolak beserta catatan keputusan. |
| Pascakondisi gagal | Keputusan baru tidak dinyatakan tersimpan. |
| Aturan bisnis/asumsi | Pengajuan yang tersimpan belum dianggap disetujui sebelum Dosen Wali menetapkan keputusan. |

### Alur utama
1. Dosen Wali membuka daftar pengajuan KRS yang menunggu keputusan.
2. Sistem menampilkan detail pengajuan.
3. Dosen Wali memeriksa pengajuan.
4. Dosen Wali memilih Setujui atau Tolak.
5. Dosen Wali memasukkan catatan keputusan.
6. Sistem menyimpan keputusan dan catatan.
7. Sistem menampilkan konfirmasi bahwa keputusan berhasil disimpan.

### Alur alternatif/pengecualian
- Jika pengajuan tidak ditemukan atau tidak lagi menunggu keputusan, sistem memberi tahu Dosen Wali bahwa pengajuan tidak dapat diproses.
- Jika keputusan atau catatan belum lengkap, sistem meminta Dosen Wali melengkapi data.
- Jika penyimpanan gagal, sistem menampilkan pesan gagal dan keputusan tidak dinyatakan berhasil tersimpan.

## Hasil uji konsistensi tiga situasi
1. **Validasi berhasil, mahasiswa tidak mengunduh bukti:** pengajuan tetap tersimpan dengan status Menunggu persetujuan dosen wali.
2. **Validasi gagal:** pengajuan tidak dinyatakan berhasil tersimpan.
3. **Validasi berhasil, mahasiswa memilih unduh bukti:** pengajuan tersimpan dan sistem menjalankan SIA-UC05 sebagai perilaku tambahan.

Ketiga situasi tersebut konsisten dengan diagram: validasi selalu disertakan oleh Ajukan KRS, sedangkan unduh bukti hanya berjalan pada kondisi yang ditentukan.
