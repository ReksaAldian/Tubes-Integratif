# Tubes-Integratif

**Reksa Aldian Rahmandy Putra 1202192048 [  IT 02-01  ]**

-------

## Step by Step

------

1. Install Composer 
  
  ![8](https://user-images.githubusercontent.com/95138486/173070199-77a7ba25-6cc7-4038-9ddd-acd70d4be53d.PNG)

2. Download dan Install XAMPP (Install Composer terlebih dahulu agar dapat membuat HTDOCS)
  
![1](https://user-images.githubusercontent.com/95138486/173071765-1b0354cc-b385-4759-bea3-949945cd0083.PNG)

![2](https://user-images.githubusercontent.com/95138486/173071845-a040d3b9-49e5-4591-a200-e4c911b792e6.PNG)

![3](https://user-images.githubusercontent.com/95138486/173071882-d1fb12c1-a0c2-4cba-bff6-4ff2800ef535.PNG)

3. Setelah itu masuk ke CMD dan masuk ke direktori HTDOCS

![4](https://user-images.githubusercontent.com/95138486/173073121-e30e05dd-7d4f-4f50-9208-542116b0afc7.PNG)

4. Buat Folder dan Mulai Instalasi Laravel dengan Perintah 

```
composer create-project --prefer-dist laravel/laravel nama_projectmu
```

![5](https://user-images.githubusercontent.com/95138486/173073519-d80b876e-a3f3-437b-af0c-c8930fc087c8.PNG)

5. Selanjutnya ketik 

```
php artisan serve
```

![6](https://user-images.githubusercontent.com/95138486/173076913-721253bf-d407-45ce-8762-18629e9e81e5.PNG)

6. Jika muncul tulisan (Laravel development server started) langkah selanjutnya adalah membuka link yang telah disediakan oleh Laravel.

```
127.0.0.1:8000
```

![7](https://user-images.githubusercontent.com/95138486/173076427-3188539e-cec1-43a0-86c8-a9b4652fe557.PNG)

-------

## PHASE 2

------

1. Membuat Project

```
composer create=project --prefer-dist laravel/laravel project_anda
```
![1](https://user-images.githubusercontent.com/95138486/175770808-5c17798e-6035-4ac5-949e-30ff81d67351.PNG)

2. Mengubah DB_DATABASE di .env sesuai dengan nama database yang dibuat di phpmyadmin

![2](https://user-images.githubusercontent.com/95138486/175770970-e52a20c6-301a-4ca2-bd53-616e9e985dea.PNG)

3. Membuat RSS Table dan News Table

```
php artisan make:migration create_rss_table
php artisan make:migration create_news_table
```
![3](https://user-images.githubusercontent.com/95138486/175770984-ae473162-a53c-47ff-8413-8677a1f1d723.PNG)

4. Tambah kolom Name dan URL pada tabel RSS 

![4](https://user-images.githubusercontent.com/95138486/175771007-f68d3fa0-08a4-4d29-82f0-40981b2cb9fc.PNG)

5. Tambahkan kolom title, img_url, description, source_url,  dan rss_id pada tabel news, seperti pada gambar dibawah

![5](https://user-images.githubusercontent.com/95138486/175771053-f5938c28-31af-48f9-bda8-78aac522eab0.PNG)

6. Untuk Menjalankan Migrasi yang telah dibuat , Jalankan Perintah 

```
php artisan migrate
```

![6](https://user-images.githubusercontent.com/95138486/175771079-f35bc1e7-4a2a-4f10-a323-89ecc558947f.PNG)

7. Check pada PHP My Admin di Web Browser

![7](https://user-images.githubusercontent.com/95138486/175771118-815a976a-2cc9-4267-8146-1eb7838c306a.PNG)

8. Buat koneksi  model  ke database  dengan membuat seeder dan controller untuk tabel Rss dan News, dengan command

```
php artisan make:model Rss –seed –controller
```

![8](https://user-images.githubusercontent.com/95138486/175771146-285b8410-1c2c-46a8-a9ce-9a67c6849814.PNG)

9. Tambahkan script  ```protected $table = 'rss';``` pada file Rss.php dan ubah file RssSeeder.php serta DatabaseSeeder.php seperti pada gambar dibawah

![12](https://user-images.githubusercontent.com/95138486/175771333-3c150c18-d74c-4d01-95c6-eaec2a5c40d7.PNG)

![13](https://user-images.githubusercontent.com/95138486/175771358-f3ce1b08-f4ff-41b6-bc1a-e1b0c1cb6a15.PNG)

![14](https://user-images.githubusercontent.com/95138486/175771383-2aa650f6-f2eb-4654-9fa3-ef741d777f57.PNG)

10. Cek koneksi menggunakan perintah

```
php artisan db:seed
```

![9](https://user-images.githubusercontent.com/95138486/175771408-1a727c92-ed81-4812-90e6-7cbc2cba9ce0.PNG)

![15](https://user-images.githubusercontent.com/95138486/175771436-23f850c7-1d09-44e9-a48f-023251857acf.PNG)

```
php artisan make:model News --seed --controller
```

![16](https://user-images.githubusercontent.com/95138486/175771493-74372ecf-f76c-487b-9220-0a675b87e2ee.PNG)

Tambahkan script  ```protected $table = 'news';``` pada file News.php dan ubah file NewsController.php serta web.php seperti pada gambar dibawah.

![17](https://user-images.githubusercontent.com/95138486/175771535-f2cbc816-6635-4016-b8d4-7247ff0b13db.PNG)

![18](https://user-images.githubusercontent.com/95138486/175771547-cc8d3251-ac42-4c9c-bb9c-722a1618fb31.PNG)

![19](https://user-images.githubusercontent.com/95138486/175771564-bc4ff132-2191-42cf-8040-7e6535ceb686.PNG)

11. Check pada localhost ```http://127.0.0.1:8000/aggregate/1``` 

![20](https://user-images.githubusercontent.com/95138486/175771606-91c75609-986c-4f9b-8826-3cc3434d7aa5.PNG)

12. Buat logic untuk get rss data dengan id_rss, dengan script seperti pada gambar dibawah

![18](https://user-images.githubusercontent.com/95138486/175771646-d95877f4-7830-428f-88c1-ab8fe79f7a46.PNG)\

Parsing XML ke Object

![18](https://user-images.githubusercontent.com/95138486/175771692-83701a94-9a7b-442a-978d-c04ab08feaa7.PNG)

Hasil

![21](https://user-images.githubusercontent.com/95138486/175771669-29add64f-c7b7-416a-983a-e94a4199e596.PNG)

13. Check database pada tabel News 

![22](https://user-images.githubusercontent.com/95138486/175771761-a55ff325-8d2e-4cd7-b133-8f88c706e68c.PNG)

Hasil

Hasil Aggregate ke 2

![23](https://user-images.githubusercontent.com/95138486/175771782-7aaf359d-c042-4e22-8090-927a069c4ac2.PNG)

Hasil Aggregate ke 3

![24](https://user-images.githubusercontent.com/95138486/175771818-20fede71-5cd0-4df0-8eb4-a7ef88c2e651.PNG)

Hasil Aggregate ke 4

![25](https://user-images.githubusercontent.com/95138486/175771836-42fe1921-0438-48a1-9ff4-d5a6caf6b18d.PNG)


## TERIMA KASIH

------

























