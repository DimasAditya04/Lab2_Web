# TUGAS PEMROGRAMAN WEB 2

Nama  : Dimas Aditya Putranto

Nim   : 312210489

Kelas : TI.22.A5

Mata Kuliah : Pemrograman Web

Dosen Pengampu : Agung Nugroho, S.Kom., M.Kom.


## Tugas menggunakan PHP dasar

# Belajar PHP Dasar

![hello](https://github.com/DimasAditya04/Lab2_Web/assets/130146099/3740442d-9cec-4ce5-92ff-b1c06d3e6668)

Hasil:

![Screenshot (181)](https://github.com/DimasAditya04/Lab2_Web/assets/130146099/076914c8-9075-499d-bfdc-f9d255419006)

# Menggunakan Variabel

![Variabel](https://github.com/DimasAditya04/Lab2_Web/assets/130146099/828036ba-6467-445e-827e-0f34b8fe6726)

Hasil:

![Screenshot (182)](https://github.com/DimasAditya04/Lab2_Web/assets/130146099/71d8cef2-73c2-4ffb-8891-315751efbe30)

# Form Input

![form_input](https://github.com/DimasAditya04/Lab2_Web/assets/130146099/a92608d7-5bef-4ee7-af49-0df4b4460728)

Hasil:

![Screenshot (184)](https://github.com/DimasAditya04/Lab2_Web/assets/130146099/f6e9b668-d805-42cd-a6eb-ed3caa8cf90f)

# Tugas
![Code_k4QL8UveeF](https://github.com/steprtm/lab2web/assets/129705802/35797c5a-5da3-4716-b973-01370e6899d4)

Hasil:

![Screenshot (185)](https://github.com/DimasAditya04/Lab2_Web/assets/130146099/3b295104-68e6-479f-b011-c3ef138d3041)

## Penjelasan
1. Struktur HTML
```
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
        <label>Tanggal Lahir: </label>
        <input type="date" name="tanggal_lahir">
        <label>Pekerjaan: </label>
        <select name="pekerjaan">
            <option value="Operator">Operator</option>
            <option value="Developer">Developer</option>
            <option value="Manager">Manager</option>
        </select>
        <input type="submit" value="Kirim">
    </form>
```
**Input Nama:** Pengguna memasukkan nama mereka.

**Input Tanggal Lahir:** Pengguna memilih tanggal lahir menggunakan kontrol input tanggal.

**Pilihan Pekerjaan:** Pengguna memilih pekerjaan dari dropdown, yang akan mempengaruhi perhitungan gaji.

2. Logika PHP, Proses Formulir
```
<?php
if ($_SERVER["REQUEST_METHOD"] == "POST" && isset($_POST['nama']) && isset($_POST['tanggal_lahir']) && isset($_POST['pekerjaan'])) {
    $nama = htmlspecialchars($_POST['nama']);
    $tanggal_lahir = $_POST['tanggal_lahir'];
    $pekerjaan = $_POST['pekerjaan'];
```
**Pengecekan Metode dan Data:** Memeriksa apakah formulir telah dikirim menggunakan metode POST dan semua data yang diperlukan ada.

**Sanitisasi Input:** Fungsi htmlspecialchars digunakan untuk menghindari serangan XSS (Cross-Site Scripting) dengan membersihkan input nama dari tag HTML atau karakter khusus.

3. Kalkulasi Umur
```
    $birthdate = new DateTime($tanggal_lahir);
    $today = new DateTime('today');
    $age = $birthdate->diff($today)->y;
```
**Objek DateTime:** Digunakan untuk memanipulasi tanggal dengan mudah.

**Perhitungan Selisih Tahun:** Menghitung selisih tahun antara tanggal lahir dan hari ini untuk mendapatkan umur.

4. Perhitungan Gaji dan Pajak
```
    $salaries = [
        "Operator" => 1000000,
        "Developer" => 3000000,
        "Manager" => 5000000
    ];
    $taxRates = [
        "Operator" => 0.1,
        "Developer" => 0.15,
        "Manager" => 0.2
    ];
    $gaji = isset($salaries[$pekerjaan]) ? $salaries[$pekerjaan] : 0;
    $pajak = isset($taxRates[$pekerjaan]) ? $taxRates[$pekerjaan] : 0;
    $thp = $gaji - ($gaji * $pajak);
```

**Array:** Menyimpan nilai gaji dan pajak berdasarkan jenis pekerjaan.

**Kalkulasi Gaji Bersih:** Menghitung gaji bersih dengan mengurangkan pajak dari gaji kotor.

5. Menampilkan Hasil
```
    echo "Selamat Datang $nama<br>";
    echo "Usia Anda: $age tahun<br>";
    echo "Pekerjaan: $pekerjaan<br>";
    echo "Gaji sebelum pajak = Rp. " . number_format($gaji, 0, ',', '.') . "<br>";
    echo "Gaji yang dibawa pulang = Rp. " . number_format($thp, 0, ',', '.');
}
?>
</body>
</html>
```
**Output:** Menggunakan echo untuk menampilkan teks dan data yang diproses ke pengguna.


## Semoga Membantu
