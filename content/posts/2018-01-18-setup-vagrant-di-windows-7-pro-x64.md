---
title: 
date: 2017-04-14T19:39:08+07:00
showDate: true
draft: false
tags: ["blog"]
---
Di Windows, hampir semua yang terkait dengan pemasangan aplikasi sangatlah mudah, next next next finish. Seperti itu kira-kira gambaran yang ada dalam otak saya dan saya tuangkan dalam tulisan tak mutu ini. Beberapa hari yang lalu, saya mencoba setup vagrant di Windows 7. Instalasi sungguh tidak ada kendala, lancar jaya. Tetapi, kendala justru muncul ketika `vagrant up`, bengong, tidak ada reaksi, ditunggu sampai lumutan juga tidak membuahkan hasil, layaknya menunggu jawaban dari doi (bukan pengalaman saya).

Akhirnya saya jalankan mode debug, dan tanya ke mbah *you know him*. Ternyata yang jadi masalah adalah powershell, harus diupdate ke versi 3. Setelah install **WMF**, akhirnya powershell naik versi dan `vagrant up` berjalan mulus, semulus singkong yang baru dikupas.

Itu saja tulisan artikel ini, sangat gaje dan mungkin nirfaedah.
