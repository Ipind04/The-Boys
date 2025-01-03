##  Struktur Tabel (MySQL)
### 1 Query Tabel books
```
CREATE TABLE books (
    id INT AUTO_INCREMENT PRIMARY KEY,
    title VARCHAR(255) NOT NULL,
    author VARCHAR(255) NOT NULL,
    publisher VARCHAR(255) NOT NULL,
    year INT NOT NULL
);

```
### 2 Formulir Input dan Proses Perekaman Data
#### Membuat file bernama create_book.php:
```
<?php
// Koneksi ke database
$host = 'localhost';
$dbname = 'buku';
$user = 'root';
$pass = '';

try {
    $pdo = new PDO("mysql:host=$host;dbname=$dbname", $user, $pass);
    $pdo->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
} catch (PDOException $e) {
    die("Koneksi gagal: " . $e->getMessage());
}

// Proses penyimpanan data
if ($_SERVER['REQUEST_METHOD'] === 'POST') {
    $title = $_POST['title'];
    $author = $_POST['author'];
    $publisher = $_POST['publisher'];
    $year = $_POST['year'];

    $sql = "INSERT INTO books (title, author, publisher, year) VALUES (:title, :author, :publisher, :year)";
    $stmt = $pdo->prepare($sql);

    try {
        $stmt->execute([
            ':title' => $title,
            ':author' => $author,
            ':publisher' => $publisher,
            ':year' => $year,
        ]);
        echo "Data berhasil disimpan!";
    } catch (Exception $e) {
        echo "Gagal menyimpan data: " . $e->getMessage();
    }
}
?>

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tambah Buku</title>
</head>
<body>
    <h1>Tambah Buku</h1>
    <form action="create_book.php" method="POST">
        <label for="title">Judul Buku:</label><br>
        <input type="text" id="title" name="title" required><br><br>

        <label for="author">Penulis:</label><br>
        <input type="text" id="author" name="author" required><br><br>

        <label for="publisher">Penerbit:</label><br>
        <input type="text" id="publisher" name="publisher" required><br><br>

        <label for="year">Tahun Terbit:</label><br>
        <input type="number" id="year" name="year" required><br><br>

        <button type="submit">Simpan</button>
    </form>
</body>
</html>
```

### 3 Membaca Data dari Tabel
#### Buat file bernama read_books.php
```
<?php
// Koneksi ke database
$host = 'localhost';
$dbname = 'buku';
$user = 'root';
$pass = '';

try {
    $pdo = new PDO("mysql:host=$host;dbname=$dbname", $user, $pass);
    $pdo->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
} catch (PDOException $e) {
    die("Koneksi gagal: " . $e->getMessage());
}

// Mengambil data dari tabel
$sql = "SELECT * FROM books";
$stmt = $pdo->query($sql);
$books = $stmt->fetchAll(PDO::FETCH_ASSOC);
?>

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Daftar Buku</title>
</head>
<body>
    <h1>Daftar Buku</h1>
    <table border="1">
        <thead>
            <tr>
                <th>ID</th>
                <th>Judul Buku</th>
                <th>Penulis</th>
                <th>Penerbit</th>
                <th>Tahun Terbit</th>
            </tr>
        </thead>
        <tbody>
            <?php foreach ($books as $book): ?>
                <tr>
                    <td><?= htmlspecialchars($book['id']) ?></td>
                    <td><?= htmlspecialchars($book['title']) ?></td>
                    <td><?= htmlspecialchars($book['author']) ?></td>
                    <td><?= htmlspecialchars($book['publisher']) ?></td>
                    <td><?= htmlspecialchars($book['year']) ?></td>
                </tr>
            <?php endforeach; ?>
        </tbody>
    </table>
</body>
</html>
```
## Output 
### Mengimput data 1
![menginput data](https://github.com/user-attachments/assets/67c2b6c0-9974-48a1-b2a0-4513622cd583)

### Mengimput data 2
![menginput data2](https://github.com/user-attachments/assets/33d91074-e312-4ca6-bc30-504dca5ee594)

### Mengimput data 3
![menginput data3](https://github.com/user-attachments/assets/264cd2da-83eb-48f1-8b51-1491c1e0741c)

### Daftar buku yang di tambahkan 
![daftar buku](https://github.com/user-attachments/assets/4efe8a0c-363b-4c27-b1f8-38179988c9d6)

### data yang tersimpan pada Database dan Tabel
![Data base dan Tabel](https://github.com/user-attachments/assets/bc0f539d-6279-43cc-8dad-3b64ac49d80a)


