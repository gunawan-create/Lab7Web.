## LAPORAN PRAKTIKUM 1 - 6
NAMA : ALI GUNAWAN | KELAS : I241C | NIM : 312410400

## Praktikum 1: PHP Framework (Codeigniter)
## Langkah-langkah Praktikum 1
### Step 1 | Mengaktifkan extention pada xampp
Sebelum anda memulai menggunakan Framework Codeigniter, anda perlu melakukan konfigurasi terlebih dahulu pada 
webserver. dan Untuk mengaktifkan ekstentionnya, anda perlu buka **XAMPP Control Panel**, lalu pada bagian Apache anda
klik Config -> **PHP.ini**

<img width="990" height="645" alt="Screenshot 2026-04-05 121041" src="https://github.com/user-attachments/assets/b9104c42-360e-4f73-ada4-fe40d1be71e6" />

Setelah anda masuk kebagian tab **php.ini**, ada Beberapa ekstensi PHP yang perlu anda aktifkan untuk kebutuhan pengembangan 
Codeigniter 4. 

Fitur:
- php-json ekstension untuk bekerja dengan **JSON;** 
- php-mysqlnd native driver untuk **MySQL;** 
- php-xml ekstension untuk bekerja dengan **XML;** 
- php-intl ekstensi untuk membuat aplikasi multibahasa; 
- libcurl (opsional), jika ingin pakai **Curl.**

<img width="1159" height="693" alt="Screenshot 2026-04-04 135305" src="https://github.com/user-attachments/assets/5f99a4f7-6f4e-460f-a1e4-cca7cf916768" />

Pada bagian extention, hilangkan tanda ; (titik koma) pada ekstensi yang akan diaktifkan. 
Kemudian simpan kembali filenya dan restart Apache web server.

### Step 2 | Installasi Codeigniter 4 pada web
Setelah anda mengaktifkan extentionnya, sekarang anda perlu melakukan installasi Codeigniter 4 dapat dilakukan dengan dua cara, yaitu cara manual dan menggunakan composer. Pada praktikum ini kita menggunakan cara manual. diantaranya

- Download Codeigniter 4 dari website **https://codeigniter.com/download**  
- Ekstra file zip ini Codeigniter ke direktori **htdocs/lab11_ci.** 
- setelah itu Ubah nama direktory **framework-4.x.xx** menjadi **ci4.** 
- kemudian buka xampp, pada tab apache anda klik start, setelahnya anda buka browser dengan alamat **http://localhost/lab11_ci/ci4/public/**

<img width="1919" height="1128" alt="Screenshot 2026-04-04 144708" src="https://github.com/user-attachments/assets/3c2eb1d5-b5f8-454d-87a4-ed8e18bb365f" />

### Step 3 | Menjalankan CLI (Command Line Interface) 
Setelah menginstall Codeigniter 4 , selanjutnya anda perlu mengkonfigurasi CLI pada terminal. Untuk mengakses 
CLI buka terminal/command prompt pada bagian xampp.

<img width="587" height="92" alt="image" src="https://github.com/user-attachments/assets/3bd7eb55-a5bb-4e75-b1a3-dc02f812ce54" />

Arahkan lokasi direktori pada **(xampp/htdocs/lab11_ci/ci4/)** yang sesuai dengan project anda buat tadi.

Perintah yang dapat dijalankan untuk memanggil CLI Codeigniter yakni **php spark**

<img width="1502" height="860" alt="Screenshot 2026-04-04 154639" src="https://github.com/user-attachments/assets/45b38f9e-9f69-4236-9459-6c99bcd06365" />

### Step 4 | Mengaktifkan Mode Debugging 
setelah menjalankan CLI pada terminal, anda dapat melakukan fitur mode debugging untuk memudahkan developer dan mengetahui pesan error apabila terjadi kesalahan dalam membuat kode program. 

<img width="1919" height="1129" alt="Screenshot 2026-04-04 144558" src="https://github.com/user-attachments/assets/8ffafdc8-cb90-4e6e-928f-2941d13fffcd" />

Secara default fitur ini masih belum aktif. Ketika terjadi error pada aplikasi akan ditampilkan pesan kesalahan seperti berikut. 

Semua jenis error akan ditampilkan sama. Untuk memudahkan mengetahui jenis errornya, maka perlu diaktifkan mode debugging dengan mengubah nilai konfigurasi pada environment variable **CI_ENVIRINMENT** menjadi **development.** 

<img width="444" height="179" alt="Screenshot 2026-04-04 145101" src="https://github.com/user-attachments/assets/9f8c6761-8c88-450b-9db4-60c1ec108aca" />

Setelah itu, Ubah nama file **env** menjadi **.env** kemudian buka file tersebut dan ubah nilai variable **CI_ENVIRINMENT** menjadi **development.** dan hasil tampilannya akan seperti ini.

<img width="1919" height="1127" alt="Screenshot 2026-04-04 144612" src="https://github.com/user-attachments/assets/3fa7d47f-50f0-4336-903d-07b1f0e06f47" />

Jika anda ingin mencoba error pada program, anda dapat mengubah kode pada file 
**app/Controller/Home.php** hilangkan titik koma pada akhir kode.

<img width="653" height="382" alt="Screenshot 2026-04-04 145038" src="https://github.com/user-attachments/assets/58414d36-dafa-4554-baeb-c1473b3fb7b2" />

Berikut beberapa struktur direktori CI4 dan file yang anda gunakan dalam program.

<img width="1132" height="620" alt="Screenshot 2026-04-04 153021" src="https://github.com/user-attachments/assets/4a2bcdc5-eac2-4d8d-89e7-468c1c26d52c" />

### Step 5 | Menentukan Routing dan Controller
Pada Codeigniter, request yang diterima oleh file index.php akan diarahkan ke Router untuk mengudikasikan oleh router tesebut yang diarahkan ke Controller.  
Router sendiri terletak pada file **app/config/Routes.php**

<img width="858" height="636" alt="Screenshot 2026-04-04 154133" src="https://github.com/user-attachments/assets/e59cb483-6e64-4283-8165-8d4269caf52c" />

Pada file ini kita dapat mendefinisikan route untuk aplikasi yang kita buat.
Misalnya;

<img width="413" height="50" alt="image" src="https://github.com/user-attachments/assets/d73b212d-3e46-4469-aefd-3c54fa4bc32f" />

Kode tersebut akan mengarahkan rute untuk halaman home. 

### Step 6 | Membuat Route Baru. 
Selanjutnya anda Tambahkan kode berikut di dalam Routes.php 

<img width="526" height="97" alt="image" src="https://github.com/user-attachments/assets/68a5c2ae-d30b-47e2-92d8-493d6a274380" />

Untuk mengetahui route yang ditambahkan sudah benar, buka CLI dan jalankan perintah berikut. 
**php spark routes** 

<img width="1449" height="567" alt="Screenshot 2026-04-04 155512" src="https://github.com/user-attachments/assets/e8836842-dc7d-46ad-9477-610770c881a1" />

Selanjutnya anda dapat mencoba akses route yang telah dibuat dengan mengakses alamat url **http://localhost:8080/about**

<img width="1919" height="1129" alt="Screenshot 2026-04-04 202009" src="https://github.com/user-attachments/assets/8782d930-1ceb-45d0-8670-05fabd92417c" />

Ketika diakses akan mucul tampilan error 404 file not found, itu artinya file/page tersebut tidak ada. Untuk dapat mengakses halaman tersebut, harus dibuat terlebih dahulu Contoller yang sesuai dengan routing yang dibuat yaitu Contoller Page. 

### Step 7 | Membuat Controller 
Kemudian membuat Controller Page. Buat file baru dengan nama **page.php** pada 
direktori Controller kemudian isi kodenya seperti berikut. 

<img width="978" height="686" alt="image" src="https://github.com/user-attachments/assets/9c49650e-1491-4b20-99ee-098b248fc063" />

Selanjutnya anda refresh Kembali browser, maka akan ditampilkan hasilnya yaotu halaman sudah dapat diakses. dan hasil tampilannya akan seperti ini.

<img width="1918" height="1128" alt="Screenshot 2026-04-04 202647" src="https://github.com/user-attachments/assets/b9987db4-25c2-4507-b9d3-fe8d9550bdd4" />

### Step 8 | mengubah status routing 
Secara default fitur autoroute pada Codeiginiter sudah aktif. Untuk mengubah status autoroute dapat mengubah nilai variabelnya. Untuk menonaktifkan ubah nilai **true** menjadi **false.**

<img width="378" height="63" alt="Screenshot 2026-04-04 203400" src="https://github.com/user-attachments/assets/3a660ad5-0786-4896-8b61-c6bdbfa5547d" />

lalu Tambahkan method baru pada Controller Page seperti berikut. 

<img width="526" height="144" alt="Screenshot 2026-04-04 203421" src="https://github.com/user-attachments/assets/2695f05c-6e32-48c7-b03f-5278a90028aa" />

Dalam Method ini belum ada pada routing, sehingga cara mengaksesnya dengan menggunakan alamat: **http://localhost:8080/page/tos**

<img width="1919" height="1126" alt="Screenshot 2026-04-04 203503" src="https://github.com/user-attachments/assets/55f7f292-fd06-4170-9e4a-c3ca2ceb1899" />

