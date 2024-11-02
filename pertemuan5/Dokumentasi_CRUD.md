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
Berikut adalah kode HTML untuk form tambah kendaraan:
```
html
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
```
## 3. Menyimpan Data ke Database
Kode PHP untuk menyimpan data kendaraan ke dalam tabel, berada dalam file tambah_kendaraan.php:
```<?php
// Koneksi ke database
$conn = new mysqli('localhost', 'root', '', 'pemeliharaan_kendaraan');

if ($_SERVER['REQUEST_METHOD'] == 'POST') {
    $merk = $_POST['merk'];
    $model = $_POST['model'];
    $tahun = $_POST['tahun'];
    $status = $_POST['status'];

    // SQL Query untuk menyimpan data
    $sql = "INSERT INTO kendaraan (merk, model, tahun, status) VALUES ('$merk', '$model', '$tahun', '$status')";

    if ($conn->query($sql) === TRUE) {
        echo "Data berhasil disimpan";
    } else {
        echo "Error: " . $conn->error;
    }
}

$conn->close();
?>
```

## 4. Menampilkan Daftar Kendaraan
File lihat_kendaraan.phpyang digunakan untuk membaca dan menampilkan daftar kendaraan:
```
<?php
// Koneksi ke database
$conn = new mysqli('localhost', 'root', '', 'pemeliharaan_kendaraan');

// SQL Query untuk mengambil data kendaraan
$sql = "SELECT * FROM kendaraan";
$result = $conn->query($sql);

echo "<h1>Daftar Kendaraan</h1>";
if ($result->num_rows > 0) {
    echo "<table border='1'>
            <tr>
                <th>ID</th>
                <th>Merk</th>
                <th>Model</th>
                <th>Tahun</th>
                <th>Status</th>
                <th>Aksi</th>
            </tr>";
    // Looping data dan menampilkannya
    while ($row = $result->fetch_assoc()) {
        echo "<tr>
                <td>" . $row['id'] . "</td>
                <td>" . $row['merk'] . "</td>
                <td>" . $row['model'] . "</td>
                <td>" . $row['tahun'] . "</td>
                <td>" . $row['status'] . "</td>
                <td>
                    <a href='ubah_kendaraan.php?id=" . $row['id'] . "'>Edit</a>
                    <a href='hapus_kendaraan.php?id=" . $row['id'] . "'>Hapus</a>
                </td>
            </tr>";
    }
    echo "</table>";
} else {
    echo "Tidak ada data kendaraan.";
}

$conn->close();
?>
```
## 5. Mengedit Data Kendaraan
File ubah_kendaraan.phpuntuk mengedit data kendaraan berdasarkan ID:
```
<?php
// Koneksi ke database
$conn = new mysqli('localhost', 'root', '', 'pemeliharaan_kendaraan');
$id = $_GET['id'];
$sql = "SELECT * FROM kendaraan WHERE id=$id";
$result = $conn->query($sql);
$row = $result->fetch_assoc();
?>
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Edit Kendaraan</title>
</head>
<body>
    <h1>Edit Kendaraan</h1>
    <form action="ubah_kendaraan.php?id=<?= $id ?>" method="POST">
        <label for="merk">Merk Kendaraan:</label>
        <input type="text" name="merk" value="<?= $row['merk'] ?>" required><br>

        <label for="model">Model Kendaraan:</label>
        <input type="text" name="model" value="<?= $row['model'] ?>" required><br>

        <label for="tahun">Tahun:</label>
        <input type="number" name="tahun" value="<?= $row['tahun'] ?>" required><br>

        <label for="status">Status Kendaraan:</label>
        <input type="text" name="status" value="<?= $row['status'] ?>" required><br>

        <input type="submit" value="Simpan Perubahan">
    </form>
</body>
</html>

<?php
if ($_SERVER['REQUEST_METHOD'] == 'POST') {
    $merk = $_POST['merk'];
    $model = $_POST['model'];
    $tahun = $_POST['tahun'];
    $status = $_POST['status'];

    // SQL Query untuk update data
    $sql = "UPDATE kendaraan SET merk='$merk', model='$model', tahun='$tahun', status='$status' WHERE id=$id";

    if ($conn->query($sql) === TRUE) {
        echo "Data berhasil diupdate";
    } else {
        echo "Error: " . $conn->error;
    }

    $conn->close();
}
?>
```

## 6. Menghapus Data Kendaraan
File hapus_kendaraan.phpyang digunakan untuk menghapus data kendaraan:
```
<?php
// Koneksi ke database
$conn = new mysqli('localhost', 'root', '', 'pemeliharaan_kendaraan');

$id = $_GET['id'];

// SQL Query untuk menghapus data
$sql = "DELETE FROM kendaraan WHERE id=$id";

if ($conn->query($sql) === TRUE) {
    echo "Data berhasil dihapus";
} else {
    echo "Error: " . $conn->error;
}

$conn->close();

// Redirect ke halaman daftar kendaraan
header("Location: lihat_kendaraan.php");
?>
```
