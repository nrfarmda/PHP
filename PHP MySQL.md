# Koneksi Database
 
 ## program
 ```php
<?php

// Kredensial database

$koneksi = mysqli_connect('localhost', 'root', '', 'rental_mada');

  

// Memeriksa apakah koneksi berhasil

if ($koneksi) {

    echo "<br> koneksi aman <br>";

} else {

    die("Error, tidak bisa koneksi ke database");
}
```
 
 ## hasil
![](gambar1.png)

 ## analisis
 - Koneksi ke database: Kode menggunakan fungsi `mysqli_connect` untuk menghubungkan ke database `rental_fina` yang berada di localhost dengan username `root` dan password kosong. Jika koneksi berhasil, maka akan menampilkan pesan "koneksi aman".
- Eksekusi query: Kode menggunakan fungsi `mysqli_query` untuk menjalankan query SQL `SELECT * FROM mobil` yang digunakan untuk mengambil semua data dari tabel `mobil`.
- Mengambil hasil query: Kode menggunakan fungsi `mysqli_fetch_assoc` untuk mengambil hasil query dan menyimpannya dalam variabel `$result`. Fungsi ini mengembalikan array yang berisi hasil query dalam bentuk associative array.
- Menampilkan data: Kode menggunakan loop `foreach` untuk menampilkan data mobil beserta pemiliknya. Namun, ada kesalahan pada kode ini. Kode menggunakan variabel `$select` yang berisi hasil query, tetapi tidak dapat di-looping menggunakan `foreach` karena `$select` adalah resource, bukan array. Seharusnya menggunakan `$result` yang berisi hasil query dalam bentuk array.
# Tampilan Data
## program
```php
<!DOCTYPE html>

<html lang="en">

<head>

    <meta charset="UTF-8">

    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>index tabel</title>

</head>

<body>

    <h2>Data Siswa Berprestasi</h2>

    <a href="tambah.php">+Tambah Data Baru</a><br><br>

    <p>

        <a href="export.php">Export Excel</a>

    </p>

    <table border="5">

    <tr>

        <th>id_siswa</th>

        <th>Gambar</th>

        <th>nama</th>

        <th>email</th>

        <th>jenis_kelamin</th>

        <th>alamat</th>

        <th>Aksi</th>

    </tr>

  

    <?php

    include "koneksi.php";

    $i = 1;

    $query = mysqli_query($koneksi, "SELECT * FROM siswa");

    while ($data = mysqli_fetch_array($query)) {

    ?>

  

    <tr>

        <td><?php echo $i; ?></td>

        <td>

            <img src="img/<?= $data['gambar'] ?>" width="50">

        </td>

        <td><?php echo $data['nama']; ?></td>

        <td><?php echo $data['email']; ?></td>

        <td><?php echo $data['jenis_kelamin']; ?></td>

        <td><?php echo $data['alamat']; ?></td>

  

        <td>

            <a href="ubah.php?id=<?= $data['id_siswa']; ?>">Ubah</a> |

            <a href="hapus.php?id=<?= $data['id_siswa']; ?>">Hapus</a> |

        </td>

    </tr>

    <?php

    $i++;

    }

    ?>

    </table>

</body>

</html>
```
## hasil
![](gambar.png)
### analisis
- **Deklarasi DOCTYPE:** Baris ini menentukan jenis dokumen sebagai HTML.
- **Tag HTML:** Tag `<html>`menandai awal dokumen HTML.
- **Atribut lang:** Atribut `lang="en"`menentukan bahasa dokumen sebagai bahasa Inggris.
- **Bagian kepala:** Bagian `<head>`berisi informasi meta tentang dokumen.
    - **Charset:** Tag `<meta charset="UTF-8">`mendefinisikan pengkodean karakter sebagai UTF-8, memungkinkan untuk menampilkan berbagai karakter.
    - **Area pandang:** Tag `<meta name="viewport" content="width=device-width, initial-scale=1.0">`memastikan halaman merespons dengan baik pada ukuran layar yang berbeda.
    - **Judul:** Tag `<title>index tabel</title>`menentukan judul halaman web, yang ditampilkan pada tab browser.
