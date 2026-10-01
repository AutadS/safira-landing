# Safira Homestay — Landing Page

Landing page statis untuk Safira Homestay, dekat Halim Perdana Kusuma, Jakarta Timur.

## Struktur

```
safira-homestay/
├── index.html        # Halaman utama (semua kode ada di sini)
├── .htaccess         # Konfigurasi Hostinger (cache gambar, sembunyikan .git)
├── vercel.json       # Konfigurasi Vercel (hanya dipakai jika deploy di Vercel)
├── images/           # Semua foto & logo
└── README.md
```

Tidak ada build step. Ini situs HTML/CSS/JS murni, jadi bisa langsung di-deploy.

## Cara update konten

Semua teks, harga, dan nomor WhatsApp ada di dalam `index.html`. Cari bagian yang ingin diubah, edit, lalu commit & push ke branch `main` — Hostinger otomatis memperbarui situs (auto-deploy).

- **Harga kamar**: di kartu kamar (`<article class="room" ...>`), ubah teks harga (`Rp300rb`) **dan** atribut `data-price="300000"` di kartu yang sama. Formulir "Cek ketersediaan kamar" dan harga "Mulai dari" di bar bawah (mobile) otomatis membaca `data-price`. Harga di jawaban FAQ ditulis manual, jadi ikut diubah.
- **Nomor WhatsApp**: ganti semua `6282151151873` di `index.html` (termasuk konstanta `WA` di bagian `<script>`).
- **Foto galeri**: setiap foto adalah `<button class="g" data-cat="...">`. Kategori filter: `kamar`, `balkon`, atau `lobi`. Tambahkan kelas `tall` (tinggi) atau `wide` (lebar) untuk variasi ukuran; teks `alt` dipakai sebagai keterangan di lightbox.
- **Foto latar hero**: tiga slide di `<div class="hero-media">`; slide 2 & 3 memakai `data-bg`.
- **Tanya jawab (FAQ)**: setiap pertanyaan adalah satu blok `<details class="qa">`.
- **Pratinjau link (WhatsApp/Facebook)**: gambar `images/og.jpg`; alamat domain ada di tag `og:url` dan `og:image` di `<head>`.

Untuk mengganti foto: ganti file di folder `images/` dengan nama yang sama, atau ubah `src`/`url()` di `index.html`.

## Prototipe `kepo/` (intro 3D)

Prototipe pembuka versi "anti-mainstream": gerbang *kepo*, logo Safira 3D, kamera masuk lewat pintu (lengkungan logo), lalu adegan lobi yang bergerak mengikuti scroll. Ada tombol bahasa **gaul / ortu**.

- Halaman: `kepo/index.html` (semua kode di satu file), aset di `kepo/assets/`. Setelah masuk `main`, bisa dibuka di `https://safirahalim.com/kepo/`. Halaman ini `noindex`, jadi tidak muncul di Google.
- Library dari CDN jsDelivr: Three.js (3D), GSAP + ScrollTrigger (animasi), Lenis (scroll halus). Tanpa build step.
- Semua teks ada di objek `COPY` (bagian `<script>`), dengan versi `gaul` dan `ortu`.
- Bentuk logo 3D diambil dari path SVG `#markPath` (hasil jiplak logo asli), sehingga logo di loader, 3D, dan versi 2D selalu sama.
- Perangkat tanpa WebGL atau yang mengaktifkan "kurangi gerakan" otomatis mendapat versi 2D yang lebih ringan.

## Kontak & tautan yang tertanam

- WhatsApp: 0821-5115-1873
- Google Maps: https://maps.app.goo.gl/HeUpbVfFSv11maqf6

## Deploy ke Hostinger (safirahalim.com)

1. hPanel → **Websites → Add website** → pilih domain `safirahalim.com` → pilih website kosong (bukan WordPress/Website Builder).
2. Buka dashboard website → **Advanced → Git** → **Connect with GitHub**, beri akses ke repo `safira-landing`.
3. Pilih repo ini, branch `main`, folder tujuan `public_html`, lalu **Deploy**. Jika gagal karena folder tidak kosong, hapus `default.php` di `public_html` lewat File Manager, lalu deploy ulang.
4. Setiap push ke `main` akan ter-deploy otomatis. Tombol **Redeploy** di halaman Git untuk menarik ulang secara manual.
5. **Security → SSL**: pasang SSL gratis, lalu aktifkan **Force HTTPS**.

## Alternatif: deploy ke Vercel

1. Push repo ini ke GitHub.
2. Di Vercel: **Add New → Project → Import** repo ini.
3. Framework Preset: **Other**. Build command dikosongkan. Output directory default.
4. **Deploy**.
