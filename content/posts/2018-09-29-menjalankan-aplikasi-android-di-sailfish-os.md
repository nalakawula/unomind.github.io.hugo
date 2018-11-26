---
title: 
date: 2017-04-14T19:39:08+07:00
showDate: true
draft: false
tags: ["blog"]
---
Sistem operasi tanpa aplikasi, sungguh laksana piring tanpa nasi. Begitu juga dengan sailfish OS. Kesan pertama memakai sailfish OS "WAW", gegas, gesture nikmat, konsisten, UI/UX yang mengesankan. Saya tidak sedang melebih-lebihkan, memang begitu yang saya rasakan. Dan yang paling mencengangkan adalah systemd yang dipakai. Cool.

Sayang-seribu sayang, dukungan aplikasi di sailfish OS benar-benar minim. Maklum, sistem operasi minoritas. Siapa sih developer yang mau bikin aplikasi tanpa pangsa pasar yang jelas? Wasting time. Hal tersebut yang kemudian mengilhami developer untuk membenamkan dukungan android ke sailfish OS, melalui **aliendalvik**. Penasaran? sama. Sayangnya, kita mesti membeli lisensi untuk hal tersebut *sad emoticon*.

Hampir putus asa, tapi ada kabar bahwa ada beberapa individu yang berhasil menjalankan aliendalvik di sailfish port. Ada harapan, setelah mengarungi dalamnya forum talk maemo, akhirnya saya bisa run aliendalvik di sailfish. Berikut ini langkah-langkah yang saya tempuh:
1. Tentu saja memasang sailfish OS
2. Dump paket aliendalvik dan dependensinya dari official device, saya dump dari xperia X yang sudah terpasang aliendalik (lebih tepatnya, minta ke pemilik device ini).
3. SSH ke device sailfish kita
```
ssh nemo@192.168.2.15
```
4. Masuk ke mode root
```
devel-su
```
5. Masuk ke direktori hasil dump aliendalvik, nstall paket secara serentak, pernah coba satu-satu error.
```
zypper in *.rpm
```
6. sesuaikan isi `/opt/alien/system/script/` dengan device kita.
7. rename `/etc/media_platform.xml`
7. run service aliendalvik `systemctl start aliendalvik`

Kalau sukses, bisa install apk. Saya telah coba install whatsapp dan tekegram X, fdroid, dan yalp. Semua berjalan lancar.
<script async src="https://telegram.org/js/telegram-widget.js?4" data-telegram-post="unomindgithubio/5" data-width="100%" data-userpic="false"></script>


Log aliendalvik yang berhasil run: [https://del.dog/logad-1.diff](https://del.dog/logad-1.diff)