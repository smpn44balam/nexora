# Ringkasan Sistem Ujian44 V2 (untuk dilanjutkan di obrolan baru)

## Arsitektur
- Frontend statis (GitHub Pages): `index.html` (siswa), `nilai.html` (guru), `config.js` (pengaturan).
- Backend: Google Apps Script `Code.gs` + Google Sheet (Ujian, Soal, Sesi, Log, Pengaturan).
- Aksi API: `list` (GET), `start`, `save`, `log`, `submit`, `results` (POST, text/plain).
- **PENTING: `Code.gs` TIDAK ada di zip `nexora-main`.** Kirim isinya di obrolan baru, atau minta ditulis ulang dari nol.

## Sudah dikerjakan (sisi frontend)
- #6 Catatan 3 poin di halaman mulai dihapus.
- #7 Slot logo: taruh file `logo.png` (persegi, <100 KB) di folder yang sama dengan index.html. Tidak ada file = otomatis tersembunyi.
- #9 Dukungan wacana: bila soal punya field `wacana` dari backend, teks tampil di atas soal (bisa digulir). Soal berwacana tidak diacak urutannya.
- #11 Kirim wajib lengkap: dialog menampilkan jumlah soal, terjawab, belum dijawab, dan nomor kosong. Tombol kirim disembunyikan sampai semua terjawab. Waktu habis tetap kirim otomatis.
- #13 Penalti 20/40/60 detik (config.js).
- #10 sebagian: `inset:0` diganti agar overlay tidak rusak di HP lama/iPhone lama.
- #14 sudah ada: refresh melanjutkan sesi, penalti tidak hilang karena refresh, jawaban cadangan di localStorage.

## Update (Code.gs sudah diterima dan ditulis ulang -> `Code.gs` di zip)
Selesai: #1 token + jam buka/tutup (kolom Token, Buka, Tutup di sheet Ujian), #3/#4 tingkat -> kelas -> nama otomatis dari sheet Siswa (nama divalidasi server), #2 susulan/remedial (kolom Jenis di Sesi, filter di nilai.html, dibuka dengan PasswordGuru sebagai kode pengawas), #5 jam & durasi tampil di bawah pilihan mapel, #8 cache soal/daftar siswa/daftar ujian, #9 kolom Wacana, #16 sheet Petunjuk + dropdown YA/TIDAK.
Hasil cek Code.gs lama: kunci jawaban tidak pernah dikirim ke browser (aman); server sudah menolak jawaban telat (toleransi 3 menit), jadi risiko ubah jam HP kecil.

## Cara pasang update
1. Ganti isi Code.gs di Apps Script, jalankan `setupAwal` lagi (data lama aman; menambah kolom/sheet baru).
2. Deploy > Kelola deployment > Versi baru.
3. Isi sheet Siswa (kolom Kelas contoh 7A, Absen, Nama, Aktif) dan kolom Token/Buka/Tutup di sheet Ujian.
4. Upload index.html, nilai.html, config.js (+ logo.png) ke GitHub.

## Belum dikerjakan
- #12 rumus/tabel (usulan KaTeX), #5 12 mapel hanya perlu 12 baris di sheet Ujian, #17 arsip per periode (cara salin file sudah di sheet Petunjuk).
- Tombol token/jam hanya diuji sintaks; uji di HP nyata (Android lama + iPhone) sebelum dipakai.
- Soal berwacana: saat ini wacana diulang tiap soal (isi sama di baris-baris soalnya), tampil di atas soal.
- Risiko iPhone/fullscreen: lihat penjelasan di atas (tidak berubah).
