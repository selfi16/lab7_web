# lab7_web
Nama : Selfi Aulia Rahmanisa Yunus

Nim  : 312310243
## Persiapan Lingkungan Praktikum:
- Install XAMPP sebagai server lokal untuk menjalankan PHP dan Apache. Unduh dari situs XAMPP dan ekstrak di lokasi yang Anda pilih (misalnya, d:\xampp).
- Jalankan XAMPP melalui XAMPP Control Panel, pastikan Apache dan MySQL aktif.
- Uji server dengan membuka `http://localhost` di browser. Jika halaman XAMPP tampil, server telah berfungsi dengan baik.

## Buat Direktori Project:
- Buat folder baru bernama `lab7_php_dasar` di dalam folder `htdocs` (misalnya, `d:\xampp\htdocs\lab7_php_dasar`).
- Akses folder tersebut di browser dengan URL: `http://localhost/lab7_php_dasar/`.

## Kode PHP Dasar:
- Buat file `php_dasar`.php di dalam folder `lab7_php_dasar`.
Salin kode berikut untuk menampilkan teks "Hello World":
php
``` php
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>PHP Dasar</title>
</head>
<body>
    <h1>Belajar PHP Dasar</h1>
    <?php
        echo "Hello World";
    ?>
</body>
</html>
``` 
- Akses hasilnya di http://localhost/lab7_php_dasar/php_dasar.php.

![image](https://github.com/user-attachments/assets/3ed53e48-9e11-4ce2-a4e8-f1d1cf4e18af)



## Variable PHP
Menambahkan variable pada program.
``` php
<h1>Menggunakan Variable</h1>
    
    <?php
    $nim = "312310243";
    $nama = "Selfi Aulia Rahmanisa Yunus";
    echo "NIM : " . $nim . "<br>";
    echo "Nama : $nama";
    ?>
```

![image](https://github.com/user-attachments/assets/186f0b85-8f6e-4f65-b5dd-2331e6e20533)




## Predefine Variable $_GET
```php
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>PHP Dasar</title>
</head>
<body>
    <h2>Predefine Variable</h2>
    <?php
        if (isset($_POST['nama'])) {
            echo 'Selamat Datang ' . $_POST['nama'];
        }
    ?>
</body>
</html>
```

![image](https://github.com/user-attachments/assets/8d78d3ef-4a69-42e8-b457-f1d6d9851da8)



## Membuat Form Input
``` php
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
        if (isset($_POST['nama'])) {
            echo 'Selamat Datang ' . $_POST['nama'];
        }
    ?>
</body>
</html>
```

![image](https://github.com/user-attachments/assets/3236dbc6-2dfa-4a33-b39d-0abb5a368de7)



## Operator
```php
<?php
$gaji = 1000000;
$pajak = 0.1;
$thp = $gaji - ($gaji*$pajak);
echo "Gaji sebelum pajak = Rp. $gaji <br>";
echo "Gaji yang dibawa pulang = Rp. $thp";
?>
```

## Kondisi IF
```php
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
```

## Kondisi Switch
```php
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
?>
```

## Perulangan for
```php
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
```

## Perulangan while
```php
<?php
echo "Perulangan 1 sampai 10 <br />";
$i=1;
while ($i<=10) {
echo "Perulangan ke: " . $i . '<br />';
$i++;
}
?>
```

## Perulangan dowhile
```php
<?php
echo "Perulangan 1 sampai 10 <br />";
$i=1;
do {
echo "Perulangan ke: " . $i . '<br />';
$i++;
} while ($i<=10);
?>
```

# Membuat program sederhana
Membuat program PHP sederhana dengan menggunakan form input yang menampilkan
nama, tanggal lahir dan pekerjaan. Kemudian tampilkan outputnya dengan menghitung
umur berdasarkan inputan tanggal lahir. Dan pilihan pekerjaan dengan gaji yang
berbeda-beda sesuai pilihan pekerjaan.

```php
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hitung Umur dan Gaji</title>
    <style>
        body { font-family: Arial, sans-serif; margin: 20px; }
        form { margin-bottom: 20px; }
        label { display: inline-block; width: 100px; margin-top: 10px; }
        input[type="text"], input[type="date"], select { width: 200px; padding: 5px; }
        input[type="submit"] { margin-top: 10px; padding: 5px 15px; }
    </style>
</head>
<body>
    <h2>Form Input Data</h2>
    <form method="post">
        <label>Nama:</label>
        <input type="text" name="nama" required><br>
        
        <label>Tanggal Lahir:</label>
        <input type="date" name="tanggal_lahir" required><br>
        
        <label>Pekerjaan:</label>
        <select name="pekerjaan" required>
            <option value="Programmer">Programmer</option>
            <option value="Desainer">Desainer</option>
            <option value="Manager">Manager</option>
        </select><br><br>
        
        <input type="submit" value="Kirim">
    </form>
    <hr>

    <?php
    if ($_SERVER["REQUEST_METHOD"] == "POST") {
        // Ambil data dari form
        $nama = htmlspecialchars($_POST["nama"]);
        $tanggal_lahir = $_POST["tanggal_lahir"];
        $pekerjaan = $_POST["pekerjaan"];

        // Menghitung umur berdasarkan tanggal lahir
        $tanggal_lahir_obj = new DateTime($tanggal_lahir);
        $sekarang = new DateTime();
        $umur = $sekarang->diff($tanggal_lahir_obj)->y;

        // Menentukan gaji berdasarkan pekerjaan
        $gaji = 0;
        switch ($pekerjaan) {
            case "Programmer":
                $gaji = 10000000;
                break;
            case "Desainer":
                $gaji = 8000000;
                break;
            case "Manager":
                $gaji = 15000000;
                break;
            default:
                $gaji = 0;
        }

        // Tampilkan hasil
        echo "<h3>Hasil Input</h3>";
        echo "Nama: $nama <br>";
        echo "Tanggal Lahir: " . $tanggal_lahir_obj->format('d-m-Y') . "<br>";
        echo "Umur: $umur tahun <br>";
        echo "Pekerjaan: $pekerjaan <br>";
        echo "Gaji: Rp. " . number_format($gaji, 0, ',', '.') . "<br>";
    }
    ?>
</body>
</html>
```

## Penjelasan Kode:
1. HTML Form:
- Form ini menggunakan metode `POST` untuk mengirim data.
- Input meliputi nama, tanggal lahir, dan pekerjaan, serta tombol kirim.
  
2. Pengolahan Data PHP:
- Kode PHP di dalam `if ($_SERVER["REQUEST_METHOD"] == "POST")` hanya akan dijalankan jika form disubmit.
- Validasi dan Pengamanan: `htmlspecialchars()` digunakan untuk menghindari risiko XSS dengan membersihkan input `nama`.
- Menghitung Umur: Menggunakan `DateTime` untuk menghitung umur berdasarkan tanggal lahir yang diinput.
- Menentukan Gaji: Menggunakan `switch` untuk memilih gaji berdasarkan pekerjaan.

3. Menampilkan Hasil:
- Nama, tanggal lahir (diformat menjadi `dd-mm-yyyy`), umur, pekerjaan, dan gaji akan ditampilkan setelah form dikirim.

## Cara Mengakses Program:
Simpan kode di atas sebagai `form_umur.php` di dalam folder lab7_php_dasar.
Akses melalui URL `http://localhost/lab7_php_dasar/form_umur.php`.
Isi form dan tekan Kirim untuk melihat hasil output.

![image](https://github.com/user-attachments/assets/88f45dac-7779-4917-bfd7-d31b8b08bd14)
