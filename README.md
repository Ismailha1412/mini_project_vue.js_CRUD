# mini_project_vue.js_CRUD (Normalisasi Database)
A. Pengertian

Normalisasi Database adalah proses pengorganisasi suatu database untuk mengurangi redundansi data atau duplicate data sehingga data tersebut terstruktur dengan baik

Langkah-Langkah normalisasi yaitu
1. UNF (Unormalized Form)
2. 1NF (First Normal Form)
3. 2NF (Second Normal Form)
4. 3NF (Third Normal Form)
5. BCNF (Boyce-Codd Normal Form)
6. 4NF (Fourth Normal Form)
7. 5NF (Fifth Normal Form)

Namun normalisasi database hingga tahap 3NF sudah termasuk database yang terstruktur.

B. UNF (Unormalized Form)

UNF adalah bentuk tabel universal. Data dalam UNF biasanya berupa laporan yaitu data yang biasa diterima dan dibaca oleh manusia. Namun data ini tidak bisa dibaca oleh sistem. Oleh karena itu, perlu dilakukan normalisasi agar semua data bisa tersimpan di dalam database sehingga tidak ada data yang redundansi atau data yang sama (duplicate). Perhatikan contoh berikut:

![image](https://github.com/user-attachments/assets/141d959c-1556-4847-9670-bf6d7d1b193c)



Tabel di atas merupakan tabel UNF dimana masih terdapat kolom atau baris yang merge. Oleh karena iitu perlu dilakukan normalisasi tahap 1

C. 1NF (First Normal Form)

1NF dimaksudkan setiap baris dan kolom hanya berisi satu nilai. Adapun aturan dalam 1NF yaitu
1. Atribut name yang unik
2. Setiap atribut diisi oleh 1 data
3. Setiap baris harus berbeda dengan baris lainnya
4. Tidak ada repeating group

Dengan mengikuti aturan tersebut maka tabel di atas akan menjadi seperti ini

![image](https://github.com/user-attachments/assets/ba9db3e0-a39c-456a-a76e-e699f3266149)




Setelah itu, kita tentukan Primary Key. Primary Key haruslah unique. Jika kita hanya menggunakan NIM saja, maka kode ini akan muncul lagi dibawah. Hal ini berarti tidak unique. Oleh karena itu perlu dilakukan composite key dimana menggabungkan 2 atribut sehingga menjadi primary key yang unique dan tidak akan berulang kembali. Disini saya membuat Primary Key dari NIM dan Kode Matkul. Berikut tampilan Primary Key untuk tabel tersebut.

![image](https://github.com/user-attachments/assets/613bd55f-567d-4b77-9da8-6c803f7c8c14)




D. 2NF (Second Normal Form)

Tahap selanjutnya adalah mengubah tabel tersebut menjadi 2NF. Adapun aturan dalam 2NF yaitu
1. Tabel harus berada dalam bentuk 1NF
2. Semua atribut yag bukan Primary Key harus bergantung pada Primary Key

Setelah aturan tersebut dipenuhi kita harus memisahkan tabel tersebut ke beberapa tabel berdasarkan Primary Key. Tabel tersebut akan menjadi seperti di bawah ini
1. Tabel Matkul

   ![image](https://github.com/user-attachments/assets/98e3a688-7182-4fb0-ad37-9ec3aa98735c)



Seperti yang terlihat bahwa atribut Nama Matkul dan SKS bergantung kepada Kode Matkul

2. Tabel Mahasiswa

    ![image](https://github.com/user-attachments/assets/3f5b4099-ee43-4960-be52-3f5b4d526336)




Begitu juga halnya dengan atribut Nama, Prodi, dan Jurusan bergantung kepada atribut NIM.

3. Tabel Nilai

   ![image](https://github.com/user-attachments/assets/380b45aa-c3cd-4547-a200-e36df959f446)


Tabel ini menunjukkan bahwa Nilai bergantung pada Primary Key NIM dan Kode Matkul


E. 3NF (Third Normal Form)

Tahap berikutnya adalah mengubah tabel tersebut ke bentuk 3NF. Adapun syaratnya adalah
1. Tabel harus berbentuk 2NF
2. Semua atribut non-Primary Key tidak boleh bergantung pada atribut lainnya yang bukan Primary Key

Yang harus dilakukan adalah memisahkan atribut yang bergantung pada atribut non-Primary Key menjadi tabel lainnya. Dari tabel sebelumnya terlihat bahwa prodi bergantung pada Jurusan. Misalnya jika ada penambahan prodi baru, maka prodi tersebut tidak bisa ditambahkan karena atribut prodi harus bergantung pada NIM. Sedangkan NIM belum ada karena tidak ada mahasiswa. Oleh karena itu, kita harus memisahkan atribut ini menjadi tabel baru. Berikut tampilan tabel dalam bentuk 3NF
1. Tabel Matkul

   ![image](https://github.com/user-attachments/assets/2e05fdeb-81b8-4750-8711-54ffc482e59b)




2. Tabel Mahasiswa

   ![image](https://github.com/user-attachments/assets/21edddb6-3225-4ae4-a9f8-30d3af4a52bb)



3. Tabel Nilai

   ![image](https://github.com/user-attachments/assets/380b45aa-c3cd-4547-a200-e36df959f446)
   
5. Tabel Jurusan
   
   ![image](https://github.com/user-attachments/assets/9dc18684-bca1-42ba-9fe5-53f4d6e28bd2)