### Step 9 | Membuat View 
Selanjutnya membuat view pada tampilan web agar lebih menarik. Buat file baru dengan nama **about.php** pada direktori view **(app/view/about.php)** kemudian isi kodenya seperti berikut. 

<img width="855" height="404" alt="Screenshot 2026-04-04 204831" src="https://github.com/user-attachments/assets/46f344de-b1a2-46df-b50f-ab1e93a73bd8" />

Kemudian ubah method about pada class Controller Page menjadi seperti ini

<img width="1039" height="238" alt="Screenshot 2026-04-04 204904" src="https://github.com/user-attachments/assets/b0398894-08b8-493a-8831-9cbd8fdcc3d5" />

Setelah itu refresh kembali pada halaman tersebut.

<img width="1919" height="1126" alt="Screenshot 2026-04-04 204728" src="https://github.com/user-attachments/assets/1f23d8fe-0b3b-4298-9f04-15651ad834c5" />

### Step 10 | Membuat Layout Web dengan CSS
Buat file css pada direktori public dengan nama style.css (copy file dari praktikum **lab4_layout.** Kita akan gunakan layout yang pernah dibuat pada **praktikum 4.**

<img width="540" height="291" alt="Screenshot 2026-04-04 205402" src="https://github.com/user-attachments/assets/3bc78115-35aa-4f76-9b9f-3fb42f94abfb" />

Kemudian buat folder template pada direktori view kemudian buat file **header.php** dan **footer.php**  
file **app/view/template/header.php**

<img width="893" height="608" alt="image" src="https://github.com/user-attachments/assets/c77ffc29-4db6-4a18-9747-2ff8358b5e74" />

file **app/view/template/footer.php**

<img width="1178" height="698" alt="image" src="https://github.com/user-attachments/assets/5f22f44c-6f9a-42e0-bde0-d23c145b41db" />
 
Kemudian ubah file app/view/about.php seperti berikut.

<img width="661" height="238" alt="image" src="https://github.com/user-attachments/assets/3791bad2-be59-4dd0-86ea-d71144f1ede5" />

 
Selanjutnya refresh tampilan pada halaman **http://localhost:8080/about**

<img width="1289" height="712" alt="Screenshot 2026-04-04 210931" src="https://github.com/user-attachments/assets/8479f1ea-1c2a-4369-b941-c06b2bc2048c" />

## Pertanyaan dan Tugas
Melengkapi kode program untuk menu lainnya yang ada pada Controller Page, sehingga semua
link pada navigasi header dapat menampilkan tampilan dengan layout yang sama.

### Langkah 1 | Menambahkan direktori views pada file about
Membuat file artikel.php seperti yang ada pada navigasi di direktori views. lalu di isi dengan kode yang sama seperti di file about.php.
```php
<?= $this->include('template/header'); ?>

<h1><?= $title; ?></h1>
<hr>
<p><?= $content; ?></p>

<?= $this->include('template/footer');
```

### Langkah 2 | Membuat direktori views pada file page
Kemudian menambahkan kode seperti dibawah pada file page.php:
```php
public function artikel()
    {
        return view('artikel', [
            'title'   => 'Halaman Artikel',
            'content' => 'Ini halaman artikel.'
        ]);
    }
```

### Langkah 3 | Menambahkan route pada halaman artikel
Kemudian tambahkan routes untuk artikel di dihalaman Routes.php.
```php
<?php

use CodeIgniter\Router\RouteCollection;

/**
 * @var RouteCollection $routes
 */
$routes->get('/', 'Home::index');
$routes->get('/artikel', 'Page::artikel');
$routes->get('/about', 'Page::about');
$routes->get('/contact', 'Page::contact');
```
Setelah menambahkan route untuk bagian artikel dan navigasi lainnya agar navigasinya ketika diklik akan terarah ke halaman artikel. maka jalankan perintah php spark serve di shell xampp.

<img width="959" height="563" alt="image" src="https://github.com/user-attachments/assets/e2a07488-dcd0-4bdd-824b-f72bafe9a0c9" />

Kemudian Hasil tampilan websitenya akan muncul seperti gambar dibawah ini.

### Tampilan About

<img width="956" height="563" alt="Screenshot 2026-06-12 185140" src="https://github.com/user-attachments/assets/a5e63a77-2078-4145-af10-59e484d3e30b" />

### Tampilan Contact

<img width="959" height="563" alt="Screenshot 2026-06-12 185745" src="https://github.com/user-attachments/assets/79f5b461-db8b-4401-87ca-998f5ff07b30" />

### Tampilan Artikel

<img width="959" height="565" alt="Screenshot 2026-06-12 185756" src="https://github.com/user-attachments/assets/83cbec31-7d7f-4fcd-935f-58cf6680beef" />


## Praktikum 2: Framework Lanjutan (CRUD) 
## Langkah-langkah Praktikum 2
### Step 1 | Membuat Database
Buka CLI atau terminal,Setelah itu membuat database dengan nama **labci4**

<img width="628" height="186" alt="Screenshot 2026-04-05 204843" src="https://github.com/user-attachments/assets/69accb6e-c4b5-44fc-9167-967dff7584b3" />

### Step 2 | Membuat Tabel

<img width="617" height="295" alt="Screenshot 2026-04-05 205024" src="https://github.com/user-attachments/assets/3a63506b-c19b-4451-8d39-88dd42399fc7" />

### Step 3 | Mengkonfigurasi koneksi pada database 
Selanjutnya membuat konfigurasi untuk menghubungkan dengan database server. Konfigurasi dapat dilakukan dengan dua acara, yaitu pada file **app/config/database.php** atau menggunakan **file .env.** Pada praktikum ini kita gunakan konfigurasi pada **file .env.**

<img width="561" height="345" alt="Screenshot 2026-04-05 232705" src="https://github.com/user-attachments/assets/30777e4e-efe2-447b-a78c-b242775f91c0" />

### Step 4 | Membuat Model 
Kemudian membuat Model untuk memproses data Artikel. Buat file baru pada direktori**app/Models** dengan nama **ArtikelModel.php**

<img width="902" height="471" alt="Screenshot 2026-04-05 233056" src="https://github.com/user-attachments/assets/87114b4c-e07b-472d-a8e0-e1a8015637fb" />

### Step 5 | Membuat Controller 
Menambahkan Controller baru dengan nama **Artikel.php** pada direktori **app/Controllers.**

<img width="943" height="495" alt="Screenshot 2026-04-05 233252" src="https://github.com/user-attachments/assets/56f9d5b4-dc59-48ed-9723-22646853fbbf" />

### Step 6 | Membuat View 
Setelah itu membuat direktori baru dengan nama **artikel** pada direktori **app/views**, kemudian buat file baru 
dengan nama **index.php.**

<img width="997" height="595" alt="Screenshot 2026-04-05 233449" src="https://github.com/user-attachments/assets/f2c7af0f-13c1-4574-b7f4-b2323ebbf48e" />

Selanjutnya buka browser kembali, dengan mengakses url **http://localhost:8080/artikel**

<img width="1919" height="1128" alt="Screenshot 2026-04-05 235747" src="https://github.com/user-attachments/assets/098a0b7a-70a4-420e-a5b8-dd3ed2ef89a6" />

Hasinya Belum ada data yang ditampilkan. Kemudian coba anda tambahkan beberapa data pada database agar dapat ditampilkan datanya. 

<img width="1101" height="275" alt="image" src="https://github.com/user-attachments/assets/1b556271-933b-476c-b36a-f24ead9e6cb4" />
 
Refresh kembali browser, sehingga akan ditampilkan hasilnya.

<img width="1919" height="1127" alt="Screenshot 2026-04-06 002718" src="https://github.com/user-attachments/assets/aecfbf73-524b-455b-b309-8db0d505b04c" />

### Step 7 | Membuat Tampilan Detail Artikel 
Menampilkan pada saat judul berita, maka akan diarahkan ke halaman yang berbeda. kemudian Tambahkan fungsi baru pada **Controller Artikel** dengan nama **view().** 

<img width="891" height="449" alt="image" src="https://github.com/user-attachments/assets/e175bf85-b649-4848-aafe-7f241afeb6ba" />

### Step 8 | Menambahkan View Detail 
Buat view baru untuk halaman detail dengan nama **app/views/artikel/detail.php.**

<img width="848" height="261" alt="image" src="https://github.com/user-attachments/assets/b51b9ec2-87aa-4938-8888-026cb953b381" />

### Step 9 | Membuat Routing untuk artikel detail 
Buka Kembali file **app/config/Routes.php**, kemudian tambahkan routing untuk artikel detail. 

<img width="632" height="63" alt="Screenshot 2026-04-06 003557" src="https://github.com/user-attachments/assets/8d18336b-acd0-4ab1-8fff-627afe65ec32" />

**Hasil Tampilannya**

<img width="1919" height="1129" alt="Screenshot 2026-04-07 162339" src="https://github.com/user-attachments/assets/004aa9b2-de4e-42fd-b1df-0bc52ffd8bd7" />

### Step 10 | Membuat Menu Admin 
Menu admin adalah untuk proses CRUD data artikel. Buat method baru pada Controller 
Artikel dengan nama **admin_index().**

<img width="770" height="225" alt="image" src="https://github.com/user-attachments/assets/6939dcdc-afa3-4b76-89c6-903a622e8eb7" />

Selanjutnya buat view untuk tampilan admin dengan nama **admin_index.php**

<img width="923" height="613" alt="image" src="https://github.com/user-attachments/assets/650eda95-4cae-4b31-947f-94de7bff5f9d" />

<img width="938" height="703" alt="image" src="https://github.com/user-attachments/assets/a233a243-90bd-470b-930b-34201202220c" />

Tambahkan routing untuk menu admin seperti berikut: 

<img width="665" height="184" alt="Screenshot 2026-04-07 163127" src="https://github.com/user-attachments/assets/08997cbc-90b1-465e-9289-dacdfa6c21c0" />

Akses menu admin dengan url **http://localhost:8080/admin/artikel**

<img width="1919" height="1128" alt="Screenshot 2026-04-07 183548" src="https://github.com/user-attachments/assets/5a024c55-b532-4646-a5be-0373df61d08a" />

### Step 11 | Menambah Data Artikel 
Tambahkan fungsi/method baru pada **Controller Artikel** dengan nama **add().**

<img width="894" height="585" alt="image" src="https://github.com/user-attachments/assets/ef5e9e8e-e451-4d13-a132-93de9d55c6cf" />

Kemudian buat view untuk form tambah dengan nama **form_add.php**

<img width="841" height="422" alt="image" src="https://github.com/user-attachments/assets/5561d97d-26f0-423c-a073-475c8f5557f1" />

**Hasil Tampilan**

<img width="1919" height="1131" alt="Screenshot 2026-04-07 201218" src="https://github.com/user-attachments/assets/7fbc0747-8d30-4146-8452-077618221a17" />

### Step 12 | Mengubah Data 
Tambahkan fungsi/method baru pada **Controller Artikel** dengan nama **edit().**

<img width="1047" height="646" alt="image" src="https://github.com/user-attachments/assets/c62cfdcc-49a5-4074-a862-093e9f5320df" />

Kemudian buat view untuk form tambah dengan nama form_edit.php 

<img width="882" height="458" alt="image" src="https://github.com/user-attachments/assets/f426a513-d991-440d-a96f-105fef58653a" />

**Hasil Tampilan**

<img width="1918" height="1128" alt="Screenshot 2026-04-07 233901" src="https://github.com/user-attachments/assets/5c4426b2-a643-4945-934b-69fd42295931" />

### Step 13 | Menghapus Data 
Tambahkan fungsi/method baru pada Controller Artikel dengan nama delete().  

<img width="546" height="208" alt="image" src="https://github.com/user-attachments/assets/1de21efb-5ddc-4cf4-8162-a9e77a8a4910" />

## Pertanyaan dan Tugas
Selesaikan programnya sesuai Langkah-langkah yang ada. Anda boleh melakukan improvisasi.

### Langkah 1 | Menambahkan kolom pencarian
```php
<form method="get">
    <input type="text" name="keyword" placeholder="Cari artikel">
    <button type="submit">Cari</button>
</form>
```
Kode ini untuk membuat kolom pencarian agar artikel yang telah dibuat dapat dicari dengan cepat.

Hasil Tampilan;
<img width="565" height="280" alt="image" src="https://github.com/user-attachments/assets/f57eee42-9d7f-4052-b2c9-174c016c7d22" />

### Langkah 2 | Menambahkan pagination

```php
<?= $pager->links(); ?>
```
Kode ini untuk membuat setiap page agar artikel dapat tersusun rapih.

Hasil Tampilan;
<img width="959" height="563" alt="Screenshot 2026-06-12 223645" src="https://github.com/user-attachments/assets/22de6fa2-fba4-4fd6-9d6d-59db6b5e558e" />

### Langkah 3 | Tampilan button kembali pada halaman edit artikel

<img width="959" height="565" alt="Screenshot 2026-06-12 222513" src="https://github.com/user-attachments/assets/52b6f112-1724-4c08-a919-3eb34b205c66" />

### Langkah 4 | Tampilan button kembali pada halaman tambah artikel

<img width="959" height="563" alt="Screenshot 2026-06-12 222601" src="https://github.com/user-attachments/assets/dac43351-2d8a-4b5c-b8d2-502a752a3fba" />

## Praktikum 3: View Layout dan View Cell 
## Langkah-langkah Praktikum 3
### Step 1 | Membuat Layout Utama 
Membuat folder layout pada **app/Views/** lalu Buat file **main.php** di dalam folder layout dengan kode berikut 

<img width="1057" height="894" alt="image" src="https://github.com/user-attachments/assets/39511b90-2ed9-4339-ae89-efccce4bcb95" />

<img width="971" height="501" alt="image" src="https://github.com/user-attachments/assets/7d74219e-2e65-4521-a773-9eb195a0a170" />

**Hasil Tampilan**

<img width="1919" height="1126" alt="Screenshot 2026-04-08 225800" src="https://github.com/user-attachments/assets/a06a52bc-3ddc-4890-9161-edfd8367de47" />

### Step 2 | Modifikasi File View 
Mengubah **app/Views/home.php** agar sesuai dengan layout baru: 

<img width="548" height="281" alt="image" src="https://github.com/user-attachments/assets/2e0994ae-6090-4965-853e-09295f82f226" />

### Step 3 | Membuat Class View Cell 
Membuat folder **Cells** di dalam app/ dan membuat file **ArtikelTerkini.php** di dalam **app/Cells/** dengan kode berikut,

<img width="909" height="509" alt="image" src="https://github.com/user-attachments/assets/2a133286-5836-4f83-a2ed-2264d5037738" />

### Step 4 | Membuat View untuk View Cell 
Membuat folder **components** di dalam **app/Views/** dan Membuat file **artikel_terkini.php** di dalam **app/Views/components/** dengan kode berikut:

<img width="867" height="234" alt="image" src="https://github.com/user-attachments/assets/20475a34-2a83-46d0-80f7-efd6abce7663" />

## Pertanyaan dan tugas
Sesuaikan data dengan praktikum sebelumnya, perlu melakukan perubahan field pada
database dengan menambahkan tanggal agar dapat mengambil data artikel terbaru.

### Langkah 1 | Menambahkan tanggal pada file artikel
```php
$artikel = $model
        ->orderBy('tanggal', 'DESC')
        ->limit(5)
        ->findAll();
```
Kode ini berfungsi untuk mengurutkan data berdasarkan tanggal terbaru dan membatasi jumlah data yang ditampilkan. Dan menambahkan kolom tanggal pada tabel database.

### Langkah 2 | Tampilan data tanggal artikel pada xampp

<img width="767" height="111" alt="image" src="https://github.com/user-attachments/assets/6f0b2fca-3b5e-482e-bdfa-2609819ed903" />

Pada gambar diatas data artikel berurutan sesuai dengan tanggal dimana artikel tersebut sesuai dengan tanggal terbaru. Selesaikan programnya sesuai Langkah-langkah yang ada. Kita boleh melakukan improvisasi, sebagai berikut.

### Soal 1 
Apa manfaat utama dari penggunaan View Layout dalam pengembangan aplikasi?
```
1. Meningkatkan pengalaman UI/UX.
2. Struktur yang rapih.
3. Tampilan menjadi lebih efisien.
4. Membantu aplikasi lebih responsif.
```

### Soal 2 
Jelaskan perbedaan antara View Cell dan View biasa.
Perbedaan antara view cell dan View biasa adalah kalau View biasa itu ketika dipanggil harus melalui controller dan tidak fleksibel ketika dipakai dibanyak halaman. sedangkan View Cell ini tanpa memerlukan Controller yang banyak, fleksibel, dan bisa dipakai berulang.

### Soal 3
Ubah View Cell agar hanya menampilkan post dengan kategori tertentu.
```php
<?php

namespace App\Cells;

use App\Models\ArtikelModel;

class ArtikelTerkini 
{
    public function index()
    {
        $model = new ArtikelModel();

        $data = $model
            ->where('kategori IS NOT NULL')
            ->where('kategori !=', '')
            ->orderBy('tanggal', 'DESC')
            ->findAll();
        $grouped = [];

        foreach ($data as $row) {
            $kategori = $row['kategori'] ?? 'Lainnya';
            $grouped[$kategori][] = $row;
        }

        return view('components/artikel_terkini', [
            'grouped' => $grouped
        ]);
    }
}
```
Dari kode diatas berfungsi untuk memfilter artikel berdasarkan kategori tertentu. Data yang diambil akan ditampilkan pada View Cell.

### Soal 4
Mengubah tampilan view/artikel_terkini.php agar tampil perkategori.
```php
<div class="widget-box">
    <h3 class="title">Artikel Terkini</h3>

    <?php foreach ($grouped as $kategori => $items): ?>
        
        <h4><?= $kategori ?></h4>
        <ul>
            <?php foreach ($items as $row): ?>
                <li>
                    <a href="<?= base_url('/artikel/' . $row['slug']) ?>">
                        <?= $row['judul'] ?>
                    </a>
                </li>
            <?php endforeach; ?>
        </ul>

    <?php endforeach; ?>
</div>
```

Hasil Tampilannya;

<img width="959" height="565" alt="Screenshot 2026-06-13 152330" src="https://github.com/user-attachments/assets/81d1a825-2f5c-47d7-9cab-40446cf06822" />

## Praktikum 4: View Layout dan View Cell 
## Langkah-langkah Praktikum 4
### Step 1 | Membuat Tabel User

<img width="625" height="250" alt="Screenshot 2026-04-09 094434" src="https://github.com/user-attachments/assets/144b5d7a-5516-43f0-818c-b3b2797f6642" />

### Step 2 | Membuat Model User 
Selanjutnya anda buat **Model** untuk memproses data Login. Buat file baru pada direktori 
**app/Models** dengan nama **UserModel.php** 

<img width="905" height="331" alt="image" src="https://github.com/user-attachments/assets/98fff3b6-b5bd-4029-8be9-8176dfef8a48" />

### Step 3 | Membuat Controller User 
Selanjutnya Buat Controllers baru dengan nama **User.php** pada direktori **app/Controllers.** Kemudian 
tambahkan method **index()** untuk menampilkan daftar user, dan **method login()** untuk proses 
login. 

<img width="966" height="702" alt="image" src="https://github.com/user-attachments/assets/609686e9-3ddc-4722-8086-fe04e3388d0d" />

<img width="862" height="517" alt="image" src="https://github.com/user-attachments/assets/9f0c598c-d4e4-47f6-bb02-3d05123aa6cd" />

<img width="902" height="421" alt="image" src="https://github.com/user-attachments/assets/0ea7da2d-dd69-466d-aa1d-c826e3694b0c" />

### Step 4 | Membuat View Login 
Buat direktori baru dengan nama user pada direktori **app/views,** kemudian buat file baru 
dengan nama **login.php.** 

<img width="1107" height="952" alt="image" src="https://github.com/user-attachments/assets/2cf4e03a-5ab3-4228-bf80-b507e555bb74" />

### Step 5 | Menambahkan Database Seeder 
Untuk keperluan ujicoba modul login, kita perlu memasukkan data user dan password kedaalam database. Untuk itu buat 
database seeder untuk tabel user. Buka CLI, kemudian tulis perintah berikut: 

<img width="899" height="75" alt="Screenshot 2026-04-09 095406" src="https://github.com/user-attachments/assets/4912602f-751f-4820-bf05-67262e5966e1" />

Selanjutnya, buka file **UserSeeder.php** yang berada di lokasi direktori 
**/app/Database/Seeds/UserSeeder.php** kemudian isi dengan kode berikut,

<img width="907" height="553" alt="image" src="https://github.com/user-attachments/assets/811fef60-f6ab-4710-8015-e20b78b49b77" />

Selanjutnya buka kembali CLI dan ketik perintah berikut: 

<img width="927" height="90" alt="Screenshot 2026-04-09 095432" src="https://github.com/user-attachments/assets/19839407-cd70-4e73-8679-ddde9526edba" />

### Step 6 | Uji Coba Login 
Selanjutnya buka url **http://localhost:8080/user/login** seperti berikut: 

<img width="1919" height="1127" alt="Screenshot 2026-04-09 100934" src="https://github.com/user-attachments/assets/e8f32c75-c5a2-4f2a-9b75-bfc6961e476a" />

### Step 7 | Menambahkan Auth Filter 
Selanjutnya membuat filer untuk halaman admin. Buat file baru dengan nama **Auth.php** pada 
direktori **app/Filters.**

<img width="889" height="621" alt="image" src="https://github.com/user-attachments/assets/20f0ab2e-d6ba-458a-9eee-2337d75c54f3" />

Selanjutnya buka file **app/Config/Filters.php** tambahkan kode berikut:

<img width="452" height="50" alt="image" src="https://github.com/user-attachments/assets/484a091f-59ad-4410-aa53-cd481e641bd1" />

Seperti ini bentukannya;

<img width="603" height="257" alt="image" src="https://github.com/user-attachments/assets/dffbb0c0-1a3f-4576-bcb2-f5b3b50a325a" />

Setelah itu anda buka file **app/Config/Routes.php** dan sesuaikan kodenya.

<img width="804" height="239" alt="image" src="https://github.com/user-attachments/assets/970234c4-c540-4030-8d5a-3efa998e41a2" />

### Step 8 | Percobaan Akses Menu Admin 
Buka url dengan alamat **http://localhost:8080/admin/artikel** ketika alamat tersebut diakses 
maka, akan dimuculkan halaman login.

<img width="1919" height="1125" alt="image" src="https://github.com/user-attachments/assets/8f2f9430-f15f-42a2-ad42-af166f2d2fad" />

### Step 9 | Menambahkan Fungsi Logout 
Tambahkan method logout pada Controller User seperti berikut:

<img width="606" height="202" alt="image" src="https://github.com/user-attachments/assets/1faf3588-5dae-4421-ba42-158892edcf48" />

## Praktikum 5: Pagination dan Pencarian 
## Langkah-langkah Praktikum 5
### Step 1 | Membuat Pagination 
Untuk membuat pagination, buka Kembali Controller Artikel, kemudian modifikasi kode 
pada method **admin_index** seperti berikut.

<img width="705" height="335" alt="image" src="https://github.com/user-attachments/assets/a2276abd-6837-47dd-9186-92526aee0c8f" />

Kemudian buka file **views/artikel/admin_index.php** dan tambahkan kode berikut 
dibawah deklarasi tabel data. 

<img width="283" height="51" alt="image" src="https://github.com/user-attachments/assets/946c8ec4-a1cd-4d95-904e-8da8772487d7" />

Selanjutnya buka kembali menu daftar artikel, tambahkan data lagi untuk melihat 
hasilnya.

<img width="1919" height="1125" alt="Screenshot 2026-04-15 140429" src="https://github.com/user-attachments/assets/e31894bc-1ebd-4674-8b39-b0fa6c58311d" />

### Step 2 | Membuat Pencarian 
Untuk membuat pencarian data, buka kembali **Controller Artikel**, pada method 
**admin_index** ubah kodenya seperti berikut,

<img width="777" height="393" alt="image" src="https://github.com/user-attachments/assets/566af78d-eccd-4f0b-b05a-446c1e47780b" />

Kemudian buka kembali file **views/artikel/admin_index.php** dan tambahkan form 
pencarian sebelum deklarasi tabel seperti berikut,

<img width="950" height="143" alt="image" src="https://github.com/user-attachments/assets/33b7badc-f0de-44dc-809d-1fec8b507459" />

Dan pada link pager ubah seperti ini

<img width="466" height="63" alt="image" src="https://github.com/user-attachments/assets/f369e8fc-eff4-4edb-b8d5-37de4eb4b663" />

Selanjutnya ujicoba dengan membuka kembali halaman admin artikel, masukkan kata 
kunci tertentu pada form pencarian.

<img width="1919" height="1022" alt="Screenshot 2026-04-14 130953" src="https://github.com/user-attachments/assets/ebfb3c94-2207-42aa-b9e4-5659f0df0730" />

## Praktikum 6: Pagination dan Pencarian 
## Langkah-langkah Praktikum 6
### Step 1 |  Membuat Tabel Kategori 
Pada praktikum ini, Kita akan membuat tabel baru bernama **`kategori`** untuk mengkategorikan artikel.

<img width="681" height="225" alt="Screenshot 2026-04-15 141625" src="https://github.com/user-attachments/assets/3c6b1396-b384-4b8f-ab0e-80e41f11ae9a" />

### Step 2 |  Mengubah Tabel Artikel 
Untuk menambahkan foreign key **`id_kategori`** pada tabel **`artikel`**, anda bisa membuat relasi dengan tabel **`kategori`**.  

<img width="1020" height="261" alt="Screenshot 2026-04-15 142357" src="https://github.com/user-attachments/assets/885fde57-6826-4a25-9885-0ef4d5aafa95" />

### Step 3 | Membuat Model Kategori 
Buat file model baru di **`app/Models`** dengan nama **`KategoriModel.php`**, 

<img width="901" height="433" alt="Screenshot 2026-04-15 143512" src="https://github.com/user-attachments/assets/6eeaa4ff-f3dd-41d2-9397-bbe89ef49c92" />

### Step 4 | Memodifikasi Model Artikel 
Modifikasi `ArtikelModel.php` untuk mendefinisikan relasi dengan `KategoriModel`

<img width="1202" height="669" alt="Screenshot 2026-04-15 144332" src="https://github.com/user-attachments/assets/d1a4c844-1b96-44cb-b6fa-c9c7d7eb8034" />

### Step 5 | Memodifikasi Controller Artikel 
Modifikasi `Artikel.php` untuk menggunakan model baru dan menampilkan data relasi:

<img width="1073" height="654" alt="image" src="https://github.com/user-attachments/assets/98656e70-990b-4713-88e2-d4013debe816" />

<img width="1137" height="918" alt="image" src="https://github.com/user-attachments/assets/135b6839-98dc-4aac-9c6c-0e7b73108c8c" />

<img width="1033" height="768" alt="image" src="https://github.com/user-attachments/assets/26d0d403-dad8-4c91-91bd-8a1a34ce1b9f" />

<img width="1044" height="820" alt="image" src="https://github.com/user-attachments/assets/b90afd34-8c16-45c5-8f49-320c7f6dc473" />

<img width="1162" height="422" alt="image" src="https://github.com/user-attachments/assets/3ea79a7c-77c8-464f-b478-dd8a39cb1d3d" />

### Step 6 | Memodifikasi View 
Menyesuaikan floder view/artikel untuk masing-masing view di index.php:

<img width="935" height="565" alt="image" src="https://github.com/user-attachments/assets/b375690b-fd5c-431e-9421-4fcff9ce111c" />

**admin_index.php**

<img width="1306" height="925" alt="image" src="https://github.com/user-attachments/assets/e576a0c6-ae0b-46b4-8394-90a1811f2856" />

<img width="1286" height="747" alt="image" src="https://github.com/user-attachments/assets/d391a5b0-6acf-4fff-8a03-cd009bc44b11" />

<img width="1242" height="115" alt="image" src="https://github.com/user-attachments/assets/d61dd686-2ae5-48e0-8f42-02b4220c5e37" />

**form_add.php**

<img width="1148" height="742" alt="image" src="https://github.com/user-attachments/assets/70a70819-c707-4dbe-9a40-8cffa7d85402" />

**form_edit.php**

<img width="1188" height="848" alt="image" src="https://github.com/user-attachments/assets/089da809-6ad0-4867-97ce-058f22769ad1" />

Menampilkan daftar artikel dengan nama kategori

<img width="1919" height="1127" alt="Screenshot 2026-04-17 095856" src="https://github.com/user-attachments/assets/092472e9-24c9-48cd-a6f1-f2a920915a13" />

### Step 7 | Testing
Menampilkan daftar artikel dengan nama kategori.

<img width="959" height="565" alt="Screenshot 2026-06-13 201941" src="https://github.com/user-attachments/assets/c06b6637-279b-4615-a71d-3aad1eb6f08f" />

Menampilan tambah artikel baru dengan memilih kategorinya

<img width="959" height="563" alt="Screenshot 2026-06-13 202048" src="https://github.com/user-attachments/assets/ee56c16f-2fb9-49a5-b63e-4a4b55554b50" />

<img width="959" height="566" alt="Screenshot 2026-06-13 202122" src="https://github.com/user-attachments/assets/cd14b1bc-ba39-4ce2-b01f-4b48e40fc40a" />

Menampilan edit artikel dan bisa mengubah kategori sesuai artikel yang dibuat.

<img width="959" height="563" alt="Screenshot 2026-06-13 202212" src="https://github.com/user-attachments/assets/242db811-b65b-4e3c-a1ab-cb6874685ac0" />

<img width="959" height="562" alt="Screenshot 2026-06-13 202407" src="https://github.com/user-attachments/assets/4b81701a-35e8-4cc7-8e0e-6c0d0c8aa9d3" />

Menghapus artikel
Sebelum :

<img width="959" height="566" alt="Screenshot 2026-06-13 202122" src="https://github.com/user-attachments/assets/2a5f168f-9dd8-4619-a70f-99bd66cdb066" />

Sesudah :

<img width="959" height="562" alt="Screenshot 2026-06-13 202116" src="https://github.com/user-attachments/assets/7e97184f-11a7-4226-9858-f5b402911b1b" />

## Pertanyaan dan Tugas
### Langkah 1 | Memperbarui tampilan detail artikel dengan kategori 
Modifikasi tampilan detail artikel (artikel/detail.php) untuk menampilkan nama kategori
artikel.
```php
<?= $this->include('template/header'); ?>

<article class="entry">
    <h2><?= $artikel['judul']; ?></h2>

    <p><b>Kategori:</b> <?= $artikel['nama_kategori']; ?></p>

    <img src="<?= base_url('/gambar/' . $artikel['gambar']); ?>" 
         alt="<?= $artikel['judul']; ?>">

    <p><?= $artikel['isi']; ?></p>
</article>

<?= $this->include('template/footer'); ?>
```

Hasil Tampilannya;

<img width="959" height="563" alt="Screenshot 2026-06-13 203546" src="https://github.com/user-attachments/assets/f11c8f02-174c-42ab-8b03-ef29edbd3a83" />

### Langkah 2 | Menambahkan tampilan daftar header kategori dihalaman utama user
setelah itu, Tambahkan fitur untuk menampilkan daftar kategori di halaman utama
```php
<?= $this->include('template/header'); ?>

<?php if ($artikel): foreach ($artikel as $row): ?>
    <article class="entry">
            <h2><a href="<?= base_url('/artikel/' . $row['slug']); ?>"><?=
$row['judul']; ?></a></h2>
        <p>Kategori: <?= $row['nama_kategori'] ?></p>
         <img src="<?= base_url('/gambar/' . $row['gambar']); ?>" alt="<?=
$row['judul']; ?>">
        <p><?= substr($row['isi'], 0, 200); ?></p>
    </article>
    <hr class="divider" />
<?php endforeach; else: ?>
    <article class="entry">
        <h2>Belum ada data.</h2>
    </article>
<?php endif; ?>

<?= $this->include('template/footer'); ?>
```

Hasil Tampilannya;

<img width="959" height="563" alt="Screenshot 2026-06-13 204312" src="https://github.com/user-attachments/assets/9378c2ad-d8f3-4a1e-aa84-5d4edeaa5c1f" />

### Langkah 3 | menampilkan fungsi artikel berdasarkan kategori tertentu.

<img width="848" height="391" alt="Screenshot 2026-06-13 204519" src="https://github.com/user-attachments/assets/ba21cf1d-eb01-47dc-89bb-481d2ac740b6" />

## Praktikum 7: Upload File Gambar
## Langkah-langkah Praktikum 7
### Step 1 |  Mengupload gambar pada artikel 
Selanjutnya, menambahkan fungsi unggah pada **controller** di **method add**:
```php
public function add()
    {
        // Validation...
        $validation = \Config\Services::validation();
        $validation->setRules(['judul' => 'required']);
        $isDataValid = $validation->withRequest($this->request)->run();
        if ($this->request->getMethod() == 'post' && $this->validate([
            'judul' => 'required',
               'id_kategori' => 'required|integer' // Ensure id_kategori is required and an integer
        ])) {
            $file = $this->request->getFile('gambar');
            $file->move(ROOTPATH . 'public/gambar');
            $model = new ArtikelModel();
            $model->insert([
                'judul' => $this->request->getPost('judul'),
                'isi' => $this->request->getPost('isi'),
                'slug' => url_title($this->request->getPost('judul')),
                'id_kategori' => $this->request->getPost('id_kategori'),
                'gambar' => $file->getName(),
            ]);
            return redirect()->to('/admin/artikel');
        } else {
            $kategoriModel = new KategoriModel();
            $data['kategori'] = $kategoriModel->findAll(); 
            $data['title'] = "Tambah Artikel";
            return view('artikel/form_add', $data);
        }
    }
```
Method yang sudah digunakan guna menambahkan gambar artikel berita.

Menambahkan kode tombol input gambar pada  **views/artikel/form_add.php:**
```php
<p>
 <input type="file" name="gambar">
</p>
```
Lalu menyesuaikan tag form dengan menambahkan **ecrypt type:**
```php
<form action="" method="post" enctype="multipart/form-data">
```
Kode tersebut ditambahkan agar fungsi input gambar dapat bekerja dengan baik.
Kemudian uji coba upload gambar pada tambah artikel.

<img width="959" height="563" alt="Screenshot 2026-06-14 152823" src="https://github.com/user-attachments/assets/5eb80179-3ce5-46d7-a76a-971ae1315d0f" />

Hasil Tampilannya;

<img width="959" height="563" alt="Screenshot 2026-06-15 002103" src="https://github.com/user-attachments/assets/920db6f2-324e-49be-af91-790931f92ea0" />

```php
<?php if (!empty($row->gambar)): ?>
                            <img src="<?= base_url('/gambar/' . $row->gambar); ?>" width="80" style="display:block; margin-bottom:5px;">
                        <?php endif; ?>
```
kode ini berguna untuk menampilkan pada halaman daftar artikel admin.

Version halaman user;

<img width="959" height="563" alt="Screenshot 2026-06-15 002914" src="https://github.com/user-attachments/assets/f46e9fb2-9b10-43ac-9957-65e43979da8f" />

<img width="959" height="563" alt="Screenshot 2026-06-15 003043" src="https://github.com/user-attachments/assets/95f6924e-89d9-46cb-b688-ae30a0317a60" />

## Praktikum 8: AJAX
## Langkah-langkah Praktikum 8
AJAX atau Asynchronous JavaScript and XML merupakan gabungan dari teknologi pengembangan aplikasi web yang membuat aplikasi web menjadi lebih responsif terhadap interaksi pengguna. 
Keutungan menggunakan AJAX:
```
- Meningkatkan User Experience (UX).
- Menghemat Bandwidth.
- Mempertahankan State Aplikasi.
```
```
Contoh:
- Live chat applications
- Autocomplete suggestions
- Real-time updates
- Validasi formulir secara real-time
```
### Step 1 | Menambahkan Pustaka jQuery
mendownload pustaka tersebut terlebih dahulu dan diekstrak filenya. setelah di ekstrak taruh pada **folder public/assets/js.**

<img width="290" height="184" alt="image" src="https://github.com/user-attachments/assets/c8d58d31-d886-4be7-bf29-5f2f8b1d59da" />

### Step 2 | Membuat model
Membuat AJAX Controller agar model dapat diakses melalui AJAX.
```php
<?php

namespace App\Controllers;

use CodeIgniter\Controller;
use CodeIgniter\HTTP\Request;
use CodeIgniter\HTTP\Response;
use App\Models\ArtikelModel;

class  AjaxController extends Controller
{
    public function index()
    {
        return view('ajax/index');
    }

    public function getData()
    {
        $q = $this->request->getVar('q') ?? '';
        $kategori_id = $this->request->getVar('kategori_id') ?? '';
    
        $model = new ArtikelModel();
        
        $builder = $model->db->table('artikel')
            ->select('artikel.*, kategori.nama_kategori')
            ->join('kategori', 'kategori.id_kategori = artikel.id_kategori', 'left');
    
        if ($q != '') {
            $builder->like('artikel.judul', $q);
        }
    
        if ($kategori_id != '') {
            $builder->where('artikel.id_kategori', $kategori_id);
        }
    
        $data = $builder->get()->getResultArray();
    
        return $this->response->setJSON($data);
    }

    public function delete($id)
    {
        $model = new ArtikelModel();
        $data = $model->delete($id);

        $data = [
            'status' => 'OK'
        ];

        return $this->response->setJSON($data);
    }

    public function store()
    {
        $model = new ArtikelModel();

        $file = $this->request->getFile('gambar');
        $namaGambar = '';
        if ($file && $file->isValid() && !$file->hasMoved()) {
            $file->move(ROOTPATH . 'public/gambar');
            $namaGambar = $file->getName();
        }

        $model->insert([
            'judul'       => $this->request->getPost('judul'),
            'isi'         => $this->request->getPost('isi'),
            'slug'        => url_title($this->request->getPost('judul')),
            'id_kategori' => $this->request->getPost('id_kategori'),
            'gambar'      => $namaGambar,
        ]);

        return $this->response->setJSON(['status' => 'OK']);
    }

    public function getById($id)
    {
        $model = new ArtikelModel();
        $data = $model->find($id);
        return $this->response->setJSON($data);
    }

    public function update($id)
    {
        $model = new ArtikelModel();

        $file = $this->request->getFile('gambar');
        $namaGambar = $this->request->getPost('gambar_lama');
        if ($file && $file->isValid() && !$file->hasMoved()) {
            $file->move(ROOTPATH . 'public/gambar');
            $namaGambar = $file->getName();
        }

        $model->update($id, [
            'judul'       => $this->request->getPost('judul'),
            'isi'         => $this->request->getPost('isi'),
            'slug'        => url_title($this->request->getPost('judul')),
            'id_kategori' => $this->request->getPost('id_kategori'),
            'gambar'      => $namaGambar,
        ]);

        return $this->response->setJSON(['status' => 'OK']);
    }
}
```
Fungsi:
- mengirim data JSON menggunakan AJAX,
- Penghubung database,
- Pengelola CRUD artikel,
- Menampilkan data artikel.

### Step 2 | Membuat view
```php
<?= $this->include('template/admin_header'); ?>

<h2><?= $title; ?></h2>
<br>

<div class="row mb-3">
    <div class="col-md-6">
        <form id="filterForm" class="form-inline">
            <input type="text" name="q" id="q" placeholder="Cari judul artikel" class="form-control mr-2">
            
            <select name="kategori_id" id="kategori_id" class="form-control mr-2">
                <option value="">Semua Kategori</option>
                <?php foreach ($kategori as $k): ?>
                    <option value="<?= $k['id_kategori']; ?>">
                        <?= $k['nama_kategori']; ?>
                    </option>
                <?php endforeach; ?>
            </select>

            <button type="submit" class="btn btn-primary">Cari</button>
        </form>
    </div>
</div>

<table class="table" id="artikelTable">
    <thead>
        <tr>
            <th>ID</th>
            <th>Gambar</th>
            <th>Judul</th>
            <th>Kategori</th>
            <th>Status</th>
            <th>Aksi</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td colspan="6">Loading data...</td>
        </tr>
    </tbody>
</table>

<script src="<?= base_url('assets/js/jquery-4.0.0.min.js') ?>"></script>

<script>
$(document).ready(function() {

    function loadData(q = '', kategori_id = '') {
        $('#artikelTable tbody').html('<tr><td colspan="6">Loading data...</td></tr>');

        $.ajax({
            url: "<?= base_url('ajax/getData') ?>",
            method: "GET",
            data: {
                q: q,
                kategori_id: kategori_id
            },
            dataType: "json",
            success: function(data) {
                var html = '';

                if (data.length > 0) {
                    for (var i = 0; i < data.length; i++) {
                        var row = data[i];

                        html += '<tr>';
                        html += '<td>' + row.id + '</td>';

                        html += '<td>';
                        if (row.gambar) {
                            html += '<img src="<?= base_url('/gambar/') ?>' + row.gambar + '" width="80">';
                        }
                        html += '</td>';

                        html += '<td><b>' + row.judul + '</b><br><small>' + row.isi.substring(0,50) + '</small></td>';
                        html += '<td>' + row.nama_kategori + '</td>';
                        html += '<td>' + row.status + '</td>';

                        html += '<td>';
                        html += '<a href="<?= base_url('/admin/artikel/edit/') ?>' + row.id + '" class="btn btn-sm btn-info">Ubah</a> ';
                        html += '<a href="#" class="btn btn-sm btn-danger btn-delete" data-id="' + row.id + '">Hapus</a>';
                        html += '</td>';

                        html += '</tr>';
                    }
                } else {
                    html = '<tr><td colspan="6">Tidak ada data</td></tr>';
                }

                $('#artikelTable tbody').html(html);
            }
        });
    }

    // Load awal
    loadData();

    // Filter
    $('#filterForm').submit(function(e) {
        e.preventDefault();
        var q = $('#q').val();
        var kategori_id = $('#kategori_id').val();
        loadData(q, kategori_id);
    });

    // Delete
    $(document).on('click', '.btn-delete', function(e) {
        e.preventDefault();
        var id = $(this).data('id');

        if (confirm('Yakin hapus data?')) {
            $.ajax({
                url: "<?= base_url('admin/artikel/delete/') ?>" + id,
                method: "GET",
                success: function() {
                    loadData();
                }
            });
        }
    });

});
</script>

<?= $this->include('template/admin_footer'); ?>
```
Fungsi:
- Menampilkan data artikel secara AJAX,
- Melakukan pencarian artikel,
- Filter berdasarkan kategori,
- Menghapus artikel tanpa reload halaman.

Hasil Tampilannya;

<img width="959" height="565" alt="Screenshot 2026-06-15 003408" src="https://github.com/user-attachments/assets/a2e12a83-f392-4e16-af69-66ca0bf468a8" />

## Pertanyaan dan Tugas
### Step 1 | Memnambahkan pada file form add dan form edit.
**form add:**
```php
<?= $this->include('template/admin_header'); ?>

<h2><?= $title; ?></h2>
<form id="formTambah" action="" method="post" enctype="multipart/form-data">
    <?= csrf_field(); ?>
    <p>
        <label for="judul">Judul</label>   
    <input type="text" name="judul" id="judul" required>
    </p>
    <p>
        <label for="isi">Isi</label>
        <textarea name="isi" id="isi" cols="50" rows="10"></textarea>
    </p>
    <p>
        <label for="id_kategori">Kategori</label>
        <select name="id_kategori" id="id_kategori" required>
            <?php foreach($kategori as $k): ?>
                <option value="<?= $k['id_kategori']; ?>"><?= $k['nama_kategori']; ?></option>
            <?php endforeach; ?>
        </select>
        <p>
            <input type="file" name="gambar">
        </p>
    </p>
    <p><input type="submit" value="Kirim" class="btn btn-large"></p><br>
    <a href="<?= base_url('admin/artikel'); ?>" class="btn btn-large">Kembali</a></p>
</form>

<script src="<?= base_url('assets/js/jquery-4.0.0.min.js') ?>"></script>
<script>
$('#formTambah').submit(function(e) {
    e.preventDefault();
    var formData = new FormData(this);
    $.ajax({
        url: "<?= base_url('ajax/store') ?>",
        method: "POST",
        data: formData,
        processData: false,
        contentType: false,
        success: function(res) {
            if (res.status == 'OK') {
                alert('Artikel berhasil ditambahkan!');
                window.location.href = "<?= base_url('admin/artikel') ?>";
            }
        },
        error: function() {
            alert('Gagal menyimpan data!');
        }
    });
});
</script>

<?= $this->include('template/admin_footer'); ?>
```
Fungsi:
- Menyimpan data realtime,
- Redirect otomatis setelah berhasil.
- Menyimpan artikel ke database tanpa reload halaman.

Hasil Tampilannya;

<img width="959" height="563" alt="Screenshot 2026-06-14 152448" src="https://github.com/user-attachments/assets/b3c6a27a-6985-4440-929d-3930c2779803" />

**form edit:**
```php
<?= $this->include('template/admin_header'); ?>

<h2><?= $title; ?></h2>
<form id="formUbah" action="" method="post" enctype="multipart/form-data">
    <p>
        <label for="judul">Judul</label>
         <input type="text" name="judul" value="<?= $artikel['judul']; ?>"
id="judul" required>
    </p>
    <p>
        <label for="isi">Isi</label>
        <textarea name="isi" id="isi" cols="50" rows="10"><?= $artikel['isi'];
    ?></textarea>
    </p>
    <p>
        <label for="id_kategori">Kategori</label>
        <select name="id_kategori" id="id_kategori" required>
            <?php foreach($kategori as $k): ?>
                         <option value="<?= $k->id_kategori; ?>" <?=
($artikel['id_kategori'] == $k->id_kategori) ? 'selected' : ''; ?>><?=
$k->nama_kategori; ?></option>
            <?php endforeach; ?>
        </select>
    </p>
    <p>
        <?php if($artikel['gambar']): ?>
            <img src="<?= base_url('/gambar/' . $artikel['gambar']) ?>" width="150"><br><br>
        <?php endif; ?>
        <label for="gambar">Ubah Gambar</label>
        <input type="file" name="gambar" id="gambar">
        <input type="hidden" name="gambar_lama" value="<?= $artikel['gambar']; ?>">
    </p>
    <p><input type="submit" value="Kirim" class="btn btn-large"></p><br>
    <a href="<?= base_url('admin/artikel'); ?>" class="btn btn-large">Kembali</a></p>
</form>

<script src="<?= base_url('assets/js/jquery-4.0.0.min.js') ?>"></script>
<script>
$('#formUbah').submit(function(e) {
    e.preventDefault();
    var formData = new FormData(this);
    $.ajax({
        url: "<?= base_url('ajax/update/' . $artikel['id']) ?>",
        method: "POST",
        data: formData,
        processData: false,
        contentType: false,
        success: function(res) {
            if (res.status == 'OK') {
                alert('Artikel berhasil diubah!');
                window.location.href = "<?= base_url('admin/artikel') ?>";
            }
        },
        error: function() {
            alert('Gagal mengubah data!');
        }
    });
});
</script>

<?= $this->include('template/admin_footer'); ?>
```
Fungsi:
- Redirect ke halaman admin artikel setelah berhasil update,
- Submit form ubah artikel menggunakan AJAX
  
Hasil Tampilannya;

<img width="959" height="563" alt="Screenshot 2026-06-14 152823" src="https://github.com/user-attachments/assets/12c0b433-ca7f-4251-bfd5-0b20f06ae3d0" />

## Praktikum 9: Implementasi AJAX Pagination dan Search
## Langkah-langkah Praktikum 9
### Step 1 | Persiapan
Siapkan MySQL server berjalan, pastikan tabel artikel dan kategori suda terisi, dan pastikan library jQuery sudah terpasang.

### Step 2 | Modifikasi Controller Artikel
Mengubah method pada **admin index** di **file Artikel.php.** Agar data dalam format JSON jika request AJAX.
```php
public function admin_index()
    {
        $title = 'Daftar Artikel (Admin)';
        $model = new ArtikelModel();

        $q = $this->request->getVar('q') ?? '';
        $kategori_id = $this->request->getVar('kategori_id') ?? '';
        $page = $this->request->getVar('page') ?? 1;

        $builder = $model->select('artikel.*, kategori.nama_kategori')
                         ->join('kategori', 'kategori.id_kategori = artikel.id_kategori');

        if ($q != '') {
            $builder->like('artikel.judul', $q);
        }
        if ($kategori_id != '') {
            $builder->where('artikel.id_kategori', $kategori_id);
        }

        $sort = $this->request->getVar('sort') ?? '';
        if ($sort == 'judul_asc') $builder->orderBy('artikel.judul', 'ASC');
        if ($sort == 'judul_desc') $builder->orderBy('artikel.judul', 'DESC');
        if ($sort == 'id_asc') $builder->orderBy('artikel.id', 'ASC');
        if ($sort == 'id_desc') $builder->orderBy('artikel.id', 'DESC');

        $artikel = $builder->paginate(5, 'default', $page);
        $pager = $model->pager;

        $data = [
            'title'       => $title,
            'q'           => $q,
            'kategori_id' => $kategori_id,
            'artikel'     => $artikel,
            'pager'       => $pager,
        ];

        if ($this->request->isAJAX()) {
            $data['pager'] = $pager->getDetails();
            return $this->response->setJSON($data);
        } else {
            $kategoriModel = new KategoriModel();
            $data['kategori'] = $kategoriModel->findAll();
            return view('artikel/admin_index', $data);
        }
    }
```
Penjelasan fungsi:
- nomor halaman untuk pagination, default halaman 1,
- Menerapkan pagination dengan nomor halaman yang diberikan,
- Kata kunci pencarian judul artikel, default kosong,
- Return JSON berisi artikel dan detail pager (getDetails()) untuk pagination.

### Step 3 | Modifikasi View
```php
<?= $this->include('template/admin_header'); ?>
<h2><?= $title; ?></h2>
<br>

<div id="loading-indicator" style="display:none; text-align:center; padding: 20px;">
    <div class="spinner-border text-primary" role="status">
        <span class="sr-only">Loading data...</span>
    </div>
</div>

<div class="row mb-3">
    <div class="col-md-8">
        <form id="filterForm" class="form-inline">
            <input type="text" name="q" id="q" placeholder="Cari judul artikel" class="form-control mr-2">

            <select name="kategori_id" id="kategori_id" class="form-control mr-2">
                <option value="">Semua Kategori</option>
                <?php foreach ($kategori as $k): ?>
                    <option value="<?= $k['id_kategori']; ?>">
                        <?= $k['nama_kategori']; ?>
                    </option>
                <?php endforeach; ?>
            </select>

            <select name="sort" id="sort" class="form-control mr-2">
                <option value="">Urutkan</option>
                <option value="id_asc">ID Terkecil</option>
                <option value="id_desc">ID Terbesar</option>
                <option value="judul_asc">Judul A-Z</option>
                <option value="judul_desc">Judul Z-A</option>
            </select>

            <button type="submit" class="btn btn-primary">Cari</button>
        </form>
    </div>
</div>

<div id="article-container"></div>
<br>
<div id="pagination-container" class="pagination"></div>


<script src="<?= base_url('assets/js/jquery-4.0.0.min.js') ?>"></script>
<script>
$(document).ready(function () {
    const articleContainer = $('#article-container');
    const paginationContainer = $('#pagination-container');

    const fetchData = (url) => {
        $('#loading-indicator').show();
        $('#article-container').html('');
        $('#pagination-container').html('');

        $.ajax({
            url: url,
            type: 'GET',
            dataType: 'json',
            headers: {
                'X-Requested-With': 'XMLHttpRequest'
            },
            success: function (data) {
                renderArticles(data.artikel);
                renderPagination(data.pager, data.q, data.kategori_id);
            },
            error: function () {
                $('#article-container').html('<div class="alert alert-danger">Gagal memuat data.</div>');
            },
            complete: function () {
                $('#loading-indicator').hide();
            }
        });
    };

    const renderArticles = (articles) => {
        let html = '<table class="table table-bordered table-striped">';
        html += '<thead><tr><th>ID</th><th>Gambar</th><th>Judul</th><th>Kategori</th><th>Status</th><th>Aksi</th></tr></thead><tbody>';

        if (articles && articles.length > 0) {
            articles.forEach(row => {
                html += `<tr>
                    <td>${row.id}</td>
                    <td>
                        ${row.gambar
                            ? `<img src="<?= base_url('/gambar/') ?>${row.gambar}" width="80">`
                            : '-'}
                    </td>
                    <td><b>${row.judul}</b><br><small>${row.isi.substring(0, 50)}</small></td>
                    <td>${row.nama_kategori}</td>
                    <td>${row.status}</td>
                    <td>
                        <a href="<?= base_url('/admin/artikel/edit/') ?>${row.id}" class="btn btn-sm btn-info">Ubah</a>
                        <a href="#" class="btn btn-sm btn-danger btn-delete" data-id="${row.id}">Hapus</a>
                    </td>
                </tr>`;
            });
        } else {
            html += '<tr><td colspan="6" class="text-center">Tidak ada data.</td></tr>';
        }

        html += '</tbody></table>';
        $('#article-container').html(html);
    };

    const renderPagination = (pager, q, kategori_id) => {
        if (!pager || pager.pageCount <= 1) return;
                    
        let sort = $('#sort').val();
        let html = '<nav><ul class="pagination">';
                    
        for (let i = 1; i <= pager.pageCount; i++) {
            let url = `<?= base_url('/admin/artikel') ?>?page=${i}&q=${q ?? ''}&kategori_id=${kategori_id ?? ''}&sort=${sort ?? ''}`;
            html += `<li class="page-item ${i == pager.currentPage ? 'active' : ''}">
                        <a class="page-link pagination-link" href="${url}">${i}</a>
                     </li>`;
        }
                    
        html += '</ul></nav>';
        paginationContainer.html(html);
    };

    $('#filterForm').on('submit', function (e) {
        e.preventDefault();
        const q = $('#q').val();
        const kategori_id = $('#kategori_id').val();
        const sort = $('#sort').val();
        fetchData(`<?= base_url('/admin/artikel') ?>?q=${q}&kategori_id=${kategori_id}&sort=${sort}`);
    });

    $('#kategori_id').on('change', function () {
        $('#filterForm').trigger('submit');
    });

    $('#sort').on('change', function () {
        $('#filterForm').trigger('submit');
    });


    $(document).on('click', '.pagination-link', function (e) {
        e.preventDefault();
        const url = $(this).attr('href');
        if (url && url !== '#') {
            fetchData(url);
        }
    });

    $(document).on('click', '.btn-delete', function (e) {
        e.preventDefault();
        const id = $(this).data('id');
        if (confirm('Yakin hapus data ini?')) {
            $.ajax({
                url: `<?= base_url('admin/artikel/delete/') ?>${id}`,
                method: 'GET',
                success: function () {
                    $('#filterForm').trigger('submit');
                },
                error: function () {
                    alert('Gagal menghapus data.');
                }
            });
        }
    });

    fetchData('<?= base_url('/admin/artikel') ?>');
});
</script>

<?= $this->include('template/admin_footer'); ?>
```
Penjelasan fungsi:
- jQuery mengirim request ke server secara otomatis
- Form tidak reload halaman
- Tidak memakai tabel artikel dan pagination secara langsung.

Hasil Tampilannya;

<img width="959" height="565" alt="Screenshot 2026-06-15 201838" src="https://github.com/user-attachments/assets/d9dee2ca-434b-49c2-add2-533134f7307b" />

## Pertanyaan dan Tugas
### Step 1 | Modifikasi tampilan data artikel dan pagination sesuai kebutuhan desain.
```php
table-bordered table-striped
```
menambahkan class tersebut agar tabel artikel lebih mudah untuk dibaca.

### Step 2 | Tambahkan indikator loading saat data sedang diambil dari server.
```php
$('#loading-indicator').show();  // saat AJAX mulai
// ...
complete: function () {
    $('#loading-indicator').hide();  // saat AJAX selesai
}
```
ketika request ke server dimulai, indikator ditampilkan. Setelah server mengembalikan response berhasil atau gagal, idikator disembunyikan kembali melalui callback complete di AJAX. indikator ini memberi tahu pengguna bahwa data sedang diproses.

Hasil Tampilannya;

**Sebelum**
<img width="958" height="563" alt="Screenshot 2026-06-16 164907" src="https://github.com/user-attachments/assets/5484c4e8-4450-4fcb-8bc4-2d9416ce7eb3" />

**Pogres**
<img width="959" height="563" alt="Screenshot 2026-06-16 164708" src="https://github.com/user-attachments/assets/e055775b-6604-4e6f-831e-c78e5c946892" />

**Sesudah**
<img width="959" height="599" alt="Screenshot 2026-06-15 211955" src="https://github.com/user-attachments/assets/0b75ff5e-48bc-47f4-92d9-88fd9bb3875a" />

### Step 3 | Implementasikan fitur sorting (mengurutkan artikel berdasarkan judul, dll.) dengan AJAX.
```php
<select name="sort" id="sort" class="form-control mr-2">
                <option value="">Urutkan</option>
                <option value="id_asc">ID Terkecil</option>
                <option value="id_desc">ID Terbesar</option>
                <option value="judul_asc">Judul A-Z</option>
                <option value="judul_desc">Judul Z-A</option>
</select>

$sort = $this->request->getVar('sort') ?? '';
        if ($sort == 'judul_asc') $builder->orderBy('artikel.judul', 'ASC');
        if ($sort == 'judul_desc') $builder->orderBy('artikel.judul', 'DESC');
        if ($sort == 'id_asc') $builder->orderBy('artikel.id', 'ASC');
        if ($sort == 'id_desc') $builder->orderBy('artikel.id', 'DESC');
```
Dapat merubah dropdown sesuai keingingan berdasarkan urutan: pilihan ID Terkecil, ID Terbesar, Judul A-Z, dan Judul Z-A. form otomatis ter-submit dan mengirim parameter sort ke server tanpa reload halaman.

Hasil Tampilannya;
**berdasarkan urutan abjad:**

<img width="959" height="563" alt="Screenshot 2026-06-16 165010" src="https://github.com/user-attachments/assets/00dd8e97-50ab-4c39-8834-cffece180e78" />

**berdasarkan urutan ID:**

<img width="959" height="565" alt="Screenshot 2026-06-16 165047" src="https://github.com/user-attachments/assets/13b73897-df4a-447a-8ddc-8effde6c4188" />

## Praktikum 10: API
## Langkah-langkah Praktikum 10
Rest API (Representational State Transfer) merupakan antarmuka yang memungkinkan dua sistem atau aplikasi berbeda untuk saling berkomunikasi dan bertukar data melalui internet.

### Step 1 | Mendownload REST Client
Mendownload aplikasi Postman. Aplikasi tersebut berfungsi sebagai REST Client dan digunakan untuk testing REST API.

*https://www.postman.com/downloads/*

### Step 2 | Membuat Model
Membuat file REST Controller dengan nama **Post.php** di **direktori app\Controllers.**
```php
<?php

namespace App\Controllers;

use CodeIgniter\RESTful\ResourceController;
use CodeIgniter\API\ResponseTrait;
use App\Models\ArtikelModel;

class Post extends ResourceController
{
    use ResponseTrait;
    // all users
    public function index()
    {
        $model = new ArtikelModel();
        $data['artikel'] = $model->orderBy('id', 'DESC')->findAll();
        return $this->respond($data);
    }
    // create
    public function create()
    {
        $model = new ArtikelModel();
        $data = [
            'judul' => $this->request->getVar('judul'),
            'isi' => $this->request->getVar('isi'),
        ];
        $model->insert($data);
        $response = [
            'status' => 201,
            'error' => null,
            'messages' => [
                'success' => 'Data artikel berhasil ditambahkan.'
            ]
        ];
        return $this->respondCreated($response);
    }
    // single user
    public function show($id = null)
    {
        $model = new ArtikelModel();
        $data = $model->where('id', $id)->first();
        if ($data) {
            return $this->respond($data);
        } else {
            return $this->failNotFound('Data tidak ditemukan.');
        }
    }
    // update
    public function update($id = null)
    {
        $model = new ArtikelModel();
        $id = $this->request->getVar('id');
        $data = [
            'judul' => $this->request->getVar('judul'),
            'isi' => $this->request->getVar('isi'),
        ];
        $model->update($id, $data);
        $response = [
            'status' => 200,
            'error' => null,
            'messages' => [
                'success' => 'Data artikel berhasil diubah.'
            ]
        ];
        return $this->respond($response);
    }
    // delete
    public function delete($id = null)
    {
        $model = new ArtikelModel();
        $data = $model->where('id', $id)->delete($id);
        if ($data) {
            $model->delete($id);
            $response = [
                'status' => 200,
                'error' => null,
                'messages' => [
                    'success' => 'Data artikel berhasil dihapus.'
                ]
            ];
            return $this->respondDeleted($response);
        } else {
            return $this->failNotFound('Data tidak ditemukan.');
        }
    }
}
```
Fungsi:
- Menampilkan data
- Menambah data
- Merubah data
- Menghapus data

### Step 3 | Membuat Routing REST API
Setelah membuat modelnya, lanjut untuk membuat routes-nya agar REST API dapat diakses. Pada file Routes.php. Tambahkan kode berikut:
```php
$routes->resource('post');
```
Lalu cek routenya dengan menjalankan perintah pada shell di xampp:
```
php spark routes
```
Akan muncul seperti ini.

<img width="959" height="562" alt="Screenshot 2026-06-16 170123" src="https://github.com/user-attachments/assets/a680b40c-605e-4b12-814a-1567d67d7704" />

### Step 3 | Testing REST API CodeIgniter
Buka aplikasi Postman yang telah didownload. pilih **create new** dan pilih lagi bagian **HTTP Request.**

<img width="959" height="562" alt="Screenshot 2026-06-16 171337" src="https://github.com/user-attachments/assets/54d4c761-59ef-402e-a2c7-e88416d90503" />

- Menampilkan Semua Data
Pilih method GET dan masukka URL seperti berikut:
```http://localhost:8080/post```
Lalu, klik **send** dan tampilan Hasilnya kurang lebih seperti ini.

<img width="959" height="562" alt="Screenshot 2026-06-16 210523" src="https://github.com/user-attachments/assets/79ca561d-a4d6-4c37-a91e-7a63e5d82de2" />

- Menampilkan Data Spesifik
Menggunakan **method GET.** mengubah ID artikel dengan URL berikut:
```http://localhost:8080/post/3```
Lalu, klik send. hasilnya akan muncul aritkel dengan ID no 3.

<img width="564" height="283" alt="image" src="https://github.com/user-attachments/assets/99f7da16-06e1-485c-8d15-93b658afc03f" />

- Mengubah Data
Ubah **method** dari **GET** menjadi **PUT.** Kemudian, lalu masukkan URL dengan ID artikel yang mau diubah. Pilih **tab Body.** Kemudian, pilih **x-www-form-uriencoded** dan Masukkan nama atribut tabel pada kolom **KEY** dan nilai data yang baru pada kolom **VALUE**. Lalu **send.**
```http://localhost:8080/post/2```
Hasil.

<img width="959" height="562" alt="Screenshot 2026-06-16 212324" src="https://github.com/user-attachments/assets/06289a84-9c47-4359-bc1c-e7c97e4221b4" />

- Menambahkan Data
Pilih **method POST** dan masukkan URL berikut:
```http://localhost:8080/post```
Pilih tab **Body** dan pilih **x-www-form-uriencoded.** masukkan atribute pada kolom **KEY** dan niai data baru pada **VALUE.** Lalu klik **send.**
Hasil.

<img width="959" height="563" alt="Screenshot 2026-06-16 212425" src="https://github.com/user-attachments/assets/f53f4564-8f8b-43a8-8e4f-2a601c828e69" />

- Menghapus Data
Pilih **method DELETE.** Lalu, masukkan URL dengan data yang ingin dihapus. Masukkan URL seperti berikut:
```http://localhost:8080/post/4```
Hasilnya.

<img width="959" height="560" alt="Screenshot 2026-06-16 212828" src="https://github.com/user-attachments/assets/bbb844b6-3a4d-4d17-a4d0-aa862d7b75d8" />

## Pertanyaan dan Tugas
Selesaikan programnya sesuai Langkah-langkah yang ada. Anda boleh melakukan improvisasi.
