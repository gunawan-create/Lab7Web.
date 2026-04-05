## LAPORAN PRAKTIKUM 1 - 4
NAMA : ALI GUNAWAN | KELAS : I241C | NIM : 312410400

## Instruksi Praktikum 
1. Persiapkan text editor misalnya VSCode. 
2. Buat folder baru dengan nama lab11_php_ci pada docroot webserver (htdocs) 
3. Ikuti langkah-langkah praktikum yang akan dijelaskan berikutnya.

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
