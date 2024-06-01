# Apa itu Dinamis?
Web dinamis adalah jenis situs web yang mampu menghasilkan halaman web secara dinamis berdasarkan permintaan pengguna. Artinya, kontennya bisa berubah sesuai dengan input atau keadaan yang diberikan oleh pengguna. Situs web dinamis biasanya menggunakan bahasa pemrograman dan teknologi tertentu untuk mengelola dan menghasilkan konten yang dinamis.
# Apa itu PHP?
PHP (Hypertext Preprocessor) adalah salah satu bahasa pemrograman yang sering digunakan untuk mengembangkan situs web dinamis. PHP adalah bahasa pemrograman sisi server, yang berarti kode PHP dieksekusi di sisi server, bukan di sisi klien (browser pengguna). Dalam konteks situs web dinamis, PHP digunakan untuk menghubungkan antara server web dan [[database]], mengolah data, dan menghasilkan konten dinamis.
# Program pertama PHP
## Cara 
1. Buka XAMPP, kemudian klik tombol start pada 'apache'
2. Open file manager
3. Open di Drive D
4. Kemudian Open folder XAMPP
5. Lalu open folder htdocs
6. Buat folder baru di dalam htdocs 
7. Lalu open folder yang sudah Anda buat
8. Open VSCode
9. Open folder yang sudah Anda buat di VSCode
10. Buat file baru di VSCode dengan ekstensi .php di folder yang sudah Anda buka
# PHP Dasar
## Echo
### Kutip satu
kutip satu hanya bisa membaca teks atau STRING, variabel dan string
dipisahkan dengan tanda titik
### Kutip dua
kutip dua bisa membaca nilai dari variabel
### Penjelasan
1. Penggunaan Dasar:
   - `echo` adalah perintah dasar dalam PHP yang digunakan untuk menampilkan teks atau nilai pada halaman web.
   - Anda dapat menggunakan `echo` untuk menampilkan teks statis atau untuk menampilkan nilai dari variabel atau ekspresi.
   - `echo` dapat menerima satu atau lebih argumen yang dipisahkan oleh tanda titik (.) untuk menggabungkan teks dan variabel

2. Menampilkan Teks:
   - Anda dapat menggunakan `echo` untuk langsung menampilkan teks statis dalam tanda kutip ganda ("") atau tanda kutip tunggal ('').
   - Contoh: `echo "Halo, dunia!";`

3. Menampilkan Nilai Variabel:
   - Anda dapat menggunakan `echo` untuk menampilkan nilai dari variabel dalam teks yang ditampilkan.
   - Gunakan operator konkatenasi (tanda titik) untuk menggabungkan teks dan variabel.
   - Contoh:
     ```php
     $nama = "John Doe";
     echo "Halo, nama saya " . $nama . ".";
     ```

4. Menampilkan HTML:
   - Selain teks, Anda juga dapat menggunakan `echo` untuk menampilkan kode HTML di dalam skrip PHP.
   - Uji coba berikut menunjukkan penggunaan `echo` untuk menampilkan elemen HTML:

     ```php
     echo "<h1>Selamat Datang!</h1>";
     echo "<p>Ini adalah halaman web PHP.</p>";
     ```
     
5. Penggunaan Kutipan:
   - Anda dapat menggunakan tanda kutip ganda ("") atau tanda kutip tunggal ('') untuk mengelilingi teks dalam `echo`.
   - Misalnya, `echo "Halo, nama saya 'John'.";`

6. Menggunakan Pemisah:
   - Saat menggunakan `echo` dengan beberapa argumen, Anda dapat menggunakan koma (,) sebagai pemisah antara argumen.
   - Contoh: `echo "Halo,", " nama saya ", $nama, ".";`

Materi `echo` pada PHP memungkinkan Anda untuk menampilkan teks, nilai variabel, dan bahkan kode HTML di dalam skrip PHP. Hal ini berguna dalam menghasilkan tampilan dinamis pada halaman web yang sedang Anda bangun.
## Komentar
### Single line
Komentar Satu Baris:
   - Komentar satu baris dimulai dengan tanda `//` atau `#`.
   - Semua teks setelah tanda tersebut hingga akhir baris diabaikan oleh interpreter PHP.
   - Contoh:
```php

//ini komentar 1 baris menggunakan dua slice

```
### Multiple line
Komentar multibaris dimulai dengan `/*` dan diakhiri dengan `*/`.
   - Semua teks di antara tanda tersebut diabaikan oleh interpreter PHP.
   - Komentar multibaris dapat mencakup beberapa baris kode.
   - Contoh:
```php

/*
ini
komentar
multibaris
menggunakan satu slice dan bintang
*/
```

Tujuan Penggunaan Komentar:
   - Memberikan penjelasan tentang tujuan dan fungsionalitas kode.
   - Membantu dalam pemeliharaan dan pemahaman kode untuk pengembang dan anggota tim lainnya.
   - Menyembunyikan atau menonaktifkan sebagian kode untuk uji coba atau sementara.
   - Meninggalkan catatan atau pesan kepada diri sendiri atau pengembang lain tentang kode tertentu.
Penggunaan komentar yang baik sangat penting dalam pemrograman untuk menjaga kejelasan dan keberlanjutan kode. Dengan menggunakan komentar yang tepat, Anda dapat meningkatkan kemudahan pemeliharaan dan kolaborasi dalam pengembangan perangkat lunak.
## Variabel & Konstanta
### Variabel
 *Variabel*: Variabel adalah simbol yang digunakan untuk menyimpan nilai yang dapat berubah selama jalannya program. Dalam PHP, variabel dinyatakan dengan awalan dolar ($) diikuti dengan nama variabel,
- Variabel adalah tempat penyimpanan untuk nilai-nilai dalam sebuah program.
- Setiap variabel memiliki nama yang unik yang digunakan untuk mengidentifikasinya.
- Variabel dapat menyimpan berbagai jenis data seperti angka, teks, boolean, array, dan lainnya.

```php
$ketua_gank = "bombom";
```

Variabel di atas menyimpan data ketua_genk dengan nilai "bombom". Nilai variabel ini dapat diubah selama jalannya program.
### Constanta
*Konstanta*: Konstanta adalah nilai yang tetap dan tidak dapat diubah selama jalannya program. Mereka berguna untuk menyimpan nilai yang tidak boleh berubah, seperti nilai pi (π) atau nilai-nilai pengaturan yang tetap. Dalam PHP, konstanta didefinisikan menggunakan fungsi define().
- Konstanta adalah nilai yang tetap dan tidak berubah selama jalannya program.
- Nilai konstanta didefinisikan sekali dan tidak dapat diubah kembali.
- Biasanya digunakan untuk menyimpan nilai-nilai seperti konstanta matematis atau pengaturan yang tetap.
```php
const KepSek = "Herwelis";
echo 'KepSeknya Pak ' . KepSek;
```
Dalam contoh di atas, kita mendefinisikan konstanta dKepSek dengan nilai "Herwelis".
## Operator
### Aritmatika
#### Penjelasan
Operator aritmatika merupakan operator untuk melakukan operasi aritmatika.
Operator aritmatika terdiri dari:

| Nama Operator | Simbol |
| ------------- | ------ |
| Penjumlahan   | `+`    |
| Pengurangan   | `-`    |
| Perkalian     | `*`    |
| Pemangkatan   | `**`   |
| Pembagian     | `/`    |
| Sisa Bagi     | `%`    |
#### Program
```php
$a = 5;
$b = 2;

// penjumlahan
$c = $a + $b;
echo "$a + $b = $c";
echo "<hr>";

// pengurangan
$c = $a - $b;
echo "$a - $b = $c";
echo "<hr>";

// Perkalian
$c = $a * $b;
echo "$a * $b = $c";
echo "<hr>";

// Pembagian
$c = $a / $b;
echo "$a / $b = $c";
echo "<hr>";

// Sisa bagi
$c = $a % $b;
echo "$a % $b = $c";
echo "<hr>";

// Pangkat
$c = $a ** $b;
echo "$a ** $b = $c";
```
#### Hasil
![[php.png]]
### Perbandingan
#### Penjelasan
Operator perbandingan adalah operator untuk membandingkan dua buah nilai.
Hasil operasi dari operator perbandingan akan menghasilkan nilai dengan tipe data _boolean_, yaitu `true` (benar) dan `false` (salah).
Berikut ini daftar operator relasi:

