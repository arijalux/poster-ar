# Poster AR — Sample (MindAR)

Scan gambar target → video muncul menempel di atas gambar. Berjalan di browser HP, tanpa install app.

## Isi folder

| File | Fungsi |
|---|---|
| `index.html` | Halaman AR (MindAR + A-Frame) |
| `assets/targets.mind` | Target hasil kompilasi (dipakai engine AR) |
| `assets/target-image.png` | Gambar target — ini yang di-scan (contoh: kartu sample MindAR) |
| `assets/video.mp4` | Video yang muncul di atas target (sample Big Buck Bunny) |

## Cara test cepat di laptop

1. Jalankan server lokal di folder ini:
   ```
   python3 -m http.server 8080
   ```
2. Buka `http://localhost:8080` di Chrome, tekan **Mulai Scan**, izinkan kamera.
3. Buka `assets/target-image.png` di HP (atau print), lalu arahkan webcam laptop ke gambar itu → video muncul menempel di gambar.

> Kamera hanya diizinkan browser di `localhost` atau HTTPS. Jadi untuk test dari HP, deploy dulu (lihat bawah).

## Cara deploy (untuk di-scan pengunjung pameran)

Paling gampang pakai **Netlify Drop**:
1. Buka https://app.netlify.com/drop
2. Drag & drop folder `poster-ar-sample` ini.
3. Dapat URL HTTPS (misal `https://xxx.netlify.app`) → jadikan QR code, tempel di poster.

## Ganti dengan poster & video kamu sendiri

1. **Video**: ganti `assets/video.mp4` (MP4 H.264, 720p, idealnya < 10 MB).
2. **Target**: compile gambar poster kamu di https://hiukim.github.io/mind-ar-js-doc/tools/compile
   — upload gambar, download hasilnya, timpa `assets/targets.mind`.
   Simpan juga gambarnya sebagai `assets/target-image.png` untuk testing.
3. Sesuaikan `height` di tag `<a-video>` dalam `index.html` dengan rasio video kamu
   (height = 1 × tinggi_video / lebar_video, karena width plane = 1 = lebar target).
