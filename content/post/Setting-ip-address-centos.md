---
title: "Setting IP Address di CentOS"
date: 2019-06-06
categories:
- Linux
tags:
- Linux
- CentOS
- Server
keywords:
- linux
- server
- centos
---
<!--more-->

![Logo](https://4.bp.blogspot.com/-RUoyHKZetNQ/V7WNn6yttqI/AAAAAAAACMo/iIiGrs8Y0nYR_MGu_DKrzIXbVaVmel-5wCLcB/s1600/Localhost.png)


Pada tulisan kali ini saya akan menuliskan step by step cara setting IP address di CentOS. Tanpa basa basi langsung aja simak baik-baik, Sebelumnya pastikan kita sudah install OS CentOS kalo belum bisa lihat di [sini.](https://roysans.github.io/2019/06/install-centos-on-virtualbox/)


Jika sudah install CentOS maka kita bisa lanjut untuk konfigurasi IP Address, berkas konfigurasi IP Address pada CentOS terletak di `/etc/sysconfig/network-script/ifup-ens33` untuk `ens33` adalah nama interfaces atau kartu jaringan yang kita gunakan untuk melihat nama interfaca yang kita gunakan bisa menggunakan perintah `nmcli d` maka akan menampilkan semua interfaces.

	DEVICE   TYPE      STATE         CONNECTION         
	ens33    ethernet  connected     Wired connection 1 
	lo       loopback  unmanaged     --                 

### IP address static
IP Address static adalah IP Address yang kita tentukan sendiri mulai dari IP, Netmask, Gateway, Network dan Broadcastnya untuk menentukan semua tentunya tidak asal-asal begitu saja melainkan kita harus mencarinya dengan melakukan subnneting.
buka file IP Address dengan perintah berikut:

	vi /etc/sysconfig/network-script/ifup-ens33
<blockquote>
<p>Note: untuk vi adalah text editor yang saya gunakan yang memang defaultnya terpasang di CentOS jika tidak terbiasa dengan vi maka kita bisa install nano dengan perintah "yum install nano" tanpa tanda ". Pada vi untuk edit ketik i untuk masuk ke mode edit</p>
</blockquote>

kemudian tambahkan script konfigurasi seperti berikut:
![](https://raw.githubusercontent.com/RoySans/img/master/IP-address/static/1.PNG)

kemudian save dan keluar dengan mengetikkan tombol **esc** kemudian **:** lalu **wq** untuk vi sedangkan pada nano bisa dengan kombinasi **ctr + x** kemudian **y** lalu **enter**.

setelah itu jangan lupa untuk merestart service networknya dengan pertintah `service network restart` agar hasil konfigurasi kita bisa ter-load.
Untuk melihat apakan hasil konfigurasi sudah berhasil maka gunakan perintah `ip a`.
![](https://raw.githubusercontent.com/RoySans/img/master/IP-address/static/1.PNG)

###IP address DHCP
Kebalikan dari IP address static, IP address DHCP adalah IP address yang disediakan oleh penyedia IP address atau bisa disebut DHCP Server, kita yang meminta IP biasanya disebut DHCP Client. Penyedia IP ini adalah [ISP](https://id.wikipedia.org/wiki/Penyelenggara_jasa_Internet) yang kita gunakan, jadi kita tidak perlu repot-repot menentukan IP address sendiri. Sebelum konfigurasi IP adress DHCP pastikan CentOS kita terhubung ke internet kemudian masukan perintah:

	vi /etc/sysconfig/network-script/ifup-ens33
Kemudian tambahkan script seperti gambar berikut:
![](https://raw.githubusercontent.com/RoySans/img/master/IP-address/dhcp/1.PNG)


kemudian save dan keluar dengan mengetikkan tombol **esc** kemudian **:** lalu **wq** untuk vi sedangkan pada nano bisa dengan kombinasi **ctr + x** kemudian **y** lalu **enter**.

setelah itu jangan lupa untuk merestart service networknya dengan pertintah `service network restart` agar hasil konfigurasi kita bisa ter-load.
Untuk melihat apakan hasil konfigurasi sudah berhasil maka gunakan perintah `ip a`.
![](https://raw.githubusercontent.com/RoySans/img/master/IP-address/dhcp/2.PNG)


Mungkin segitu saja tulisan saya kali ini atas segala kekurangannya saya mengucapkan mohon maaf.