| Nama Operator           | Simbol           |
| ----------------------- | ---------------- |
| Lebih Besar             | `>`              |
| Lebih Kecil             | `<`              |
| Sama Dengan             | `==` atau `===`  |
| Tidak Sama dengan       | `!=` atau `!==`  |
| Lebih Besar Sama dengan | `>=`             |
| Lebih Kecil Sama dengan | `<=`             |
#### Program
```php
// lebih besar
$c = $a > $b;
echo "$a > $b: $c";
echo "<hr>";

// lebih kecil
$c = $a < $b;
echo "$a < $b: $c";
echo "<hr>";

// lebih sama dengan
$c = $a == $b;
echo "$a == $b: $c";
echo "<hr>";

// lebih tidak sama dengan
$c = $a != $b;
echo "$a != $b: $c";
echo "<hr>";
```
#### hasil
![[php1.png]]
### Logika
#### Penjelasan
Operator logika adalah operator untuk melakukan operasi logika seperti `AND`, `OR`, dan `NOT`.
Operator logika terdiri dari:

| Nama Operator         | Simbol |
| --------------------- | ------ |
| Logika AND            | `&&`   |
| Logika OR             | `\|`   |
| Negasi/kebalikan/ NOT | `!`    |
#### Program
```php
$a = true;
$b = false;

// variabel $c akan bernilai false
$c = $a && $b;
printf("%b && %b = %b", $a,$b,$c);
echo "<hr>";

// variabel $c akan bernilai true
$c = $a || $b;
printf("%b || %b = %b", $a,$b,$c);
echo "<hr>";

// variabel $c akan bernilai false
$c = !$a;
printf("!%b = %b", $a, $c);
echo "<hr>";
```

#### Hasil
![[php2.png]]
## Conditional Statement
### if
#### Penjelasan
If merupakan struktur percabangan yang digunakan untuk mengevaluasi suatu kondisi dan menjalankan blok kode tertentu jika kondisi tersebut bernilai benar (true). Jika kondisi bernilai salah (false), maka blok kode tersebut akan dilewati dan program akan melanjutkan ke pernyataan berikutnya.
#### Struktur
```php
if (<kondisi>){
// Blok kode yang dijalankan jika kondisi bernilai true
}
```
#### Program
```php
//if
$total_belanja = 150000;
if($total_belanja > 100000){
    echo "Anda dapat hadiah!";
}
```
#### Hasil
![[php3.png]]
#### Analisis
Array yang dideklarasikan adalah `$barang` dengan isi elemen-elemennya yaitu "Buku Tulis", "Penghapus", dan "Spidol".
Pada blok kode berikutnya, nilai-nilai dalam array `$barang` ditampilkan menggunakan pernyataan `echo`.
- Pernyataan `echo $barang[0]."<br>";` akan menampilkan elemen pertama dalam array `$barang`, yaitu "Buku Tulis", diikuti dengan tag `<br>` untuk membuat baris baru pada tampilan.
- Pernyataan `echo $barang[1]."<br>";` akan menampilkan elemen kedua dalam array `$barang`, yaitu "Penghapus", diikuti dengan tag `<br>`.
- Pernyataan `echo $barang[2]."<br>";` akan menampilkan elemen ketiga dalam array `$barang`, yaitu "Spidol", diikuti dengan tag `<br>`.
#### Kesimpulan program
Program di atas menginisialisasi sebuah array dengan nama `$barang` yang berisi tiga elemen, yaitu "Buku Tulis", "Penghapus", dan "Spidol". Kemudian, program menampilkan isi dari array tersebut dengan menggunakan pernyataan `echo`. Setiap elemen array ditampilkan secara terpisah dengan menggunakan indeks array, yaitu `$barang[0]`, `$barang[1]`, dan `$barang[2]`.
### if-else
#### Penjelasan
Percabangan If/Else adalah permemiliki dua pilihan. Jika `<kondisi>` bernilai `true`, maka blok `if` akan dikerjakan dan jika `<kondisi>` bernilai `false`, maka blok `else` akan dikerjakan.
#### Struktur
```php
if (kondisi) {
    // Blok kode yang dijalankan jika kondisi bernilai true
} else {
    // Blok kode yang dijalankan jika kondisi bernilai false
}
```
#### Program
```php
//if-else
$umur = 13;
if (<kondisi> ){
    echo "Kamu tidak boleh membuka situs ini!";
} else {
    echo "Selamat datang di website kami!";
}
```
#### Hasil
![[php4.png]]
#### Analisis
Jika variabel `$umur` memiliki nilai kurang dari 18, maka pesan "Kamu tidak boleh membuka situs ini!" akan ditampilkan. Jika variabel `$umur` memiliki nilai 18 atau lebih, maka pesan "Selamat datang di website kami!" akan ditampilkan.
#### Kesimpulan program
- Program menggunakan variabel `$umur` dengan nilai 13.
- Terdapat pernyataan `if-else` yang digunakan untuk menentukan pesan yang akan dicetak berdasarkan kondisi yang dievaluasi.
- Namun, dalam kode tersebut, kondisi yang spesifik untuk menentukan apakah pengguna diperbolehkan membuka situs atau tidak tidak ditentukan. Kode `<kondisi>` perlu diganti dengan ekspresi atau pernyataan yang relevan.
- Pesan "Kamu tidak boleh membuka situs ini!" akan dicetak jika kondisi yang dievaluasi bernilai `true` (atau jika kondisi yang dievaluasi tidak sama dengan `false`).
- Jika kondisi yang dievaluasi bernilai `false` (atau jika kondisi yang dievaluasi sama dengan `false`), maka pesan "Selamat datang di website kami!" akan dicetak.
- Tanpa mengetahui kondisi yang spesifik dalam `<kondisi>`, tidak dapat diberikan analisis yang lebih rinci tentang program tersebut.
### if-else if-else
#### Penjelasan
`if-else if-else` adalah sebuah struktur pengendalian alur dalam pemrograman yang digunakan untuk mengevaluasi beberapa kondisi secara berurutan dan menjalankan blok kode yang sesuai dengan kondisi yang pertama kali terpenuhi.
#### Struktur
```php
if (kondisi1) {
    // Blok kode yang dijalankan jika kondisi1 bernilai true
} elseif (kondisi2) {
    // Blok kode yang dijalankan jika kondisi2 bernilai true
} else {
    // Blok kode yang dijalankan jika semua kondisi bernilai false
}
```
#### Program
```php
$nilai = 88;
if ($nilai > 90) {
    $grade = "A+";
} elseif($nilai > 80){
    $grade = "A";
} elseif($nilai > 70){
    $grade = "B+";
} elseif($nilai > 60){
    $grade = "B";
} elseif($nilai > 50){
    $grade = "C+";
} elseif($nilai > 40){
    $grade = "C";
} elseif($nilai > 30){
    $grade = "D";
} elseif($nilai > 20){
    $grade = "E";
} else {
    $grade = "F";
}
echo "Nilai anda: $nilai<br>";
echo "Grade: $grade";
```
#### Hasil
![[php5.png]]
#### Analisis
- Karena nilai 88 lebih besar dari 80, kondisi `$nilai > 80` bernilai `true`.
- Oleh karena itu, variabel `$grade` akan diisi dengan nilai "A".
- Hasil keluaran program akan menjadi:
```
Nilai anda: 88
Grade: A
```
#### Kesimpulan program
- Variabel `$nilai` memiliki nilai 88.
- Terdapat serangkaian pernyataan `if-elseif-else` yang digunakan untuk mengevaluasi nilai dan menentukan grade yang sesuai.
- Evaluasi dimulai dengan kondisi `$nilai > 90`. Jika kondisi tersebut bernilai `true`, maka variabel `$grade` akan diisi dengan nilai "A+".
- Jika kondisi pertama tidak terpenuhi, maka kondisi berikutnya dievaluasi berurutan. Jika kondisi dalam `elseif` bernilai `true`, maka variabel `$grade` akan diisi dengan nilai yang sesuai.
- Jika tidak ada kondisi dalam `if` atau `elseif` yang bernilai `true`, maka blok kode dalam `else` akan dieksekusi, dan variabel `$grade` akan diisi dengan nilai "F".
- Setelah semua kondisi dievaluasi, pesan yang mencetak nilai dan grade akan ditampilkan.
### Switch-case
#### Penjelasan
`switch-case` adalah sebuah struktur pengendalian alur dalam pemrograman yang digunakan untuk memilih tindakan yang akan diambil berdasarkan nilai suatu ekspresi atau variabel.
#### Struktur
```php
switch (ekspresi) {
    case nilai1:
        // Blok kode yang dijalankan jika ekspresi sama dengan nilai1
        break;
    case nilai2:
        // Blok kode yang dijalankan jika ekspresi sama dengan nilai2
        break;
    default:
        // Blok kode yang dijalankan jika ekspresi tidak sama dengan nilai manapun
        break;
}
```
#### Program
```php
$level = 3;
switch($level){
    case 1:
        echo "Pelajari HTML";
        break;
    case 2:
        echo "Pelajari CSS";
        break;
    default:
        echo "Kamu bukan programmer!";
}
```
#### Hasil
![[php6.png]]
 #### Analisis
- Karena nilai `$level` adalah 3, tidak ada case yang cocok dengan nilai tersebut.
- Oleh karena itu, blok kode dalam default akan dieksekusi.
#### Kesimpulan program
- Variabel `$level` memiliki nilai 3.
- Terdapat pernyataan `switch` yang digunakan untuk mengevaluasi nilai `$level` dan memilih tindakan yang sesuai.
- Evaluasi dimulai dengan case pertama, yaitu `case 1`. Jika nilai `$level` sama dengan 1, maka pesan "Pelajari HTML" akan dicetak.
- Jika tidak cocok dengan case pertama, evaluasi akan melanjutkan ke case berikutnya, yaitu `case 2`. Jika nilai `$level` sama dengan 2, maka pesan "Pelajari CSS" akan dicetak.
- Jika tidak ada case yang cocok dengan nilai `$level`, maka blok kode dalam default akan dieksekusi. Pesan "Kamu bukan programmer!" akan dicetak.
- Setelah blok kode dalam case atau default dieksekusi, pernyataan `break` digunakan untuk menghentikan eksekusi dan keluar dari switch.
## Array
### Array 1 dimensi
#### Penjelasan
Array satu dimensi adalah struktur data yang digunakan untuk menyimpan sekumpulan nilai dalam satu variabel. Array ini terdiri dari elemen-elemen yang ditempatkan dalam urutan yang terdefinisi.
#### Struktur
```php
$nama_array = [nilai1, nilai2, nilai3, ...];
```
#### Program
```php
$barang = ["Buku Tulis", "Penghapus", "Spidol"];
echo $barang[0]."<br>";
echo $barang[1]."<br>";
echo $barang[2]."<br>";
```
#### Hasil
![[php7.png]]
#### Analisis
- Array `$barang` memiliki tiga elemen yang mewakili nama barang: "Buku Tulis", "Penghapus", dan "Spidol".
- Menggunakan sintaksis `$barang[indeks]`, program mencetak elemen-elemen array tersebut dengan menambahkan tag `<br>` setelah setiap elemen untuk memberikan baris baru.
- Pernyataan `echo $barang[0]` mencetak elemen pertama dari array, yaitu "Buku Tulis".
- Pernyataan `echo $barang[1]` mencetak elemen kedua dari array, yaitu "Penghapus".
- Pernyataan `echo $barang[2]` mencetak elemen ketiga dari array, yaitu "Spidol".
#### Kesimpulan
- Array `$barang` dideklarasikan dengan tiga elemen yang mewakili nama barang: "Buku Tulis", "Penghapus", dan "Spidol".
- Elemen-elemen array diakses dan dicetak menggunakan indeks. Pernyataan `echo $barang[0]` mencetak elemen pertama, `echo $barang[1]` mencetak elemen kedua, dan `echo $barang[2]` mencetak elemen ketiga.
- Dalam contoh ini, elemen-elemen array dicetak dengan menambahkan tag `<br>` setelah setiap elemen untuk memberikan baris baru dalam output.
### Array Asosiatif
#### Penjelasan
Array asosiatif adalah struktur data dalam pemrograman yang menggunakan kunci (key) sebagai indeks untuk mengakses elemen-elemennya. Setiap elemen dalam array asosiatif terdiri dari pasangan kunci-nilai, di mana kunci digunakan untuk mengidentifikasi elemen tertentu dan nilai merupakan data yang terkait dengan kunci tersebut.
#### Struktur
```php
$nama_array = [
    "kunci1" => "nilai1",
    "kunci2" => "nilai2",
    "kunci3" => "nilai3",
];
```
#### Program
```php
artikel = [
    "judul" => "Belajar Pemrograman PHP",
    "penulis" => "petanikode",
    "view" => 128
];
echo "<h2>".$artikel["judul"]."</h2>";
echo "<p>oleh: ".$artikel["penulis"]."</p>";
echo "<p>View: ".$artikel["view"]."</p>";
```
### Array multidimensi
#### Penjelasan
Array multidimensi adalah struktur data dalam pemrograman yang memungkinkan penyimpanan elemen-elemen dalam bentuk matriks atau tabel yang terdiri dari baris dan kolom. Dalam array multidimensi, setiap elemen juga dapat menjadi array lagi, sehingga menciptakan hierarki atau struktur yang lebih kompleks.
#### Struktur
```php
$nama_array = [
    [nilai1, nilai2, nilai3],
    [nilai4, nilai5, nilai6],
    [nilai7, nilai8, nilai9]
];
```
#### Program
```php
$matrik = [
    [2,3,4],
    [7,5,0],
    [4,3,8],
];
echo $matrik[1][0];
```
#### Hasil
![[php8.png]]
#### Analisis
- Variabel `$matrik` adalah array multidimensi yang berisi matriks angka.
- Matriks ini memiliki tiga baris dan tiga kolom.
- Setiap elemen dalam matriks diakses menggunakan indeks baris dan kolom yang terkait.
- Pernyataan `echo $matrik[1][0];` digunakan untuk mencetak elemen pada baris kedua (indeks 1) dan kolom pertama (indeks 0) dari matriks.
- Hasil keluaran program adalah nilai 7, karena elemen pada baris kedua dan kolom pertama dari matriks adalah 7.
#### Kesimpulan program
- Variabel `$matrik` adalah array multidimensi yang menyimpan matriks angka.
- Matriks ini terdiri dari tiga baris dan tiga kolom.
- Setiap elemen dalam matriks dapat diakses menggunakan indeks baris dan kolom yang terkait.
- Pernyataan `echo $matrik[1][0];` digunakan untuk mencetak elemen pada baris kedua (indeks 1) dan kolom pertama (indeks 0) dari matriks.
- Hasil keluaran program adalah nilai 7, karena elemen pada baris kedua dan kolom pertama dari matriks adalah 7.
## Var_dump
### Penjelasan
`var_dump()` adalah fungsi bawaan PHP yang digunakan untuk memeriksa isi dan tipe data dari sebuah variabel. Fungsi ini akan menampilkan informasi yang lebih rinci dibandingkan dengan `echo`
### Struktur
```php
var_dump($variable);
```
### Program
```PHP
<?php

$data = array(
    "nama" => "John Doe",
    "umur" => 35,
    "hobi" => array("membaca", "menulis", "bermain game")
);

$data2 = array(
    array("nama" => "Alya", "umur" => 25),
    array("nama" => "Peter Pan", "umur" => 15)
);

var_dump($data);
var_dump($data2);

?>
```
### Hasil
![[php9.png]]
### Analisis
1. **Deklarasi Array Asosiatif `$data`**: Program ini mendeklarasikan sebuah array asosiatif bernama `$data` yang berisi beberapa elemen, yaitu:
- `"nama"` dengan nilai "John Doe"
- `"umur"` dengan nilai 35
- `"hobi"` dengan nilai array yang berisi "membaca", "menulis", dan "bermain game"
2. **Deklarasi Array Multidimensi `$data2`**: Program juga mendeklarasikan sebuah array multidimensi bernama `$data2` yang berisi dua array asosiatif, masing-masing dengan kunci `"nama"` dan `"umur"`.
3. **Penggunaan `var_dump()`**: Program menggunakan fungsi `var_dump()` untuk mencetak isi dari kedua array tersebut.
### Kesimpulan Program
- Program ini mendemonstrasikan penggunaan array asosiatif (array dengan indeks berbentuk string) dan array bersarang (array yang berisi array lain).
- Fungsi `var_dump()` digunakan untuk memeriksa struktur dan isi dari variabel, dalam hal ini adalah array `$data` dan `$data2`.
- Contoh ini dapat digunakan sebagai dasar untuk memahami manipulasi dan akses data menggunakan array dalam program PHP.
## Looping (perulangan)
### For
#### Penjelasan
For adalah sebuah pernyataan pengulangan dalam pemrograman yang digunakan untuk melakukan tugas berulang dalam sebuah blok kode. For umumnya digunakan untuk mengakses dan memanipulasi elemen-elemen dalam sebuah struktur data seperti array atau daftar.
#### Struktur
```php
for (inisialisasi; kondisi; perubahan) {
    // Blok kode yang akan diulang
}
```
#### Program
```php
for($i = 0; $i < 10; $i++){
    echo "<h2>Ini perulangan ke-$i</h2>";
}
```
#### Hasil
![[php10.png]]
#### Analisis
1. **Perulangan `for`**: Program menggunakan struktur perulangan `for` untuk mengulang blok kode sebanyak 10 kali.
- Inisialisasi variabel loop `$i` dengan nilai 0.
- Kondisi perulangan: selama `$i` kurang dari 10, loop akan terus berjalan.
- Incremen variabel loop `$i` dengan menambahkan 1 setiap kali loop dijalankan.
2. **Mencetak Judul**: Dalam setiap iterasi loop, program akan mencetak sebuah judul HTML (`<h2>`) yang berisi informasi tentang nomor perulangan saat itu, menggunakan nilai variabel `$i`.
#### Kesimpulan program
- Program ini menggunakan perulangan `for` untuk mengulang sebuah blok kode sebanyak 10 kali.
- Dalam setiap iterasi, program akan mencetak sebuah judul HTML yang menampilkan nomor perulangan saat itu.
- Tujuan dari program ini adalah untuk mendemonstrasikan penggunaan perulangan `for` dalam PHP, yang merupakan salah satu struktur kontrol dasar dalam pemrograman.
- Contoh ini dapat digunakan sebagai dasar untuk memahami penggunaan perulangan dan manipulasi output dalam program PHP.
### While
#### Penjelasan
While adalah sebuah pernyataan pengulangan dalam pemrograman yang digunakan untuk menjalankan blok kode secara berulang selama kondisi tertentu bernilai benar (true). Pernyataan while mengevaluasi kondisi sebelum setiap iterasi perulangan, dan jika kondisi tersebut bernilai benar, blok kode di dalam while akan dieksekusi. Jika kondisi bernilai salah, perulangan akan berhenti dan eksekusi program akan dilanjutkan ke pernyataan setelah while.
#### Struktur
```php
while (kondisi) {
    // Blok kode yang akan diulang
    // Perubahan kondisi di dalam blok kode yang akan membuat kondisi bernilai false
}
```
#### Program
```php
$ulangi = 0;
while($ulangi < 10){
    echo "<p>Ini adalah perulangan ke-$ulangi</p>";
    $ulangi++;
}
```
#### Hasil
![[php11.png]]
#### Analisis
1. Penginisialisasian variabel: Pada baris pertama (`$ulangi = 0`), variabel `$ulangi` diinisialisasi dengan nilai 0. Ini merupakan langkah awal sebelum perulangan dimulai.
2. Kondisi perulangan: Pada baris kedua (`$ulangi < 10`), terdapat kondisi perulangan yang mengevaluasi apakah nilai `$ulangi` masih kurang dari 10. Jika kondisi ini bernilai benar (true), perulangan akan dilakukan. Jika kondisi ini bernilai salah (false), perulangan akan berhenti.
3. Pernyataan dalam perulangan: Pada baris ketiga (`echo "<p>Ini adalah perulangan ke-$ulangi</p>";`), terdapat pernyataan yang mencetak teks `Ini adalah perulangan ke-$ulangi `dengan menggunakan tag HTML `<p>`. Variabel `$ulangi` digunakan untuk menampilkan nomor perulangan saat ini. Setiap iterasi perulangan, teks ini akan dicetak dengan nilai `$ulangi` yang berbeda.
4. Pernyataan iterasi: Setiap kali satu iterasi perulangan selesai, pernyataan `$ulangi++` pada baris keempat akan dieksekusi. Pernyataan ini bertujuan untuk menambahkan nilai `$ulangi` sebesar 1 setiap kali iterasi berlangsung. Dengan demikian, variabel `$ulangi` akan terus bertambah hingga mencapai batas kondisi perulangan.
#### Kesimpulan program
1. Penginisialisasian variabel: Pada baris pertama (`$ulangi = 0`), variabel `$ulangi` diinisialisasi dengan nilai 0. Ini merupakan langkah awal sebelum perulangan dimulai.
2. Kondisi perulangan: Pada baris kedua (`$ulangi < 10`), terdapat kondisi perulangan yang mengevaluasi apakah nilai `$ulangi` masih kurang dari 10. Jika kondisi ini bernilai benar (true), perulangan akan dilakukan. Jika kondisi ini bernilai salah (false), perulangan akan berhenti.
3. Pernyataan dalam perulangan: Pada baris ketiga (`echo "<p>Ini adalah perulangan ke-$ulangi</p>";`), terdapat pernyataan yang mencetak teks `Ini adalah perulangan ke-$ulangi` dengan menggunakan tag HTML `<p>`. Variabel `$ulangi` digunakan untuk menampilkan nomor perulangan saat ini. Setiap iterasi perulangan, teks ini akan dicetak dengan nilai `$ulangi` yang berbeda.
4. Pernyataan iterasi: Setiap kali satu iterasi perulangan selesai, pernyataan `$ulangi++` pada baris keempat akan dieksekusi. Pernyataan ini bertujuan untuk menambahkan nilai `$ulangi` sebesar 1 setiap kali iterasi berlangsung. Dengan demikian, variabel `$ulangi` akan terus bertambah hingga mencapai batas kondisi perulangan.
### Do-while
#### Penjelasan
Do-while adalah sebuah pernyataan pengulangan dalam pemrograman yang digunakan untuk menjalankan blok kode secara berulang selama kondisi tertentu bernilai benar (true). Pernyataan do-while mirip dengan pernyataan while, namun perbedaannya terletak pada pengevaluasian kondisi. Pada do-while, blok kode akan dijalankan terlebih dahulu sebelum kondisi dievaluasi.
#### Struktur
```php
do {
    // Blok kode yang akan diulang
    // Perubahan kondisi di dalam blok kode yang akan membuat kondisi bernilai false
} while (kondisi);
```
#### Program
```php
$ulangi = 10;
do {
    echo "<p>ini adalah perulangan ke-$ulangi</p>";
    $ulangi--;
} while ($ulangi > 0);
```
#### Hasil
![[php12.png]]
#### Analisis
1. enginisialisasian variabel: Pada baris pertama (`$ulangi = 10`), variabel `$ulangi` diinisialisasi dengan nilai 10. Ini merupakan langkah awal sebelum perulangan dimulai.
2. Blok kode perulangan: Pada baris kedua hingga keempat, terdapat blok kode yang dijalankan dalam perulangan. Pada setiap iterasi, teks `Ini adalah perulangan ke-$ulangi` dicetak menggunakan tag HTML `<p>`, di mana `$ulangi` adalah nomor perulangan saat ini. Selain itu, pada baris ketiga (`$ulangi--`), nilai `$ulangi` dikurangi 1 setiap kali iterasi berlangsung.
3. Kondisi perulangan: Pada baris terakhir (`while ($ulangi > 0)`), terdapat kondisi perulangan yang mengevaluasi apakah nilai `$ulangi` masih lebih besar dari 0. Jika kondisi ini bernilai benar (true), perulangan akan dilakukan. Jika kondisi ini bernilai salah (false), perulangan akan berhenti.
#### Kesimpulan program
Program menggunakan perulangan do-while untuk mencetak teks `ini adalah perulangan ke-$ulangi` sebanyak 10 kali, di mana `$ulangi` adalah nomor perulangan dari 10 hingga 1. Setiap iterasi perulangan, teks tersebut dicetak dengan nomor perulangan yang berbeda, dan nilai `$ulangi` akan dikurangi 1 menggunakan pernyataan `$ulangi--`.
Perulangan do-while digunakan dalam program ini, sehingga blok kode dijalankan setidaknya satu kali sebelum kondisi perulangan dievaluasi. Dalam contoh ini, blok kode mencetak teks `Ini adalah perulangan ke-$ulangi` dengan nilai awal `$ulangi` adalah 10. Kemudian, nilai `$ulangi` dikurangi 1 pada setiap iterasi.
### Foreach
#### Penjelasan
Foreach adalah sebuah konstruksi pengulangan yang digunakan dalam pemrograman untuk mengulang elemen-elemen dalam sebuah array atau objek yang dapat diiterasi. Konstruksi foreach dapat digunakan untuk mengakses setiap elemen dalam struktur data tersebut tanpa perlu menggunakan indeks.
#### Struktur
```php
foreach ($array as $nilai) {
    // Blok kode yang akan diulang
}
```
#### Program
```php
$books = [
    "Panduan Belajar PHP untuk Pemula",
    "Membangun Aplikasi Web dengan PHP",
    "Tutorial PHP dan MySQL",
    "Membuat Chat Bot dengan PHP"
];
echo "<h5>Judul Buku PHP:</h5>";
echo "<ul>";
foreach($books as $buku){
    echo "<li>$buku</li>";
}
echo "</ul>";
```
#### Hasil
![[php13.png]]
#### Analisis
1. Inisialisasi array `$books`: Pada baris pertama, terdapat inisialisasi array `$books` yang berisi empat elemen dengan judul-judul buku tentang PHP.
2. Mencetak judul: Pada baris ketiga, teks `<h5>Judul Buku PHP:</h5>` dicetak menggunakan tag HTML `<h5>`. Teks ini akan menampilkan judul yang mengindikasikan bahwa daftar buku PHP akan dicetak.
3. Mencetak daftar buku: Pada baris kelima hingga kesembilan, terdapat blok kode foreach. Pernyataan foreach digunakan untuk mengiterasi setiap elemen dalam array `$books`. Pada setiap iterasi, nilai elemen saat ini akan diikat ke variabel sementara `$buku`. Di dalam blok kode foreach, teks `<li>$buku</li>` dicetak menggunakan tag HTML `<li>`. Teks ini akan mencetak judul buku PHP yang sedang diiterasi.
4. Menutup daftar buku: Pada baris terakhir, teks `</ul>` dicetak menggunakan tag HTML `<ul>`. Ini digunakan untuk menutup daftar buku yang telah dicetak.
#### Kesimpulan program
- Array `$books` berisi empat elemen yang merupakan judul-judul buku tentang PHP.
- Pertama, program mencetak teks `<h5>Judul Buku PHP:</h5>` menggunakan tag HTML `<h5>`. Teks ini menandakan bahwa daftar buku PHP akan dicetak.
- Selanjutnya, program mencetak tag pembuka `<ul>` untuk memulai daftar buku.
- Dalam perulangan foreach, setiap elemen dalam array `$books` diikat ke variabel sementara `$buku`. Di dalam blok kode foreach, judul buku `$buku` dicetak sebagai elemen daftar menggunakan tag HTML `<li>`. Pada setiap iterasi, judul buku yang berbeda akan dicetak.
- Setelah perulangan selesai, program mencetak tag penutup `</ul>` untuk menutup daftar buku.
## Function
### Penjelasan
Fungsi di PHP adalah blok kode yang dapat digunakan kembali untuk melakukan tugas-tugas tertentu. Fungsi dapat menerima parameter (input) dan dapat mengembalikan nilai (output).
### Struktur
```php
function namaFungsi($parameter1, $parameter2, ...) {
    // Blok kode yang akan dieksekusi
    // Dapat berisi berbagai jenis pernyataan (statement)
    return nilai_yang_dikembalikan;
}
```
### Program
```php
<?php

function tambah($a, $b) {

    $hasil = $a + $b;
    return $hasil;
}

$angka1 = 5;
$angka2 = 3;
$hasil_penjumlahan = tambah($angka1, $angka2);

echo "Hasil penjumlahan: " . $hasil_penjumlahan;

?>
```
### Hasil
![[php14.png]]
### Analisis
1. Program ini mendefinisikan sebuah fungsi bernama `tambah()` yang menerima dua parameter `$a` dan `$b`.
2. Dalam fungsi `tambah()`, variabel `$hasil` akan menyimpan hasil penjumlahan antara `$a` dan `$b`.
3. Fungsi `tambah()` mengembalikan nilai yang disimpan dalam `$hasil`.
4. Di luar fungsi `tambah()`, program mendeklarasikan dua variabel `$angka1` dan `$angka2` dengan nilai 5 dan 3.
5. Program memanggil fungsi `tambah()` dengan argumen `$angka1` dan `$angka2`, dan menyimpan hasilnya dalam variabel `$hasil_penjumlahan`.
6. Akhirnya, program mencetak pesan "Hasil penjumlahan: " diikuti dengan nilai yang tersimpan dalam `$hasil_penjumlahan`.
### Kesimpulan
1. Program ini mengdemonstrasikan penggunaan fungsi dalam PHP untuk melakukan operasi penjumlahan.
2. Fungsi `tambah()` bertindak sebagai sebuah modul yang dapat digunakan kembali untuk melakukan penjumlahan antara dua angka.
3. Penggunaan fungsi memungkinkan program menjadi lebih modular, reusable, dan mudah dibaca dan dipelihara.
4. Pemanggilan fungsi `tambah()` dengan argumen `$angka1` dan `$angka2` menunjukkan fleksibilitas fungsi, di mana Anda dapat memanggil fungsi dengan nilai yang berbeda setiap kali.
5. Secara keseluruhan, program ini mendemonstrasikan pemahaman dasar tentang fungsi dalam pemrograman PHP, yang merupakan konsep penting bagi pelajar kelas 11 SMK jurusan RPL.
## PHP Form
### GET Method
#### Penjelasan
Metode GET adalah salah satu cara untuk mengirimkan data dari sisi klien (browser) ke sisi server (PHP) melalui URL. Data yang dikirimkan melalui metode GET akan terlihat dalam URL.
#### Program

