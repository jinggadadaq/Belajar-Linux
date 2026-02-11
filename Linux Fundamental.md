# **Pengaturan Dasar**

### **1\. Mengatur hostname (nama host server)**

`# hostnamectl set-hostname <hostname>`

Untuk mengganti nama host (hostname) sistem/server Anda.

### **2\. Mengatur zona waktu (timezone)**

`# timedatectl set-timezone Asia/Jakarta`

Untuk mengatur waktu sistem ke zona waktu Jakarta (WIB).

### **3\. Pengaturan jaringan (IP statis)**

`# vim /etc/netplan/00-installer-config.yaml`

`Contoh konfigurasi:`

`network:`  
  `ethernets:`  
    `enp0s3:`  
      `dhcp4: false`  
      `addresses: ['172.23.x.x/20']`  
      `routes:`  
        `- to: default`  
          `via: 172.23.0.1`  
      `nameservers:`  
        `addresses: ['8.8.8.8']`  
  `version: 2`

Mengatur IP statis, gateway, dan DNS pada Ubuntu Server menggunakan Netplan.

## **Perintah Dasar Linux**

### **1\. Menampilkan user yang sedang digunakan**

`# whoami`

Menampilkan nama user saat ini.

### **2\. Menampilkan siapa saja user yang login**

`# who`

Menampilkan daftar semua user yang sedang login ke sistem.

### **3\. Menampilkan hostname server**

`# hostnamectl`

Menampilkan detail nama host dan informasi sistem lainnya.

### **4\. Menampilkan tanggal dan waktu**

`# timedatectl`

Menampilkan dan mengatur waktu sistem.

## **Asesment Server**

### **1\. Menampilkan sistem operasi yang digunakan**

`# cat /etc/os-release`

Menampilkan informasi OS Linux.

### **2\. Menampilkan nama kernel**

`# uname`

Menampilkan nama sistem kernel.

### **3\. Menampilkan info prosesor**

`# lscpu`

Menampilkan informasi CPU/arsitektur.

### **4\. Menampilkan penggunaan RAM**

`# free -h`

Menampilkan penggunaan memori secara ringkas (dalam format human-readable).

### **5\. Menampilkan partisi/penyimpanan**

`# lsblk`

Menampilkan daftar partisi disk.

`# df -h`

Menampilkan penggunaan disk (format terbaca manusia).

# **Manajemen File & Direktori**

## **Manajemen Direktori**

### **1\. Membuat direktori**

`# mkdir idn`

Membuat folder baru bernama `idn`.

### **2\. Masuk dan keluar direktori**

`# cd idn`

Masuk ke direktori `idn`.

### 3\. Menampilkan isi direktori

`# ls`

Melihat isi folder.

### 4\. Menampilkan path lokasi saat ini

`# pwd`

Menampilkan direktori aktif saat ini.

### 5\. Menghapus direktori kosong

`# rmdir idn`

Menghapus folder `idn` jika kosong.

# **Manajemen File**

### **1\. Membuat file kosong**

`# touch file1.txt`

Membuat file kosong bernama `workshop`.

### **2\. Membuat file berisi teks**

`# echo "Hello World" >> file2.txt`

Menambahkan "Hello World" ke file `idn_workshop`.

### **3\. Menampilkan isi file**

`# cat file2.txt`

Menampilkan isi seluruh file.

### **4\. Menampilkan 10 baris pertama/terakhir file** 

`# head /folder/file tujuan`

Menampilkan 10 baris awal file syslog.

`# tail /folder/file tujuan`

Menampilkan 10 baris akhir.

### **5\. Menghapus file**

`# rm file1.txt`

Menghapus file bernama `workshop`.

### **6\. Menyalin file atau folder**

`# cp idn_workshop ~/sysadmin`

Menyalin file ke direktori lain.

### 7\. **Memindahkan atau mengubah nama file/folder**

`# mv idn_workshop nama_peserta`

Memindahkan/rename file.

# **Manajemen User & Grup**

## **User**

### **1\. Membuat user baru**

`# adduser nama_peserta`

Membuat user sistem baru.

### **2\. Melihat daftar user**

`# cat /etc/passwd`

Menampilkan seluruh user.

### **3\. Mengubah password user**

`# passwd nama_user`

Mengatur atau mengubah password user.

### **4\. Mengubah ID user atau menambahkan ke grup**

`# usermod -u 10000 jingga`  
`# usermod -aG nama_group nama_user`

Mengubah UID user dan menambahkan user ke grup.

## **Grup**

### **1\. Membuat grup baru**

`# groupadd idn_workshop`

Membuat grup `idn`.

### **2\. Melihat daftar grup**

`# cat /etc/group`

Melihat seluruh grup.

### **3\. Mengganti nama grup**

`# groupmod -n nama_baru nama_lama`

