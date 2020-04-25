Visualisasi data merupakan representasi visual dan teknik interaksi dengan memanfaatkan indera penglihatan manusia yang diolah dalam pikiran sehingga memungkinkan pengguna dapat melihat, menjelajahi, dan memahami sejumlah besar informasi sekaligus.Visualisasi informasi membantu pengguna untuk memperoleh pengetahuan melalui berbagai macam variabel data yang disajikan dalam bentuk grafis.
### Tahapan Visualisasi
### 1. Menentukan Data Row
Data row dapat bersumber dari berbagai macam sumber daya terstruktur misalnya sql, json, excel, csv, atau xml. Data row tersebut harus disesuaikan dengan framework pengembangan yang kita gunakan. Misalnya jika kita menggunakan Codeigniter sebagai framework pengembangan maka data row harus tersedia dalam format array PHP. Sumber data dapat berupa sql database atau JSON file. Disini akan menggunakan file json yang telah disiapkan sebelumnya, yaitu data sales.json. File ini disimpan 

### 2. Menyusun Problem Statement
Kita perlu untuk menyusun problem statemen yang dapat menggambarkan informasi apa saja yang akan disampaikan kepada pengguna. Seperti dibawah ini :
* Bagaimana data penjualan berdasarkan region.
* Bagaimana data penjualan berdasdarkan sales.
* Bagaimana data penjualan berdasarkan produk.
* Bagaimana data penjualan berdasarkan bulan di tahun tertentu.
Tambahan Problem Statement : 
* Pendapatan Bulanan dari Hasil Penjualan
* Harga rata-rata per item tertinggi

### 3. Membuat data tabel dalam format cross tabulation
Langkah berikutnya adalah menyusun cross tabulation berdasarkan baris data dan problem statement. Satu probem statement akan menghasilkan satu cross tabulation. Mungkin tahap ini akan memerlukan algoritma untuk membuat data row menjadi format cross tabulation yang kita inginkan.

### 4. Menentukan teknik visualisasi
Teknik visualisasi merupakan bentuk visual yang digunakan untuk menampilkan data. Secara umum teknik visualisasi terdiri dari Pie Chart (diagram lingkaran), Bar Chart (diagram batang), line chart (diagram garis), atau gabungan antara bar chart dan line chart. Pada tahap ini, kita menganisa teknik yang tepat untuk setiap cross tabulation yang sudah dibuat pada tahap sebelumnya.

### 5. Menentukan layout
Tahap layouting merupakan tahap menentukan posisi dari setiap visualisasi pada layar utama visualisasi agar pengguna dapat menerima sejumlah besar informasi sekaligus. Oleh sebab itu halaman visualisasi sebaiknya merupakan single page sehingga aspek penyampaian informasi secara sekaligus dapat terpenuhi

## Membuat Grafik
### 1. Data Pendapatan Bulanan dari Hasil Penjualan
### 2. Data Harga rata-rata per item tertinggi 
LANGKAH - LANGKAH : 
* Menyusun layout dalam Codeigniter. Update file visin.php dengan menambahkan kode berikut:
<img width="431" alt="1" src="https://user-images.githubusercontent.com/56018831/80267078-2a1add80-8654-11ea-8b5a-e3070002da51.png">

* Memvisualkan data menggunakan Google Charts. Tambahkan beberapa function untuk membuat grafik, yang ditambahkan pada file controllers/Visin.php adalah seperti berikut:
<img width="494" alt="2" src="https://user-images.githubusercontent.com/56018831/80267727-56842900-8657-11ea-87c9-7a3663c0f62c.png">

<img width="505" alt="3" src="https://user-images.githubusercontent.com/56018831/80267722-5552fc00-8657-11ea-8b61-e89261166aa8.png"> 

<img width="500" alt="4" src="https://user-images.githubusercontent.com/56018831/80267770-9814d400-8657-11ea-976b-47a8ff3aedbc.png">

* Selanjutnya update kode Javascript yang ada pada file view/visin.php menjadi seperti berikut ini:
  - Menambahkan variable 
<img width="366" alt="5" src="https://user-images.githubusercontent.com/56018831/80267920-6f410e80-8658-11ea-81f9-908365e96813.png">

* Kode di atas menunjukkan bahwa proses menggambar grafik dilakukan oleh fungsi drawChart(dataArray,type,container). Teknik ini dipakai untuk mengurangi penulisan kode secara berulang. Parameter pada fungsi drawChart() diantaranya adalah:
* dataArray
Data dalam format Array yang diperoleh dari hasil parsing data yang diperoleh dari variabel PHP. Proses parsing data dilakukan menggunakan Javascript menggunakan fungsi JSON.parse().
* type
Tipe chart yang digunakan (‘pie', ‘bar', ‘column')
* container
Nama id dari elemen yang akan digunakan sebagai container grafik. Menampilkan data harga dan penjualan dilakukan oleh kode berikut:
<img width="346" alt="6" src="https://user-images.githubusercontent.com/56018831/80268087-89c7b780-8659-11ea-8cd3-0694f9daf408.png">

Jalankan browser maka akan terlihat tampilan seperti berikut:

<img width="917" alt="7" src="https://user-images.githubusercontent.com/56018831/80268226-49b50480-865a-11ea-9fcc-0908b3e5a174.png">


Beberapa contoh grafik yang telah dibuat sebelumnya : 
<img width="904" alt="8" src="https://user-images.githubusercontent.com/56018831/80268262-913b9080-865a-11ea-8b8a-420387dd6f2a.png">
<img width="909" alt="9" src="https://user-images.githubusercontent.com/56018831/80268263-91d42700-865a-11ea-9913-9618ccaef63f.png">
