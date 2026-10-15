# Lab4Web - Praktikum 4: CSS Layout

| | |
|---|---|
| **Nama** | Guruh Khaerullah Kusvhi |
| **NIM** | _(312310630)_ |
| **Kelas** | I231C - Teknik Informatika |
| **Mata Kuliah** | Pemrograman Web |

## Struktur Folder

```
Lab4Web/
├── lab4_box/
│   └── lab4_box.html          # latihan box element, float, clearfix
├── lab4_layout/
│   ├── home.html              # halaman utama
│   ├── artikel.html           # halaman artikel
│   ├── about.html             # tugas 1
│   ├── kontak.html            # tugas 2
│   ├── style.css
│   └── images/
├── screenshots/
└── README.md
```

---

## Bagian 1: Box Element (`lab4_box/lab4_box.html`)

### 1.1 Box element tanpa float
Tiga `<div>` di dalam `<section>` diberi `padding: 10px` dan warna latar berbeda. Tanpa `float`, setiap `div` adalah elemen *block*, sehingga lebarnya penuh dan tersusun ke bawah.

![Box tanpa float](screenshots/01-box-tanpa-float.png)

### 1.2 CSS Float
Menambahkan `float: left` pada selector `div`. Elemen "mengambang" ke kiri sehingga ketiga box berjajar menyamping dan lebarnya menyesuaikan isi.

```css
div {
    float: left;
    padding: 10px;
}
```

![Box dengan float](screenshots/02-box-float.png)

### 1.3 Clearfix
Menambahkan `div4` setelah `div3`, lalu `clear: left` dan `float: none`. Properti `clear` membuat `div4` turun ke bawah elemen float di sebelah kirinya, jadi tidak ikut berjajar.

```css
.div4 {
    background-color: blue;
    clear: left;
    float: none;
}
```

![Clearfix left](screenshots/03-clearfix-left.png)

### 1.4 Eksperimen nilai `clear`
| Nilai | Hasil |
|---|---|
| `left` | Div 4 turun di bawah float kiri (gambar di atas). |
| `both` | Sama seperti `left` di sini, karena Div 4 turun di bawah float kiri maupun kanan. |
| `right` | Tidak berpengaruh, sebab semua elemen float ke kiri. Div 4 tidak turun: kotak birunya memanjang di belakang Div 1-3 dan teks "Div 4" bergeser ke kanan Div 3. |

![clear both](screenshots/04-clear-both.png)
![clear right](screenshots/05-clear-right.png)

---

## Bagian 2: Layout Web Sederhana (`lab4_layout/`)

### 2.1 Kerangka layout dengan HTML5 semantic element
`home.html` dibungkus `<div id="container">`, berisi `<header>`, `<nav>`, `<section id="hero">`, `<section id="wrapper">` (berisi `<section id="main">` dan `<aside id="sidebar">`), dan `<footer>`. Belum ada CSS.

![Kerangka](screenshots/06-layout-kerangka.png)

### 2.2 CSS dasar dan header (`style.css`)
Import Google Font Open Sans, reset margin/padding (`*`), pengaturan `body`, `#container` selebar 980px di tengah halaman dengan `box-shadow`, serta styling `header`.

![Header](screenshots/07-layout-header.png)

### 2.3 Navigasi
`nav` diberi warna biru, link dibuat `inline-block` dengan `padding`, dan efek `:hover` / `.active`.

![Navigasi](screenshots/08-layout-navigasi.png)

### 2.4 Hero panel
Menambahkan konten `<section id="hero">` (judul, paragraf, tombol) dan CSS dengan latar abu-abu dan padding.

![Hero](screenshots/09-layout-hero.png)

### 2.5 Main content dan sidebar (float)
`#main` (640px) dan `#sidebar` (260px) sama-sama `float: left` sehingga tampil berdampingan.

![Main dan sidebar](screenshots/10-layout-main-sidebar-float.png)

### 2.6 Sidebar widget
Dua `.widget-box` di dalam `<aside>`: daftar link dan teks, dengan CSS border, judul biru, dan efek hover.

![Widget](screenshots/11-layout-sidebar-widget.png)

### 2.7 Footer
`clear: both` pada footer agar berada di bawah elemen float `#main` dan `#sidebar`.

![Footer](screenshots/12-layout-footer.png)

### 2.8 Main content: kolom box
Tiga `.box` (lebar 33.33%, `float: left`) di dalam `.row`, gambar dibuat lingkaran dengan `border-radius: 50%`. Pseudo-element `.row:after { clear: both; }` dipakai sebagai clearfix.

![Content box](screenshots/13-layout-content-box.png)

### 2.9 Main content: artikel
Dua `<article class="entry">` dengan gambar `float: left` dan `float: right` (kelas `right-img`), dipisah `<hr class="divider">`.

![Artikel](screenshots/14-layout-content-artikel.png)

### 2.10 Tombol dan hasil akhir
Menambahkan CSS `.btn`, `.btn-large`, `.btn-default` agar tampilan sama dengan Gambar 4.7 pada modul.

![Hasil akhir](screenshots/15-layout-final-home.png)

### 2.11 Halaman Artikel
Dibuat `artikel.html` supaya menu Artikel tidak mengarah ke halaman kosong.

![Artikel](screenshots/16-halaman-artikel.png)

---

## Tugas

### Tugas 1: Layout menu About (`about.html`)
Menggunakan kerangka layout yang sama, berisi deskripsi diri (foto, teks, keahlian), portfolio (3 box), dan pendidikan.

![About](screenshots/17-tugas1-halaman-about.png)

### Tugas 2: Layout menu Contact (`kontak.html`)
Berisi form isian: nama, email, subjek, dan message, serta tombol kirim. Dibuat dengan `.form-group`, `label`, `input`, dan `textarea`.

![Kontak](screenshots/18-tugas2-halaman-kontak.png)

---

## Catatan Perbaikan dari Modul
- Selector `box img` pada modul kurang tanda titik, ditulis `.box img`.
- Pada modul, HTML memakai `class="right-img"` tetapi bagian CSS-nya ditulis `rightimg` di salah satu tempat. Di sini keduanya memakai `right-img`.
- Gambar placeholder diganti file lokal di `images/` (bukan dari dummyimage.com) agar tetap tampil tanpa internet.