- **Bagian isi:** Bagian `<body>`berisi konten halaman web yang terlihat.
    - **Judul:** Tag `<h2>Data Siswa Berprestasi</h3>`menampilkan judul "Data Siswa Berprestasi" (Bahasa Indonesia untuk "Data Siswa Berprestasi").
    - **Tautan:**
        - Ini `<a href="tambah.php">+Tambah Data Baru</a><br><br>`membuat tautan dengan teks "+Tambah Data Baru" (Bahasa Indonesia untuk "Tambahkan Data Baru") yang menunjuk ke "tambah.php " untuk menambahkan entri baru.
        - Ini `<a href="export.php">Export Excel</a>`membuat tautan dengan teks "Ekspor Excel" yang menunjuk ke "ekspor.php " untuk mengekspor data ke format Excel.
    - **Tabel:** Tag `<table border="5">`membuat tabel dengan lebar batas 5.
        - **Tajuk Tabel:** Bagian `<tr>`... `</tr>`mendefinisikan baris tajuk tabel.
            - Setiap `<th>`tag mendefinisikan sel header untuk kolom tertentu (id_siswa, Gambar, nama dll. ).
        - **Badan Tabel:** Skrip PHP mengisi badan tabel dengan data dari database.
### kesimpulan
Program PHP dan SQL di atas berfungsi untuk melakukan koneksi ke database, menjalankan query seleksi, dan menampilkan data dari tabel "daftar_mobil". Program ini akan menampilkan nama-nama pemilik mobil yang ada dalam tabel tersebut dengan format nomor plat dan nama pemilik. Namun, perlu diperhatikan bahwa bagian yang mengakses data menggunakan `$select` dalam perulangan `foreach` tidak tepat. Seharusnya, variabel `$select` diganti dengan `mysqli_fetch_assoc($select)` untuk mengambil setiap baris data secara berurutan. Dalam kode yang diberikan, perulangan `foreach` tidak akan berfungsi dengan benar. Jika ingin menampilkan semua baris data, perlu dilakukan perubahan pada kode tersebut.
# Tambahkan Data
### program
```php
<?php

//koneksi ke database

$koneksi = mysqli_connect('localhost', 'root', '', 'rental_mada');

  

if ($koneksi) {

    echo "<br> koneksi aman <br>";

} else {

    echo "error, tidak bisa koneksi ke database";

}

  
  

//jalankan query seleksi

$select = mysqli_query($koneksi, "SELECT * FROM daftar_mobil");

  

//menampilkan struktur array dari data tabel yang dijalankan di atas

// var_dump($result);

  

echo 'Berikut nama-nama pemilik mobil<br>';

$a = 1;

foreach($select as $key => $data){

    echo $a++ . ", " . $data['no_plat'] . " : " . $data['pemilik'] . '<br>';

}

//Tambahkan data baru ke tabel daftar_mobil

$no_plat_baru = "AB 1234 CD";

$pemilik_baru = "John Doe";

$insert = mysqli_query($koneksi, "INSERT INTO daftar_mobil (no_plat, pemilik) VALUES ('$no_plat_baru', '$pemilik_baru')");

if ($insert) {

    echo "Data baru berhasil ditambahkan ke tabel daftar_mobil";

} else {

    echo "Gagal menambahkan data baru ke tabel daftar_mobil";

}

  

// echo '<p>Halo ' . $result['pemilik'] . '!!</p><br>';

?>
```
### hasil
![](gambar4.png)
### analisis
**Koneksi ke Database:**
- Kode menggunakan fungsi `mysqli_connect()` untuk terhubung ke database MySQL dengan nama "rental_mada".
- Fungsi ini menerima 4 parameter:
    - `localhost`: Nama host server database.
    - `root`: Nama pengguna database (default untuk MySQL).
    - `''`: Kata sandi pengguna database (kosongkan jika tidak memiliki kata sandi).
    - `rental_mada`: Nama database yang ingin dihubungkan.
- Kode menggunakan blok `if` untuk mengecek apakah koneksi berhasil.
    - Jika berhasil, kode menampilkan pesan "koneksi aman".
    - Jika gagal, kode menampilkan pesan "error, tidak bisa koneksi ke database".

**Menjalankan Query Seleksi:**
- Kode menggunakan fungsi `mysqli_query()` untuk menjalankan query seleksi `SELECT * FROM daftar_mobil`.
    - Query ini memilih semua data dari tabel "daftar_mobil".
- Hasil query disimpan dalam variabel `$select`.

**Menampilkan Data Pemilik Mobil:**
- Kode menggunakan perulangan `foreach` untuk iterasi melalui hasil query.
    - Di dalam perulangan, kode:
        - Menampilkan nomor urut (`$a++`).
        - Menampilkan nomor plat mobil (`$data['no_plat']`).
        - Menampilkan nama pemilik mobil (`$data['pemilik']`).
- Kode menampilkan string "Berikut nama-nama pemilik mobil" sebelum perulangan.

**Menambahkan Data Baru ke Tabel:**
- Kode mendefinisikan dua variabel baru:
    - `$no_plat_baru`: Nilai nomor plat mobil baru ("AB 1234 CD").
    - `$pemilik_baru`: Nilai nama pemilik mobil baru ("John Doe").
