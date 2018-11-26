---
title: 
date: 2017-04-14T19:39:08+07:00
showDate: true
draft: false
tags: ["blog"]
---
Windows 7 memiliki fitur _Internet Connection Sharing (ICS)_, yaitu sebuah fitur yang memungkinkan kita untuk membagi koneksi internet dari satu adapter ke adapter lain. Bukan fitur yang wah, sih. Di distribusi linux rasanya fitur tersebut lebih *mantab soul*. Alhail GNU/Linux.

Secara _default_ IP hasil konfigurasi ICS adalah 192.168.137.x, bagaimana caranya agar ip default-nya bukan ip tsb? Berikut ini caranya:
1. Masuk Registry Editor
2. Pada panel kiri, cari:
```
HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\SharedAccess\Parameters
```
3. Setelah itu, pada bagian panel kanan akan akan ada **Scope Address** dan **StandAloneDHCPAddress**, ubah nilai dari dua paramater tsb dengan ip address yg kita kehendaki.
4. Reboot
5. Profit
![Registry ICS]({{ site.baseurl }}/assets/img/ics1.png)

![Registry ICS]({{ site.baseurl }}/assets/img/ics2.png)

Sudah sih, hanya seperti itu.
