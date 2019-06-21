---
title: "Install CentOS on VirtualBox"
date: 2019-06-01
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

CentOS adalah salah satu distribusi Linux yang merupakan keturunan dari Linux RHEL (Red Hat Enterprise Linux), CentOS sendiri sangat andal dalam penggunaannya sebagai Server. Sedangkan VirtualBox adalah software virtualisasi dimana kita bisa install system operasi secara virtual. Pada tulisan saya kali ini akan membahas bagaimana cara menginstall CentOS di VM VirtualBox, sebelum lanjut ke tahap install pastikan kita sudah meyiapkan bahan seperti ISO CentOS bisa di download di [sini](https://www.centos.org/download/) dan sofware VirtualBox di [sini](https://www.virtualbox.org/wiki/Downloads).


![Logo](https://cdn.freebiesupply.com/logos/large/2x/centos-logo-png-transparent.png)


## Setting VirtualBox
Setelah VirtualBox berhasil diinstall kemudian buka dengan cara klik 2x pada icon VirtualBox di desktop masing-masing, untuk proses installasi tidak dijelaskan karena saya yakin kalian semua bisa, tinggal klik..klikk saja :D. Berikut tampilan awal VBox: <br />
![](https://raw.githubusercontent.com/RoySans/img/master/Install-CentOS/1.png)
Untuk membuat VM baru klik **New** di pojok kiri atas.


aka akan muncul Option seperti Nama Tipe dan versi seperti berikut, kita akan beralih ke Expert Mode untuk pengaturan yang lebih spesifik maka klik **Expert Mode**. <br />
![](https://raw.githubusercontent.com/RoySans/img/master/Install-CentOS/2.png)

Maka kita akan beralih ke Expert Mode, di mode ini kita akan menentukan nama VM, jenis sistem operasi yang akan diinstall dan tipenya. Untuk ukuran memory disesuaikan masing-masing, saran saya jangan terlalu besar karena kita hanya akan praktik menginstall saja, jika terlalu besar maka resource yang digunakan juga besar khawatir laptop/PC yang digunakan menjadi lelet. <br />
![](https://raw.githubusercontent.com/RoySans/img/master/Install-CentOS/3.png)


Setelah mengatur Nama, memori selanjutnya mengatur ukuran HDD yang akan digunakan dan tipe HDD. Sama seperti sebelumnya untuk ukuran disesuaikan masing-masing. <br />
![](https://raw.githubusercontent.com/RoySans/img/master/Install-CentOS/4.png)


Oke jika semua sudah di setting langkah selanjutnya adalah tinggal menjalankan VM yang sudah kit buat caranya adalah dengan klik **Mula** atau **Run**. <br />
![](https://raw.githubusercontent.com/RoySans/img/master/Install-CentOS/5.png)

Untuk melanjutkan install CentOS kita harus memasukkan file ISO yang sudah kita download sebelumnya, jika belum download di ![sini](https://www.centos.org/download/")
![](https://raw.githubusercontent.com/RoySans/img/master/Install-CentOS/6.png)


Jika semua sudah kita setting seperti Nama VM, Ukuran Memory. HDD dan ISO maka otomatis kita akan Booting ke CentOS. Untuk install pilih paling atas <i>Install CentOS 7</i> kemudian **enter**. <br />
![](https://raw.githubusercontent.com/RoySans/img/master/Install-CentOS/7.png)


Berikut adalah tampilan dari CentOS, pilih bahasa yang akan di gunakan selama proses installasi berlangsung saya menggunakan English US karena sudah terbiasa jika menggunakan bahasa lain maka akan berbeda, kemudian **Continue**. <br />
![](https://raw.githubusercontent.com/RoySans/img/master/Install-CentOS/8.png)


Berikut adalah beberapa pengaturan yang harus kita setting, jika di salah satu option terdapat tanda !(seru) maka kita harus setting dahulu. <br />
![](https://raw.githubusercontent.com/RoySans/img/master/Install-CentOS/9.png)


Pada gambar di bawah ini terdapat tanda ! di option Hardisk karena saya belum mengalokasikan HDD, untuk setting klik 2x pada icon HDD. <br /> 
![](https://raw.githubusercontent.com/RoySans/img/master/Install-CentOS/10.png)


Jika kita klik maka akan ke menu <**INSTALLATION DESTINATION**, di sini kita akan mengalokasikan HDD atau istilahnya pemartisian atau partisi. Perhatikan gambar di bawah ini pastikan HDD kita terbaca, kemudian di **Storage Option** jika kita baru petamakali menginstall Linux bisa memilih option <i>Automatically configure partitioning</i> yang artinya proses pemartisian HDD akan otomatis dilakukan oleh sistem tetapi jika kita memilih option <i>I will configure partitioning</i> maka sebrbaliknya kita akan melakukan partisi HDD secara manual tidak di sarankan bagi yang belum mengerti, jika sudah klik **Done**. <br />
![](https://raw.githubusercontent.com/RoySans/img/master/Install-CentOS/11.png)


Jika semua sudah di setting dan tidak ada tanda ! maka kita bisa klik **Begin Installation** untuk melanjutkan proses installasi. <br />
![](https://raw.githubusercontent.com/RoySans/img/master/Install-CentOS/12.png)


Proses intallasi sedang berjalan, sembari menunggu kita diharuskan untuk setting password <i>root</i> dan mebuat user baru. Root adalah user yang memiliki hak akses tertinggi di Linux dimana root ini bisa melakukan segala hal di sistem operasi Linux seperti menghapus file dan lain sebagainya berbeda dengan user biasa yang aka kita buat ini. Root mungkin jika di Windows sama seperti Administrator. <br />
![](https://raw.githubusercontent.com/RoySans/img/master/Install-CentOS/13.png)


Setelah mengatur password untuk root dan membuat user baru kita tinggal menunggu sampai installasi selesai, selesainya proses installasi ditandai dengan **Reboot** seperti gambar berikut klik maka sistem otomatis akan restart dan selamat proses installasi sudah selesai :). Jika proses Reboot sudah selesai kita tinggal login dengan user yang sudah kita buat sebelumnya. <br />
![](https://raw.githubusercontent.com/RoySans/img/master/Install-CentOS/16.png)


Apa Selanjutnya? <br />
[Setting IP Address di CentOS](/)
[Install dan Konfigurasi DNS Server](/)