# Ujian44 V2 (Percobaan) — Panduan Pasang

Terpisah total dari web ujian utama: repo GitHub baru, Google Sheet baru, Apps Script baru.

## A. Google Sheet + Apps Script (±10 menit)
1. Buat Google Sheet BARU, beri nama "Ujian44 V2".
2. Menu Ekstensi > Apps Script. Hapus isi default, tempel seluruh isi `Code.gs`, simpan.
3. Pilih fungsi `setupAwal` di bar atas > Jalankan. Setujui izin akses (Lanjutan > Buka... > Izinkan).
   Sheet Ujian, Soal, Sesi, Log, Pengaturan terbentuk beserta 5 soal contoh.
4. Di sheet **Pengaturan**, ganti `ganti-password-ini` dengan password guru.
5. Deploy > Deployment baru > jenis Aplikasi web.
   Jalankan sebagai: **Saya**. Yang memiliki akses: **Siapa saja**. Deploy.
6. Salin URL berakhiran `/exec`.

## B. GitHub Pages (±5 menit)
1. Buat repo BARU bernama `ujian44-v2` (jangan pakai repo ujian utama).
2. Upload `index.html`, `nilai.html`, `config.js`.
3. Edit `config.js`: isi `scriptUrl` dengan URL /exec tadi.
4. Settings > Pages > Branch main, folder root > Save.
5. Alamat siswa: `https://USERNAME.github.io/ujian44-v2/`
   Alamat guru: `https://USERNAME.github.io/ujian44-v2/nilai.html`

## C. Mengisi soal
Sheet **Ujian**: satu baris per ujian (Kode, NamaUjian, DurasiMenit, Aktif=YA/TIDAK, Acak=YA/TIDAK, TampilNilai=YA/TIDAK).
Sheet **Soal**: Kode (harus sama dengan sheet Ujian), No, Soal, A–E (E boleh kosong), Kunci (huruf), Gambar (opsional, link https atau link file Google Drive yang dibagikan "Siapa saja dengan link").

## D. Setelah mengubah kode Apps Script
Deploy > Kelola deployment > ikon pensil > Versi: Versi baru > Deploy. URL tetap sama.
