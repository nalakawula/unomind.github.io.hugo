---
title: "Flash Boot Android Menggunakan Fastboot"
date: 2017-05-20T23:00:08+07:00
showDate: true
draft: false
tags: ["blog"]
---
Melanjutkan artikel [membongkar boot.img](/posts/2017-05-20-bongkar-boot.img-android-di-fedora-25)

Sekarang akan saya bahas cara flash file `new-boot.img` yang telah dibuat, metode yang saya pakai adalah menggunakan `fastboot` karena sangat mudah.

* Aktifkan `usb debugging` di hp
* Tancapkan ke laptop
* Buka Terminal
* `cd` ke lokasi new-boot.img
* reboot HP ke mode `fastboot`

```
adb reboot-bootloader
```

* Setelah muncul tulisan fastboot di layar HP, jalankan perintah ini:

```
fastboot flash boot new-boot.img
```
Hanya butuh beberapa detik untuk selesai

* Reboot HP

```
fastboot reboot
```

Selamat, sekarang `/system` sudah termount dalam mode `rw`

:+1:
