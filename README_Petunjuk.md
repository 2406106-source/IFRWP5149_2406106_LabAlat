# Paket Pengerjaan Pertemuan 3 — Sistem Informasi Akademik

Paket ini berisi dokumen kebutuhan, empat use case description, sumber Mermaid, file diagram draw.io yang dapat diedit, dan ekspor PNG.

## Struktur
- `01_skenario/P03_SIA_kebutuhan_v01.md`
- `01_skenario/P03_SIA_deskripsi_usecase_v01.md`
- `04_model_analisis/P03/SIA/P03_SIA_usecase_mermaid_v01.mmd`
- `04_model_analisis/P03/SIA/P03_SIA_usecase_v01.drawio`
- `04_model_analisis/P03/SIA/P03_SIA_usecase_v01.png`

## Langkah penyelesaian
1. Ekstrak ZIP.
2. Periksa kedua dokumen Markdown.
3. Buka `P03_SIA_usecase_v01.drawio` di https://app.diagrams.net/ untuk memastikan file bisa dibuka dan tata letak dapat diedit.
4. Jika perlu, rapikan tata letak agar garis asosiasi tidak menutupi teks, dan simpan perubahan.
5. Ekspor ulang PNG dari draw.io setelah memastikan diagram final.
6. Masukkan NIM ke nama file jika dosen mewajibkan format `P03_<NIM>_SIA_usecase_v01.drawio` dan `P03_<NIM>_SIA_usecase_v01.png`.
7. Jangan mengubah atau menimpa file jadwal Pertemuan 2. Tugas praktik P03 ini berfokus pada use case KRS UC03–UC06.
8. Jika ada perbaikan setelah review, simpan sebagai versi `v02`; jangan menimpa versi `v01`.

## Pemeriksaan notasi
- Aktor: Mahasiswa dan Dosen Wali berada di luar batas sistem.
- Use case: UC03, UC04, UC05, UC06 berada di dalam batas sistem.
- `«include»`: panah dari Ajukan KRS menuju Validasi KRS.
- `«extend»`: panah dari Unduh Bukti Pengajuan KRS menuju Ajukan KRS.
- Kondisi extend: `[mahasiswa memilih unduh bukti]`.
- Extension point: `Konfirmasi pengajuan tersimpan`.
- Pengajuan yang lolos validasi tetap berhasil meskipun bukti tidak diunduh.


## Checklist akhir sebelum dikumpulkan
- [ ] Ganti nama file dengan NIM sesuai format yang diminta dosen.
- [ ] Buka file `.drawio` di diagrams.net dan pastikan objek diagram bisa diedit.
- [ ] Periksa arah panah `include` dan `extend`.
- [ ] Periksa ejaan nama aktor dan use case.
- [ ] Ekspor PNG dari draw.io setelah pemeriksaan terakhir.
- [ ] Simpan dokumen kebutuhan dan deskripsi use case bersama diagram.
