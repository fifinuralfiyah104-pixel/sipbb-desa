# SIP-PBB Desa

SIP-PBB Desa adalah aplikasi web ringan untuk membantu pemerintah desa mengelola administrasi Pajak Bumi dan Bangunan Perdesaan dan Perkotaan (PBB-P2) secara praktis, terstruktur, dan mudah digunakan.

## Description

SIP-PBB Desa adalah aplikasi web untuk mengelola ketetapan, pembayaran, kolektor, data wajib pajak, laporan, surat tagihan, QR informasi dokumen, serta backup dan restore data PBB-P2 desa melalui antarmuka yang sederhana.

## Fitur

- Dashboard realisasi PBB-P2 dan ringkasan pembayaran.
- Import ketetapan PBB dari file Excel.
- Import pembayaran kumulatif berkali-kali tanpa mengunggah ulang ketetapan.
- Import dan pembaruan data kolektor.
- Manajemen data Subjek Pajak dan pemetaan NOP.
- Edit wilayah dan kolektor pada Data Master NOP.
- Pencarian NOP, nama, alamat, kolektor, dan data subjek pajak.
- Laporan rekapitulasi ketetapan, pembayaran, tunggakan, wilayah, dan kolektor.
- Generator surat tagihan PBB-P2.
- QR informatif untuk dokumen surat.
- Ekspor data dan laporan ke CSV atau Excel sesuai fitur yang tersedia.
- Backup dan restore database melalui JSON.
- Penyimpanan lokal tanpa server database.
- Dukungan penggunaan melalui file lokal atau web server/NAS.

## Teknologi

- HTML, CSS, dan JavaScript dalam satu file aplikasi.
- Tailwind CSS melalui CDN.
- Chart.js untuk visualisasi data.
- SheetJS untuk membaca dan menulis file Excel.
- Font Awesome dan Google Fonts untuk tampilan antarmuka.
- `localStorage` browser untuk penyimpanan data aplikasi.

## Persyaratan

- Browser modern seperti Google Chrome, Microsoft Edge, atau Mozilla Firefox.
- JavaScript aktif.
- Koneksi internet saat menggunakan versi yang memuat dependensi dari CDN.
- File Excel mengikuti format kolom yang disediakan oleh template aplikasi.

## Menjalankan aplikasi

1. Buka `index.html` menggunakan browser modern, atau letakkan folder aplikasi pada web server/NAS.
2. Buka menu **Pengaturan** untuk mengisi identitas desa.
3. Siapkan backup JSON sebelum melakukan penghapusan atau perubahan besar.
4. Import data ketetapan sebagai master tahun berjalan.
5. Import data pembayaran dan kolektor sesuai kebutuhan.
6. Periksa hasil pada Dashboard, Data Master NOP, dan Laporan.

## Alur import yang disarankan

1. Import **Ketetapan** terlebih dahulu.
2. Import **Kolektor** untuk memperbarui wilayah dan petugas.
3. Import **Pembayaran** dari BPPKAD. File pembayaran diperlakukan sebagai snapshot kumulatif sampai tanggal tertentu.
4. Import pembayaran berikutnya kapan saja tanpa mengulang import ketetapan.
5. Simpan backup JSON setelah perubahan penting.

## Penyimpanan dan sinkronisasi data

Data aplikasi disimpan pada `localStorage` browser berdasarkan origin dan perangkat. File `index.html` yang berada di NAS hanya menyajikan aplikasi; data tidak otomatis tersimpan atau tersinkron ke NAS.

Untuk memindahkan data antarperangkat:

1. Gunakan menu backup untuk mengunduh file JSON.
2. Pindahkan file JSON melalui media atau penyimpanan yang aman.
3. Gunakan menu restore pada perangkat tujuan.
4. Simpan backup di lokasi terbatas karena isinya dapat memuat data wajib pajak dan pembayaran.

## Keamanan

- Gunakan Cloudflare Access atau mekanisme autentikasi lain jika aplikasi dipublikasikan melalui internet.
- Aktifkan MFA untuk akun yang mengakses aplikasi atau NAS.
- Jangan membuka port administrasi NAS langsung ke internet.
- Batasi akses backup JSON dan buat backup berkala.
- Periksa file impor sebelum digunakan.
- Cloudflare Tunnel melindungi jalur koneksi, tetapi tidak menggantikan autentikasi aplikasi.
- Penyimpanan `localStorage` bukan database terpusat dan bukan penyimpanan terenkripsi.

## Lisensi

Proyek ini menggunakan lisensi MIT. Lihat file [LICENSE](LICENSE).

## Catatan

Aplikasi ini dirancang untuk membantu administrasi dan rekapitulasi internal desa. Validasi, pencocokan, dan pengesahan data tetap mengikuti prosedur resmi pemerintah desa dan instansi terkait.
