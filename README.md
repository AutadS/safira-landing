# Safira Homestay — Landing Page

Landing page statis untuk Safira Homestay, dekat Halim Perdana Kusuma, Jakarta Timur.

## Struktur

```
safira-homestay/
├── index.html        # Halaman utama (semua kode ada di sini)
├── vercel.json       # Konfigurasi Vercel (caching gambar)
├── images/           # Semua foto & logo
└── README.md
```

Tidak ada build step. Ini situs HTML/CSS/JS murni, jadi bisa langsung di-deploy.

## Cara update konten

Semua teks, harga, dan nomor WhatsApp ada di dalam `index.html`. Cari bagian yang ingin diubah, edit, lalu commit & push — Vercel otomatis memperbarui situs.

- **Harga kamar**: di kartu kamar (`<article class="room" ...>`), ubah teks harga (`Rp300rb`) **dan** atribut `data-price="300000"` di kartu yang sama. Formulir "Cek ketersediaan kamar" dan harga "Mulai dari" di bar bawah (mobile) otomatis membaca `data-price`. Harga di jawaban FAQ ditulis manual, jadi ikut diubah.
- **Nomor WhatsApp**: ganti semua `6282151151873` di `index.html` (termasuk konstanta `WA` di bagian `<script>`).
- **Foto galeri**: setiap foto adalah `<button class="g" data-cat="...">`. Kategori filter: `kamar`, `balkon`, atau `lobi`. Tambahkan kelas `tall` (tinggi) atau `wide` (lebar) untuk variasi ukuran; teks `alt` dipakai sebagai keterangan di lightbox.
- **Foto latar hero**: tiga slide di `<div class="hero-media">`; slide 2 & 3 memakai `data-bg`.
- **Tanya jawab (FAQ)**: setiap pertanyaan adalah satu blok `<details class="qa">`.
- **Pratinjau link (WhatsApp/Facebook)**: gambar `images/og.jpg`; alamat domain ada di tag `og:url` dan `og:image` di `<head>`.

Untuk mengganti foto: ganti file di folder `images/` dengan nama yang sama, atau ubah `src`/`url()` di `index.html`.

## Kontak & tautan yang tertanam

- WhatsApp: 0821-5115-1873
- Google Maps: https://maps.app.goo.gl/HeUpbVfFSv11maqf6

## Deploy ke Vercel

1. Push repo ini ke GitHub.
2. Di Vercel: **Add New → Project → Import** repo ini.
3. Framework Preset: **Other**. Build command dikosongkan. Output directory default.
4. **Deploy**.