FORM
```PHP
<!DOCTYPE html>

<html lang="en">

<head>

    <title>Document</title>

</head>
<body>

    <!-- Pada atribut action, kalian tuliskan nama file php yang bertugas untuk mengelola atau menangkap data dari form tersebut. -->

    <form action="proses_get.php" method="GET">

        <input type="text" name="nama_lengkap" placeholder="Masukkan nama">

        <input type="number" name="umur" placeholder="Masukkan umur"> <br>
        
        <button type="submit">Kirim</button>

    </form>
    
</body>

</html>
```

PROSES
```PHP
<?php

// Key dari array-nya, sesuai dengan nama dari atribut name di setiap input-nya

$nama = $_GET["nama_lengkap"];
$umur = $_GET["umur"];

?>

<!DOCTYPE html>

<html lang="en">

<head>

    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>XI RPL 1 - GET</title>

</head>

<body>

    <p>Nama anda
        <!-- Ini adalah versi singkatnya dari php echo,
             yang fungsinya untuk menampilkan data -->

          <?= $nama ?>
    </p>
  
    <p>Umur anda <?= $umur ?> tahun</p>

</body>
</html>
```
#### Hasil

# Apa itu web dinamis dan PHP?

>[!WEB DINAMIS]
>Web dinamis adalah jenis situs web yang dapat menghasilkan konten yang berubah atau disesuaikan secara dinamis berdasarkan permintaan pengguna. Konten dinamis dapat dihasilkan melalui interaksi dengan pengguna, pengambilan data dari [[basis data]], integrasi dengan layanan eksternal, dan pemrosesan logika bisnis. Web dinamis menggunakan bahasa pemrograman server-side untuk menghasilkan dan mengelola konten dinamis ini.

