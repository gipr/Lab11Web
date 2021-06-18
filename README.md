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

Semua jenis error akan ditampilkan sama. Untuk memudahkan mengetahui jenis errornya, maka perlu diaktifkan mode debugging dengan mengubah nilai konfigurasi pada environment variable CI_ENVIRINMENT menjadi development.

![Screenshot (71)](https://user-images.githubusercontent.com/65975985/122580226-ee28b000-d07f-11eb-97c7-60b48fa1d4d0.png)

Ubah nama file env menjadi .env kemudian buka file tersebut dan ubah nilai variable CI_ENVIRINMENT menjadi development.

# Struktur Direktori

Untuk lebih memahami Framework Codeigniter 4 perlu mengetahui struktur direktori dan file yang ada. Buka pada Windows Explorer atau dari Visual Studio Code -> Open Folder. Terdapat beberapa direktori dan file yang perlu dipahami fungsi dan kegunaannya. • .github folder ini kita butuhkan untuk konfigurasi repo github, seperti konfigurasi untuk build dengan github action; • app folder ini akan berisi kode dari aplikasi yang kita kembangkan; • public folder ini berisi file yang bisa diakses oleh publik, seperti file index.php, robots.txt, favicon.ico, ads.txt, dll; • tests folder ini berisi kode untuk melakukan testing dengna PHPunit; • vendor folder ini berisi library yang dibutuhkan oleh aplikasi, isinya juga termasuk kode core dari system CI. • writable folder ini berisi file yang ditulis oleh aplikasi. Nantinya, kita bisa pakai untuk menyimpan file yang di-upload, logs, session, dll. Sedangkan file-file yang berada pada root direktori CI sebagai berikut. • .env adalah file yang berisi variabel environment yang dibutuhkan oleh aplikasi. • .gitignore adalah file yang berisi daftar nama file dan folder yang akan diabaikan oleh Git. • build adalah script untuk mengubah versi codeigniter yang digunakan. Ada versi release (stabil) dan development (labil). • composer.json adalah file JSON yang berisi informasi tentang proyek dan daftar library yang dibutuhkannya. File ini digunakan oleh Composer sebagai acuan. • composer.lock adalah file yang berisi informasi versi dari libraray yang digunakan aplikasi. • license.txt adalah file yang berisi penjelasan tentang lisensi Codeigniter; • phpunit.xml.dist adalah file XML yang berisi konfigurasi untuk PHPunit. • README.md adalah file keterangan tentang codebase CI. Ini biasanya akan dibutuhkan pada repo github atau gitlab. • spark adalah program atau script yang berfungsi untuk menjalankan server, generate kode, dll.
![Screenshot (72)](https://user-images.githubusercontent.com/65975985/122580363-11ebf600-d080-11eb-94c9-b8e533b5b3ee.png)
Fokus kita pada folder app, dimana folder tersebut adalah area kerja kita untuk membuat aplikasi. Dan folder public untuk menyimpan aset web seperti css, gambar, javascript, dll.

# Membuat Route Baru

Tambahkan kode berikut di dalam Routes.php

    $routes->get('/about', 'Page::about');
    $routes->get('/contact', 'Page::contact');
    $routes->get('/faqs', 'Page::faqs');

Untuk mengetahui route yang ditambahkan sudah benar, buka CLI dan jalankan perintah berikut.

    - php spark routes

![Screenshot (73)](https://user-images.githubusercontent.com/65975985/122580812-90e12e80-d080-11eb-99f6-7dd582f072c3.png)

Selanjutnya coba akses route yang telah dibuat dengan mengakses alamat url http://localhost:8080/about

![Screenshot (74)](https://user-images.githubusercontent.com/65975985/122580895-a6eeef00-d080-11eb-954c-20e24494bfa0.png)

Ketika diakses akan mucul tampilan error 404 file not found, itu artinya file/page tersebut tidak ada. Untuk dapat mengakses halaman tersebut, harus dibuat terlebih dahulu Contoller yang sesuai dengan routing yang dibuat yaitu Contoller Page.

# Membuat Controller 

Selanjutnya adalah membuat Controller Page. Buat file baru dengan nama page.php pada direktori Controller kemudian isi kodenya seperti berikut.

    <?php
    namespace App\Controllers;
    class Page extends BaseController
    {
    public function about()
    {
    echo "Ini halaman About";
    }
    public function contact()
    {
    echo "Ini halaman Contact";
    }
    public function faqs()
    {
    echo "Ini halaman FAQ";
    }
    }

Selanjutnya refresh Kembali browser, maka akan ditampilkan hasilnya yaotu halaman sudah dapat diakses.

![Screenshot (75)](https://user-images.githubusercontent.com/65975985/122582575-7f992180-d082-11eb-875e-6d89c2f36a32.png)

# Auto Routing

Secara default fitur autoroute pada Codeiginiter sudah aktif. Untuk mengubah status autoroute dapat mengubah nilai variabelnya. Untuk menonaktifkan ubah nilai true menjadi false. 

    $routes->setAutoRoute(true);

Tambahkan method baru pada Controller Page seperti berikut.

    public function tos()
    {
    echo "ini halaman Term of Services";
    }

![Screenshot (76)](https://user-images.githubusercontent.com/65975985/122588429-49ab6b80-d089-11eb-8b8c-95cd5fce07c6.png)

# Membuat View

Selanjutnya adalam membuat view untuk tampilan web agar lebih menarik. Buat file baru dengan nama about.php pada direktori view (app/view/about.php) kemudian isi kodenya seperti berikut.

    <!DOCTYPE html>
    <html lang="en">
    <head>
    <meta charset="UTF-8">
    <title><?= $title; ?></title>
    </head>
    <body>
    <h1><?= $title; ?></h1>
    <hr>
    <p><?= $content; ?></p>
    </body>
    </html>

![Screenshot (77)](https://user-images.githubusercontent.com/65975985/122590117-4dd88880-d08b-11eb-9774-6d9f417916af.png)

# Membuat Layout Web dengan CSS

Pada dasarnya layout web dengan css dapat diimplamentasikan dengan mudah pada codeigniter. Yang perlu diketahui adalah, pada Codeigniter 4 file yang menyimpan asset css dan javascript terletak pada direktori public.

Buat file css pada direktori public dengan nama style.css (copy file dari praktikum lab4_layout. Kita akan gunakan layout yang pernah dibuat pada praktikum 4.

![Screenshot (78)](https://user-images.githubusercontent.com/65975985/122590205-6ba5ed80-d08b-11eb-9e56-f35de9f6eb16.png)

Kemudian buat folder template pada direktori view kemudian buat file header.php dan footer.php
File app/view/template/header.php

    <!DOCTYPE html>
    <html lang="en">
    <head>
    <meta charset="UTF-8">
    <title><?= $title; ?></title>
    <link rel="stylesheet" href="<?= base_url('/style.css');?>">
    </head>
    <body>
    <div id="container">
    <header>
    <h1>Layout Sederhana</h1>
    </header>
    <nav>
    <a href="<?= base_url('/');?>" class="active">Home</a>
    <a href="<?= base_url('/artikel');?>">Artikel</a>
    <a href="<?= base_url('/about');?>">About</a>
    <a href="<?= base_url('/contact');?>">Kontak</a>
    </nav>
    <section id="wrapper">
    <section id="main">

File app/view/template/footer.php

    </section>
    <aside id="sidebar">
    <div class="widget-box">
    <h3 class="title">Widget Header</h3>
    <ul>
    <li><a href="#">Widget Link</a></li>
    <li><a href="#">Widget Link</a></li>
    </ul>
    </div>
    <div class="widget-box">
    <h3 class="title">Widget Text</h3>
    <p>Vestibulum lorem elit, iaculis in nisl volutpat, malesuada
    tincidunt arcu. Proin in leo fringilla, vestibulum mi porta, faucibus felis.
    Integer pharetra est nunc, nec pretium nunc pretium ac.</p>
    </div>
    </aside>
    </section>
    <footer>
    <p>&copy; 2021 - Universitas Pelita Bangsa</p>
    </footer>
    </div>
    </body>
    </html>
    
Kemudian ubah file app/view/about.php seperti berikut.

    <?= $this->include('template/header'); ?>
    <h1><?= $title; ?></h1>
    <hr>
    <p><?= $content; ?></p>
    <?= $this->include('template/footer'); ?>

Selanjutnya refresh tampilan pada alamat http://localhost:8080/about

![Screenshot (79)](https://user-images.githubusercontent.com/65975985/122590491-d820ec80-d08b-11eb-91e1-d9d21e74325f.png)



