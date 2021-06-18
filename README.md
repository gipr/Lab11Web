# Lab11Web
1. Buat folder baru dengan nama lab11_php_ci pada docroot webserver (htdocs)
# ![Screenshot (64)](https://user-images.githubusercontent.com/65975985/122579213-e1578c80-d07e-11eb-853e-73de6b3629a4.png)
2. Ikuti langkah-langkah praktikum yang akan dijelaskan berikutnya.

# Langkah Praktikum
# Persiapan
Sebelum memulai menggunakan Framework Codeigniter, perlu dilakukan konfigurasi pada webserver. Beberapa ekstensi PHP perlu diaktifkan untuk kebutuhan pengembangan Codeigniter 4. Berikut beberapa ekstensi yang perlu diaktifkan: • php-json ekstension untuk bekerja dengan JSON; • php-mysqlnd native driver untuk MySQL; • php-xml ekstension untuk bekerja dengan XML; • php-intl ekstensi untuk membuat aplikasi multibahasa; • libcurl (opsional), jika ingin pakai Curl.

Untuk mengaktifkan ekstentsi tersebut, melalu XAMPP Control Panel, pada bagian Apache klik Config -> PHP.ini
![Screenshot (65)](https://user-images.githubusercontent.com/65975985/122579705-617df200-d07f-11eb-80ae-80913a52f8a7.png)
Pada bagian extention, hilangkan tanda ; (titik koma) pada ekstensi yang akan diaktifkan. Kemudian simpan kembali filenya dan restart Apache web server.
![Screenshot (66)](https://user-images.githubusercontent.com/65975985/122579730-693d9680-d07f-11eb-9b8e-41ea6fdec26a.png)

# Instalasi Codeigniter 4
untuk melakukan instalasi Codeigniter 4 dapat dilakukan dengan dua cara, yaitu cara manual dan menggunakan composer. Pada praktikum ini kita menggunakan cara manual. • Unduh Codeigniter dari website https://codeigniter.com/download • Extrak file zip Codeigniter ke direktori htdocs/lab11_ci. • Ubah nama direktory framework-4.x.xx menjadi ci4. • Buka browser dengan alamat http://localhost/lab11_ci/ci4/public/
![Screenshot (67)](https://user-images.githubusercontent.com/65975985/122579817-7eb2c080-d07f-11eb-9777-5f816abe3cc8.png)

# Menjalankan Command Line Interface
Codeigniter 4 menyediakan CLI untuk mempermudah proses development. Untuk mengakses CLI buka terminal/command prompt.
![Screenshot (68)](https://user-images.githubusercontent.com/65975985/122579894-9722db00-d07f-11eb-9cbe-1e6fe90be776.png)
Arahkan lokasi direktori sesuai dengan direktori kerja project dibuat (xampp/htdocs/lab11_ci/ci4/) Perintah yang dapat dijalankan untuk memanggil CLI Codeigniter adalah:
![Screenshot (69)](https://user-images.githubusercontent.com/65975985/122579919-9e49e900-d07f-11eb-97fd-da964523eef1.png)

# Mengaktifkan mode Debug
Codeigniter 4 menyediakan fitur debugging untuk memudahkan developer untuk mengetahui pesan error apabila terjadi kesalahan dalam membuat kode program. Secara default fitur ini belum aktif. Ketika terjadi error pada aplikasi akan ditampilkan pesan kesalahan seperti berikut.
![Screenshot (70)](https://user-images.githubusercontent.com/65975985/122580134-d81aef80-d07f-11eb-9be6-6d7c20407d8c.png)