- Kode menggunakan fungsi `mysqli_query()` untuk menjalankan query insert `INSERT INTO daftar_mobil (no_plat, pemilik) VALUES ('$no_plat_baru', '$pemilik_baru')`.
    - Query ini menambahkan data baru ke tabel "daftar_mobil" dengan nilai nomor plat dan nama pemilik yang ditentukan.
- Kode menggunakan blok `if` untuk mengecek apakah query insert berhasil.
    - Jika berhasil, kode menampilkan pesan "Data baru berhasil ditambahkan ke tabel daftar_mobil".
    - Jika gagal, kode menampilkan pesan "Gagal menambahkan data baru ke tabel daftar_mobil".
### kesimpulan
Program PHP dan SQL di atas berfungsi untuk melakukan koneksi ke database, menjalankan query seleksi, menampilkan data dari tabel "daftar_mobil", dan menambahkan data baru ke tabel tersebut. Program ini akan menampilkan nama-nama pemilik mobil yang ada dalam tabel, kemudian menambahkan data baru dengan nomor plat dan pemilik yang ditentukan. Harap diingat bahwa sebelum menjalankan program ini, pastikan koneksi ke database telah berhasil dan struktur tabel "daftar_mobil" telah sesuai. Juga, perhatikan bahwa program ini menggunakan data yang telah ditentukan sebelumnya untuk penambahan data baru. Anda dapat mengubah nilai variabel `$no_plat_baru` dan `$pemilik_baru` sesuai dengan data yang ingin ditambahkan.
# Ubah Data
## program
```php
<?php
  
//koneksi ke database
$koneksi = mysqli_connect('localhost', 'root', '', 'rental_rahmat');

if ($koneksi) {
    echo "<br> koneksi aman <br>";
} else {
    echo "error, tidak bisa koneksi ke database";
}

//jalankan query seleksi
$select = mysqli_query($koneksi, "SELECT * FROM daftar_mobil");
  
echo 'Berikut nama-nama pemilik mobil sebelum perubahan<br>';
  
$a = 1;
foreach($select as $key => $data){
    echo $a++ . ", " . $data['no_plat'] . " : " . $data['pemilik'] . '<br>';
}

//Ubah data dalam tabel daftar_mobil
$no_plat_lama = "AB 1234 CD";
$pemilik_baru = "Amir";

$update = mysqli_query($koneksi, "UPDATE daftar_mobil SET pemilik='$pemilik_baru' WHERE no_plat='$no_plat_lama'");

if ($update) {
    echo "Data berhasil diubah";
} else {
    echo "Gagal mengubah data";
}

//jalankan query seleksi setelah perubahan
$select_after_update = mysqli_query($koneksi, "SELECT * FROM daftar_mobil");

echo 'Berikut nama-nama pemilik mobil setelah perubahan<br>';

$a = 1;
foreach($select_after_update as $key => $data){
    echo $a++ . ", " . $data['no_plat'] . " : " . $data['pemilik'] . '<br>';
}

?>
```
### hasil
![](gambar5.png)
### analisis
**Koneksi ke Database:**
- Kode menggunakan fungsi `mysqli_connect()` untuk terhubung ke database MySQL dengan nama "rental_rahmat".
- Fungsi ini menerima 4 parameter:
    - `localhost`: Nama host server database.
    - `root`: Nama pengguna database (default untuk MySQL).
    - `''`: Kata sandi pengguna database (kosongkan jika tidak memiliki kata sandi).
    - `rental_rahmat`: Nama database yang ingin dihubungkan.
- Kode menggunakan blok `if` untuk mengecek apakah koneksi berhasil.
    - Jika berhasil, kode menampilkan pesan "koneksi aman".
    - Jika gagal, kode menampilkan pesan "error, tidak bisa koneksi ke database".

**Menampilkan Daftar Pemilik Mobil Sebelum Perubahan:**
- Kode menggunakan fungsi `mysqli_query()` untuk menjalankan query seleksi `SELECT * FROM daftar_mobil`.
    - Query ini memilih semua data dari tabel "daftar_mobil".
- Hasil query disimpan dalam variabel `$select`.
- Kode menggunakan perulangan `foreach` untuk iterasi melalui hasil query.
    - Di dalam perulangan, kode:
        - Menampilkan nomor urut (`$a++`).
        - Menampilkan nomor plat mobil (`$data['no_plat']`).
        - Menampilkan nama pemilik mobil (`$data['pemilik']`).
- Kode menampilkan string "Berikut nama-nama pemilik mobil sebelum perubahan" sebelum perulangan.

**Mengubah Data dalam Tabel:**
- Kode mendefinisikan dua variabel baru:
    - `$no_plat_lama`: Nilai nomor plat mobil lama ("AB 1234 CD").
    - `$pemilik_baru`: Nilai nama pemilik mobil baru ("Amir").
