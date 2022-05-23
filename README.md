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








Berikut kode yang digunakan:

```php
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>PHP Dasar</title>
</head>
<body>
    <!-- Variabel $_GET -->
    <h2>Predefine Variabel</h2>
<?php
    echo 'Selamat Datang'. $_GET['nama'];
?>
</body>
</html>
```

## PEMBUATAN FORM INPUT DENGAN VARIABLE $_POST

![menambahkan_gambar](img/FORM%20INPUT.png)

Untuk mendapat tampilan diatas, buatlah file baru dengan nama file disini saya namakan Lat2.php dalam directory Lab7_php_dasar. Kemudian tambahkan kode berikut:

```php
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>PHP Dasar</title>
</head>
<body>
<h2>Form Input</h2>
<form method="post">
    <label>Nama: </label>
    <input type="text" name="nama">
    <input type="submit" value="Kirim">
</form>
<?php
    echo 'Selamat Datang ' . $_POST['nama'];
?>
</body>
</html>
```

## OPERATOR

![menambahkan_gambar](img/OPERATOR.png)

Untuk mendapat tampilan diatas, buatlah file baru dengan nama file disini saya namakan Lat3.php dalam directory Lab7_php_dasar. Kemudian tambahkan kode berikut:

```php
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>PHP Dasar</title>
</head>
<body>
<?php
    $gaji = 1000000;
    $pajak = 0.1;
    $thp = $gaji - ($gaji*$pajak);
        echo "Gaji sebelum pajak = Rp. $gaji <br>";
        echo "Gaji yang dibawa pulang = Rp. $thp";
?>
</body>
</html>
```

## KONDISI IF

![menambahkan_gambar](img/KONDISI%20IF.png)

Untuk mendapat tampilan pengkondisian IF ELSE seperti diatas, buatlah file baru dengan nama file disini saya namakan Lat4.php dalam directory Lab7_php_dasar. Kemudian tambahkan kode berikut:

```php
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>PHP Dasar</title>
</head>
<body>
    <h2>Kondisi IF</h2>
<?php
    $nama_hari = date("l");
        if ($nama_hari == "Sunday") {
            echo "Minggu";
        } elseif ($nama_hari == "Monday") {
            echo "Senin";
        } else {
            echo "Selasa";
        }
?>
</body>
</html>
```

## KONDISI SWITCH

![menambahkan_gambar](img/KONDISI%20SWITCH.png)

Untuk mendapat tampilan pengkondisian SWITCH CASE dengan break seperti diatas, buatlah file baru dengan nama file disini saya namakan Lat5.php dalam directory Lab7_php_dasar. Kemudian tambahkan kode berikut:

```php
<h2>Kondisi Switch</h2>
<?php
    $nama_hari = date("l");
    switch ($nama_hari) {
        case "Sunday":
            echo "Minggu";
            break;
        case "Monday":
            echo "Senin";
            break;
        case "Tuesday":
            echo "Selasa";
            break;
        default:
            echo "Sabtu";
    }
    echo"/$nama_hari";
?>
```

## PERULANGAN FOR

![menambahkan_gambar](img/PERULANGAN%20FOR.png)

Untuk mendapat tampilan seperti diatas, buatlah file baru dengan nama file disini saya namakan Lat6.php dalam directory Lab7_php_dasar. Kemudian tambahkan kode berikut:

```php
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>PHP Dasar</title>
</head>
<body>
    <h2>Perulangan For</h2>
<?php
        echo "Perulangan 1 sampai 10 <br />";
    for ($i=1; $i<=10; $i++) {
        echo "Perulangan ke: " . $i . '<br />';
    }
        echo "Perulangan Menurun dari 10 ke 1 <br />";
    for ($i=10; $i>=1; $i--) {
        echo "Perulangan ke: " . $i . '<br />';
    }
?>
</body>
</html>
```

## PERULANGAN WHILE

![menambahkan_gambar](img/PERULANGAN%20WHILE.png)

