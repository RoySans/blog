---
title: "Mengatasi Git Push Rejected"
date: 2019-06-17T06:02:35-04:00
categories:
- uncategories
tags:
- Git
- Github
keywords:
- github
---

<!--more-->
Pada saya ingin melakukan Push ke repository GitHub dari repository lokal saya mendapatkan pesan seperti berikut:

	To https://github.com/RoySans/roysans.github.io.git
	 ! [rejected]        master -> master (fetch first)
	error: failed to push some refs to 'https://github.com/RoySans/roysans.github.io.git'
	hint: Updates were rejected because the remote contains work that you do
	hint: not have locally. This is usually caused by another repository pushing
	hint: to the same ref. You may want to first integrate the remote changes
	hint: (e.g., 'git pull ...') before pushing again.
	hint: See the 'Note about fast-forwards' in 'git push --help' for details.
Setelah saya muter-muter di internet ternyata kita hanya menambahkan parameter `--force` atau `-f` keduanya sama saja, sehingga menjadi `gitpush origin master --force`.
