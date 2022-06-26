# Lab11Web

| Nama      | Fakhrudin Nizar|
| ----------- | ----------- |
| NIM     | 312010195      |
| Kelas   | TI.20.D.1    |
| Matkul  | Pemrograman Web |

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

### *PRAKTIKUM 12: FRAMEWORK LANJUTAN (CRUD)*

### Langkah-langkah Praktikum

### 1. Untuk memulai membuat aplikasi CRUD sederhana, yang perlu disiapkan adalah database server menggunakan MySQL. Pastikan MySQL Server sudah dapat dijalankan melalui XAMPP.

![image](https://user-images.githubusercontent.com/74331125/174431451-61f285bd-b11b-4fb8-98a5-a92e6de9e937.png)

### 2. Konfigurasi Koneksi Database

Selanjutnya membuat konfigurasi untuk menghubungkan dengan database server. Konfigurasi dapat dilakukan dengan dua cara, yaitu pada file `app/config/database.php` atau menggunakan `file .env`. Pada praktikum ini kita gunakan konfigurasi pada file `.env.` Konfigurasi dapat dilakukan dengan cara mengubah beberapa kode pada file `htdocs\lab11_ci\ci4\.env`. Dan hilangkan tanda pagar `#` didepan

![image](https://user-images.githubusercontent.com/74331125/174431735-d4609c4f-57c3-48a4-885b-87365dc73e8c.png)

### 3. Membuat Model

Selanjutnya adalah membuat Model untuk memproses data Artikel. Buat file baru pada direktori `app/Models` dengan nama `ArtikelModel.php`

![image](https://user-images.githubusercontent.com/74331125/174431766-4c2555fa-aa32-40ad-ab53-6bdcd08e03dc.png)

### 4. Membuat Controller

Buat Controller baru dengan nama `Artikel.php` pada direktori `app/Controllers.`

![image](https://user-images.githubusercontent.com/74331125/174431790-9b7abbf5-edce-4f95-aad6-6ff305c97576.png)

### 5.  Membuat View

Buat direktori baru dengan nama `artikel` pada direktori `app/views`, kemudian buat file baru dengan nama `index.php`

![image](https://user-images.githubusercontent.com/74331125/174431959-9b3bf0ae-ed59-4997-af3a-ce2708c53c53.png)

- Selanjutnya buka browser kembali, dengan mengakses url http://localhost:8080/artikel

![image](https://user-images.githubusercontent.com/74331125/174432007-b8c4812e-e174-4c37-b832-fb19b0ef5ebf.png)

- jika Belum ada data yang diampilkan. Kemudian coba tambahkan beberapa data pada database agar dapat ditampilkan datanya.

![image](https://user-images.githubusercontent.com/74331125/174432018-affd4b4b-3098-4df8-a5d5-6a83a6ff7bbb.png)

- Refresh kembali browser, sehingga akan ditampilkan hasilnya.

![image](https://user-images.githubusercontent.com/74331125/174432041-179b74e8-25da-4851-8173-ff1d47aa1c1c.png)

### 6.  Membuat Tampilan Detail Artikel

Tampilan pada saat judul berita di klik maka akan diarahkan ke halaman yang berbeda. Tambahkan fungsi baru pada `Controller Artikel` dengan nama `view().`

![image](https://user-images.githubusercontent.com/74331125/174432126-dbe64fe2-f197-44c1-aa35-5ecd356b990a.png)

### 7.  Membuat View Detail

Buat view baru untuk halaman detail dengan nama `app/views/artikel/detail.php.`

![image](https://user-images.githubusercontent.com/74331125/174432163-5fd9d9a0-ea47-4690-b2eb-92cb166cb80a.png)

### 8. Membuat Routing untuk artikel detail

Buka Kembali file `app/config/Routes.php`, kemudian tambahkan routing untuk `artikel detail`.

![image](https://user-images.githubusercontent.com/74331125/174432195-3bc22a44-734e-4045-8ea9-87ed866bfaf3.png)

- Kemudian Refresh kembali

![image](https://user-images.githubusercontent.com/74331125/174432226-48cf9fd6-77b2-4549-8ab9-8ac147459705.png)

### 9. Membuat Menu Admin

- Menu admin adalah untuk proses `CRUD` data `artikel`. Buat method baru pada `Controller Artikel` dengan nama `admin_index()`.

![image](https://user-images.githubusercontent.com/74331125/174432263-247a56fa-abf8-43c3-8026-c0db6de5a179.png)

- Selanjutnya buat view untuk tampilan admin dengan nama `admin_index.php`

![image](https://user-images.githubusercontent.com/74331125/174432278-73eba2a3-79d7-4dd4-a5f2-3295c05270ec.png)

- membuat file `admin_header.php`

![image](https://user-images.githubusercontent.com/74331125/174432297-29714d64-8180-4572-8bfd-6e523a52e37e.png)

- Membuat file admin_footer.php

![image](https://user-images.githubusercontent.com/74331125/174432322-ad582f0d-f7aa-42fa-bbdc-021bc3589444.png)

- Membuat admin.css

![image](https://user-images.githubusercontent.com/74331125/174432353-95a4272b-2554-49ff-8b7d-cc94fffae952.png)

![image](https://user-images.githubusercontent.com/74331125/174432359-388557a7-28e3-434c-912d-d113bec21cdc.png)

![image](https://user-images.githubusercontent.com/74331125/174432364-8fd7dce7-21bb-488c-a099-f0807c39231c.png)

![image](https://user-images.githubusercontent.com/74331125/174432370-6b6dab39-62b3-4aed-9cb1-baa925f71c06.png)

- Refresh browser

![image](https://user-images.githubusercontent.com/74331125/174432402-58f6be5a-863e-49c0-813b-c56e2d9362bd.png)

- Tambahkan routing untuk menu admin seperti berikut:

![image](https://user-images.githubusercontent.com/74331125/174432414-fedd4927-3ba6-44c2-94eb-e96608147549.png)

- Akses menu admin dengan url http://localhost:8080/admin/artikel

![image](https://user-images.githubusercontent.com/74331125/174432443-414cbbd5-e145-415f-89e8-1a87e2065efc.png)

### 10. Menambah Data Artikel

- Tambahkan `fungsi/method` baru pada `Controller Artikel` dengan nama `add()`.

![image](https://user-images.githubusercontent.com/74331125/174432464-3b56a541-5938-4c48-ba58-315fbd5cd61d.png)

- Kemudian buat view untuk form tambah dengan nama `form_add.php`

![image](https://user-images.githubusercontent.com/74331125/174432477-cb0fa9be-daa6-4f5b-b5f3-b0abb54efbb7.png)

- Setelah itu klik `tambah artikel` maka tampilan nya seperti berikut.

![image](https://user-images.githubusercontent.com/74331125/174432538-57ac6157-90a6-4a68-904c-c440a1ffe2d2.png)

### 12. Mengubah Data

- Tambahkan `fungsi/method` baru pada `Controller Artikel` dengan nama `edit()`.

![image](https://user-images.githubusercontent.com/74331125/174432555-adf80e43-ee0b-4775-88d2-c693e5c88364.png)

- Kemudian buat `view` untuk form tambah dengan `nama form_edit.php`

![image](https://user-images.githubusercontent.com/74331125/174432570-a0d9a30a-0705-4c57-933c-7ad80d916146.png)

- Hasil Browser

![image](https://user-images.githubusercontent.com/74331125/174432584-614c427d-66cf-4c2b-89dd-581a21163b21.png)

### 13. Menghapus Data

![image](https://user-images.githubusercontent.com/74331125/174432598-5fdab169-02b4-47db-bc74-e8ffcb44762f.png)

### *Praktikum 13 : Framework Lanjutan (Modul Login)*

### 1. Membuat Tabel User

![image](https://user-images.githubusercontent.com/74331125/175804409-76b7d7ba-2358-4b8f-bacf-7fa1d454019c.png)

### 2. Membuat Model User

- Selanjutnya adalah membuat Model untuk memproses data Login. Buat file baru pada direktori `app/Models` dengan nama `UserModel.php`

![image](https://user-images.githubusercontent.com/74331125/175804463-9d48e204-057e-43ec-a57a-f5e839060fd6.png)

### 3. Membuat Controller User

- Buat Controller baru dengan nama `User.php` pada direktori `app/Controllers`. Kemudian tambahkan `method index()` untuk menampilkan daftar `user`, dan `method login()` untuk proses `login`.

![image](https://user-images.githubusercontent.com/74331125/175804561-d39eb515-4285-4d82-bf3d-442d7613c91a.png)
![image](https://user-images.githubusercontent.com/74331125/175804662-34b16e69-f813-4e33-859c-f159a7d11448.png)

### 4. Membuat View Login

- Buat direktori baru dengan nama `user` pada direktori `app/views`, kemudian buat file baru dengan nama `login.php`.

![image](https://user-images.githubusercontent.com/74331125/175804764-7e1cea15-e181-49a9-b060-512ee99f9ba6.png)

### 5. Membuat Database Seeder

- Database seeder digunakan untuk membuat data `dummy`. Untuk keperluan ujicoba modul `login`, kita perlu memasukkan data `user` dan `password` kedaalam database. Untuk itu buat database seeder untuk `tabel user`. Buka `CLI`, kemudian tulis perintah berikut:

![image](https://user-images.githubusercontent.com/74331125/175804870-7e455047-f04d-428b-baa7-406dc4c57178.png)

### 6. Selanjutnya, buka file `UserSeeder.php` yang berada di lokasi direktori `/app/Database/Seeds/UserSeeder.php` kemudian isi dengan kode berikut:

![image](https://user-images.githubusercontent.com/74331125/175804913-220ac38a-2a4c-4484-9ad3-1928925a6c9f.png)

- Selanjutnya buka kembali CLI dan ketik perintah berikut:

![image](https://user-images.githubusercontent.com/74331125/175804936-864e156f-7818-4f6c-b692-b7e3da7c22b9.png)

- Selanjutnya uji coba Login dengan membuka url `http://localhost:8080/user/login` seperti berikut:

![image](https://user-images.githubusercontent.com/74331125/175804999-ece7c614-b9f1-4455-9877-c8c43c45284d.png)

### 7. Menambahkan Auth Filter

- Selanjutnya membuat filer untuk halaman `admin`. Buat file baru dengan nama `Auth.php` pada direktori `app/Filters`.

![image](https://user-images.githubusercontent.com/74331125/175805034-ea8e1c7c-9d90-4410-9195-1fe84ffe86d4.png)

- Selanjutnya buka file `app/Config/Filters.php` tambahkan kode berikut:

![image](https://user-images.githubusercontent.com/74331125/175805079-7c966776-4939-4dbc-9586-3bee93cf655a.png)

- Selanjutnya buka `file app/Config/Routes.php` dan sesuaikan kodenya.

![image](https://user-images.githubusercontent.com/74331125/175805098-db615f89-c0d7-41a8-acfd-c7f222f8cdbd.png)

### 8. Percobaan Akses Menu Admin

- Buka url dengan alamat http://localhost:8080/user/login ketika alamat tersebut diakses maka, akan dimuculkan halaman login.

![image](https://user-images.githubusercontent.com/74331125/175805130-c3d6eed5-019f-49ed-8044-58d415f4ebfe.png)

### 9. Fungsi Logout

- Tambahkan method logout pada `Controller User` seperti berikut:

![image](https://user-images.githubusercontent.com/74331125/175805183-d42cd351-2076-4d6d-8041-facdb077f764.png)
