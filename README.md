# Lab9Web
## Nama : Nur Laila    
## Nim: 312310149
PHP Modular

## 1. buat folder baru pada docroot webserver (htdocs)
![image](https://github.com/user-attachments/assets/85e8218f-0ebb-48f0-872d-6e83f45440e0)   

## 2. Masuk ke VsCode dan masuk ke folder Latihanweb9_modular
### Buat file baru dengan nama header.php
![image](https://github.com/user-attachments/assets/9d204378-cd03-46e1-9110-d6178761cb0d)   
 ```sh
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Contoh Modularisasi</title>
<link href="style.css" rel="stylesheet" type="text/stylesheet"
media="screen" />
</head>
<body>
        <div class="container">
        <header>
            <h1>Modularisasi Menggunakan Require</h1>
        </header>
        <nav>
            <a href="home.php">Home</a>
            <a href="about.php">Tentang</a>
            <a href="kontak.php">Kontak</a>
        </nav>
```
![image](https://github.com/user-attachments/assets/1fbc3e3b-c8e7-418d-86eb-a351cecf8366)   
File ini berisi struktur awal dokumen HTML, termasuk elemen `<head>` untuk metadata seperti judul halaman dan tautan ke file CSS. Bagian ini juga mencakup navigasi utama website yang akan digunakan bersama di semua halaman.    


### Buat file baru dengan nama footer.php
![image](https://github.com/user-attachments/assets/be617c43-1634-447d-89f4-c4cbf1e78472)   
```sh
        <footer>
            <p>&copy; 2021, Informatika, Universitas Pelita Bangsa</p>
        </footer>
    </div>
</body>
</html>
```
![image](https://github.com/user-attachments/assets/de76d205-4beb-4d22-b542-a007de2fd83d)   
File ini berisi penutup struktur HTML, termasuk footer halaman. Footer biasanya digunakan untuk informasi hak cipta, tautan tambahan, atau informasi penting lainnya.   


### Buat file baru dengan nama home.php
![image](https://github.com/user-attachments/assets/42b64a2e-a081-42fc-b026-8abd2b51e2bb)   
```sh
<?php require('header.php'); ?>

<div class="content">
    <h2>Ini Halaman Home</h2>
    <p>Ini adalah bagian content dari halaman.</p>
</div>

<?php require('footer.php'); ?>
```
![image](https://github.com/user-attachments/assets/0b14d7a9-8a6a-4883-8a4c-8e6414dbe608)   
File ini adalah halaman utama situs. File ini memanfaatkan `require()` untuk menyisipkan `header.php` di bagian atas dan footer.php di bagian bawah, sehingga hanya konten spesifik halaman (seperti teks dan paragraf) yang perlu ditulis di file ini.   


### Buat file baru dengan nama about.php
![image](https://github.com/user-attachments/assets/4fb30542-d007-4b83-ae38-7344e80906b7)  
```sh
<?php require('header.php'); ?>

<div class="content">
    <h2>Ini Halaman About</h2>
    <p>Ini adalah bagian content dari halaman.</p>
</div>

<?php require('footer.php'); ?>
```
![image](https://github.com/user-attachments/assets/2e077eed-8f79-4ec1-9d8e-47c37cfe2861)   
File ini adalah halaman tentang `(About)`. Sama seperti `home.php`, file ini juga menggunakan `require()` untuk menyisipkan header dan footer, sementara konten utama yang ditampilkan adalah deskripsi tentang website atau organisasi.   

## TUGAS DAN JAWABAN
Implementasikan konsep modularisasi pada kode program praktikum 8 tentang
database, sehingga setiap halamannya memiliki template tampilan yang sama.  

Berikut adalah implementasi tugas lab 8 dengan modularisasi, terdiri dari beberapa bagian seperti header, footer, dan halaman lainnya seperti `index.php`, `tambah.php`, dan `ubah.php`. 

### buat file header dengan nama tugas_header.php
```sh
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Modularisasi - Praktikum 8</title>
    <link href="style.css" rel="stylesheet" type="text/css" />
</head>
<body>
    <div class="container">
        <header>
            <h1>Sistem Data Barang</h1>
        </header>
        <nav>
            <a href="index.php">Home</a>
            <a href="tambah.php">Tambah Barang</a>
        </nav>
```
![image](https://github.com/user-attachments/assets/0bb836d4-225e-4374-a211-b616ea05dccb)   

### buat file footer dengan nama tugas_footer.php
```sh
        <footer>
            <p>&copy; 2024, Sistem Informasi, Universitas Pelita Bangsa</p>
        </footer>
    </div>
</body>
</html>
```
![image](https://github.com/user-attachments/assets/0f3da355-7468-4c92-a32b-ea3460ce854b)   

### buat file index dengan nama index.php
```sh
<?php
require('tugas_header.php'); 

$conn = new mysqli("localhost", "root", "", "latihan1");

if ($conn->connect_error) {
    die("Koneksi gagal: " . $conn->connect_error);
}
?>

<div class="content">
    <h2>Data Barang</h2>
    <a href="tambah.php" style="margin-bottom: 10px; display: inline-block;">Tambah Data</a>
    <table border="1" cellspacing="0" cellpadding="10">
        <tr>
            <th>ID</th>
            <th>Kategori</th>
            <th>Nama</th>
            <th>Gambar</th>
            <th>Harga Beli</th>
            <th>Harga Jual</th>
            <th>Stok</th>
            <th>Aksi</th>
        </tr>
        <?php
     
        $sql = "SELECT * FROM data_barang";
        $result = $conn->query($sql);

      
        if ($result->num_rows > 0) {
            while ($row = $result->fetch_assoc()) {
                echo "<tr>
                    <td>{$row['id_barang']}</td>
                    <td>{$row['kategori']}</td>
                    <td>{$row['nama']}</td>
                    <td><img src='{$row['gambar']}' alt='{$row['nama']}' width='50'></td>
                    <td>{$row['harga_beli']}</td>
                    <td>{$row['harga_jual']}</td>
                    <td>{$row['stok']}</td>
                    <td>
                        <a href='ubah.php?id={$row['id_barang']}'>Ubah</a> |
                        <a href='hapus.php?id={$row['id_barang']}' onclick='return confirm(\"Yakin ingin menghapus data ini?\")'>Hapus</a>
                    </td>
                </tr>";
            }
        } else {
            echo "<tr><td colspan='8'>Tidak ada data</td></tr>";
        }

        $conn->close();
        ?>
    </table>
</div>

<?php
require('footer.php'); 
?>
```
![image](https://github.com/user-attachments/assets/dd074538-d1bc-435e-b5b2-a9292f917986)   
Koneksi Database: Menghubungkan ke database latihan1 untuk mengambil data barang.   
Tampil Data: Menampilkan data barang dalam tabel HTML.   
Aksi: Menyediakan link untuk mengubah dan menghapus data barang.  

### file tambah
```sh
<?php
require('tugas_header.php'); 

$conn = new mysqli("localhost", "root", "", "latihan1");

if ($_SERVER['REQUEST_METHOD'] === 'POST') {
    $kategori = $_POST['kategori'];
    $nama = $_POST['nama'];
    $gambar = $_POST['gambar'];
    $harga_beli = $_POST['harga_beli'];
    $harga_jual = $_POST['harga_jual'];
    $stok = $_POST['stok'];

    $sql = "INSERT INTO data_barang (kategori, nama, gambar, harga_beli, harga_jual, stok) 
            VALUES ('$kategori', '$nama', '$gambar', '$harga_beli', '$harga_jual', '$stok')";
    
    if ($conn->query($sql) === TRUE) {
        echo "<p>Data berhasil ditambahkan</p>";
    } else {
        echo "<p>Error: " . $conn->error . "</p>";
    }
}
?>

<div class="content">
    <h2>Tambah Data Barang</h2>
    <form method="post">
        <label>Kategori:</label><br>
        <input type="text" name="kategori" required><br>
        <label>Nama:</label><br>
        <input type="text" name="nama" required><br>
        <label>Gambar:</label><br>
        <input type="text" name="gambar" required><br>
        <label>Harga Beli:</label><br>
        <input type="number" name="harga_beli" required><br>
        <label>Harga Jual:</label><br>
        <input type="number" name="harga_jual" required><br>
        <label>Stok:</label><br>
        <input type="number" name="stok" required><br><br>
        <button type="submit">Simpan</button>
    </form>
</div>

<?php
require('footer.php'); 
?>
```
![image](https://github.com/user-attachments/assets/a0c65f61-bbe2-4bd2-aa9f-ddf8f804176f)   
Form Input: Menyediakan form untuk menambah data barang baru.   
Proses Tambah: Setelah form disubmit, data barang disimpan ke database menggunakan query `INSERT INTO`.  


### file ubah
```sh
<?php
require('header.php');

$id = $_GET['id'];
$conn = new mysqli("localhost", "root", "", "db_barang");
$sql = "SELECT * FROM barang WHERE id=$id";
$result = $conn->query($sql);
$row = $result->fetch_assoc();
?>

<div class="content">
    <h2>Ubah Barang</h2>
    <form method="post" action="proses_ubah.php">
        <input type="hidden" name="id" value="<?php echo $row['id']; ?>">
        <label for="nama">Nama Barang:</label>
        <input type="text" id="nama" name="nama" value="<?php echo $row['nama']; ?>" required>
        <br>
        <label for="harga">Harga:</label>
        <input type="number" id="harga" name="harga" value="<?php echo $row['harga']; ?>" required>
        <br>
        <label for="stok">Stok:</label>
        <input type="number" id="stok" name="stok" value="<?php echo $row['stok']; ?>" required>
        <br>
        <button type="submit">Ubah</button>
    </form>
</div>

<?php
require('footer.php'); 
?>
```
![image](https://github.com/user-attachments/assets/ef50a6a5-546f-4ab8-bcd5-9500db0616ea)   
Menampilkan form untuk mengedit data barang berdasarkan id yang diterima melalui parameter `GET`.   
Setelah form di-submit, data di-update ke database dengan query `UPDATE`.   

### file hapus
```sh
<?php
require('tugas_header.php'); // Memanggil header

// Koneksi ke database
$conn = new mysqli("localhost", "root", "", "latihan1");

// Periksa koneksi
if ($conn->connect_error) {
    die("Koneksi gagal: " . $conn->connect_error);
}

// Validasi parameter 'id'
if (!isset($_GET['id']) || empty($_GET['id'])) {
    echo "<p>ID tidak ditemukan. <a href='index.php'>Kembali ke halaman utama</a></p>";
    exit;
}

$id = intval($_GET['id']); // Pastikan id adalah angka untuk mencegah SQL injection

// Hapus data barang
$sql_delete = "DELETE FROM data_barang WHERE id_barang = $id";

if ($conn->query($sql_delete) === TRUE) {
    echo "<p>Data berhasil dihapus. <a href='index.php'>Kembali ke halaman utama</a></p>";
} else {
    echo "<p>Terjadi kesalahan: " . $conn->error . "</p>";
}

$conn->close();
?>

<?php
require('footer.php'); // Memanggil footer
?>
```
![image](https://github.com/user-attachments/assets/5a5ded40-428e-4198-988d-d25177fd0567)   
Menghapus data barang berdasarkan id yang diterima melalui parameter `GET`.
Query `DELETE` digunakan untuk menghapus data di database.  

### file style.css
```sh
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    background-color: #f4f4f4;
}

.container {
    width: 80%;
    margin: auto;
    overflow: hidden;
}

header {
    background: #333;
    color: #fff;
    padding: 10px 0;
    text-align: center;
}

nav {
    margin: 10px 0;
    text-align: center;
}

nav a {
    margin: 0 15px;
    text-decoration: none;
    color: #333;
}

footer {
    background: #333;
    color: #fff;
    text-align: center;
    padding: 10px 0;
    margin-top: 20px;
}
```





