---
title: "Disable Tombol Kapasitip HP Android ROM CM13-Google-Seed"
date: 2017-05-20T22:39:08+07:00
showDate: true
draft: false
tags: ["blog"]
---
Bosan menggunakan tombol fisik? ingin ganti ke softkey? sudah ganti tapi tombol fisik terasa *annoying*?

Mudah saja. Disable aja tombol kapasitipnya.
Caranya? check this out:

* Hubungkan HP ke Laptop
* Aktifkan `USB Debugging` di HP
* Buka Termninal
* Jalankan perintah adb shell dan minta hak ases `root`:

```shell
adb shell
su
```

* Edit file `Generic.kl`:

```shell
vim /system/usr/keylayout/Generic.kl
```

* Cari tulisan:
    - `key 139   MENU`
    - `key 172   HOME`
    - `key 158   BACK`

    Kemudian beri tanda `#` didepannya

* Simpan
* Exit adb shell
* Reboot HP

```shell
adb reboot
```
