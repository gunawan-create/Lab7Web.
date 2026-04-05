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

Semua jenis error akan ditampilkan sama. Untuk memudahkan mengetahui jenis errornya, maka perlu diaktifkan mode debugging dengan mengubah nilai konfigurasi pada environment 
variable **CI_ENVIRINMENT** menjadi **development.** 

<img width="444" height="179" alt="Screenshot 2026-04-04 145101" src="https://github.com/user-attachments/assets/9f8c6761-8c88-450b-9db4-60c1ec108aca" />