Mengubah nama grup.

### **4\. Menghapus grup**

`# groupdel nama_grup`

Menghapus grup tertentu.

## **Hak Akses & Kepemilikan**

### **1\. Mengatur hak akses file**

`# chmod 640 file_name`

Memberi izin baca & tulis ke owner, baca ke grup, tidak ada akses untuk lainnya.

### **2\. Mengubah kepemilikan file**

`# chown nama_user file_name`

Mengganti pemilik file.

### **3\. Mengubah grup dari file**

`# chgrp nama_grup file_name`

Mengganti grup pemilik file.

## **Apa Itu WebServer**

**Web Server** adalah software yang digunakan untuk menyimpan, memproses, dan mengirimkan halaman web ke client melalui jaringan. **Web Server** menggunakan protokol **HTTP (80)** atau **HTTPS (443)**.

## **Installation**

Jadi disini kita akan melakukan instalasi webserver dengan menggunakan apache,apa itu apache merupakan sebuah perangkat lunak server web gratis dan open-source yang populer, dikelola oleh Apache Software Foundation.

Langkah-langkah instalasi:

1. Update si ubuntunya lalu install sekalian saja si apache2-nya:  
   * `# apt update -y && apt upgrade -y`  
   * `# apt install apache2 -y`  
2. Lalu setelah Update dan instalasinya selesai selanjutanya verifikasi service apache2 apakah dia sudah berjalan.  
   * `# systemctl status apache2`  
3. Jika statusnya sudah active kita bisa coba akses IP server kita masuk ke browser bisa menggunakan chrome,firefox,microsoft egde dll.  
   * http://(IP server).

## **1\. Install paket**

`# apt install mysql-server php php-mysql libapache2-mod-php php-cli php-curl php-gd php-mbstring php-xml php-xmlrpc php-zip unzip wget -y`

* **Apache2** → web server.  
* **MySQL Server** → database.  
* **PHP & modul** → untuk menjalankan WordPress.

## **2\. Konfigurasi MySQL**

Jalankan:

`# mysql_secure_installation`

Ikuti:

* Set password root MySQL (jika belum).  
* Remove anonymous users: **Y**  
* Disallow root login remotely: **Y**  
* Remove test database: **Y**  
* Reload privileges: **Y**

Login ke MySQL:

`# mysql`

Buat database & user WordPress:

`# CREATE DATABASE wordpress_db;`  
`# CREATE USER 'wpuser'@'localhost' IDENTIFIED BY 'P@ssw0rd2025';`  
`# SELECT User, Host FROM mysql.user;`  
`# GRANT ALL PRIVILEGES ON *.* TO 'wpuser'@'localhost';`  
`# FLUSH PRIVILEGES;`  
`# EXIT;`

## **3\. Download & install WordPress**

Pindah ke folder web:

`# cd /var/www/html`  
`# rm index.html`

Download:

`# wget https://wordpress.org/latest.tar.gz`

Ekstrak:

`# tar -xvzf latest.tar.gz`

Pindahkan isi folder **wordpress** ke `/var/www/html`:

`# mv wordpress/* .`

Hapus file yang tidak perlu:

`# rm -rf wordpress latest.tar.gz`

## **4\. Set permission**

`# chown -R www-data:www-data /var/www/html/`  
`# chmod -R 755 /var/www/html/`

## **5\. Konfigurasi Apache untuk WordPress**

Buat VirtualHost:

`# vim /etc/apache2/sites-available/wordpress.conf`

Isi:

`<VirtualHost *:80>`  
    `ServerAdmin admin@example.com`  
    `DocumentRoot /var/www/html`  
    `ServerName localhost`

    `<Directory /var/www/html>`  
        `Options Indexes FollowSymLinks`  
        `AllowOverride All`  
        `Require all granted`  
    `</Directory>`

    `ErrorLog ${APACHE_LOG_DIR}/error.log`  
    `CustomLog ${APACHE_LOG_DIR}/access.log combined`  
`</VirtualHost>`

Simpan, lalu jalankan:

`# a2ensite wordpress.conf`  
`# a2enmod rewrite`  
`# systemctl restart apache2`

## **6\. Konfigurasi WordPress**

Salin file konfigurasi contoh:

`# cp /var/www/html/wp-config-sample.php /var/www/html/wp-config.php`

Edit:

`# vim /var/www/html/wp-config.php`

Ubah bagian database:

`define( 'DB_NAME', 'wordpress_db' );`  
`define( 'DB_USER', 'wpuser' );`  
`define( 'DB_PASSWORD', 'P@ssw0rd2025' );`  
`define( 'DB_HOST', 'localhost' );`

Simpan

## **7\. Akses WordPress**

Buka browser → `http://IP-SERVER/`  
Lanjutkan wizard instalasi WordPress.

