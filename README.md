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





