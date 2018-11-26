---
title: 
date: 2017-04-14T19:39:08+07:00
showDate: true
draft: false
tags: ["blog"]
---

![utilman.png]({{ site.baseurl }}/assets/img/utilman.png)
Gambar 1: utilman.exe (https://www.online-tech-tips.com/)
{: style="color:gray; font-size: 80%; text-align: center;"}

Mungkin, kelak akan kita akan mengalami keadaan tidak bisa login ke desktop Windows 10 karena lupa password. Akan tetapi keadaan memaksa kita untuk dapat masuk. Untuk bypass password login Windows 10, ada banyak cara. Apa yang saya tulis disini hanyalah salah satunya. Tentunya sudah saya lakukan, karena tulisan ini saya maksudkan untuk "jika saya lupa". Solusi yang saya tulis disini yaitu memanfaatkan `utilman.exe` yang ada di login screen Windows 10.

### Persiapan
Kita harus memiliki:
1. Image Windows Installer
2. Media untuk `boot` (Saya sarankan menggunakan Flashdisk)

### Eksekusi
Step by step-nya adalah sebagai berikut:
1. Buat bootable media Windows.
2. Boot dari bootable media tadi.
3. Setelah berhasil boot dan masuk ke pemilihan __regional and language__, silakan tekan <kbd>SHIFT</kbd> + <kbd>F10</kbd> sehingga muncul jendela command prompt.
4. Backup file `utilman.exe`.
```shell
move e:\Windows\System32\Utilman.exe e:\Windows\System32\Utilman.exe.bak
```
5. Copy `cmd.exe` menjadi `utilman.exe` dengan maksud agar ketika di login screen windows dan kita klik `Utility Manager` yang muncul adalah jendela `CMD`.
```shell
copy e:\Windows\System32\cmd.exe e:\Windows\System32\Utilman.exe
```
Catatan: `e` adalah partisi system  Windows, silakan disesuaikan.
6. Reboot dan boot dari HDD windows.
```shell
wpeutil reboot
```
7. Setelah muncul login screen, klik `Utility Manager` dan jreng jreng muncul jendela CMD.
8. Buat user baru dan jadikan administrator.
```shell
net user <username> /add
net localgroup administrators <username> /add
```
9. Tutup CMD, dan reboot.
10. Login ke akun yang tadi dibuat.
11. Profit.

Nah dari akun baru yang kita buat, kita dapat mereset password akun yang lain.

Terimakasih