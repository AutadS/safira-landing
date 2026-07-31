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

Untuk mengganti foto: ganti file di folder `images/` dengan nama yang sama, atau ubah `src`/`url()` di `index.html`.

## Kontak & tautan yang tertanam

- WhatsApp: 0821-5115-1873
- Google Maps: https://maps.app.goo.gl/HeUpbVfFSv11maqf6

## Deploy ke Vercel

1. Push repo ini ke GitHub.
2. Di Vercel: **Add New → Project → Import** repo ini.
3. Framework Preset: **Other**. Build command dikosongkan. Output directory default.
4. **Deploy**.