>[!PHP]
>PHP (PHP: Hypertext Preprocessor) adalah salah satu bahasa pemrograman yang sering digunakan untuk mengembangkan web dinamis. PHP adalah bahasa pemrograman sisi server yang dirancang khusus untuk pengembangan web. Itu dapat diintegrasikan dengan HTML untuk menghasilkan konten dinamis. PHP berjalan di sisi server, yang berarti kode PHP dieksekusi di server web sebelum hasilnya dikirim ke browser pengguna.

# Echo & commentar
## Echo
1. Penggunaan Dasar:
   - echo adalah perintah dasar dalam PHP yang digunakan untuk menampilkan teks atau nilai pada halaman web.
   - Anda dapat menggunakan echo untuk menampilkan teks statis atau untuk menampilkan nilai dari variabel atau ekspresi.
   - echo dapat menerima satu atau lebih argumen yang dipzzzzzzzzzzzzzzzzzzzzisahkan oleh tanda titik (.) untuk menggabungkan teks dan variabel.

2. Menampilkan Teks:
   - Anda dapat menggunakan echo untuk langsung menampilkan teks statis dalam tanda kutip ganda ("") atau tanda kutip tunggal ('').
   - Contoh: echo "Halo, dunia!";

3. Menampilkan Nilai Variabel:
   - Anda dapat menggunakan echo untuk menampilkan nilai dari variabel dalam teks yang ditampilkan.
   - Gunakan operator konkatenasi (tanda titik) untuk menggabungkan teks dan variabel.
