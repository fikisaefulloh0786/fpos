# fpos
# Final Project OS Server & System Admin
## _Dokumentasi dari instalasi_
- Nama  : Muh Fiki Saefulloh
- Kelas : OS 2
- NIM   : 22.83.0786
## Latar Belakang

untuk menyelesaikan tugas final project mata kuliah OS Server dan System Admin ini saya memilih
untuk membuat layanan Web Server. Karena saat ini layanan web sangat banyak peminat.


## Bahan Yang diperlukan Untuk Membuat Web Server

Beberapa yang saya siapkan sebelum memulai pembuatan web server, saya membutuhkan beberapa tools, diantaranya :

- [Oracle VM 6.1](https://www.virtualbox.org/wiki/Download_Old_Builds_6_1) - Virtual Mechine
- [iso ubuntu ](https://ubuntu.com/download/server) - Ubuntu Server 20.04.6
- [Master FileZilla](https://filezilla-project.org/download.php?type=client) - FileZilla


## Report Update
12 September 2023   - Menentukan Jenis Layanan Apa Yang Hendak Di buat
15 September 2023   - Mulai Melakukan Instalasi Ubuntu Server
30 September 2023   - Mengistall FTP
1 Oktober 2023      - Menginstall Apache2
2 Oktober 2023      - PHP versi 8
16 Oktober 2023     - Membuat Repository Github
17 Oktober 2023     - Mengisi Repository Github

#### Menginstall FTP
FTP adalah protokol komunikasi standar yang digunakan untuk mentransfer dari berkas komputer dari sebuah peladen ke sebuah klien pada jaringan komputer.

Beberapa langkah yang saya lalui untuk menginstal Apache2 antara lain : 

Melakukan update repository dengan perintah :

```sh
sudo apt-get update
```

Setelah update repository selesai, iangkah selanjutnya adalah mengistall package vsftpd dengan perintah :

```sh
sudo apt-get install vsftpd
```

Selanjutnya masuk ke menu konfigurasi vsftpd, dengan perintah :

```sh
nano /etc/vsftpd.conf
```

Hiilangkan tanda pagar pada write_enable. dan simpan.

Lalu setelah selesai konfigurasi, restart vsftpd dengan perintah: 

```sh
systemctl restart vsftpd
```

Lalu periksa kembali status vsftp dengan perintah dibawah, jika berhasil dalam proses instalasi maka akan tertera active (running)

```sh
systemctl status vsftpd
```

Lalu coba masuk ke aplikasi FileZilla untuk memeriksa apakah bisa terhubung dengan cara mecoba menguplad file ke ubuntu server. Maukkan IP ubuntu server pada host, ussername dan password. 
lalu jika proses upload berhasil periksalah file yang dicopy tersebut secara default biasanya akan langsung mengarah ke file user, lalu cek dengan perintah 

```sh
ls /home/username/
```

#### Menginstall Apache2
Apache2 adalah server web yang dapat dijalankan di banyak sistem operasi (Unix, BSD, Linux, Microsoft Windows dan Novell Netware serta platform lainnya) yang berguna untuk melayani dan memfungsikan situs web. Protokol yang digunakan untuk melayani fasilitas web/www ini menggunakan HTTP.

Beberapa langkah yang saya lalui untuk menginstal Apache2 antara lain : 

Lalukan update repository terlebih dahulu dengan perintah :

```sh
sudo apt-get update
```

Untuk mengistall apache2  gunakan perintah seperti dibawah ini :

```sh
sudo apt-get install apache2
```

Jika proses instalasi telah selesai maka langkah selanjutnya ialah menjalankan apache2 dengan perintah :

```sh
sudo systemctl start apache2
```

Untuk mengechek apakah apache berhasil di instal dan berjalan, gunakan perintah seperti dibawah ini.

```sh
sudo systemctl status apache2
```

jika proses instalai berhasil maka akan tampak tulisan Active (Running).

Lalu setelah mengecek menggunakan prompt lalu buka brwoser lalu ketikkan ip ubuntu server anda, maka akan terdirect ke web ubuntu Apache2 Default Page

## Install PHP Versi 8

PHP adalah bahasa skrip yang umum digunakan untuk pengembangan web, karena dapat menyisipkan kode PHP ke dalam HTML. PHP juga dapat berinteraksi dengan server back-end atau database, seperti MySQL atau PostgreSQL. Untuk menjalankan skrip PHP di Ubuntu server, Anda membutuhkan interpreter PHP dan web server, seperti Apache2.

Peranan PHP di web server adalah sebagai berikut:
PHP dapat menghasilkan konten HTML yang bervariasi sesuai dengan permintaan pengguna, waktu, atau data lainnya1.
PHP dapat berinteraksi dengan database untuk menyimpan, mengambil, atau memanipulasi data.
PHP dapat mengontrol akses pengguna, mengirim dan menerima cookie, dan mengenkripsi data.
PHP dapat mengeksekusi kode di sisi server, sehingga tidak membebani browser pengguna

berikut langkah yang digunakan  untuk mengistal PHP8.0 dengan Apache:

Lalukan update repository terlebih dahulu dengan perintah :

```sh
sudo apt-get update
```

lalu masukkan perintah dibawah untuk mengistall php8.0

```sh
sudo apt install php8.0 libapache2-mod-php8.0
```

lalu restart apache2 dengan perintah

```sh
sudo systemctl restart apache2
```



[//]: # (These are reference links used in the body of this note and get stripped out when the markdown processor does its job. There is no need to format nicely because it shouldn't be seen. Thanks SO - http://stackoverflow.com/questions/4823468/store-comments-in-markdown-syntax)

   [dill]: <https://github.com/joemccann/dillinger>
   [git-repo-url]: <https://github.com/joemccann/dillinger.git>
   [john gruber]: <http://daringfireball.net>
   [df1]: <http://daringfireball.net/projects/markdown/>
   [markdown-it]: <https://github.com/markdown-it/markdown-it>
   [Ace Editor]: <http://ace.ajax.org>
   [node.js]: <http://nodejs.org>
   [Twitter Bootstrap]: <http://twitter.github.com/bootstrap/>
   [jQuery]: <http://jquery.com>
   [@tjholowaychuk]: <http://twitter.com/tjholowaychuk>
   [express]: <http://expressjs.com>
   [AngularJS]: <http://angularjs.org>
   [Gulp]: <http://gulpjs.com>

   [PlDb]: <https://github.com/joemccann/dillinger/tree/master/plugins/dropbox/README.md>
   [PlGh]: <https://github.com/joemccann/dillinger/tree/master/plugins/github/README.md>
   [PlGd]: <https://github.com/joemccann/dillinger/tree/master/plugins/googledrive/README.md>
   [PlOd]: <https://github.com/joemccann/dillinger/tree/master/plugins/onedrive/README.md>
   [PlMe]: <https://github.com/joemccann/dillinger/tree/master/plugins/medium/README.md>
   [PlGa]: <https://github.com/RahulHP/dillinger/blob/master/plugins/googleanalytics/README.md>
