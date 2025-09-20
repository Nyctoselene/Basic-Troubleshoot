# Basic Troubleshooting di MikroTik

Kali ini saya akan membahas solusi untuk beberapa masalah yang sering ditemukan pada saat pertamakali melakukan konfig pada MikroTik
 
**A. Tidak bisa login ke mikrotik**\
 ⦁ Cek apakah kabel UTP sudah terpasang dengan benar\
 ⦁ Pastikan anda mendengar suara “klik’ saat Anda memasang kabel UTP baik itu kabel UTP untuk ISP, RouterBoard maupun untuk PC klien.\

**B. Tidak bisa Akses menggunakan WInBox**\
 ⦁ Router dalam Keadaan Default Configuration\ 
  Apa itu default configuration? Default configuration adalah konfigurasi awal yang disediakan saat kita membeli MikroTik. Pada ether1 dalam Default Configuration biasanya terdapat semacam firewall yang memblock MNDP (MikroTik Network Discovery Protocol) yang membuat WinBox tidak dapat menemukan RouterBoard Anda. Default Configuration juga biasanya juga terjadi setelah RouterBoard direset. Baik itu Hard Reset (melakukan reset langsung pada Router) maupun Soft-Reset (melakukan reset melalui WinBox). Saat melakukan Hard-Reset RouterBoard cenderung akan kembali ke Default Configuration. Lalu saat melakukan Soft-Reset Lupa untuk mencentang menu “No Default Configuration”. Solusinya adalah anda dapat melakukan Soft-Reset lalu Centang menu “No Default Configuration” seperti dibawah ini

![Reset](Reset.png)
 
  ⦁	Neighbor Discovery Tidak Aktif\
   Kemungkinan kedua hampir mirip dengan kasus nomor satu Neighbor Discovery yang tidak aktif akan menyebabkan RouterBoard tidak terdeteksi pada Winbox. Walaupun begitu anda masih bisa terhubung menggunakan IP atau MAC Address jika Anda ingat. Namun jika tidak ada IP pada RouterBoard atau Anda lupa, anda dapat mereset RouterBoard Anda. Cara untuk disable Neighbor Discovery adalah melalui menu IP > Neighbor > Discovery Setting lalu pilih menu all

![Neighbor](Neighbor.png)
 
  ⦁	Pastikan MAC-Server aktif\
   MAC_Server adalah suatu fitur eksklusif yang hanya ada pada WInBox dimana Anda dapat terkoneksi dengan RouterOS menggunakan MAC-Address. Cara memastikannya adalah buka menu Tools > MAC-Server > Mac Winbox Server lalu pastikan Allowed Interface list nya adalah all
 
![MAC](MAC.png)

  ⦁	Interface Virtual masih Enable\
   Interface Virtual bisa berasal dari vmware atau virtualbox misalnya. Untuk mendisablenya Anda dapat masuk ke menu Open Network & Sharing center dari Control Panel

**C. Tidak bisa akses melalui Telnet**\
  ⦁ Pastikan Port 23 Aktif\
   Telnet Memiliki Port Default yaitu 23, jadi pastikan terlebih dahulu port 23 di Mikrotik dalam keadaan enable. Kita bisa mengecek nya melalui command ip service print pada terminal WinBox (Jika Sudah login WinBox

**D. Tidak bisa akses melalui SSH**\
  ⦁ Pastikan Port 22 Aktif\
   SSH Memiliki Port Default yaitu 22, jadi pastikan terlebih dahulu port 22 di Mikrotik dalam keadaan enable. Kita bisa mengecek nya melalui command ip service print pada terminal WinBox (Jika Sudah login WinBox.

**E. Perangkat mikrotik/RB error [indikator lampu port ethernet menyala semuanya]**\
  ⦁ Ganti Power Supply\
   Masalah indikator lampu menyala semua bisa jadi karena Power Supply yang kecil atau board Anda tidak bekerja dengan baik tegangan tertentu. Pastikan Power Supply sesuai dengan kebutuhan MikroTik.

**D. MikroTik selalu restart**\
  ⦁ Upgrade versi RouterBoardOS\
   Versi RouterBoardOS yang lawas dapat menjadi salah satu penyebab MikroTik selalu restart, maka upgrade versi RouterBoard OS anda dengan cara berikut:\
   1. Tekan dan tahan tombol reset;\
   2. Colokkan perangkat ke sumber daya;\
   3. Anda hanya perlu menahan tombol reset selama 1-2 detik dan bootloader cadangan akan dimuat;\
   4. Ketika perangkat telah dimuat, buka CLI dan jalankan perintah untuk mengupgrade bootloader Anda “/system routerboard upgrade”\

# Kesimpulan: 
⦁	Usahakan jangan panik ketika menemukan masalah seperti diatas, periksa kembali apakah anda sudah melakukan semuanya dengan benar\
⦁	Hard reset selalu menjadi pilihan terakhir semua masalah\
dapat saya sampaikan, mohon maaf apabila ada salah kata atau kekurangan dalam penyampaian. Akhir kata, Wassalam

