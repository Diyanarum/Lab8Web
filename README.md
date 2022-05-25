# PEMOGRAMAAN WEB

Diyan Arum Maheswari (312010133)

Teknik Informatika - UNIVERSITAS PELITA BANGSA
______________________________________________

## MEMBUAT APLIKASI CRUD SEDERHANA

Untuk dapat membuat aplikasi CRUD ini, ada beberapa hal yang harus disiapkan. Pertama, karena disini menggunaka MySQL sebagai database servernya pastikanlah MySQL kalian sudah dapat dijalankan melalui Xampp seperti gambar dibawah.

![menambahkan_gambar](img/XAMPP.png)

Jika MySQL dan Webserver Apachenya sudah running, selanjutnya bukalah web browser PHPMyAdmin dengan URL: http://localhost:8080/phpmyadmin/

## PEMBUATAN DATABASE

Kalian bisa langsung saja membuat database pada PHPMyAdmin dengan mengklik tombol MySQL yang ada diatas kemudian masukan kode dibawah kemudian klik kirim.

```mysql
CREATE DATABASE Latihan1;
```

![menambahkan_gambar](img/MEMBUAT%20DATABASE.png)


## PEMBUATAN TABEL 

![menambahkan_gambar](img/MEMBUAT%20TABEL.png)

Setelah database berhasil dibuat. Selanjutnya proses pembuatan tabel pada database tersebut. Pembuatannya sama dengan sebelumnya, kalian hanya perlu menekan tombol MySQL pada Database sebelumnya kemudian masukan kode berikut:

```mysql
CREATE TABLE data_barang (
        id_barang int(10) auto_increment Primary Key,
        kategori varchar(30),
        nama varchar(30),
        gambar varchar(100),
        harga_beli decimal(10,0),
        harga_jual decimal(10,0),
        stok int(4)
);
```

## PENAMBAHAN DATA

![menambahkan_gambar](img/NAMBAH%20DATA%20TABEL.png)

Untuk dapat menambahkan data pada tabel yang sudah dibuat sebelumnya, kalian hanya perlu memasukan kode berikut pada bagian MySQLnya:

```mysql
INSERT INTO data_barang (kategori, nama, gambar, harga_beli, harga_jual, stok)
VALUES ('Elektronik', 'HP Samsung Android', 'hp_samsung.jpg', 2000000, 2400000, 5),
('Elektronik', 'HP Xiaomi Android', 'hp_xiaomi.jpg', 1000000, 1400000, 5),
('Elektronik', 'HP OPPO Android', 'hp_oppo.jpg', 1800000, 2300000, 5);
```

## PEMBUATAN PROGRAM CRUD

Pertama, buatlah sebuah folder baru dengan nama Lab8_php_database pada root directory web server (C:\xampp\htdocs\Lab8Web)

![menambahkan_gambar](img/CEK%20WEB.png)

Kemudian untuk dapat mengaksesnya pada web server, gunakanlah URL : http://localhost:8080/Lab8Web/Lab8_php_database/


## MEMBUAT FILE KONEKSI DATABASE

Buatlah file baru dalam Directory Lab_php_dasar dengan nama file koneksi.php kemuadian masukan kode berikut:

```php
<?php
$host = "localhost:3307";
$user = "root";
$pass = "";
$db = "latihan1";

$conn = mysqli_connect($host, $user, $pass, $db);
if ($conn == false)
{
    echo "Koneksi ke server gagal.";
    die();
} else echo "Koneksi berhasil";
?>
```

 dan untuk mengaksesnya dapat menggunakan URL : http://localhost:8080/Lab8Web/Lab8_php_database/koneksi.php jika koneksi berhasil maka anda akan mendapatkan hasil seperti gambar dibawah ini.

![menambahkan_gambar](img/CEK%20KONEKSI%20.png)










# <P align="center"> THANK'S FOR YOUR ATTENTION!! SEE YOU!!
