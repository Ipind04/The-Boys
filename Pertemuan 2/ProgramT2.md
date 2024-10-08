# SISTEM INFORMASI RENTAL MOTOR BERBASIS WEB
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

| Aspek     | Kebutuhan Pengguna | Kebutuhan Adimistraktor    |
|-----------|--------------------|----------|
| Fungsional| Mencari dan melihat daftar motor yang tersedia, melakukan penyewaan, melihat riwayat penyewaan | Mengelola data kendaraan, mengatur data pelanggan, memproses transaksi penyewaan, membuat laporan keungan. |
|    Antarmuka Penggunaan    | Desain yang user-friendly, navigasi yang intuitif, tampilan informasi yang jelas   | Dashboard yang mudah digunakan untuk mengelola informasi rental, notifikasi untuk transaksi baru  |
| Kinerja   | Waktu loading yang cepat, aplikasi responsif di berbagai perangkat   | Monitoring kinerja sistem, laporan penggunaan sumber daya untuk mengidentifikasi masalah |
| Keamanan | Proteksi data pribadi pengguna, enkripsi pada saat transaksi, autentikasi pengguna | Backup data secara berkala, kontrol akses untuk admin dan pengguna, sistem logging untuk melacak aktivitas |
| Integrasi | Integrasi dengan metode pembayaran online | Integrasi dengan sistem akuntansi dan laporan keuangan |
| Dukungan | Penduan pengguna dan FAQ, fitur bantuan online | Dokumentasi sistem dan pelatihan untuk administrator |
#### Mengapa analisis kebuthan penting?
### 1.Memahami Kebutuhan Pengguna: 
Analisis kebutuhan membantu dalam mengidentifikasi dan memahami kebutuhan pengguna, baik dari sisi pelanggan maupun administrator. Ini memastikan bahwa sistem yang dibangun sesuai dengan harapan dan kebutuhan mereka.
### 2.Menentukan fungsionalitas yang tepat
Dengan melakukan analisis kebutuhan, tim pengembang dapat menentukan fitur-fitur yang harus ada dalam sistem, seperti manajemen kendaraan, proses penyewaan, dan laporan keungan. Hal ini mencegak pengembangan fitur yang tidak relevan atau tidak diperlukan.
### 3.Meningkatkan Efisiensi dan efektivitas
Analisis kebutuhan yang baik membantu dalam merancang sistem yang lebih efisien. Dengan memahami alur kerja dan kebutuhan, sistem dapat dirancang untuk mengurani langkah-langkah yang tidak perlu, sehingga meningkatkan produktivitas.
### 4.Mencegah kesalahan dan biaya tambahan
Jika kebutuhan tidak dianalisis dengan baik, bisa terjadi kesalahan dalam pengembangan yang mengakibatkan kebutuhan tambahan atau revisi. Ini dapat menyebabkan peningkatan biaya dan waktu pengerjaan
### 5.Mendukung pengambil keputusan
Dengan data dan informasi yang jelas tentang kebutuhan, pemangku kepentingan dapat membuat keputusan yang lebih baik terkait desain, pengembangan, dan pengelolaan sistem.
### 6. Menjamin keamanan dan kepatuhan
Analisis kebutuhan membatu dalam mengidentifikasi aspek-aspek keamanan yang perlu diperhatikan, seperti perlindungan data pribadi dan transaksi. Ini penting untuk mematuhi regulasi yang berlaku dan menjaga kepercayaan pengguna.
### 7.Peningkatan pengalaman pengguna
Dengan memahami kebutuhan pengguna, sistem dapat dirancang untuk memberikan pengalaman yang lebih baik, baik dalam penggunaan sehari-hari maupun dalam proses penyewaan. Hal ini dapat meningkatkan kepuasan pelanggan dan loyalitas.
### 8.Dasar untuk pengujian dan validasi
Analisis kebutuhan memberikan kriteria yang jelas untuk pengujian dan validasi sistem. Ini memungkinkan pengembangan untuk memastikan bahwa sistem yang dibangun memenuhi semua kebutuhan yang telah didentifikasi.
#### Teknik pengumpulan data analisis kebutuhan
### 1. Wawancara : 
Melakukan wawancara dengan pemangku kepentingan, serta pemilik rental, karyawan, dan pelanggan untuk menggali informasi mendalam tentang kebutuhan, harapan, dan tantangan yang dihadapi dalam proses penyewaan motor.
### 2. Kuesioner : 
Membagi kuesioner kepada pelanggan dan karyawan untuk mengumpulkan informasi secara kuantitatif untuk mendapatkan data yang dapat dianalisis mengenai preferensi pengguna, fitur yang diinginkan, dan tingkat keputusan terhadap sistem yang ada.
### 3. Obeservasi :
Mengamati proses penyewaan motor yang berlangsung di rental untuk memahami alur kerja, interaksi antara pengguna dan sistem saat ini, serta mengidentifikasi potensi masalah atau kebutuhan yang belum terpenuhi.
### 4. Diskusi Kelompok :
Mengumpulkan sekelompok orang (pelanggan, karyawan) untuk berdiskusi tentang fitur dan kebutuhan sistem.
### 5. Analisis Online :
Menggunakan platform survei online untuk menjangkau lebih banyak responden.
# KESIMPULAN
Analisis kebutuhan ini mencangkup aspek-aspek penting yang harus dipenuhi oleh sistem informasi pendataan rental motor berbasis web. Dengan pemenuhan kebutuhan ini, diharapkan sistem dapat berjalan dengan efisien dan memberikan pengalaman pengguna yang baik