Contoh: 
```php
     $nama = "John Doe";
     echo "Halo, nama saya " . $nama . ".";
```

4. Menampilkan HTML:
   - Selain teks, Anda juga dapat menggunakan echo untuk menampilkan kode HTML di dalam skrip PHP.
   - Uji coba berikut menunjukkan penggunaan echo untuk menampilkan elemen HTML:
```php
     echo "<h1>Selamat Datang!</h1>";
     echo "<p>Ini adalah halaman web PHP.</p>";
```

5. Penggunaan Kutipan:
   - Anda dapat menggunakan tanda kutip ganda `("")` atau tanda kutip tunggal `('')` untuk mengelilingi teks dalam echo.
   - Misalnya, `echo "Halo, nama saya 'John'.";`

6. Menggunakan Pemisah:
   - Saat menggunakan echo dengan beberapa argumen, Anda dapat menggunakan koma (,) sebagai pemisah antara argumen.
   - Contoh: `echo "Halo,", " nama saya ", $nama, ".";`

Materi echo pada PHP memungkinkan Anda untuk menampilkan teks, nilai variabel, dan bahkan kode HTML di dalam skrip PHP. Hal ini berguna dalam menghasilkan tampilan dinamis pada halaman web yang sedang Anda bangun.
## Struktur dasar echo
1. <?php dan ?>: Adalah penanda awal dan akhir dari blok kode PHP. Semua kode PHP harus berada di antara penanda ini agar dapat dieksekusi dengan benar.
2. echo: Adalah perintah dalam PHP yang digunakan untuk menampilkan teks atau nilai ke dalam halaman web.
3. teks atau nilai yang ingin ditampilkan: Adalah bagian di mana Anda memasukkan teks statis, nilai variabel, atau ekspresi matematika yang ingin ditampilkan di halaman web.

Jadi, ketika kode tersebut dieksekusi, teks atau nilai yang ditentukan akan ditampilkan di halaman web sebagai hasil dari perintah echo.
Kode program
```php
<?php
    echo "Halo, dunia!";
?>
```

Hasil:
```
Halo, dunia!
```
## Commentar
Dalam PHP, komentar digunakan untuk memberikan penjelasan, catatan, atau dokumentasi di dalam kode program. Komentar tidak akan dieksekusi oleh interpreter PHP, sehingga komentar tidak akan mempengaruhi hasil program.
Berikut adalah beberapa hal yang perlu diketahui tentang komentar dalam PHP:
1. Komentar Satu Baris:
   - Komentar satu baris dimulai dengan tanda // atau #.
   - Semua teks setelah tanda tersebut hingga akhir baris diabaikan oleh interpreter PHP.
Contoh:
```php
// Ini adalah komentar satu baris
$nama = "John Doe"; // Ini adalah komentar di samping kode
```

2. Komentar Multibaris:
   - Komentar multibaris dimulai dengan /* dan diakhiri dengan */.
   - Semua teks di antara tanda tersebut diabaikan oleh interpreter PHP.
   - Komentar multibaris dapat mencakup beberapa baris kode.
Contoh:
```php
/*
Ini adalah komentar multibaris.
Ini dapat mencakup beberapa baris kode.
*/
$umur = 25;
```

3. Komentar Dokumentasi:
   - Komentar dokumen atau DocBlock digunakan untuk memberikan dokumentasi formal pada fungsi, kelas, atau metode.
   - Komentar dokumen dimulai dengan /** dan diakhiri dengan */.
   - Komentar ini sering digunakan dengan format khusus seperti PHPDoc untuk menghasilkan dokumentasi otomatis.
Contoh:
```php
     /**
      * Fungsi ini menghitung jumlah dua angka.
      *
      * @param int $a Angka pertama
      * @param int $b Angka kedua
      * @return int Hasil penjumlahan
      */
     function tambah($a, $b) {
         return $a + $b;
     }
```

4. Tujuan Penggunaan Komentar:
   - Memberikan penjelasan tentang tujuan dan fungsionalitas kode.
   - Membantu dalam pemeliharaan dan pemahaman kode untuk pengembang dan anggota tim lainnya.
   - Menyembunyikan atau menonaktifkan sebagian kode untuk uji coba atau sementara.
   - Meninggalkan catatan atau pesan kepada diri sendiri atau pengembang lain tentang kode tertentu.
Penggunaan komentar yang baik sangat penting dalam pemrograman untuk menjaga kejelasan dan keberlanjutan kode. Dengan menggunakan komentar yang tepat, Anda dapat meningkatkan kemudahan pemeliharaan dan kolaborasi dalam pengembangan perangkat lunak.
# Variable, const, operator
## Variabel 
Variabel adalah tempat untuk menyimpan dan memanipulasi data dalam program. Dalam PHP, variabel dideklarasikan dengan awalan tanda dollar ($), diikuti dengan nama variabel yang diinginkan. Variabel dapat menampung berbagai jenis data, seperti angka, string, boolean, dan lainnya. Anda dapat mengubah nilai variabel selama program berjalan.

Contoh penggunaan variabel dalam PHP:
```php
<?php
   $nama = "John Doe";
   $umur = 25;
   $statusMenikah = true;

   echo "Nama: " . $nama . "<br>";
   echo "Umur: " . $umur . "<br>";
   echo "Status Menikah: " . ($statusMenikah ? "Sudah Menikah" : "Belum Menikah") . "<br>";
?>
```

 Output yang dihasilkan:
```php
Nama: John Doe
Umur: 25
Status Menikah: Sudah Menikah
```
## Const
Konstanta adalah nilai yang tetap dan tidak dapat diubah selama program berjalan. Dalam PHP, konstanta didefinisikan menggunakan fungsi `define()`. Setelah konstanta didefinisikan, Anda tidak dapat mengubah nilainya atau mendeklarasikan kembali.

 Contoh penggunaan konstanta dalam PHP:
```php
<?php
   define("PI", 3.14);
   define("WEBSITE", "www.example.com");

   echo "Nilai PI: " . PI . "<br>";
   echo "Website: " . WEBSITE . "<br>";
?>
```

 Output yang dihasilkan:
```php
Nilai PI: 3.14
Website: www.example.com
```
## Operator 
Operator dalam PHP adalah simbol atau tanda yang digunakan untuk melakukan operasi atau manipulasi pada nilai atau variabel. Operator memungkinkan Anda untuk melakukan perhitungan matematika, perbandingan, penggabungan teks, dan operasi logika dalam program PHP. 
Berikut ini beberapa jenis operator yang tersedia dalam PHP:
1. Operator Aritmatika:
   - Operator aritmatika digunakan untuk melakukan operasi matematika seperti penjumlahan, pengurangan, perkalian, pembagian, modulus, dan sebagainya.
   - Contoh:
```php
     $a = 10;
     $b = 5;
     $c = $a + $b; // Penjumlahan
     $d = $a - $b; // Pengurangan
     $e = $a * $b; // Perkalian
     $f = $a / $b; // Pembagian
     $g = $a % $b; // Modulus (sisa pembagian)
```

1. Operator Penugasan:
   - Operator penugasan digunakan untuk memberikan nilai ke variabel.
   - Contoh:
 ```php
     $a = 10; // Penugasan nilai 10 ke variabel $a
     $b += 5; // Penugasan nilai $b + 5 ke variabel $b (sama dengan $b = $b + 5)
```

3. Operator Perbandingan:
   - Operator pembanding digunakan untuk membandingkan dua nilai dan menghasilkan nilai kebenaran (true atau false).
   - Contoh:
```php
     $a = 10;
     $b = 5;
     $c = $a == $b; // Sama dengan
     $d = $a != $b; // Tidak sama dengan
     $e = $a > $b; // Lebih besar dari
     $f = $a < $b; // Lebih kecil dari
     $g = $a >= $b; // Lebih besar dari atau sama dengan
     $h = $a <= $b; // Lebih kecil dari atau sama dengan
```
  
4. Operator Logika:
   - Operator logika digunakan untuk menggabungkan atau memanipulasi nilai kebenaran (true atau false).
   - Contoh:
```php
     $a = true;
     $b = false;
     $c = $a && $b; // Logika AND
     $d = $a || $b; // Logika OR
     $e = !$a; // Logika NOT
```
  
5. Operator String:
   - Operator string digunakan untuk menggabungkan atau memanipulasi teks.
   - Contoh:
