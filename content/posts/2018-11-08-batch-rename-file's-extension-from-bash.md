---
title: 
date: 2017-04-14T19:39:08+07:00
showDate: true
draft: false
tags: ["blog"]
---
Untuk suatu keperluan, terkadang kita perlu melakukan **batch** rename untuk banyak file. Dalam kasus ini saya ingin rename file dengan ekstensi yang seragam, dan outputnya juga seragam. Yaitu *.log menjadi *.md.

Untuk praktik, kita bisa membuat file yang banyak terlebih dahulu, misalnya 1.log - 50.log
```sh
mkdir latihan

cd latihan
```
jalankan skrip dibawah ini, untuk membuat file 1.log - 50.log. Jadi nanti akan ada 50 file:
```sh
for i in {1..50}; do touch $i.log; done 
```
kalau di `ls`:
```sh
[orangtua@mesintua latihan]$ ls
10.log  13.log  16.log  19.log  21.log  24.log  27.log  2.log   32.log  35.log  38.log  40.log  43.log  46.log  49.log  5.log  8.log
11.log  14.log  17.log  1.log   22.log  25.log  28.log  30.log  33.log  36.log  39.log  41.log  44.log  47.log  4.log   6.log  9.log
12.log  15.log  18.log  20.log  23.log  26.log  29.log  31.log  34.log  37.log  3.log   42.log  45.log  48.log  50.log  7.log
```

Sekarang saatnya batch rename:
```sh
for file in *.log; do mv "$file" "$(basename "$file" .log).md"; done
```
Kalau di `ls`
```sh
[orangtua@mesintua latihan]$ ls
10.md  13.md  16.md  19.md  21.md  24.md  27.md  2.md   32.md  35.md  38.md  40.md  43.md  46.md  49.md  5.md  8.md
11.md  14.md  17.md  1.md   22.md  25.md  28.md  30.md  33.md  36.md  39.md  41.md  44.md  47.md  4.md   6.md  9.md
12.md  15.md  18.md  20.md  23.md  26.md  29.md  31.md  34.md  37.md  3.md   42.md  45.md  48.md  50.md  7.md
```
Semoga bermanfaat