- Kode menggunakan fungsi `mysqli_query()` untuk menjalankan query update `UPDATE daftar_mobil SET pemilik='$pemilik_baru' WHERE no_plat='$no_plat_lama'`.
    - Query ini mengubah nama pemilik mobil dengan nomor plat "AB 1234 CD" menjadi "Amir".
- Kode menggunakan blok `if` untuk mengecek apakah query update berhasil.
    - Jika berhasil, kode menampilkan pesan "Data berhasil diubah".
    - Jika gagal, kode menampilkan pesan "Gagal mengubah data".

**Menampilkan Daftar Pemilik Mobil Setelah Perubahan:**
- Kode menggunakan fungsi `mysqli_query()` untuk menjalankan query seleksi `SELECT * FROM daftar_mobil` lagi.
    - Query ini memilih semua data dari tabel "daftar_mobil" setelah perubahan.
- Hasil query disimpan dalam variabel `$select_after_update`.
- Kode menggunakan perulangan `foreach` untuk iterasi melalui hasil query.
    - Di dalam perulangan, kode:
        - Menampilkan nomor urut (`$a++`).
        - Menampilkan nomor plat mobil (`$data['no_plat']`).
        - Menampilkan nama pemilik mobil (`$data['pemilik']`).
- Kode menampilkan string "Berikut nama-nama pemilik mobil setelah perubahan" sebelum perulangan.
### kesimpulan
- Menghubungkan ke database MySQL "rental_rahmat".
- Menampilkan daftar nama pemilik mobil dari tabel "daftar_mobil" sebelum perubahan.
- Mengubah nama pemilik mobil dengan nomor plat "AB 1234 CD" menjadi "Amir".
- Menampilkan daftar nama pemilik mobil dari tabel "daftar_mobil" setelah perubahan.
# Hapus Data
### program
```php
<?php

// Koneksi ke database

$koneksi = mysqli_connect('localhost', 'root', '', 'rental_mada');

  

if ($koneksi) {

    echo "<br> Koneksi aman <br>";

} else {

    echo "Error, tidak bisa koneksi ke database";

}

// Jalankan query seleksi

$select = mysqli_query($koneksi, "SELECT * FROM daftar_mobil");

echo 'Berikut nama-nama pemilik mobil sebelum penghapusan<br>';

  

$a = 1;

foreach ($select as $key => $data) {

    echo $a++ . ", " . $data['no_plat'] . " : " . $data['pemilik'] . '<br>';

}

  
  

// Hapus data dalam tabel daftar_mobil

$no_plat_hapus = "AB 1234 CD";

  

$delete = mysqli_query($koneksi, "DELETE FROM daftar_mobil WHERE no_plat='$no_plat_hapus'");

if ($delete) {

    echo "Data berhasil dihapus<br>";

} else {

    echo "Gagal menghapus data";

}

  

// Jalankan query seleksi setelah penghapusan

$select_after_delete = mysqli_query($koneksi, "SELECT * FROM daftar_mobil");

echo 'Berikut nama-nama pemilik mobil setelah penghapusan<br>';

$a = 1;

foreach ($select_after_delete as $key => $data) {

    echo $a++ . ", " . $data['no_plat'] . " : " . $data['pemilik'] . '<br>';

}

?>
```
### hasil
![](gambar6.png)
### analisis
**Koneksi ke Database:**
- Kode menggunakan fungsi `mysqli_connect()` untuk terhubung ke database MySQL dengan nama "rental_mada".
- Fungsi ini menerima 4 parameter:
    - `localhost`: Nama host server database.
    - `root`: Nama pengguna database (default untuk MySQL).
    - `''`: Kata sandi pengguna database (kosongkan jika tidak memiliki kata sandi).
    - `rental_mada`: Nama database yang ingin dihubungkan.
- Kode menggunakan blok `if` untuk mengecek apakah koneksi berhasil.
    - Jika berhasil, kode menampilkan pesan "Koneksi aman".
    - Jika gagal, kode menampilkan pesan "Error, tidak bisa koneksi ke database".

**Menampilkan Daftar Pemilik Mobil Sebelum Penghapusan:**
- Kode menggunakan fungsi `mysqli_query()` untuk menjalankan query seleksi `SELECT * FROM daftar_mobil`.
    - Query ini memilih semua data dari tabel "daftar_mobil".
- Hasil query disimpan dalam variabel `$select`.
- Kode menggunakan perulangan `foreach` untuk iterasi melalui hasil query.
    - Di dalam perulangan, kode:
        - Menampilkan nomor urut (`$a++`).
        - Menampilkan nomor plat mobil (`$data['no_plat']`).
        - Menampilkan nama pemilik mobil (`$data['pemilik']`).
