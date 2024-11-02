# CRUD Sistem Manajemen Kendaraan Pemeliharaan
Proyek ini adalah aplikasi sederhana untuk mengelola data kendaraan dengan fitur CRUD (Create, Read, Update, Delete) yang dibuat menggunakan PHP dan HTML.

## 1. Struktur Folder
### Folder ini berisi empat file PHP utama:
### tambah_kendaraan.php: Menambahkan data kendaraan.
### lihat_kendaraan.php: Menampilkan daftar kendaraan.
### ubah_kendaraan.php: Mengedit data kendaraan.
### hapus_kendaraan.php: Menghapus data kendaraan.

## 2. Formulir Tambah Kendaraan
Formulir HTML untuk menambahkan data kendaraan dalam file tambah_kendaraan.php:
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tambah Kendaraan</title>
</head>
<body>
    <h1>Tambah Kendaraan</h1>
    <form action="tambah_kendaraan.php" method="POST">
        <label for="merk">Merk Kendaraan:</label>
        <input type="text" name="merk" required><br>
        <label for="model">Model Kendaraan:</label>
        <input type="text" name="model" required><br>
        <label for="tahun">Tahun:</label>
        <input type="number" name="tahun" required><br>
        <label for="status">Status Kendaraan:</label>
        <input type="text" name="status" required><br>
        <input type="submit" value="Simpan">
    </form>
</body>
</html>


## 3. Menyimpan Data ke Database
Kode PHP untuk menyimpan data kendaraan ke dalam tabel, berada dalam file tambah_kendaraan.php:


## 4. Menampilkan Daftar Kendaraan
File lihat_kendaraan.phpyang digunakan untuk membaca dan menampilkan daftar kendaraan:

## 5. Mengedit Data Kendaraan
File ubah_kendaraan.phpuntuk mengedit data kendaraan berdasarkan ID:


## 6. Menghapus Data Kendaraan
File hapus_kendaraan.phpyang digunakan untuk menghapus data kendaraan:

