# SISTEM INFORMASI PENDATAAN RENTAL MOTOR BERBASIS WEB
## 1. Analisis Kebutuhan dari Sisi Pengguna (User)
### - Fungsional:
####  Fitur-fitur yang dibutuhkan pengguna:
* Pendaftaran dan Login: Pengguna harus bisa mendaftar dan login ke sistem menggunakan kredensial yang aman.
* Pemesanan Motor: Penggunakan harus bisa melihat daftar motor yang tersedia, memilih motor, dan memesan motor secara online.
* Histori transaksi: Pengguna membutuhkan akses ke riwayat pemesanan yang sudah dilakukan untuk mengetahui status pesanan dan histori sewa.
* Pembayaran: Sistem pembayaran yang mudah digunakan, bisa melalui metode digital seperti transfer bank atau e-wallet.
* Notofikasi: Pengguna membutuhkan notifikasi terkait konfirmasi pesanan, status pembayaran, dan pengingat jatuh tempo pengembalian.
### - Alur Kerja Pengguna:
* Masuk ke aplikasi -> Pilih motor yang tersedia -> Isi detail pemesanan -> Lakukan Pembayaran -> Terima notifikasi konfirmasi -> Kembali atau serahkan motor setelah masa sewa selesai.
### - Antarmula Pengguna (User Interface):
#### Standar atau pedoman desain yang harus diikuti:
* Desains antarmuka yang sederhada dan intuitif.
* Responsif untuk mendukung berbagai perangkat, terutama mobile dan desktop.
* Menggunakan warna yang sesuai dengan branding perusahaan dan memiliki aksesibilitas yang baik untuk berbagai pengguna.
### - Kinerja
#### 1. Respon aplikasi:
* Aplikasi harus dapat merespons dalam waktu kurang dari 3 detik untuk setiap permintaan pengguna, terutama pada pencarian motor dan pemesanan.
#### 2. Jumlah Pengguna
* Sistem harus mampu menangani ratusan hingga ribuan pengguna secara bersamaan tanpa penurunan kinerja yang signifikan, terutama di jam - jam sibuk sepertu akhir pekan atau liburan.
### - Keamanan
#### 1. Data yang perlu dilindungi: 
* Informasi pribadi pengguna (nama, alamat, nomor telepon, email).
* Detail pembayaran pengguna.
### - Perlindungan dari serangan cyber:
*  Sistem harus menggunaka SSL (Secure Socket Layer) untuk komunikasi yang aman.
* Gunakan hashing dan enskripsi untuk penyimpanan data sensitif.
* Implementasi autentikasi dua faktor (2FA) untuk login.
* Pertahanan terhadap serangan SQL Injection, Cross-Site Scripting (XSS), dan Cross-Site Request Forgery (CSRF)
## 2. Analisis Kebutuhan dari Sisi Administrator (Admin)
### - Pengelolaan Data:
#### 1. Cara mengelola data pengguna, produk, dan transaksi:
* Admin harus dapat menambah, mengedit, dan menghapus data pengguna, motor serta transaksi melalui panel admin
* Harus ada fitur pemcarian dan filtering untuk mempermudah pengelolaan data.
#### 2. Backup dan restore data: 
* Sisitem harus menyediakan backup otomatis dan manual untuk menjaga keamanan data jika terjadi kesalahan atau serangan.
* Fitur restore diperlukan untuk memulihkan data yang hilang atau rusak.
### - Laporan
#### 1. Laporan yang dibutuhkan oleh administrator:
* Laporan pendapatan harian, mingguan, dan bulanan berdasarkan transaksi.
* Laporan pemesanan untuk mengetahui tingkat penyewaan motor.
* Laporan pengguna aktif yang sering menggunakan layanan.
### - Pengembangan dan pemeliharaan:
#### 1. Cara memperbaharui dan mengembangkan aplikasi:
* Sistem haris dibangun dengan arsitektur modular sehingga fitur baru dapat ditambahkan tanpa mengganggu sistem yang sudah ada.
* Pengambangan aplikasi dapat dilakukan dengan version control seperti Git, dan adanya lingkungan staging untuk uji coba sebelum aplikasi dipublikasikan.
#### 2. Cara mengatasi masalah teknis:
* Harus ada tim support yang dapat dihubungi melalui sistem tiket untuk menangani masalah pengguna.
* Monitoring sistem secara real-time untuk mendeteksi masalah seperti overload server atau error pada aplikasi.
* Sistem log yang mendetil untuk membantu dalam pemecahan masalah.