- Kode menampilkan string "Berikut nama-nama pemilik mobil sebelum penghapusan" sebelum perulangan.

**Menghapus Data dalam Tabel:**
- Kode mendefinisikan variabel baru:
    - `$no_plat_hapus`: Nilai nomor plat mobil yang ingin dihapus ("AB 1234 CD").
- Kode menggunakan fungsi `mysqli_query()` untuk menjalankan query delete `DELETE FROM daftar_mobil WHERE no_plat='$no_plat_hapus'`.
    - Query ini menghapus data dari tabel "daftar_mobil" dengan nomor plat "AB 1234 CD".
- Kode menggunakan blok `if` untuk mengecek apakah query delete berhasil.
    - Jika berhasil, kode menampilkan pesan "Data berhasil dihapus".
    - Jika gagal, kode menampilkan pesan "Gagal menghapus data".

**Menampilkan Daftar Pemilik Mobil Setelah Penghapusan:**
- Kode menggunakan fungsi `mysqli_query()` untuk menjalankan query seleksi `SELECT * FROM daftar_mobil` lagi.
    - Query ini memilih semua data dari tabel "daftar_mobil" setelah penghapusan.
- Hasil query disimpan dalam variabel `$select_after_delete`.
- Kode menggunakan perulangan `foreach` untuk iterasi melalui hasil query.
    - Di dalam perulangan, kode:
        - Menampilkan nomor urut (`$a++`).
        - Menampilkan nomor plat mobil (`$data['no_plat']`).
        - Menampilkan nama pemilik mobil (`$data['pemilik']`).
- Kode menampilkan string "Berikut nama-nama pemilik mobil setelah penghapusan" sebelum perulangan.
### kesimpulan
- Menghubungkan ke database MySQL "rental_mada".
- Menampilkan daftar nama pemilik mobil dari tabel "daftar_mobil" sebelum penghapusan.
- Menghapus data dari tabel "daftar_mobil" dengan nomor plat "AB 1234 CD".
- Menampilkan daftar nama pemilik mobil dari tabel "daftar_mobil" setelah penghapusan.
# Session/Login
## session 
### program
```php
<?php

session_start();

// $username = "fatir";
// $alamat = "muh jufri 4";
  
// $_SESSION['username'] = $username;
// $_SESSION['alamat'] = $alamat;

if (isset($_POST['submit'])){
    $username = $_POST['username'];
    $password = $_POST['password'];

$koneksi = mysqli_connect('localhost', 'root', '', 'mada') or die('error koneksi');
    $result = mysqli_query($koneksi, "SELECT * FROM user WHERE username = '$username' AND password = '$password'");

    $data = mysqli_fetch_assoc($result);

    if(isset($data)) {
        $_SESSION['username'] = $data['username'];
        $_SESSION['nama'] = $data['nama'];
        $_SESSION['status'] = 'login';
        header('Location: user.php');
    } else {
        echo "username dan password salah";
    }
    var_dump($data);
}
?>

<!DOCTYPE HTML>
<html>
    <head>
       <title>login session</title>      
    </head>
    <body>
        <form method="post">
            <label >username</label>
            <input type="text" name="username">
            <br>
            <label >Password</label>
            <input type="password" name="password">
            <br>
            <button type="submit" name="submit">Login</button>
        </form>
    </body>
</html>
```

```php
<?php

session_start();

  

if ($_SESSION['status'] == 'login' && $_SESSION['username'] == 'admin') {

    header("Location: admin.php");

}

if ($_SESSION['status'] != 'login') {

    header('Location: login.php');

}

  

?>

<!DOCTYPE html>

<html lang="en">

  

<head>

    <title>Document</title>

</head>

  

<body>

    <h1>Halaman User</h1>

  

    <h1>Halo, <?= $_SESSION['nama'] ?></h1>

    <a href="logout.php">Logout</a>

  

</body>

  

</html>
```

```php
<?php

session_start();

if ($_SESSION['status'] == 'login' && $_SESSION['username'] != 'admin') {
    header("Location: user.php");
}

if ($_SESSION['status'] != 'login') {
    header('Location: login.php');
}
```

```php
<?php

session_start();

  

if ($_SESSION['status'] == 'login' && $_SESSION['username'] == 'admin') {

    header("Location: admin.php");

}

if ($_SESSION['status'] != 'login') {

    header('Location: login.php');

}

  

?>

<!DOCTYPE html>

<html lang="en">

  

<head>

    <title>Document</title>

</head>

  

<body>

    <h1>Halaman User</h1>

  

    <h1>Halo, <?= $_SESSION['nama'] ?></h1>

    <a href="logout.php">Logout</a>

  

</body>

  

</html>
```
### hasil
![](gambar8.png)

