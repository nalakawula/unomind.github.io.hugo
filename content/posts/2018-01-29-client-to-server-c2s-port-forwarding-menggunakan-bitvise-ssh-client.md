---
title: 
date: 2017-04-14T19:39:08+07:00
showDate: true
draft: false
tags: ["blog"]
---
Sebenarnya, ini merupakan hal yang sederhana, alkisah saya punya server kecil. Di server tersebut, ada sebuah *anuan* yang menggunakan port *ABCD* dan *EFGH*. Saya ingin akses anuan tersebut dapat diakses dari komputer lain menggunakan `ssh tunnel`. Kalau di linux mah *gampil* , tinggal:
```
ssh "remote-IP" -p "remote-ssh-port" -L BLABLA:localhost:ABCD -L BLILI:localhost:EFGH -l "ssh-user"
```
BLABLA = port lokal kita.
BLIBLI = port lokal kita.
Jadi ketika kita akses localhost:BLABLA akan lari ke remote-IP:ABCD. Ketika akses localhost:BLIBLI akan lari ke remote-IP:EFGH.

Kalau di Windows? Saya bingung bagaimana caranya, akhirnya browsing dan ketemu [BitVise SSH Client](https://www.bitvise.com/port-forwarding).

Caranya seperti terlihat di gambar contoh, berikut ini:
![C2S]({{ site.baseurl }}/assets/img/c2s.png)

Selebihnya tidak perlu saya jelaskan, karena BitVise ini cukup *user friendly*.

Terimakasih
