LAPORAN
UTS Administrasi Server (Cloud Computing II) 2025/2026
Dosen Pengampu : Mohamad Firdaus, M.Kom

Dimas Adriansah | 2388010027 | Informatika 6A

1. Tahap Provisioning & Security
   membuat instance EC2 di region Singapore (ap-southeast-1) menggunakan tipe t3.micro dan OS Ubuntu 24.04 LTS. Saya juga telah mengalokasikan dan menghubungkan Elastic IP 52.220.149.201 ke instance ini agar alamatnya tidak berubah.
   ![alt text](<Screenshot 2026-04-12 040203.png>)

2. Konfigurasi Keamanan (Security Group)
   saya telah mengunci akses SSH (Port 22) agar hanya bisa diakses dari IP publik saya sendiri dan membuka akses HTTP (Port 80) untuk public
   ![alt text](<Screenshot 2026-04-13 082657.png>)

3. Ketahanan & Monitoring Infrastruktur
   Untuk menjaga stabilitas, digunakan Elastic IP permanen agar alamat IP tidak berubah. Selain itu, Detailed CloudWatch Monitoring diaktifkan dengan sebuah alarm yang akan berstatus OK jika penggunaan CPU di bawah 80%.
   ![alt text](<Screenshot 2026-04-17 025712.png>)

4. Konfigurasi Web Server Nginx
   Web server Nginx diinstal melalui koneksi SSH (PuTTY). Layanan dipastikan berjalan (active) dan otomatis menyala saat server dijalankan (enabled).
   ![alt text](<Screenshot 2026-04-12 053424.png>)

5. Deployment Web CV
   Source code CV statis (HTML/CSS) dipindahkan dari laptop ke direktori /var/www/html menggunakan protokol SFTP melalui FileZilla. Konfigurasi kepemilikan (ownership) diatur menggunakan chown ke user www-data dan izin akses diatur menggunakan chmod agar website dapat diakses publik tanpa error 403.
   Link Akses Website (Elastic IP): 52.220.149.201
   ![alt text](screencapture-52-220-149-201-2026-04-13-22_52_27.png)
