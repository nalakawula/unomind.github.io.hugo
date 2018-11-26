---
title: "Mengganti Akses Github dari HTTPS ke SSH" 
date: 2017-05-25T21:39:08+07:00
showDate: true
draft: false
tags: ["blog"]
---
Selama ini, aktivitas terkait `git` selalu saya lakukan _over_ `https`. Sampai akhirnya saya jenuh setiap kali harus menulis `username` dan `password`.

Kejenuhan nan mengikat itu yang membuat saya akhirnya berpaling dari `https` ke `ssh`. memindah akses via `https` ke `ssh` sangatlah mudah di git. Setelah kita selesai setup `key` di mesin kita dan di Github.com, langkah selanjutnya adalah mengubah `remote url` di mesin lokal.

Caranya:

* Buka terminal.
* Cek `remote url` yang sekarang:

```
git remote -v
```
Output jika masih pakai https:
```
origin	https://github.com/username/nama-repo.git (fetch)
origin	https://github.com/username/nama-repo.git (push)
```

* Ubah ke `ssh` dengan menggunakan `remote set-url` :

```
git remote set-url origin git@github.com:username/nama-repo.git
```
output dari `git remote -v` nanti akan berubah menjadi:
```
origin	git@github.com:username/nama-repo.git (fetch)
origin	git@github.com:username/nama-repo.git (push)
```


Sekian
