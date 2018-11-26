---
title: 
date: 2017-04-14T19:39:08+07:00
showDate: true
draft: false
tags: ["blog"]
---
Informasi konfigurasi grub dapat diakses melalui perintah `info -f grub -n 'Simple Configurtaion'`. Untuk membuat grub menyimpan pilihan terakhir, kita harus menyunting berkas `/etc/default/grub`, 
1. edit baris `GRUB_DEFAULT=0` menjadi `GRUB_DEFAULT=saved`
2. Tambahkan baris `GRUB_SAVEDEFAULT=true`
Secara keseluruhan berikut ini milik saya:
```
GRUB_DEFAULT=saved
GRUB_SAVEDEFAULT=true
GRUB_TIMEOUT_STYLE=hidden
GRUB_TIMEOUT=10
GRUB_DISTRIBUTOR=`lsb_release -i -s 2> /dev/null || echo Debian`
GRUB_CMDLINE_LINUX_DEFAULT="splash quiet"
GRUB_CMDLINE_LINUX=""
```
3. Update grub, kalau keluarga debian bisa pakai `update-grub`, kalau fedora bisa pakai `grub-mkconfig`