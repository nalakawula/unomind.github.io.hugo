---
title: "Membuat Tautan Referensi ke Artikel Lain dalam Jekyll"
date: 2017-05-24T15:39:08+07:00
showDate: true
draft: false
tags: ["blog"]
---
Ketika kita menulis artikel untuk website, ada kalanya kita akan membuat referensi ke artikel lain yang pernah kita tulis. Jekyll pun bisa melakukan hal tersebut.

Nah, dulu saya menggunakan cara seperti ini:

```
[artikel anu]({{ site.url }}/2017/04/18/anu-ini-inu-uni/
```

Menggunakan cara seperti itu, tentu saja bisa. Namun, akan ada kendala ketika kita mengubah `permalink` situs kita.

Bagaimana caranya agar referensi yang kita buat bisa otomatis mengikuti `permalink` situs kita? Ternyata jekyll memiliki fitur ini. Untuk keperluan seperti itu, gunakan cara seperti ini:

```
[artikel anu]({{ site.baseurl }}{% post_url yyy-mm-dd-nama-artikel %})
```

Contoh:

```
[artikel anu]({{ site.baseurl }}{% post_url 2017-04-18-anu-ini-inu-uni %})
```

Nantinya, kode `html` yang dihasilkan akan mengikuti `permalink` situs kita.


Sekian
