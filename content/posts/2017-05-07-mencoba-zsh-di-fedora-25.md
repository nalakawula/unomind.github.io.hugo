---
title: "Mencoba Zsh di Fedora 25"
date: 2017-05-07T18:39:08+07:00
showDate: true
draft: false
tags: ["blog"]
---

Berawal dari perbincangan di group telegram, Saya jadi ingin mencoba (lagi) `ZSH` untuk menggantikan `BASH`. Salah satu yang saya suka dari ZSH adalah tampilannya yang menarik, ditambah lagi dengan adanya `Oh My Zsh`.

Mengganti BASH dengan ZSH di Fedora 25 terbilang cukup mudah, berikut ini caranya:

* Install paket `zsh` dan `util-linux-user`. Dari `util-linux-user` kita butuh `chsh` untuk me-replace bash dengan zsh.

```
sudo dnf install zsh util-linux-user
```

* Ganti bash menjadi zsh dengan cara:

```
chsh -s /usr/bin/zsh
```

* Tutup terminal dan buka lagi, `bash` sudah tergantikan oleh `zsh`

Nah, next time kita bahas `oh my zsh`.
