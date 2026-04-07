# Laporan Praktikum Pemrograman Web 2 - Framework CodeIgniter 4 Praktikum 1-4
---  
## Nama: Althaf Afif Faiz
## NIM: 312410404
## Kelas: I241C
## Repositori: Lab7Web
---  
## Praktikum 1: Pengenalan Framework & Instalasi
Fokus: Menyiapkan lingkungan kerja CodeIgniter 4.  
Instalasi: Mengunduh CodeIgniter 4 melalui Composer atau manual download ke folder htdocs.  
Konfigurasi .env: Mengubah env menjadi .env, mengatur CI_ENVIRONMENT = development, dan menentukan app.baseURL.  
Struktur Folder: Memahami folder app (logika aplikasi), public (aset seperti CSS/JS), dan writable.  
Running: Menjalankan server lokal menggunakan perintah php spark serve.  

<img width="1255" height="1034" alt="image" src="https://github.com/user-attachments/assets/115f45e6-1db2-42cc-b808-a89114cd47e2" />

## 1. Fungsi cd (Change Directory)

Perintah cd adalah perintah dasar pada Terminal atau Command Prompt (CLI) yang berfungsi untuk berpindah antar folder.  

- cd htdocs: Berarti Anda memerintahkan komputer untuk masuk ke dalam folder htdocs (tempat penyimpanan proyek web di XAMPP).

- cd lab11_php_ci\ci4: Digunakan untuk masuk lebih dalam ke folder spesifik proyek Anda.Mengapa penting? Kita tidak bisa menjalankan perintah CodeIgniter (seperti 
php spark) jika posisi terminal Anda masih di luar folder proyek. Terminal harus berada tepat di mana file spark berada.

## 2. Fungsi php sparkphp 

Spark adalah Command Line Tool (asisten baris perintah) khusus milik CodeIgniter 4.   

Fungsinya adalah untuk mengotomatiskan tugas-tugas pengembangan agar Anda tidak perlu melakukannya secara manual.  

Berikut adalah kegunaan utamanya dalam praktikum :  
- Membuat File Otomatis (Generators):php spark make:seeder UserSeeder: Membuatkan kerangka file seeder tanpa Anda harus membuat file .php baru secara manual.  

- php spark make:cell ArtikelTerkini: Membuatkan komponen View Cell (Class dan View-nya) secara instan .  

- Menjalankan Server:php spark serve: Menjalankan server lokal agar website bisa diakses di localhost:8080.  

- Manajemen Database:php spark db:seed UserSeeder: Memasukkan data dummy (seperti akun admin) ke database secara otomatis.  

- Melihat Konfigurasi:php spark routes: Menampilkan semua daftar URL (rute) yang aktif untuk memastikan halaman admin atau login sudah terdaftar .

<img width="1919" height="1079" alt="langkah 2" src="https://github.com/user-attachments/assets/df38d840-9c0f-45d9-ae29-1eca14239fd6" />

### Fungsi: Jika tanda # dihapus, aplikasi akan masuk ke mode pengembangan. Dalam mode ini, CodeIgniter akan menampilkan pesan error yang detail jika ada kesalahan kode, sehingga memudahkan memperbaikinya.

## Tampilan Awal dari Web :

<img width="1919" height="1033" alt="aritkel awal" src="https://github.com/user-attachments/assets/f5fe1fed-7e65-4def-af71-fe8c925bf213" />

--- 
# Praktikum 2: Framework Lanjutan (CRUD)

### Deskripsi Proyek  

Praktikum ini berfokus pada pengembangan fitur pengelolaan artikel pada sisi Admin Portal Berita. Fitur utama yang diimplementasikan meliputi:

Upload Gambar: Mengintegrasikan file sistem untuk menyimpan foto artikel.

Manajemen Database: Menambahkan kolom gambar, katagori, dan created_at.

UI/UX Admin: Dashboard responsif dengan notifikasi sukses (auto-hide).

Dinamisasi Konten: Menampilkan kategori dan waktu posting secara real-time.

### Skema Database (Migration/SQL)

Gunakan perintah SQL berikut untuk menyiapkan tabel artikel agar mendukung semua fitur:

#### DataBase :
<img width="1609" height="563" alt="image" src="https://github.com/user-attachments/assets/b2a668ea-1011-4ac5-af16-b601419ee93f" />