```php
     $a = "Hello, ";
     $b = "World!";
     $c = $a . $b; // Penggabungan teks
```
  
6. Operator Lainnya:
   - Selain operator-operator di atas, PHP juga memiliki operator lain seperti operator increment (++) dan decrement (--), operator ternary (?:), operator array, dan lain-lain.

Operator dalam PHP memungkinkan Anda untuk melakukan berbagai operasi dan manipulasi pada data, dan memungkinkan logika dan fungsionalitas yang lebih kompleks dalam program Anda. Dalam pengembangan PHP, pemahaman tentang operator sangat penting untuk membuat kode yang efisien dan efektif.
# Conditional statement
## IF 
If merupakan salah satu struktur kontrol yang digunakan dalam pemrograman untuk mengatur aliran eksekusi program berdasarkan kondisi yang diberikan. Struktur if digunakan untuk memeriksa apakah suatu kondisi benar (true) atau salah (false), dan kemudian menjalankan blok kode tertentu berdasarkan hasil evaluasi kondisi tersebut.

 ### Contoh program IF
```cs
# Mendapatkan input dari pengguna
nilai = int(input("Masukkan nilai Anda: "))

# Memeriksa nilai dan memberikan pesan berdasarkan kondisi
if nilai >= 80:
    print("Selamat! Anda mendapat nilai A.")
elif nilai >= 70:
    print("Anda mendapat nilai B.")
elif nilai >= 60:
    print("Anda mendapat nilai C.")
elif nilai >= 50:
    print("Anda mendapat nilai D.")
else:
    print("Maaf, Anda tidak lulus.")

```
## IF-ELSE
 if-else merupakan ekstensi dari struktur if yang digunakan dalam pemrograman untuk mengatur aliran eksekusi program berdasarkan kondisi yang diberikan. Struktur if-else memungkinkan kita untuk menjalankan blok kode yang berbeda tergantung pada hasil evaluasi kondisi.
### contoh struktur if-else:
```css
umur = 18

if umur >= 18:
    print("Anda sudah dewasa.")
else:
    print("Anda masih anak-anak.")
```

Pada contoh di atas, kondisi umur >= 18 dievaluasi. Jika kondisi tersebut benar (nilai True), maka blok kode di dalam if akan dieksekusi, yaitu mencetak teks "Anda sudah dewasa". Jika kondisi tersebut salah (nilai False), maka blok kode di dalam else akan dieksekusi, yaitu mencetak teks "Anda masih anak-anak".
## IF-ELSE IF-ELSE
Struktur if-else if-else, juga dikenal sebagai struktur if-elif-else, digunakan dalam pemrograman untuk mengatur aliran eksekusi program dengan mempertimbangkan beberapa kondisi yang mungkin terjadi. Struktur if-elif-else memungkinkan kita untuk mengevaluasi beberapa kondisi secara berurutan dan menjalankan blok kode yang sesuai dengan kondisi yang memenuhi.
### contoh struktur if-elif-else:
```cs
# Meminta pengguna untuk memasukkan sebuah angka
bilangan = int(input("Masukkan sebuah bilangan bulat: "))

# Memeriksa bilangan dan memberikan pesan berdasarkan kondisi
if bilangan > 0:
    print("Bilangan positif")
elif bilangan < 0:
    print("Bilangan negatif")
else:
    print("Bilangan nol")
```

Dalam contoh ini, pengguna diminta untuk memasukkan sebuah bilangan bulat. Program kemudian memeriksa bilangan tersebut dan memberikan pesan berdasarkan kondisi:
- Jika bilangan lebih besar dari 0, pesan "Bilangan positif" akan dicetak.
- Jika bilangan kurang dari 0, pesan "Bilangan negatif" akan dicetak.
- Jika bilangan sama dengan 0, pesan "Bilangan nol" akan dicetak.
## Switch-case
Switch case adalah struktur kontrol yang digunakan dalam beberapa bahasa pemrograman untuk memilih tindakan atau blok kode yang akan dieksekusi berdasarkan nilai dari suatu ekspresi atau variabel. Struktur ini memberikan alternatif yang lebih mudah dibaca dan dipahami ketika terdapat banyak kemungkinan nilai yang harus dievaluasi.

Dalam switch case, ekspresi atau variabel yang dievaluasi akan dibandingkan dengan sejumlah nilai yang mungkin. Jika nilai tersebut cocok dengan salah satu kasus (case) yang didefinisikan, maka blok kode yang terkait dengan kasus tersebut akan dieksekusi. 
### Contoh program:
```cs
def switch_case(nilai):
    if nilai == 1:
        print("Ini adalah kasus 1.")
    elif nilai == 2:
        print("Ini adalah kasus 2.")
    elif nilai == 3:
        print("Ini adalah kasus 3.")
    else:
        print("Ini adalah kasus default.")
        
# Contoh penggunaan
switch_case(2)
```

Pada contoh di atas, kita mendefinisikan fungsi switch_case yang menggunakan pendekatan if-elif-else untuk mengevaluasi nilai. Jika nilai cocok dengan salah satu kasus, maka blok kode yang sesuai akan dieksekusi. Jika tidak ada kasus yang cocok, blok kode di dalam else akan dieksekusi sebagai fallback atau default case.
# Array
## Array 1 dimensi
Array satu dimensi adalah struktur data yang digunakan untuk menyimpan sekumpulan nilai yang serupa dalam satu variabel. Setiap elemen dalam array diberi indeks yang menunjukkan posisinya dalam array. Indeks pertama dimulai dari 0, yang kedua dimulai dari 1, dan seterusnya.

Dalam array satu dimensi, semua elemen memiliki tipe data yang sama. Misalnya, array satu dimensi dapat digunakan untuk menyimpan serangkaian angka, karakter, atau objek lain yang memiliki tipe data yang sama.
### Contoh program:
```cs
# Mendefinisikan array satu dimensi
angka = [10, 20, 30, 40, 50]

# Menampilkan isi array
print("Isi array:")
for elemen in angka:
    print(elemen)

# Menampilkan panjang array
print("Panjang array:", len(angka))

# Mengakses elemen array berdasarkan indeks
print("Elemen dengan indeks 2:", angka[2])

# Mengubah nilai elemen array
angka[3] = 99
print("Array setelah mengubah elemen ke-3 menjadi 99:", angka)

# Menambahkan elemen baru ke array
angka.append(60)
print("Array setelah menambahkan elemen baru:", angka)

# Menghapus elemen dari array
angka.remove(20)
print("Array setelah menghapus elemen 20:", angka)

```

Dalam program ini, kita membuat sebuah array satu dimensi bernama angka yang berisi sekumpulan bilangan bulat. Kemudian, kita menampilkan isi array menggunakan loop for. Selanjutnya, kita menggunakan fungsi len() untuk mendapatkan panjang array, dan menggunakan indeks untuk mengakses elemen tertentu dalam array.

Setelah itu, kita mengubah nilai elemen ke-3 menjadi 99 menggunakan indeks, menambahkan elemen baru (60) ke array menggunakan metode append(), dan menghapus elemen 20 dari array menggunakan metode remove().
## Array Asosiatif
Array asosiatif (atau kadang disebut sebagai kamus, tabel hash, atau dictionary dalam beberapa bahasa pemrograman) adalah struktur data yang memungkinkan kita untuk menyimpan pasangan kunci-nilai. Setiap elemen dalam array asosiatif terdiri dari sepasang kunci (key) dan nilai (value), dan kunci digunakan untuk mengakses nilai yang terkait.

Perbedaan utama antara array asosiatif dan array satu dimensi adalah cara pengindeksannya. Pada array satu dimensi, indeksnya berupa bilangan bulat yang dimulai dari 0, sedangkan pada array asosiatif, indeksnya bisa berupa tipe data lain seperti string, bilangan bulat, atau bahkan objek.

- Contoh Program:
```cs
# Membuat dictionary (array asosiatif)
siswa = {
    "nama": "Ali",
    "umur": 17,
    "kelas": "XI IPA"
}

# Mengakses nilai berdasarkan kunci
print("Nama:", siswa["nama"])
print("Umur:", siswa["umur"])
print("Kelas:", siswa["kelas"])

```
## Array Multidimensi
Array multidimensi adalah struktur data yang terdiri dari elemen-elemen yang diatur dalam bentuk matriks atau tabel dua dimensi, di mana setiap elemen dapat diakses menggunakan dua atau lebih indeks.

