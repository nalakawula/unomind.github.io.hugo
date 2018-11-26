---
title: 
date: 2017-04-14T19:39:08+07:00
showDate: true
draft: false
tags: ["blog"]
---
Secara *default* Distribusi GNU/Linux menggunakan patokan UTC untuk *date time*. Ya bukan masalah sih, tapi kadang jadi mengganggu kalau dualboot dengan sistem operasi besutan Microsoft. Untuk mengetahui apakah sistem kita menggunakan UTC ataukah RTC, bisa gunakan salah satu fitur dari `systemd`:
```
orangtua@mesin-tua:~/unomind.github.io$ timedatectl status
                      Local time: Tue 2018-10-09 19:08:23 WIB
                  Universal time: Tue 2018-10-09 12:08:23 UTC
                        RTC time: Tue 2018-10-09 12:08:21
                       Time zone: Asia/Jakarta (WIB, +0700)
       System clock synchronized: yes
systemd-timesyncd.service active: yes
                 RTC in local TZ: no

```
Kalau mau supaya memakai RTC, tinggal eksekusi:
```
timedatectl set-local-rtc 1 --adjust-system-clock
```

Nanti hasilnya begini:
```
orangtua@mesin-tua:~/unomind.github.io$ timedatectl status
                      Local time: Tue 2018-10-09 19:08:23 WIB
                  Universal time: Tue 2018-10-09 12:08:23 UTC
                        RTC time: Tue 2018-10-09 12:08:21
                       Time zone: Asia/Jakarta (WIB, +0700)
       System clock synchronized: yes
systemd-timesyncd.service active: yes
                 RTC in local TZ: yes

Warning: The system is configured to read the RTC time in the local time zone.
         This mode can not be fully supported. It will create various problems
         with time zone changes and daylight saving time adjustments. The RTC
         time is never updated, it relies on external facilities to maintain it.
         If at all possible, use RTC in UTC by calling
         'timedatectl set-local-rtc 0'.
```

Mudah kan?