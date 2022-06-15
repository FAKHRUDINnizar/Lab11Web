# Lab11Web

| Nama      | Fakhrudin Nizar|
| ----------- | ----------- |
| NIM     | 312010195      |
| Kelas   | TI.20.D.1    |

### 1. Buat folder baru dengan nama lab11_php_ci pada docroot webserver (htdocs)

![11](https://user-images.githubusercontent.com/101658076/173844854-9bebc630-ccc8-48ba-8ddc-6ae06f093c20.png)

### 2. Untuk mengaktifkan ekstentsi tersebut, melalu XAMPP Control Panel, pada bagian Apache klik Config -> PHP.ini

![12](https://user-images.githubusercontent.com/74331125/173868827-7707df64-8be0-4f6b-8aa6-21ab3d3496e5.png)

### 3. Pada bagian extention, hilangkan tanda ; (titik koma) pada ekstensi yang akan diaktifkan. Kemudian simpan kembali filenya dan restart Apache web server.

![13](https://user-images.githubusercontent.com/74331125/173868918-5db64385-2657-4563-ba8a-da1764347a22.png)

### 4. Instalasi Codeigniter 4

Untuk melakukan instalasi Codeigniter 4 dapat dilakukan dengan dua cara, yaitu cara manual dan menggunakan composer. Pada praktikum ini kita menggunakan cara manual.

- Unduh Codeigniter dari website https://codeigniter.com/download
- Extrak file zip Codeigniter ke direktori htdocs/lab11_php_ci.
- Ubah nama direktory framework-4.x.xx menjadi ci4.
- Buka browser dengan alamat http://localhost/lab11_php_ci/ci4/public/

![2](https://user-images.githubusercontent.com/74331125/173869035-9d0b886a-8282-406e-b890-52cef9c0a22e.png)

### 5. Menjalankan CLI (Command Line Interface)

![1](https://user-images.githubusercontent.com/101658076/173846989-069ae0d0-e8aa-42f6-b64b-2d1214f1b048.png)

### 6. Mengaktifkan Mode Debugging

Codeigniter 4 menyediakan fitur debugging untuk memudahkan developer untuk mengetahui pesan error apabila terjadi kesalahan dalam membuat kode program. Secara default fitur ini belum aktif. Ketika terjadi error pada aplikasi akan ditampilkan pesan kesalahan seperti berikut.

![3](https://user-images.githubusercontent.com/74331125/173869368-ac1167db-2945-4bb3-a22f-ed1b0ec1c39b.png)

- Semua jenis error akan ditampilkan sama. Untuk memudahkan mengetahui jenis errornya, maka perlu diaktifkan mode debugging dengan mengubah nilai konfigurasi pada environment variable CI_ENVIRONMENT menjadi development. Kemudian mengubah nama file env menjadi .env lalu setelah itu buka file tersebut dan ubah nilai variable CI_ENVORNMENT menjadi development. Setelah itu hapus tanda tagar (#) pada awal baris CI_ENVIRONMENT, ubah kode pada file app/Controller/Home.php hilangkan titik koma (;) pada akhir kode seperti berikut.

![image](https://user-images.githubusercontent.com/101658076/173849991-163a7560-0a9e-43e2-a9ce-914efd1f347f.png)

![4](https://user-images.githubusercontent.com/101658076/173850181-ec03043a-dbc9-4ce2-8f2b-9ad41641c073.png)

- Maka hasilnya akan terjadi error seperti berikut.

![image](https://user-images.githubusercontent.com/101658076/173850608-8bcc1080-43cb-48d6-98fb-224f1adc3a64.png)

### 7. Routing dan Controller

Router terletak pada file app/config/Routes.php. Pada file tersebut kita dapat mendefinisikan route untuk aplikasi yang kita buat.
Contoh: ```$routes->get('/', 'Home::index'); Kode tersebut akan mengarahkan rute untuk halaman home.

### 8. Membuat Route Baru.

![image](https://user-images.githubusercontent.com/101658076/173852365-04c17190-120a-4bb4-9048-866f7d801213.png)

- Untuk mengetahui route yang ditambahkan sudah benar, buka CLI dan jalankan perintah berikut. php spark routes

![6](https://user-images.githubusercontent.com/101658076/173852893-579dc1db-12d3-4d6d-8824-073a65f2d58d.png)

- Selanjutnya coba akses route yang telah dibuat dengan mengakses alamat url http://localhost:8080/about

![7](https://user-images.githubusercontent.com/74331125/173869623-b9651126-1118-4dc4-886d-4b96b1d5d52d.png)

Ketika diakses akan mucul tampilan error 404 file not found, itu artinya file/page tersebut tidak ada. Untuk dapat mengakses halaman tersebut, harus dibuat terlebih dahulu Contoller yang sesuai dengan routing yang dibuat yaitu Contoller Page.

### 9. Membuat Controller

Selanjutnya adalah membuat Controller Page. Buat file baru dengan nama page.php pada direktori Controller kemudian isi kodenya seperti berikut.

![image](https://user-images.githubusercontent.com/101658076/173853694-94006532-8372-480b-8eb2-2dcc1e83e0a7.png)

- Selanjutnya refresh Kembali browser, maka akan ditampilkan hasilnya yaitu halaman sudah dapat diakses.

![8](https://user-images.githubusercontent.com/74331125/173869794-38098f20-531e-440f-9b26-d47871628260.png)

### 10. Auto Routing

Secara default fitur autoroute pada Codeiginiter sudah aktif. Untuk mengubah status autoroute dapat mengubah nilai variabelnya. Untuk menonaktifkan ubah nilai true menjadi false.

Tambahkan method baru pada Controller Page seperti berikut

![image](https://user-images.githubusercontent.com/101658076/173854100-e6ea7818-4724-45d2-8ea3-29fb0b30296f.png)

- Method ini belum ada pada routing, sehingga cara mengaksesnya dengan menggunakan alamat: http://localhost:8080/page/tos

![9](https://user-images.githubusercontent.com/74331125/173869927-55664ef0-676c-4c03-8f13-63b7e9d086e6.png)

### 11. Membuat View

Selanjutnya adalam membuat view untuk tampilan web agar lebih menarik. Buat file baru dengan nama about.php pada direktori view (app/view/about.php) kemudian isi kodenya seperti berikut.

![image](https://user-images.githubusercontent.com/101658076/173855451-c76d7ac5-891b-4fa1-b70e-bc5d5c5b8ffd.png)

- Ubah method about pada class Controller Page menjadi seperti berikut:

![image](https://user-images.githubusercontent.com/101658076/173860665-b9e28b2a-a375-4919-913c-8b289de49995.png)

- Kemudian lakukan refresh pada halaman tersebut.

![10](https://user-images.githubusercontent.com/74331125/173870036-efca4ffd-82a5-4d80-a6d2-d6533b53d206.png)

### 12. Membuat Layout Web dengan CSS

Pada dasarnya layout web dengan css dapat diimplamentasikan dengan mudah pada codeigniter. Yang perlu diketahui adalah, pada Codeigniter 4 file yang menyimpan asset css dan javascript terletak pada direktori public.

Buat file css pada direktori public dengan nama style.css (copy file dari praktikum lab4_layout. Kita akan gunakan layout yang pernah dibuat pada praktikum 4.

![image](https://user-images.githubusercontent.com/101658076/173861298-37d10ee0-b723-4bf2-b6d1-a501dc3e7ff9.png)

 ### Kemudian buat folder template pada direktori view kemudian buat file header.php dan footer.php

- File app/view/template/header.php

![image](https://user-images.githubusercontent.com/101658076/173861535-a4629df7-0a6f-4451-a934-d7e778644fea.png)

- File app/view/template/footer.php

![image](https://user-images.githubusercontent.com/101658076/173861851-e0810c5f-55c4-4500-be8f-cefd69052fb8.png)

### Kemudian ubah file app/view/about.php seperti berikut.

![image](https://user-images.githubusercontent.com/101658076/173862184-2bce2306-c633-4f49-b154-701ccf6ef98a.png)

- Selanjutnya refresh tampilan pada alamat http://localhost:8080/about

![image](https://user-images.githubusercontent.com/74331125/173872049-5fd48a43-0591-4a83-8432-4e4fc8e606fb.png)

### Pertanyaan dan Tugas !
Lengkapi kode program untuk menu lainnya yang ada pada Controller Page, sehingga semua link pada navigasi header dapat menampilkan tampilan dengan layout yang sama.

- About 

![image](https://user-images.githubusercontent.com/101658076/173862746-12355701-a237-49ef-88e2-c8a77f6b3fd8.png)

![image](https://user-images.githubusercontent.com/101658076/173862866-0db89ce0-411e-437e-8640-f6c515fa1956.png)

- Hasil Browser

![image](https://user-images.githubusercontent.com/74331125/173873532-c81a4a34-6553-4272-9345-1eaed25ce703.png)

- Contact

![image](https://user-images.githubusercontent.com/101658076/173863161-db936bca-87b7-445b-8a0f-5b5d05e10185.png)

- Hasil Browser

![image](https://user-images.githubusercontent.com/74331125/173873684-829a2526-ef9f-48cf-b89a-a495361f2bcc.png)
