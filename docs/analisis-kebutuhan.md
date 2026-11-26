# Analisis Kebutuhan

**Topik:** Perancangan antarmuka proses pemesanan jadwal dan pembayaran uang muka (DP)
pada komputerisasi aplikasi booking lapangan futsal.

Analisis dibagi tiga sesuai materi: kebutuhan fungsional, non-fungsional, dan kontekstual.
Ruang lingkup hanya dua proses: **pemesanan jadwal** dan **pembayaran DP**.

---

## 1. Kebutuhan Fungsional

Fitur dan tindakan utama yang ingin dilakukan pengguna.

### A. Proses pemesanan jadwal

| Kode | Kebutuhan | Layar |
|---|---|---|
| F-01 | Pengguna dapat melihat daftar lapangan beserta jenis lantai dan harga mulai | Pilih Lapangan |
| F-02 | Pengguna dapat memilih tanggal main (hari ini sampai 6 hari ke depan) | Pilih Jadwal |
| F-03 | Pengguna dapat melihat ketersediaan setiap slot jam: tersedia, terisi, atau sudah lewat | Pilih Jadwal |
| F-04 | Pengguna dapat memilih satu atau beberapa slot jam berurutan | Pilih Jadwal |
| F-05 | Aplikasi menghitung total harga otomatis sesuai tarif siang dan malam | Pilih Jadwal |
| F-06 | Pengguna dapat melihat ringkasan pesanan: jadwal, rincian harga, DP, dan sisa pelunasan | Ringkasan Pesanan |
| F-07 | Pengguna dapat mengisi nama dan nomor HP, dengan pemeriksaan format nomor HP | Ringkasan Pesanan |
| F-08 | Aplikasi mengunci slot yang dipilih selama 15 menit setelah pengguna lanjut ke pembayaran | Ringkasan Pesanan |
| F-09 | Aplikasi memberi tahu jika slot keburu dipesan pengguna lain, lalu mengarahkan memilih ulang | Pilih Jadwal |

### B. Proses pembayaran DP

| Kode | Kebutuhan | Layar |
|---|---|---|
| F-10 | Pengguna dapat memilih metode bayar: QRIS, transfer virtual account, atau e-wallet | Pilih Metode Bayar |
| F-11 | Pengguna dapat melihat instruksi pembayaran sesuai metode yang dipilih | Instruksi Pembayaran |
| F-12 | Pengguna dapat menyalin nomor virtual account dengan satu ketukan | Instruksi Pembayaran |
| F-13 | Pengguna dapat melihat sisa waktu pembayaran (hitung mundur) | Metode Bayar, Instruksi Pembayaran |
| F-14 | Pengguna dapat mengecek status pembayaran | Instruksi Pembayaran |
| F-15 | Pengguna menerima bukti booking berisi kode booking, detail jadwal, dan sisa pelunasan | Booking Berhasil |
| F-16 | Pengguna dapat menyimpan bukti booking | Booking Berhasil |
| F-17 | Jika pembayaran gagal, pengguna dapat mencoba lagi atau mengganti metode | Pembayaran Gagal |
| F-18 | Jika waktu habis, aplikasi melepas slot dan mengarahkan pengguna memilih jadwal lagi | Waktu Bayar Habis |
| F-19 | Pengguna dapat membatalkan pembayaran setelah melewati konfirmasi | Instruksi Pembayaran |

---

## 2. Kebutuhan Non-Fungsional

Kualitas interaksi dan pengalaman pengguna.

