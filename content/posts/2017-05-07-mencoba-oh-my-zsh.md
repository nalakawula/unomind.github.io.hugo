---
title: "Mencoba Oh My Zsh"
date: 2017-05-07T19:39:08+07:00
showDate: true
draft: false
tags: ["blog"]
---
Melanjutkan tulisan tentang `zsh` [disini]({{ site.baseurl }}{% post_url 2017-05-07-mencoba-zsh-di-fedora-25 %}). Jika teman-teman mengikuti artikel tersebut, pasti tampilan `zsh` -nya biasa-biasa aja. Nah, pada artikel ini akan saya sampaikan bagaimana agar shell `zsh` jadi cantik.

Caranya adalah dengan memasang `oh-my-zsh`. Simple aja, eksekusi *command* berikut di terminal:

```sh
wget --no-check-certificate http://install.ohmyz.sh -O - | sh
```

Nah untuk mengganti tema, cukup edit file `.zshrc` di /home.

```sh
nano ~/.zshrc
```

Cari baris

```sh
# See https://github.com/robbyrussell/oh-my-zsh/wiki/Themes
ZSH_THEME="robbyrussell"
```

Kemudian ganti robbyrussell dengan tema lain, misalnya :

```sh
ZSH_THEME="agnoster"
```

Selesai