![](gambar7.png)
### analisis
- Kode dimulai dengan memeriksa apakah `submit`tombol di formulir telah diklik. Ini digunakan `isset($_POST['submit'])`untuk tujuan ini.
- Jika formulir dikirimkan, kode akan mengekstrak nilai nama pengguna dan kata sandi dari formulir menggunakan `$_POST['username']`dan `$_POST['password']`, masing-masing.
 - Ini membuat koneksi ke database MySQL yang diberi nama `mada`menggunakan `mysqli_connect`kredensial ( `localhost`, , (kata sandi kosong), dan ). `root` `''``mada`
 - Jika koneksi gagal, pesan kesalahan akan ditampilkan ( `error koneksi`).
- Ini membuat kueri SQL untuk memilih semua kolom ( `*`) dari `user`tabel tempat `username`dan `password`cocok dengan nilai yang diberikan. Kueri ini rentan terhadap serangan injeksi SQL (dijelaskan nanti).
- Kueri dijalankan menggunakan `mysqli_query`.
- Hasilnya diambil sebagai array asosiatif menggunakan `mysqli_fetch_assoc`.
- Ia memeriksa apakah `isset($data)`ada `true`. Hal ini menunjukkan jika catatan pengguna ditemukan dengan kredensial yang cocok.
- Jika ditemukan record ( `isset($data)`is `true`), berarti login berhasil.
- Kode (kemungkinan) memulai sesi PHP menggunakan `session_start()`jika belum dimulai. Sesi digunakan untuk menyimpan informasi spesifik pengguna di seluruh permintaan halaman.
- Ini menetapkan beberapa variabel sesi untuk menyimpan nama pengguna, nama (dengan asumsi `nama`ada dalam tabel), dan `login`indikator status.
- Header `Location`dikirim `header('Location: user.php')`untuk mengarahkan pengguna ke halaman bernama `user.php`, yang bisa berupa halaman dasbor atau profil.
- Jika login gagal ( `isset($data)`is `false`), maka akan muncul pesan error dalam bahasa Indonesia yang menunjukkan username dan password salah.
- Pernyataan tersebut `var_dump($data)`(mungkin untuk tujuan pengembangan) mencetak isi array `$data`, yang akan berisi informasi pengguna jika login berhasil. Ini dapat berguna untuk men-debug masalah login.
### kesimpulan
File `session.php` adalah program PHP yang melakukan proses login menggunakan session. Program ini memeriksa apakah data username dan password yang diberikan cocok dengan data yang ada di database. Jika cocok, session akan diset dengan variabel-variabel dari data tersebut dan pengguna akan diarahkan ke halaman "user.php". Jika tidak cocok, pesan kesalahan akan ditampilkan. Namun, perlu diperhatikan bahwa file ini belum mengimplementasikan fitur keamanan seperti sanitasi input dan penggunaan prepared statement untuk mencegah serangan SQL Injection.
# Upload & download
## upload
### program
```php
<!DOCTYPE html>

<html lang="en">

  

<head>

    <title>Document</title>

</head>

  

<body>

    <h2>Tambah Data</h2>

    <?php

    include "koneksi.php";

  

    function upload(): string

    {

  

    $nameImage = $_FILES['gambar']['name'];

    $directoryFile = $_FILES['gambar']['tmp_name'];

    $errorImage = intval($_FILES['gambar']['error']);

    $sizeFile = $_FILES['gambar']['size'];

  

    // cek apakah gambar ada

    if ($errorImage === 4) {

        echo "<script>alert('Anda Belum Upload Gambar')</script>";

        return false;

    }

  

    // mengambil ekstensi file

    $validType = ['svg', 'jpg', 'png', 'jpeg', 'webp'];

    $extensionFile = explode(".", $nameImage);

    $extensionValid = strtolower(end($extensionFile));

  

    // cek apakah yang diupload gambar atau bukan

    if (!in_array($extensionValid, $validType)) {

        echo "<script>alert('yang anda Upload bukan gambar')</script>";

        return false;

    }

  

    // cek size file

    if ($sizeFile > 3_000_000) {

        echo "<script>alert('Ukuran File Terlalu Besar!!(Maks 3MB)')</script>";

        return false;

    }

  

    // upload file

    $nameImage = uniqid() . "." . $extensionValid;

    move_uploaded_file($directoryFile, "img/{$nameImage}");

  

    // mengembalikan namafile yg sudah divalidasi

    return $nameImage;

}

  

    if (isset($_POST['simpan'])) {

        $nama = $_POST['nama'];

        $email = $_POST['email'];

        $jenis_kelamin = $_POST['jenis_kelamin'];

        $alamat = $_POST['alamat'];

  

        $gambar = upload();

        if (!$gambar) {

            return false;

        }

  

        // * true / false

        $query = mysqli_query($koneksi, "INSERT into siswa(nama,email,

        jenis_kelamin,alamat,gambar)

        values ('$nama','$email','$jenis_kelamin','$alamat','$gambar')");

  

        if ($query == true) {

            echo "<script>

            alert('Tambah data Berhasil')

            window.location.href='table.php'

            </script>";

        } else {

            echo '<script>alert("Tambah data gagal")</script>';

        }

    }

  
  

    ?>

    <form method="post" enctype="multipart/form-data">

        <table>

            <tr>

                <td>Nama</td>

                <td><input type="text" name="nama"></td>

            </tr>

            <tr>

                <td>Email</td>

                <td><input type="text" name="email"></td>

            </tr>

            <tr>

                <td>Jenis Kelamin</td>

                <td>>

                    <select name="jenis_kelamin">

                        <option>Laki-laki</option>

                        <option>Perempuan</option>

                    </select>

                </td>

            </tr>

  

            <tr>

                <td>Alamat</td>

                <td><input type="text" name="alamat"></td>

            </tr>

  

            <tr>

                <td>Gambar</td>

                <td><input type="file" name="gambar"></td>

            </tr>

  

            <tr>

                <td></td>

                <td>

                    <button name="simpan" type="submit">Simpan</button>

                    <button type="reset">Reset</button>

                    <a href="table.php">Kembali</a>

                </td>

            </tr>

        </table>

    </form>

</body>

</html>
```
### hasil
![](gambar9.png)

