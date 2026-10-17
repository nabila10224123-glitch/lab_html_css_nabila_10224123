# Jawaban Praktikum: Nabila Raudatul Nabawiah (10224123)

## Bagian 1: Pemanasan

1. Pada aturan `nav a.active:hover { color: red; }`:
   - Selector: `nav a.active:hover`
   - Deklarasi: `color: red;`
   - Property: `color`
   - Value: `red`
   - Pseudo-class: `:hover`

2. Elemen block: `p`, `li`, `h2`. Elemen inline: `span`, `a`, `strong`.

3. Paragraf yang berwarna hijau adalah **A dan B**, karena keduanya merupakan keturunan elemen dengan class `box`.

4. Warnanya **merah**, karena selector `#title` memiliki specificity lebih tinggi daripada `.heading` dan `h1`.

5. Penutup tag tidak berurutan. Perbaikan: `<p>Hello <strong>world</strong></p>`.

## Bagian 3: Prediksi Selector Golf

**P1. Prediksi warna:**
- (a) Weekly hack nights: **hijau**.
- (b) Bring your own laptop: **oranye**.
- (c) © 2026 Student Affairs: **biru**.

Setelah diuji, hasilnya tetap sama:
- (a) Hijau karena `section p` lebih spesifik daripada `p`.
- (b) Oranye karena selector `.note` lebih spesifik daripada `section p`.
- (c) Biru karena hanya cocok dengan selector `p`.

**P2. Urutan specificity tertinggi ke terendah:**

1. `#tech p`
2. `.club p`
3. `main section p`
4. `p`

## Bagian 4: Box Model

**Q1 (content-box):**

Lebar kartu yang terlihat dari tepi border ke tepi border:

`300px + 16px + 16px + 1px + 1px = 334px`

Jadi, lebarnya adalah **334px**. Margin tidak termasuk dalam lebar tersebut.

**Q2 (border-box):**

Jika menggunakan `box-sizing: border-box`, lebar keseluruhan kartu menjadi **300px**, termasuk padding dan border. Area konten akan menyesuaikan agar semuanya muat dalam lebar tersebut.

**Pengecekan DevTools:**

- Content: lebar area konten sesuai perhitungan browser.
- Padding: 16px pada setiap sisi jika aturan kartu diterapkan.
- Border: 1px pada setiap sisi jika aturan kartu diterapkan.
- Margin: sesuai nilai CSS yang digunakan.

Nilai aktual harus diperiksa melalui DevTools pada elemen yang dipilih.

## Bagian 5: Tabel Debug

| No. | Bagian | Bug | Perbaikan | Cara Menemukannya |
|---|---|---|---|---|
| 1 | CSS body | `colour` bukan properti CSS yang valid | Ganti menjadi `color` | Membaca kode |
| 2 | CSS header | Kurang titik koma setelah deklarasi background | Tambahkan `;` | Membaca kode |
| 3 | CSS `.Card` | Nama class berbeda dengan HTML `.card` | Ubah menjadi `.card` | Membandingkan HTML dan CSS |
| 4 | CSS `#news-list` | ID berbeda dengan `newsList` | Samakan nama ID | Membandingkan HTML dan CSS |
| 5 | CSS font-size | `18 px` tidak valid | Ubah menjadi `18px` | DevTools |
| 6 | CSS text-align | `centre` bukan nilai yang valid | Ganti menjadi `center` | Membaca kode |
| 7 | Heading | `<h1>` ditutup dengan `</h2>` | Ganti menjadi `</h1>` | W3C Validator |
| 8 | Link About | Tanda kutip atribut href tidak lengkap | Gunakan `<a href="about.html">About</a>` | W3C Validator |
| 9 | Gambar | Tidak memiliki atribut alt | Tambahkan `alt="Ilustrasi berita kampus"` | W3C Validator dan aksesibilitas |

## Bagian 6: Tabel Code Review

| No. | Bagian | Masalah | Mengapa Penting | Perbaikan |
|---|---|---|---|---|
| 1 | Awal dokumen | Tidak ada `<!DOCTYPE html>` | Browser dapat menggunakan mode kompatibilitas | Tambahkan deklarasi doctype |
| 2 | Elemen html | Tidak ada atribut `lang` | Membantu teknologi bantu mengenali bahasa | Gunakan `<html lang="id">` |
| 3 | Head | Tidak ada charset dan viewport | Encoding dan tampilan perangkat tidak diatur dengan baik | Tambahkan meta charset dan viewport |
| 4 | Header | Lebar tetap 1200px | Bisa melampaui layar ponsel | Gunakan lebar responsif dan `max-width` |
| 5 | Navigasi | Menggunakan `!important` | Menyulitkan pemeliharaan CSS | Hapus `!important` |
| 6 | Content | Warna `#bbbbbb` berkontras rendah pada latar putih | Teks sulit dibaca | Gunakan warna teks lebih gelap |
| 7 | Sidebar | Aturan CSS tidak digunakan | Membuat kode tidak diperlukan | Hapus atau gunakan aturan tersebut |
| 8 | Judul kampus | Menggunakan div dan b, bukan heading | Struktur dokumen kurang semantik | Gunakan `<h1>` |
| 9 | Struktur halaman | Terlalu banyak div | Struktur bagian halaman kurang jelas | Gunakan elemen semantik HTML |
| 10 | Judul bagian | Menggunakan inline style | Sulit dipelihara | Gunakan `<h2>` dan CSS terpisah |
| 11 | Jarak konten | Menggunakan banyak `<br>` | HTML digunakan untuk mengatur jarak visual | Gunakan margin dan padding CSS |
| 12 | Gambar | Tidak ada alt | Informasi gambar tidak tersedia bagi pembaca layar | Tambahkan atribut alt |
| 13 | Input nama | Tidak memiliki label | Kurang aksesibel | Tambahkan label yang terhubung ke input |
| 14 | Input email | Menggunakan `type="text"` | Tidak ada validasi format email bawaan | Gunakan `type="email"` |
| 15 | Tombol kirim | Hanya menjalankan alert | Data tidak benar-benar dikirim | Gunakan form dan mekanisme pengiriman yang sesuai |
| 16 | Footer | Class footer tidak memiliki aturan CSS | Class tidak memberi efek gaya | Tambahkan CSS atau hapus class |

### Refleksi

1. Masalah yang paling sulit disadari hanya dari tampilan browser adalah masalah semantik dan aksesibilitas. Halaman dapat terlihat baik meskipun struktur heading, label, dan atribut gambar belum benar.

2. Masalah tersebut tetap penting karena halaman harus mudah diakses, responsif, valid, dan mudah dipelihara. Kode yang baik juga membantu developer lain memahami halaman.

3. Saya akan memeriksa struktur HTML, mencocokkan selector CSS, menguji tampilan di berbagai ukuran layar, menggunakan DevTools, dan memeriksa HTML dengan W3C Validator sebelum mengumpulkan tugas.

## Bagian 7: Exit Ticket

1. Anatomi aturan CSS terdiri dari selector dan blok deklarasi. Selector memilih elemen HTML, sedangkan deklarasi berisi property dan value. Contoh: `p { color: blue; }`.

2. Konsep yang masih perlu saya pelajari adalah specificity ketika beberapa selector mengatur elemen yang sama.

3. Sekarang saya bisa membuat struktur HTML semantik, menghubungkan menu ke section menggunakan ID, membuat tabel dan formulir berlabel, serta menulis selector CSS dasar.