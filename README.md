# TUGAS PEMROGRAMAN WEB

Nama  : Dimas Aditya Putranto

Nim   : 312210489

Kelas : TI.22.A5

Mata Kuliah : Pemrograman Web

Dosen Pengampu : Agung Nugroho, S.Kom., M.Kom.

~ Tugas Pertama menggunakan PHP dasar


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
