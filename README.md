## LAPORAN PRAKTIKUM 1 - 4
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

<img width="1919" height="1126" alt="Screenshot 2026-04-04 204728" src="https://github.com/user-attachments/assets/a1d73c7c-c520-4a2c-a3d8-c75cfeba49db" />

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

### Step 4 | Menambahkan Database Seeder 
Untuk keperluan ujicoba modul login, kita perlu memasukkan data user dan password kedaalam database. Untuk itu buat 
database seeder untuk tabel user. Buka CLI, kemudian tulis perintah berikut: 

<img width="899" height="75" alt="Screenshot 2026-04-09 095406" src="https://github.com/user-attachments/assets/4912602f-751f-4820-bf05-67262e5966e1" />

Selanjutnya, buka file **UserSeeder.php** yang berada di lokasi direktori 
**/app/Database/Seeds/UserSeeder.php** kemudian isi dengan kode berikut,

<img width="907" height="553" alt="image" src="https://github.com/user-attachments/assets/811fef60-f6ab-4710-8015-e20b78b49b77" />

Selanjutnya buka kembali CLI dan ketik perintah berikut: 

<img width="927" height="90" alt="Screenshot 2026-04-09 095432" src="https://github.com/user-attachments/assets/19839407-cd70-4e73-8679-ddde9526edba" />

### Step 5 | Uji Coba Login 
Selanjutnya buka url **http://localhost:8080/user/login** seperti berikut: 

<img width="1919" height="1127" alt="Screenshot 2026-04-09 100934" src="https://github.com/user-attachments/assets/e8f32c75-c5a2-4f2a-9b75-bfc6961e476a" />

### Step 6 | Menambahkan Auth Filter 
Selanjutnya membuat filer untuk halaman admin. Buat file baru dengan nama **Auth.php** pada 
direktori **app/Filters.**

<img width="889" height="621" alt="image" src="https://github.com/user-attachments/assets/20f0ab2e-d6ba-458a-9eee-2337d75c54f3" />

Selanjutnya buka file **app/Config/Filters.php** tambahkan kode berikut:

<img width="452" height="50" alt="image" src="https://github.com/user-attachments/assets/484a091f-59ad-4410-aa53-cd481e641bd1" />

Seperti ini bentukannya;

<img width="603" height="257" alt="image" src="https://github.com/user-attachments/assets/dffbb0c0-1a3f-4576-bcb2-f5b3b50a325a" />

Setelah itu anda buka file **app/Config/Routes.php** dan sesuaikan kodenya.

<img width="804" height="239" alt="image" src="https://github.com/user-attachments/assets/970234c4-c540-4030-8d5a-3efa998e41a2" />

### Step 7 | Percobaan Akses Menu Admin 
Buka url dengan alamat **http://localhost:8080/admin/artikel** ketika alamat tersebut diakses 
maka, akan dimuculkan halaman login.

<img width="1919" height="1125" alt="image" src="https://github.com/user-attachments/assets/8f2f9430-f15f-42a2-ad42-af166f2d2fad" />

### Step 8 | Menambahkan Fungsi Logout 
Tambahkan method logout pada Controller User seperti berikut:

<img width="606" height="202" alt="image" src="https://github.com/user-attachments/assets/1faf3588-5dae-4421-ba42-158892edcf48" />

## Praktikum 5: Pagination dan Pencarian 
## Langkah-langkah Praktikum 5
### Step 1 | Membuat Pagination 
Untuk membuat pagination, buka Kembali Controller Artikel, kemudian modifikasi kode 
pada method admin_index seperti berikut.
