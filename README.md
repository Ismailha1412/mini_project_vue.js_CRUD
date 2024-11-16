# mini_project_vue.js_CRUD (Normalisasi Database)
A. Pengertian

Normalisasi Database adalah proses pengorganisasi suatu database untuk mengurangi redundansi data atau duplicate data sehingga data tersebut bisa dibaca oleh sistem.

Langkah-Langkah normalisasi yaitu
1. UNF (Unormalized Form)
2. 1NF (First Normal Form)
3. 2NF (Second Normal Form)
4. 3NF (Third Normal Form)
5. BCNF (Boyce-Codd Normal Form)
6. 4NF (Fourth Normal Form)
7. 5NF (Fifth Normal Form)

B. UNF (Unormalized Form)

UNF adalah bentuk tabel universal. Data dalam UNF biasanya berupa laporan yaitu data yang biasa diterima dan dibaca oleh manusia. Namun data ini tidak bisa dibaca oleh sistem. Oleh karena itu, perlu dilakukan normalisasi agar semua data bisa tersimpan di dalam database sehingga tidak ada data yang redundansi atau data yang sama (duplicate). Perhatikan contoh berikut:
![image](https://github.com/user-attachments/assets/47198449-cef0-4b6f-b0d4-9cd183f14324)


Tabel di atas merupakan tabel UNF dimana masih terdapat kolom atau baris yang merge. Oleh karena iitu perlu dilakukan normalisasi tahap 1

C. 1NF (First Normal Form)

Langkah berikutnya adalah merubah tabel UNF menjadi 1NF. Adapun aturan dalam 1NF yaitu
1. Atribut name yang unik
2. Setiap atribut diisi oleh 1 data
3. Setiap baris harus berbeda dengan baris lainnya
4. Tidak ada repeating group

Dengan mengikuti aturan tersebut maka tabel di atas akan menjadi seperti ini
![image](https://github.com/user-attachments/assets/be166ae7-69b2-42dc-90c6-0df70821857f)


Setelah itu, kita tentukan Primary Key. Primary Key haruslah unique. Jika kita hanya menggunakan kode matkul saja atau NIM saja, maka kode ini akan muncul lagi dibawah. Hal ini berarti tidak unique. Oleh karena itu perlu dilakukan composite key dimana menggabungkan 2 atribut sehingga menjadi primary key yang unique dan tidak akan berulang kembali. Berikut tampilan Primary Key untuk tabel tersebut.
![image](https://github.com/user-attachments/assets/9ae26e7d-210e-4d18-bc30-74693c68578b)



D. 2NF (Second Normal Form)

Tahap selanjutnya adalah mengubah tabel tersebut menjadi 2NF. Adapun aturan dalam 2NF yaitu
1. Tabel harus berada dalam bentuk 1NF
2. Semua atribut yag bukan Primary Key harus bergantung pada Primary Key

Setelah aturan tersebut dipenuhi kita harus memisahkan tabel tersebut ke beberapa tabel berdasarkan Primary Key. Tabel tersebut akan menjadi seperti di bawah ini
1. Tabel Matkul

   ![image](https://github.com/user-attachments/assets/6630d44e-3d77-4dad-a1ae-9a9bd7f74fc5)

Seperti yang terlihat bahwa atribut Nama Matkul dan Nama Dosen bergantung kepada Kode Matkul

2. Tabel Mahasiswa

    ![image](https://github.com/user-attachments/assets/7e210e9a-5ddd-4045-b331-f1a337a0572d)

Begitu juga halnya dengan atribut Mahasiswa, Kode Jurusan, dan Nama Jurusan bergantung kepada atribut NIM

E. 3NF (Third Normal Form)

Tahap berikutnya adalah mengubah tabel tersebut ke bentuk 3NF. Adapun syaratnya adalah
1. Tabel harus berbentuk 2NF
2. Semua atribut non-Primary Key tidak boleh bergantung pada atribut lainnya yang bukan Primary Key

Yang harus dilakukan adalah memisahkan atribut yang bergantung pada atribut non-Primary Key menjadi tabel lainnya. Dari tabel sebelumnya terlihat bahwa Nama Jurusan bergantung pada Kode Jurusan. Oleh karena itu, kita harus memisahkan atribut ini menjadi tabel baru. Berikut tampilan tabel dalam bentuk 3NF
1. Tabel Matkul

   ![image](https://github.com/user-attachments/assets/f78d952b-57ac-4f84-91cc-ef6baafb6147)



2. Tabel Mahasiswa

   ![image](https://github.com/user-attachments/assets/06e4ae1b-c9b1-43c4-aabd-e121ad955af1)


3. Tabel Jurusan
   
   ![image](https://github.com/user-attachments/assets/03417f95-2881-48db-8def-aed8859d55e2)
