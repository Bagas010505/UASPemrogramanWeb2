# UASPemrogramanWeb2

![gambar](Screenshots/SS1.png)

# Halaman Login

File:

login.php

Halaman ini digunakan sebagai pintu masuk ke sistem.

Pengguna memasukkan:

Username
Password

Kemudian data login diproses oleh PHP.

Jika login berhasil, pengguna diarahkan ke:

dashboard.php

Pada project kamu, setelah login berhasil terlihat tulisan:

Selamat datang, admin

# Dashboard

File:

dashboard.php

Dashboard merupakan halaman utama setelah login.

Pada halaman ini data mahasiswa diambil dari database menggunakan SQL:

SELECT * FROM mahasiswa

Kemudian hasilnya ditampilkan dalam tabel:

No	NIM	Nama	Jurusan	Aksi
1	2026001	Bagas	Teknik Informatika	Hapus
2	2026002	Andi	Sistem Informasi	Hapus
3	2026003	Budi	Teknik Informatika	Hapus

Penjelasan:

"Dashboard digunakan untuk menampilkan data mahasiswa yang tersimpan di database. Data diambil menggunakan perintah SELECT kemudian ditampilkan dalam bentuk tabel HTML."

# Fitur Tambah Data

Pada dashboard terdapat tombol:

+ Tambah Data

Ketika tombol tersebut diklik, pengguna masuk ke:

tambah.php

Di sana terdapat form:

NIM
Nama
Jurusan

Misalnya saya memasukkan:

NIM      : 2026004
Nama     : Citra
Jurusan  : Teknik Informatika

Kemudian klik:

Simpan Data

PHP menjalankan perintah:

INSERT INTO mahasiswa
(nim, nama, jurusan)
VALUES
('2026004', 'Citra', 'Teknik Informatika')

Setelah berhasil, data Citra muncul di dashboard.

# Fitur Hapus Data

Di setiap baris terdapat tombol:

Hapus

Misalnya kita menghapus mahasiswa dengan id = 4.

PHP menjalankan:

DELETE FROM mahasiswa
WHERE id = 4

Setelah berhasil, data tersebut tidak lagi ditampilkan di dashboard.

Tadi kamu juga sudah melakukan pengujian ini. Data Citra yang sebelumnya muncul berhasil dihapus dan dashboard kembali menjadi 3 data. ✅

# Logout

Pada dashboard terdapat tombol:

Logout

Fungsinya menghapus session login.

Contohnya:

session_start();
session_destroy();


header("Location: login.php");
exit;

Setelah logout, pengguna kembali ke halaman login.

Penjelasan:

"Logout digunakan untuk mengakhiri session pengguna sehingga pengguna harus login kembali jika ingin masuk ke dashboard."