#### Tampilan dari artikel yang sudah di buat di database :

<img width="1919" height="1033" alt="aritkel awal" src="https://github.com/user-attachments/assets/c5a495a9-e5e0-460a-8fd6-1b03375e2d0f" />

#### Menampilkan detail dari artikel :
<img width="1919" height="1023" alt="image" src="https://github.com/user-attachments/assets/7ff944c1-b2ac-4309-bb38-e27d773738da" />

### CRUD :

#### 1. Create (Tambah Data)
Fungsi ini dijalankan melalui menu "Tambah Artikel" di top bar.

Proses: Anda mengisi formulir yang berisi Judul, Isi Artikel, Kategori, dan mengunggah Gambar.

Hasil: Setelah menekan simpan, data baru akan masuk ke database dan muncul sebagai baris baru di tabel utama dengan ID otomatis.

#### 2. Read (Tampilkan Data)
Ini adalah fungsi yang sedang aktif di layar Anda (Halaman Index Admin).

Proses: Sistem mengambil seluruh data dari tabel artikel di database dan menampilkannya dalam bentuk tabel yang rapi.

Detail: Anda bisa melihat pratinjau judul, kategori (Umum), foto kecil, hingga waktu pembuatan artikel secara langsung tanpa harus membuka database manual.

#### 3. Update (Ubah Data)
Fungsi ini dijalankan melalui tombol "Ubah" berwarna Oranye.

Proses: Saat diklik, sistem akan mengambil data artikel tersebut (berdasarkan ID) dan menampilkannya kembali ke dalam formulir.

Hasil: Anda bisa mengganti judul yang salah, memperbarui isi berita, atau mengganti foto lama dengan yang baru. Setelah disimpan, perubahan tersebut akan langsung memperbarui data lama di database.

#### 4. Delete (Hapus Data)
Fungsi ini dijalankan melalui tombol "Hapus" berwarna Merah.

Proses: Saat diklik, muncul peringatan konfirmasi (confirm) untuk mencegah ketidaksengajaan. Jika Anda setuju, sistem akan menghapus baris data tersebut berdasarkan ID-nya.

Hasil: Artikel akan hilang selamanya dari database dan tidak akan muncul lagi di tabel admin maupun di halaman publik.

### Tampilan dari program CRUD :
<img width="1919" height="1028" alt="image" src="https://github.com/user-attachments/assets/6b447412-881c-466e-8086-e91a33e8c472" />

### Tambah Artikel :
<img width="1919" height="1026" alt="image" src="https://github.com/user-attachments/assets/08f15407-48dd-4f11-ae4e-76273a478ae9" />

### Melihat Artikel :

Dengan Memilih Artikel ini akan diarahkan ke Artikel Public
<img width="1912" height="790" alt="image" src="https://github.com/user-attachments/assets/65733a15-80bb-4f13-8ed0-870632641d8e" />

<img width="1919" height="1039" alt="image" src="https://github.com/user-attachments/assets/87ac3172-8b3d-489f-be3e-1373ec5e08e4" />

### Ubah Artikel :
<img width="1919" height="1032" alt="image" src="https://github.com/user-attachments/assets/d6321b21-5e37-4476-ab19-520b21be04e0" />

### Hapus Artikel :
<img width="1912" height="1031" alt="image" src="https://github.com/user-attachments/assets/adedd795-b507-4aab-ad4c-cad60ccac254" />

--- 

# Praktikum 3: View Layout dan View Cell

## Pertanyaan dan Tugas
1. Sesuaikan data dengan praktikum sebelumnya, perlu melakukan perubahan field pada 
database dengan menambahkan tanggal agar dapat mengambil data artikel terbaru.  
2. Selesaikan programnya sesuai Langkah-langkah yang ada. Anda boleh melakukan
improvisasi.  
3. Apa manfaat utama dari penggunaan View Layout dalam pengembangan aplikasi?  
4. Jelaskan perbedaan antara View Cell dan View biasa.  
5. Ubah View Cell agar hanya menampilkan post dengan kategori tertentu.  

### 1. Data Base menampilkan tanggal :
<img width="1617" height="511" alt="image" src="https://github.com/user-attachments/assets/6401d537-36aa-4dfc-84a7-11758de6c9c6" />

### 2. Menambahkan fitur seaech :

#### Pada Admin :

#### Pada Public :







