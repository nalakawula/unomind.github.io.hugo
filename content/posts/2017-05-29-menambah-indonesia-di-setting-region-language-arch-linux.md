---
title: "Menambahkan Indonesia di Setting Region & Language Arch Linux" 
date: 2017-05-29T19:39:08+07:00
showDate: true
draft: false
tags: ["blog"]
---
Ketika saya melakukan pemasangan Arch Linux, `locale` yang saya gunakan dan saya _generate_ hanyalah `en_US.UTF-8 UTF-8`. Hal ini tentu saja akan menyebabkan isi dari setting `Region and Language` hanya ada `English` dan `US`.

Saya ingin, untuk bagian `format` menggunakan Indonesia, nah yang saya lakukan adalah berikut ini:

* Buka file `/etc/locale.gen`
* Cari baris `#id_ID.UTF-8 UTF-8` dan hapus tanda `#` -nya kemudian simpan
* Selanjutnya jalankan `locale-gen`

```shell
sudo locale-gen
```
* Buka setting `Region and Language`, sudah ada __Indonesia__ disana.

![Region and Language](/assets/img/region-and-language.png)
