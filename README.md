# Fatih's Blog

Proyek ini adalah website blog sederhana berbasis HTML, Bootstrap, dan CSS custom. Saat ini web terdiri dari dua halaman utama: halaman login dan halaman daftar blog.

## Tentang Web Ini

Website ini dibuat untuk menampilkan blog yang ringan, bersih, dan mudah dibaca.
Konsep utamanya:

- Halaman awal berisi form login sederhana.
- Setelah tombol masuk ditekan, pengguna diarahkan ke halaman dashboard blog.
- Dashboard menampilkan daftar artikel blog dengan tampilan minimalis.

## Isi Website

### 1. Halaman Login

File: [index.html](index.html)

Halaman ini berfungsi sebagai pintu masuk ke website. Isinya:

- Judul blog: `Fatih's Blog.`
- Subjudul singkat: `login untuk melihat blog.`
- Form input email.
- Form input kata sandi.
- Tombol untuk masuk ke dashboard.

Form login tidak memakai validasi JavaScript. Saat tombol ditekan, form langsung diarahkan ke `dashboard.html` menggunakan metode `GET`.

### 2. Halaman Dashboard Blog

File: [dashboard.html](dashboard.html)

Halaman ini adalah isi utama website. Isinya:

- Navbar sederhana di bagian atas.
- Tab kategori blog: Beranda, Tutorial, Opini, dan Berita.
- Feed artikel blog berisi beberapa kartu artikel.

Setiap artikel menampilkan:

- Nama penulis atau sumber.
- Waktu publikasi.
- Judul artikel.
- Ringkasan singkat isi artikel.
- Tag kategori.
- Estimasi waktu baca.

### 3. File CSS Kustom

File: [styles.css](styles.css)

File ini menyimpan seluruh pengaturan tampilan tambahan di luar Bootstrap, seperti:

- tipografi,
- warna,
- jarak antar elemen,
- border dan radius,
- layout header, tabs, dan artikel,
- gaya login form,
- gaya feed blog.

## Struktur File

```text
Pertemuan 7/
├── index.html
├── dashboard.html
└── styles.css
```

## Cara Kerja Web

Alur webnya sangat sederhana:

1. Pengguna membuka `index.html`.
2. Pengguna mengisi email dan kata sandi.
3. Saat tombol masuk ditekan, browser berpindah ke `dashboard.html`.
4. Dashboard menampilkan daftar artikel blog.

Karena proyek ini bersifat statis, form login hanya dipakai sebagai simulasi navigasi, bukan untuk autentikasi server.

## Detail Kode per File

### `index.html`

Bagian penting di halaman login:

```html
<form action="dashboard.html" method="get" class="login-form">
```

Artinya:

- `action="dashboard.html"` membuat form berpindah ke halaman dashboard.
- `method="get"` berarti data form dikirim lewat URL, tetapi pada proyek ini data tersebut tidak diproses lebih lanjut.

Komponen lain di halaman login:

- Judul utama dan subjudul berada di bagian tengah.
- Input email dan password memakai class Bootstrap dan class custom `md-input`.
- Tombol masuk memakai class Bootstrap `btn btn-dark` dan class custom `md-pill-btn`.

### `dashboard.html`

Bagian penting di halaman dashboard:

#### Navbar

Navbar digunakan sebagai header blog. Isinya hanya:

- nama situs,
- teks kecil `Blog sederhana`,
- link `Keluar` untuk kembali ke halaman login.

#### Tab kategori

Tab kategori dibuat sebagai elemen navigasi visual:

- Beranda
- Tutorial
- Opini
- Berita

Tab ini tidak memakai JavaScript. Tab hanya berfungsi sebagai tampilan kategori statis.

#### Feed artikel

Setiap artikel ditulis menggunakan elemen `<article>`. Struktur dasarnya:

```html
<article class="md-article">
  <div class="md-meta-row">...</div>
  <div class="md-article-body">
    <div class="md-article-text">
      <h2 class="md-article-title">...</h2>
      <p class="md-article-summary">...</p>
    </div>
  </div>
</article>
```

Susunan ini membuat artikel lebih mudah dibaca dan mudah ditambah jika nanti ingin menambahkan postingan baru.

### `styles.css`

File CSS custom ini mengatur tampilan utama web. Beberapa class penting:

#### `.md-container`

Mengatur lebar maksimum konten agar halaman tidak terlalu melebar di layar besar.

#### `.page-shell` dan `.page-shell-login`

Dipakai untuk halaman login agar kontennya berada di tengah layar secara vertikal dan horizontal.

#### `.brand-logo`, `.brand-title`, `.brand-subtitle`

Mengatur tipografi di halaman login agar terlihat lebih khas dan rapi.

#### `.md-topbar`

Mengatur navbar atas dengan posisi sticky, background putih transparan, dan garis bawah tipis.

#### `.md-tabs` dan `.md-tab`

Mengatur bar kategori blog dan indikator tab aktif.

#### `.md-main-grid`

Saat ini class ini sudah diubah menjadi layout blok biasa, bukan grid. Jadi isi blog tidak lagi memakai `grid-template-columns`.

#### `.md-blog-only`

Membatasi lebar konten blog supaya tetap nyaman dibaca.

#### `.md-article`, `.md-meta-row`, `.md-article-title`, `.md-article-summary`

Class-class ini mengatur tampilan setiap kartu artikel, mulai dari metadata penulis, judul, ringkasan, hingga tag dan bookmark.

## Teknologi yang Dipakai

- HTML5 untuk struktur halaman.
- Bootstrap 5.3.3 untuk komponen dasar dan utilitas layout.
- CSS custom untuk tampilan khusus.
- Google Fonts untuk tipografi.