Untuk mendapat tampilan seperti diatas, buatlah file baru dengan nama file disini saya namakan Lat6.php dalam directory Lab7_php_dasar. Kemudian tambahkan kode berikut:

```php
<h2>Perulangan While</h2>
<?php
        echo "Perulangan 1 sampai 10 <br />";
        $i=1;
    while ($i<=10) {
        echo "Perulangan ke: " . $i . '<br />';
        $i++;
    }
?>
```

## PERULANGAN DOWHILE

![menambahkan_gambar](img/PERULANGAN%20DOWHILE.png)

Untuk mendapat tampilan seperti diatas, buatlah file baru dengan nama file disini saya namakan Lat6.php dalam directory Lab7_php_dasar. Kemudian tambahkan kode berikut:

```php
<h2>Perulangan Dowhile</h2>
<?php
        echo "Perulangan 1 sampai 10 <br />";
        $i=1;
    do {
        echo "Perulangan ke: " . $i . '<br />';
        $i++;
        } while ($i<=10);
?>
```

# PERTANYAAN DAN TUGAS

Buatlah program PHP sederhana dengan menggunakan form input yang menampilkan nama , tanggal lahir dan pekerjaan . Kemudian tampilkan outputnya dengan menghitung umur berdasarkan inputan tanggal lahir . Dan pilihan pekerjaan dengan gaji yang berbeda-beda sesuai pilihan pekerjaan.

![menambahkan_gambar](img/TUGAS.png)

Note: Untuk kolom Tanggal Lahir gunakan format : 0000/00/00

```php
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tugas</title>
</head>
<body>
   <h2>TUGAS</h2>
    <form class="form" method="post" >
            <label>Nama: </label>
            <br>
            <input type="text" name="nama">
            <br>
            <label>Tanggal Lahir: </label>
            <br>
            <input type="text" name="tgl_lahir">
            <br>
            <label>Pekerjaan: </label>
            <br>
            <select name='pekerjaan'>
                <option value="-">>---Pilih Pekerjaan---<</option>
                <option value='Graphic Designer'>Graphic Designer</option>
                <option value='Staff Admin'>Staff Admin</option>
                <option value='HRD'>HRD</option>
                <option value='Maintenance'>Maintenance</option>
                <option value="QC">QC</option>
            </select>
            <br>
            <br>
            <button type="submit">Kirim</button>
    </form>
    <h2>HASIL</h2>

    <?php
        # Memanggil Nama
        echo 'Nama: ' . $_POST['nama'];

        # Merubah Tanggal Lahir menjadi Umur (Tahun)
        $tgl_lahir = @$_POST['tgl_lahir'];

        $lahir = new DateTime($tgl_lahir);
        $hari_ini = new DateTime();

        $diff = $hari_ini->diff($lahir);

        # Memanggil fungsi umur yg sudah dibuat diatas
        echo "<br> Umur: ". $diff->y ." Tahun";

        # Memanggil pekerjaan
        echo "<br> Pekerjaan: ". $_POST['pekerjaan'];

        # Kondisi if pekerjaan untuk menentukan gaji
        $pekerjaan = @$_POST['pekerjaan'];

        if($pekerjaan == "Graphic Designer"){
            echo '<br> Gaji: Rp. 15.000.000,-';
        }elseif($pekerjaan == "Staff Admin"){
            echo '<br> Gaji: Rp. 7.500.000,-';
        }elseif($pekerjaan == "HRD"){
            echo '<br> Gaji: Rp. 10.000.000,-';
        }elseif($pekerjaan == "Maintenance"){
            echo '<br> Gaji: Rp. 9.000.000,-';
        }elseif ($pekerjaan == "QC"){
            echo '<br> Gaji: Rp. 7.000.000,-';
        }

    ?>
  </body>
</html>
```

# <P align="center"> THANK'S FOR YOUR ATTENTION!! SEE YOU!!