![](gambar10.png)
### analisis
1. Pada bagian HTML, terdapat elemen `<form>` dengan atribut `enctype="multipart/form-data"`. Ini diperlukan agar formulir dapat mengirimkan data berupa file, dalam hal ini gambar.
2. Setelah itu, terdapat elemen input dengan `type="file"` dan `name="gambar"`. Bagian ini memungkinkan pengguna untuk memilih dan mengunggah file gambar dari perangkat mereka.
3. Pada bagian PHP, ada sebuah fungsi bernama `upload()` yang digunakan untuk mengelola proses upload gambar. Fungsi ini mengambil beberapa informasi dari `$_FILES`, seperti nama file (`$nameImage`), direktori sementara file (`$directoryFile`), kode error (`$errorImage`), dan ukuran file (`$sizeFile`).
4. Pertama, dilakukan pemeriksaan apakah gambar telah diunggah atau tidak. Jika `$errorImage` memiliki nilai 4, itu berarti tidak ada gambar yang diunggah. Dalam hal ini, pesan peringatan akan ditampilkan dan fungsi akan mengembalikan `false`.
5. Selanjutnya, ekstensi file ditentukan dengan memecah nama file menggunakan `explode()` dan mengambil bagian terakhir (`$extensionValid`). Kemudian, dilakukan pemeriksaan apakah ekstensi file tersebut ada di dalam array `$validType` yang berisi ekstensi yang diizinkan. Jika ekstensi tidak valid, pesan peringatan akan ditampilkan dan fungsi akan mengembalikan `false`.
6. Dilakukan pemeriksaan ukuran file dengan membandingkannya dengan batas maksimum yang ditetapkan (3MB dalam contoh ini). Jika ukuran file melebihi batas maksimum, pesan peringatan akan ditampilkan dan fungsi akan mengembalikan `false`.
7. Jika semua pemeriksaan berhasil, gambar akan diunggah ke direktori "img" dengan menggunakan fungsi `move_uploaded_file()`. Nama file gambar juga diubah menjadi unik dengan menggunakan fungsi `uniqid()`, ditambahkan dengan ekstensi yang valid.
8. Setelah file berhasil diunggah, nama file gambar yang telah divalidasi akan dikembalikan oleh fungsi.
9. Selanjutnya, pada bagian PHP yang mengurus penanganan formulir, dipanggil fungsi `upload()` untuk mengunggah gambar. Jika fungsi mengembalikan `false` (artinya terdapat kesalahan dalam upload gambar), maka program akan menghentikan eksekusi lebih lanjut dengan menggunakan `return`.
10. Jika upload gambar berhasil, data yang diisi pengguna seperti nama, email, jenis kelamin, alamat, dan nama file gambar akan dikumpulkan dan disimpan dalam variabel.
11. Dilakukan query SQL menggunakan `mysqli_query()` untuk memasukkan data siswa ke dalam tabel "siswa", termasuk nama file gambar yang sudah divalidasi.
12. Terakhir, terdapat penanganan pesan sukses atau gagal setelah query dieksekusi. Jika query berhasil, pesan sukses akan ditampilkan dan pengguna akan diarahkan kembali ke halaman "table.php". Jika query gagal, pesan gagal akan ditampilkan.
### kesimpulan
Program PHP tersebut memungkinkan pengguna untuk mengunggah gambar sebagai bagian dari formulir data siswa. Program ini melakukan beberapa pemeriksaan keamanan, seperti memeriksa apakah gambar diunggah, memeriksa ekstensi file, dan memeriksa ukuran file sebelum mengizinkan unggahan. Jika semua pemeriksaan berhasil, gambar akan diunggah ke direktori "img" dengan nama file yang unik. Setelah itu, data siswa beserta nama file gambar akan disimpan dalam database.
## download
### program
```php
<?php

include "koneksi.php";

  

$query = mysqli_query($koneksi, 'SELECT * FROM siswa');

  

$data = [];

$data[] = ["ID", "Nama", "Email", "Jenis Kelamin", "Alamat"];

while ($row = mysqli_fetch_assoc($query)) {

    $data[] = [

        $row['id_siswa'],

        $row['nama'],

        $row['email'],

        $row['jenis_kelamin'],

        $row['alamat']

    ];

}

  

$namafile = "excel_data.xls";

header("Content-Type: application/vnd.ms-excel");

header("Content-Disposition: attachment;filename=\"$namafile\"");

header("Cache-Control: max-age=0");

  

$output = fopen("php://output", "w");

  

foreach ($data as $row) {

    fputcsv($output, $row, "\t");

}

  

fclose($output);

exit;
```
### hasil
![](gambar11.png)
### analisis
**Menyertakan File Koneksi:**
- Baris pertama `include "koneksi.php";` menyertakan file eksternal bernama "koneksi.php".
- Diduga file tersebut berisi konfigurasi untuk koneksi ke database, seperti informasi host, username, password, dan nama database.
**Menjalankan Query Seleksi:**
- Baris `$query = mysqli_query($koneksi, 'SELECT * FROM siswa');` menjalankan query untuk mengambil semua data dari tabel "siswa".
- Hasil query disimpan dalam variabel `$query`.
**Menyiapkan Struktur Data untuk Excel:**
- Baris `$data = [];` menginisialisasi variabel `$data` sebagai array kosong.
- Baris `$data[] = ["ID", "Nama", "Email", "Jenis Kelamin", "Alamat"];` menambahkan array baru ke dalam `$data` yang berisi header untuk kolom-kolom Excel.
**Memproses Data dari Query:**
- Perulangan `while ($row = mysqli_fetch_assoc($query)) { ... }` iterasi melalui hasil query (`$query`).
- Fungsi `mysqli_fetch_assoc()` mengambil data dari hasil query baris demi baris sebagai array associative.
 - Di dalam perulangan, array baru ditambahkan ke dalam `$data` yang berisi nilai-nilai untuk setiap kolom dari data siswa yang sedang diproses.