Dalam array multidimensi, elemen-elemen disusun dalam baris dan kolom, membentuk matriks. Setiap elemen memiliki posisi yang ditentukan oleh dua atau lebih indeks, yang mendefinisikan lokasi elemen dalam matriks.
### contoh program multi:
```cs
# Mendefinisikan matriks 2D
matriks = [[1, 2, 3],
           [4, 5, 6],
           [7, 8, 9]]

# Mengakses elemen matriks menggunakan indeks baris dan kolom
elemen = matriks[1][2]
print(elemen)  # Output: 6

# Mengubah nilai elemen matriks
matriks[0][1] = 10
print(matriks[0][1])  # Output: 10

# Melakukan iterasi melalui elemen matriks
for baris in matriks:
    for elemen in baris:
        print(elemen, end=' ')
    print()
# Output:
# 1 10 3 
# 4 5 6 
# 7 8 9
```

Pada contoh tersebut, kita mengakses elemen pada baris ke-1 dan kolom ke-2 dengan menggunakan matriks[1][2], yang menghasilkan nilai 6. Selanjutnya, kita mengubah nilai elemen pada baris ke-0 dan kolom ke-1 menjadi 10 dengan matriks[0][1] = 10. Terakhir, kita melakukan iterasi melalui elemen-elemen matriks menggunakan loop for bersarang, dan mencetak matriks secara berbaris.
# Var_dumb
Variabel `dumb` dalam beberapa konteks mungkin merujuk pada berbagai hal. Namun, jika kita mempertimbangkan istilah "dumb" dalam konteks pemrograman, mungkin itu adalah kependekan dari "dumb variable" atau "dummy variable".

1. **Dumb Variable (Variabel Dumb)**: Dalam pemrograman, "dumb variable" atau "variabel dumb" sering kali digunakan untuk menyatakan variabel yang digunakan hanya sebagai penampung sementara tanpa memiliki makna atau nilai yang signifikan dalam konteks program. Variabel semacam ini sering kali digunakan sebagai tempat penyimpanan nilai sementara atau sebagai argumen dalam pemanggilan fungsi, tetapi nilainya tidak digunakan secara langsung atau penting dalam alur program.
2. **Dummy Variable (Variabel Dummy)**: "Dummy variable" atau "variabel dummy" adalah istilah yang lebih umum dalam statistik dan analisis regresi. Dalam konteks ini, "dummy variable" adalah variabel yang digunakan untuk mewakili kategori atau faktor dalam analisis data. Misalnya, dalam analisis regresi, variabel kategorikal sering kali diubah menjadi variabel dummy agar dapat dimasukkan ke dalam model regresi. Variabel dummy sering kali diwakili sebagai variabel biner (0 atau 1), di mana nilai 0 menunjukkan ketidakhadiran kategori tertentu, dan nilai 1 menunjukkan kehadiran kategori tersebut.
# Looping (pembagian)
## For
Looping for adalah sebuah konstruksi dalam pemrograman yang memungkinkan kita untuk mengulangi serangkaian pernyataan atau blok kode untuk setiap elemen dalam suatu urutan atau objek yang dapat diiterasi.

loop for terdiri dari tiga komponen utama:
- Pernyataan awal: Pernyataan ini digunakan untuk menginisialisasi variabel yang akan digunakan sebagai penghitung atau iterator dalam loop for. Biasanya, kita mengatur nilai awal variabel iterasi di sini.
- Kondisi atau kriteria terminasi: Ini adalah kondisi yang digunakan untuk memeriksa apakah iterasi harus terus berlanjut atau dihentikan. Jika kondisi ini bernilai False, loop for akan berakhir dan eksekusi akan melanjutkan ke bagian berikutnya di program.
- Pernyataan iterasi: Ini adalah pernyataan atau blok kode yang akan diulang untuk setiap elemen dalam urutan atau objek yang diiterasi. Biasanya, ini adalah bagian dari kode yang ingin kita jalankan berulang kali.
### struktur:
```cs
for elemen in urutan:
    # Blok kode yang akan diulang
```
### contoh :
```cs
# Contoh 1: Looping melalui urutan/list
urutan = [1, 2, 3, 4, 5]
for elemen in urutan:
    print(elemen)
# Output: 1 2 3 4 5

# Contoh 2: Looping melalui string
kata = "Halo"
for karakter in kata:
    print(karakter)
# Output: H a l o

# Contoh 3: Looping dengan rentang angka
for angka in range(1, 6):
    print(angka)
# Output: 1 2 3 4 5
```

Dalam contoh-contoh di atas:
Contoh 1: Looping melalui urutan/list. Setiap elemen dalam urutan diakses satu per satu dan dicetak.
Contoh 2: Looping melalui string. Setiap karakter dalam kata diakses satu per satu dan dicetak.
Contoh 3: Looping dengan rentang angka. Loop akan berjalan dari 1 hingga 5 (rentang 1-6, tetapi 6 tidak termasuk), dan setiap angka akan dicetak.
## While
Looping while adalah sebuah konstruksi dalam pemrograman yang memungkinkan kita untuk mengulangi serangkaian pernyataan atau blok kode selama kondisi tertentu bernilai True. Loop while akan terus berjalan selama kondisi yang diberikan benar, dan akan berhenti ketika kondisi tersebut menjadi False.

Penjelasan untuk setiap bagian dari struktur loop while:
- Kata kunci while digunakan untuk memulai loop while.
- Kondisi adalah kondisi yang dievaluasi setiap kali iterasi loop dilakukan. Selama kondisi ini bernilai True, blok kode dalam loop while akan terus diulang. Jika kondisi berubah menjadi False, eksekusi loop while akan berhenti, dan program akan melanjutkan ke baris kode berikutnya setelah loop while.
- Blok kode yang diindentasi setelah titik dua (:) akan diulang selama kondisi dalam loop while bernilai True. Blok kode ini adalah tempat kita menempatkan tugas atau operasi yang ingin diulang.
### Struktur dari loop while:
```cs
while kondisi:
    # Blok kode yang akan diulang
```
### contoh:
```cs
i = 0
while i < 5:
    print(i)
    i += 1
```

Contoh di atas, loop while akan terus berjalan selama nilai variabel i kurang dari 5. Pada setiap iterasi, nilai i akan dicetak, kemudian i akan ditambah 1. Loop while akan berhenti ketika i mencapai nilai 5, karena kondisi i < 5 akan menjadi False.
## Do-While
Looping "do-while" adalah jenis loop yang memungkinkan blok kode untuk dieksekusi setidaknya satu kali, dan kemudian diulang selama kondisi tertentu tetap bernilai True. Berbeda dengan loop while konvensional, loop "do-while" mengevaluasi kondisi setelah blok kode dijalankan.

Dalam struktur ini:
- While True membuat loop berjalan tanpa henti secara default.
- Blok kode yang diindentasi setelah itu akan dieksekusi terlepas dari kondisi awal.
- Setelah blok kode dieksekusi, kita memeriksa kondisi menggunakan pernyataan if. Jika kondisi memenuhi syarat, kita menggunakan pernyataan break untuk keluar dari loop.
### struktur:
```cs
while True:
    # Blok kode yang akan diulang
    # ...

    # Pengecekan kondisi untuk keluar dari loop
    if kondisi:
        break
```
### contoh:
```cs
i = 0
while True:
    print(i)
    i += 1
    if i >= 5:
        break
```
## Foreach
Loop foreach, juga dikenal sebagai loop iterasi, digunakan untuk mengulangi atau mengiterasi setiap elemen dalam suatu urutan atau koleksi objek. Loop foreach secara otomatis mengambil setiap elemen dalam urutan dan menjalankan blok kode yang terkait untuk setiap elemen tersebut.

Penjelasan untuk setiap bagian dari struktur loop foreach:
- Kata kunci for digunakan untuk memulai loop foreach.
- Elemen adalah variabel yang akan menyimpan nilai dari setiap elemen dalam urutan atau objek yang diiterasi. Nama variabel ini dapat disesuaikan sesuai kebutuhan.
- Kata kunci in digunakan untuk menandakan bahwa variabel iterasi akan mengambil nilai dari urutan atau objek yang diiterasi.
- Urutan adalah urutan atau objek yang ingin diiterasi. Ini bisa berupa list, tuple, string, atau objek yang dapat diiterasi lainnya.
### struktur foreach:
```cs
for elemen in urutan:
    # Blok kode yang akan diulang
```
### contoh program:
```cs
urutan = [1, 2, 3, 4, 5]
for elemen in urutan:
    print(elemen)
```
# PHP Form
## GET Method
## POST Method
# Function