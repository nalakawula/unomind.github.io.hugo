---
title: 
date: 2017-04-14T19:39:08+07:00
showDate: true
draft: false
tags: ["blog"]
---
Debian 9 hadir dengan Office Suite bernama LibreOffice, namun demikian tak dapat kita pungkiri bahwa dalam dunia Office Suite, Microsoft Office adalah rajanya. Kalau untuk keperluan pribadi, mungkin LibreOffice sudah cukup untuk memenuhi kebutuhan. Tapi akan menjadi lain cerita kalau menyangkut urusan pekerjaan, menyangkut khalayak banyak, dokumen yang kita olah harus dapat dibuka oleh orang lain. Sayangnya kompatibilitas LO terhadap MSO dan sebaliknya, belum cukup bagus. Oleh sebab itu, dalam artikel ini akan dibahas cara instalasi MSO 2010 di sistem operasi Debian 9 dengan bantuan program PlayOnLinux.

PlayOnLinux merupakan program yang sangat berguna untuk memudahkan instalasi aplikasi Windows di lingkungan GNU/Linux. Ia merupakan frontend untuk Wine.

Pada artikel ini, akan saya paparkan bagaimana cara instalasi MSO 2010 di Debian 9 menggunakan PlayOnLinux. Berikut ini adalah beberapa hal yang kita butuhkan:
1.	PlayOnLinux installed.
2.	Microsoft Office 2010 (32-Bit Edition) DVD atau ISO image file.
3.	Koneksi internet yang bagus.

Selanjutanya, masuk ke tahap instalasi PlayOnLinux:
1.	Update database repo Debian 9
```
sudo apt-get update
````
2.	Install PlayOnLinux
```
sudo apt-get install playonlinux -y
````
3.	Install Winbind
```
Sudo apt-get install winbind
````

Setelah itu, kita install Microsoft Office 2010:
1.	Buka PlayOnLinux
2.	Klik  tombol __Install__ di toolbar atas, atau klik  __Install a program__ di sidebar Action, maka PlayOnLinux akan update database, tunggu hingga selesai.
3.	Klik Tab __Office__  kemudian pilih __Microsoft Office 2010__ kemudian klik __Install__.
4.	Klik __Ok__ pada dialog warning, 3x Next, pilih __Use DVD-ROM(s)__, pilih __Other__, klik  Next.
5.	Arahkan ke setup.exe installer MSO 2010 dan klik Next.
6.	Ikuti wizard MSO 2010.
7.	Selesai? Klik finish.
8.	Profit.
