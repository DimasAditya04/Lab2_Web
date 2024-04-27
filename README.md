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

```
<?php

if (isset($_POST['submit'])) {
  $nama = $_POST["nama"];
  $pekerjaan = $_POST["pekerjaan"];

  if ($pekerjaan == "Software Engineer") {
    $gaji = 23000000;
  } else if ($pekerjaan == "Data Analyst") {
    $gaji = 25000000;
  } else if ($pekerjaan == "Design Graphic") {
    $gaji = 19000000;
  } else if ($pekerjaan == "Network Engineer") {
    $gaji = 22000000;
  } else if ($pekerjaan == "QA Engineer") {
    $gaji = 18000000;
  } else if ($pekerjaan == "DevOps Engineer") {
    $gaji = 23500000;
  } else {
    $gaji = 0;
  }

  $tanggal_lahir = new DateTime($_POST['tanggal_lahir']);

  $hari_ini = new DateTime('today');
  $tahun = $tanggal_lahir->diff($hari_ini)->y;
  $bulan = $tanggal_lahir->diff($hari_ini)->m;
  $hari = $tanggal_lahir->diff($hari_ini)->d;

  $umur = $tahun . " tahun " . $bulan . " bulan " . $hari . " hari ";
}




?>

<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Lab2Web</title>
  <style>
  body {
    background-color: whitesmoke;
  }

  .card {
    display: flex;
    justify-content: space-evenly;
    padding: 30px 80px;

  }

  .form {
    width: 400px;
    display: flex;
    flex-direction: column;
    gap: 14px;
    padding: 30px 20px;
    background-color: honeydew;

    border-radius: 4px;
    box-shadow: 2px 4px 4px 2px rgba(0, 0, 0, 0.5);
  }

  .data {
    font-size: 18px;
    font-family: "Fira Code";
    width: 400px;
  }

  .form-group {
    display: flex;
    flex-direction: column;
  }

  .form-group label,
  .form-group select>option {
    font-family: "Fira Code";
    font-size: 18px;
    margin-bottom: 8px;
  }

  .form-group input,
  .form-group select,
  button,
  h1 {
    padding: 8px 12px;
    font-family: "Fira Code";
  }

  button {
    background-color: black;
    color: white;
    cursor: pointer;
  }

  button:hover {
    background-color: black;
    color: white;
  }

  span {
    background: black;
    padding: 4px 8px;
    color: white;
  }
  </style>
</head>

<body>
  <div class="card">
    <form action="" class="form" method="post">
      <h1 style="text-align: center;"> Formulir Karyawan</h1>
      <div class="form-group">
        <label for="nama">Nama :</label>
        <input type="text" name="nama" id="nama" required>
      </div>
      <div class="form-group">
        <label for="tanggalahir">Tanggal Lahir :</label>
        <input type="date" name="tanggal_lahir" id="tanggalahir" required>
      </div>
      <div class="form-group">
        <label for="pekerjaan">Pekerjaan :</label>
        <select name="pekerjaan" id="pekerjaan" required>
          <option value="Software Engineer">Software Engineer</option>
          <option value="Network Engineer">Network Engineer</option>
          <option value="Data Analyst">Data Analyst</option>
          <option value="Design Graphic">Design Graphic</option>
          <option value="QA Engineer">QA Engineer</option>
          <option value="DevOps Engineer">DevOps Engineer</option>
        </select>
      </div>
      <div class="form-group">
        <button type="submit" name="submit" class="btn">Simpan</button>
      </div>
    </form>

    <div class="data">
      <h1>Data Karyawan</h1>
      <hr>
      <p>Nama : <span><?= $nama ?? "-"; ?> </span></p>
      <p>Pekerjaan : <span> <?= $pekerjaan ?? "-"; ?></span></p>
      <p>Gaji :<span> Rp. <?= number_format($gaji ?? 0, 0, "", ".") ?? "-"; ?> -;</span></p>
      <p>Umur : <span> <?= $umur ?? "-"; ?></span></p>
    </div>
  </div>
</body>

</html>
```

Hasil:

![Screenshot (166)](https://github.com/DimasAditya04/Lab2_Web/assets/130146099/8108b639-fde6-4a75-9817-42e5fdfae4c6)


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