- Nilai-nilai tersebut diambil dari key array hasil query (`$row['id_siswa']`, `$row['nama']`, dst.).
*Menyiapkan File dan Header:**
- Baris `$namafile = "excel_data.xls";` mendefinisikan nama file Excel yang akan dibuat ("excel_data.xls").
- Baris selanjutnya mengatur header HTTP untuk:
    - Menentukan tipe konten sebagai aplikasi Excel (`application/vnd.ms-excel`).
    - Menentukan header Content-Disposition untuk mengatur download file dengan nama yang ditentukan (`excel_data.xls`).
    - Menonaktifkan caching.
**Menulis Data ke File Excel:**
- Baris `$output = fopen("php://output", "w");` membuka stream output ke file yang akan dibuat ("php://output") dengan mode penulisan ("w").
- Perulangan `foreach ($data as $row) { ... }` iterasi melalui array `$data` yang berisi struktur data untuk Excel.
    - Fungsi `fputcsv($output, $row, "\t");` digunakan untuk menulis baris data ke file Excel.
        - Parameter pertama (`$output`) adalah stream output yang sudah dibuka.
        - Parameter kedua (`$row`) adalah array yang berisi data untuk setiap kolom.
        - Parameter ketiga (`"\t"`) adalah delimiter (pemisah) antar kolom, dalam hal ini menggunakan tab ("\t").
**Penutup:**
- Baris `fclose($output);` menutup stream output yang sudah dibuka.
- Baris `exit;` menghentikan skrip PHP setelah proses selesai.
### kesimpulan
Program PHP tersebut mengambil data dari tabel "siswa" dalam database MySQL menggunakan query SQL. Data tersebut kemudian diubah menjadi file Excel (.xls) yang diunduh oleh pengguna. Program ini menggunakan fungsi header untuk mengatur jenis konten dan nama file yang akan diunduh, serta menggunakan fungsi fopen, fputcsv, dan fclose untuk menghasilkan file Excel dengan data yang sesuai.