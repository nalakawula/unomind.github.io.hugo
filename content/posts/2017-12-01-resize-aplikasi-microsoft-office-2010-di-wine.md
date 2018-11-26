---
title: 
date: 2017-04-14T19:39:08+07:00
showDate: true
draft: false
tags: ["blog"]
---
Microsoft Office 2010 yang saya pasang dengan bantuan Wine, _so far so good_. Fungsi-fungsi yang saya butuhkan berjalan sebagaimana mestinya. Tapi, ada sesuatu yang aneh walaupun tidak mengganggu pekerjaan, yaitu Aplikasi MSO tidak bisa di resize menggunakan tombol resize di _tittle bar_. Misal saya buka Ms Word, ketika saya klik resize maka akan mengecil, ketika saya klik rezie sekali lagi, tidak terjadi apa-apa, seharusnya jadi maximize.

Ternyata, hal tersebut berkaitan dengan window manager dari DE. Berhubung saat ini saya menggunakan KDE, maka solusinya adalah sebagai berikut:
1. Buka __System Settings__
2. Dari __System Setttings__ buka __Window Managements__
3. Setelah __Window Management__ terbuka, Klik __Window Rules_ > __New..__
4. Pada kolom isian _Description_, isilah nama untuk rule yang akan dibuat
5. __Window Class (Application)__: Pilih regular expression dan isi dengan `.*\b(winword.exe|excel.exe|powerpnt.exe)\b.*`
6. Klik tab __Size & Position__
7. Centang __Full Screen__, Opsi __Force__, __No__
8. Centang __Ignore Requested Geometry__, Opsi __Force__, __Yes__
9. Profit

Sumber: [https://www.codeweavers.com/compatibility/crossover/forum/microsoft-office-2010?msg=157908](https://www.codeweavers.com/compatibility/crossover/forum/microsoft-office-2010?msg=157908)