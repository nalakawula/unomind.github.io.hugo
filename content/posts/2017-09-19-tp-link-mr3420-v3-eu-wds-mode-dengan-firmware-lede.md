---
title: "TP-Link MR3420-v3-EU WDS Mode Dengan Firmware Lede"
date: 2017-09-19T19:39:08+07:00
showDate: true
draft: false
tags: ["blog"]
---
![802.11-routed-relay.png](/assets/img/802.11-routed-relay.png)

Melanjutkan petualangan saya bersama TP-Link MR3420 v3 EU. Ketika menggunakan firmware original dari TP-Link, Wireless router ini mempunyai fitur WDS. Jadi satu Wireless router menjadi *client* sekaligus *Access Point*. Topologinya seperti gambar diatas. Ketika saya berpindah ke firmware berbasis openwrt, saya merindukan fitur ini.

Apakah openwrt tidak punya fitur yang serupa? punya. Tapi saya tidak tahu, saya jadi tahu setelah bertanya di group [Telegram Openwrt & IoT](https://t.me/pegelwrt).

Caranya? Ikuti saja wiki [tentang relayd](https://wiki.openwrt.org/doc/recipes/relayclient) ini.

Apakah ada kendala yang saya alami? Ada, berikut ini kendala yang saya alami:

1. MR3420 V3 EU, penyimpanan internalnya sangat kecil sehingga tidak bisa dipasang `LUCI`.
**Solusinya?** Kongigurasi dari `cli`, bisa dengan konfigurasi cara edit file, bisa jugan menggunakan [UCI](https://wiki.openwrt.org/doc/uci).
2. Saya mengalami galat `unknown package relayd` ketika install paket `relayd`.
**Solusinya?** Tambah source list opkg dengan ini:

```
src/gz base http://downloads.lede-project.org/releases/17.01.1/packages/mips_24kc/base/
```


Selebihnya lancar.