| Kode | Aspek | Kebutuhan | Penerapan di desain |
|---|---|---|---|
| NF-01 | Kecepatan respons | Perubahan pilihan slot dan total harga tampil seketika (di bawah 1 detik) setelah diketuk | Total di bagian bawah layar Pilih Jadwal langsung berubah |
| NF-02 | Kecepatan tugas | Booking selesai dalam 7 layar, sekitar 2 menit, tanpa menunggu balasan admin | Alur 7 layar tanpa langkah login di dalam proses |
| NF-03 | Keterbacaan teks | Teks isi minimal 14-15 px, teks kecil minimal 11 px; kontras teks dan latar minimal 4,5:1 (WCAG AA) | Angka penting (total, DP, kode booking, hitung mundur) ditulis lebih besar dan tebal |
| NF-04 | Responsivitas layar | Tampilan tetap utuh di lebar layar HP 360-430 px, tanpa geser ke samping; mendukung mode gelap | Satu kolom, grid jam 3 kolom, warna berbasis tema |
| NF-05 | Aksesibilitas | Target sentuh minimal 44 x 44 px; status tidak hanya dibedakan warna; setiap kolom isian punya label; fokus keyboard terlihat | Slot terisi diberi arsir, coretan, dan label "Terisi" |
| NF-06 | Kejelasan biaya | Total, DP, dan sisa pelunasan tampil sebelum pengguna membayar | Rincian harga di layar Ringkasan; nominal DP tertulis di tombol |
| NF-07 | Pencegahan kesalahan | Pengguna tidak bisa lanjut dengan data salah atau slot yang tidak tersedia | Tombol nonaktif sampai data valid; slot terisi tidak bisa dipilih |
| NF-08 | Pemulihan kesalahan | Setiap pesan gagal menyebut penyebab dan jalan keluarnya | Layar Pembayaran Gagal dan Waktu Habis punya tombol tindakan |
| NF-09 | Keamanan data | Data pribadi yang diminta seminimal mungkin (nama dan nomor HP); aplikasi tidak menyimpan data kartu | Pembayaran diteruskan ke QRIS, bank, atau e-wallet |

---

## 3. Kebutuhan Kontekstual

Kondisi saat aplikasi dipakai.

### Perangkat yang digunakan
- **Smartphone Android kelas menengah**, layar sekitar 6 inci, karena itu perangkat yang paling umum dipakai mahasiswa dan pekerja muda.
- **Sering dipakai satu tangan**, misalnya sambil berjalan atau di atas motor saat berhenti.
  Akibatnya, tombol utama diletakkan di bagian bawah layar agar terjangkau ibu jari.

### Waktu penggunaan
- **Sore sampai malam**, setelah jam kuliah atau kerja, saat pengguna mengatur jadwal main bersama teman.
- **Jadwal malam (18.00 ke atas) paling diburu**, sehingga slot cepat habis dan rawan bentrok.
  Akibatnya, aplikasi perlu kunci slot 15 menit dan pemberitahuan kalau slot direbut orang lain.
- **Sering mendadak** (hari H atau H-1).
  Akibatnya, pilihan "Hari ini" diletakkan paling depan, dan jam yang sudah lewat ditandai.

### Lokasi dan koneksi
- Dipakai di kos, kampus, atau di jalan dengan **koneksi internet yang tidak selalu stabil**.
  Akibatnya, status pembayaran harus jelas, dan pesanan tidak langsung hilang saat pembayaran gagal (slot tetap dikunci selama sisa waktu).

### Tingkat literasi digital pengguna
- **Pengguna utama:** mahasiswa dan pekerja muda usia 18-35 tahun, terbiasa memakai e-wallet, QRIS, dan aplikasi pemesanan online.
- **Kebiasaan sebelumnya:** booking lewat chat WhatsApp ke admin lapangan.
  Masalahnya: balasan lambat, jadwal ternyata sudah terisi, dan bukti transfer dikirim manual.
- **Satu orang biasanya memesan untuk satu tim.**
  Akibatnya, bukti booking harus mudah disimpan dan dibagikan ke teman satu tim.
- **Akibat untuk desain:** bahasa dibuat sederhana dan sehari-hari ("Pilih jam", "Bayar DP"), istilah teknis dihindari, dan alur dibuat lurus tanpa banyak cabang.

---

## 4. Catatan

- Harga, persentase DP (50%), dan lama kunci slot (15 menit) adalah **asumsi** untuk keperluan perancangan.
- Kebutuhan kontekstual sebaiknya **divalidasi** dengan wawancara singkat ke 3-5 orang yang rutin bermain futsal.
