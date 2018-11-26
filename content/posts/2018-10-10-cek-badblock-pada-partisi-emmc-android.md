---
title: 
date: 2017-04-14T19:39:08+07:00
showDate: true
draft: false
tags: ["blog"]
---
Seprti pada umumnya NAND Flash yang sering ditulis, pasti akan mencapai masa muncul *bad block*. Kalau di HDD sih *bad sector*. Demikian juga EMMC HP kita. Kebiasaanku yang gonta-ganti custom firmware, gonta-ganti dari *filesystem*, mungkin menyebabkan *bad block* pada EMMC. Nah, dalam tulisan ini akan saya tulis bagaimana saya cek *bad block* di HP saya.

Untuk kasus saya, HP yang saya pakai adalah Redmi Note 4 Snapdragon a.k.a Mido. Reno4 ada dua varian berdasarkan prosesornya, MTK (Nikel) dan Qualcomm (Mido). Berikut ini langkah demi langkah yang saya tempuh:
1. Reboot HP ke TWRP
2. Masuk ke menu Andvanced > Terminal
3. Pindah direktori: 
```
cd /dev/block/platform/soc/[chipID]/by-name
```
dalam kasus saya:
```
/dev/block/platform/soc/7824900.sdhci/by-name
```
4. Unmount partisi yang akan di cek, misalnya `userdata`
```
umount userdata
```
5. Cek *bad block*
```
e2fsck -cfv userdata
```

Info lebih tentang e2fsck bisa akses `e2fsk --help`