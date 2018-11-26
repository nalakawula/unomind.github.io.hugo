---
title: "Mengatasi Aktivasi Office 365 yang Muncul Berulang-ulang"
date: 2017-07-26T19:39:08+07:00
showDate: true
draft: false
tags: ["blog"]
---
![Reminder Office 365](/assets/img/365.PNG)

Kemarin, dapat Lenovo AIO PC yang mana sudah terpasang Windows 10 Home. Umumnya *unboxing*, buka kardus dan tes Power ON. Begitu hidup, akan diarahkan untuk *setup* akun Window dan Lenovo ID.

Terlalu panjang *Skip Skip*...................

Singkat cerita, ada office 365 didalamnya, saya buang dan ganti Office 2016. Setelah Windows dan Office saya aktifkan via internet, eh ada yang ngeselin. Setiap buka aplikasi Office, selalu muncul peringatan untuk aktifasi Office 365. Sungguh *shitty shit* dan *annoying*. Di restart masih sama saja.

Coba *browsing*, dengan kata kunci "annoying office 365 activation reminder" dan ternyata ada yang mengalami hal yang sama, dan sudah ada solusinya. Berikut saya kutip dari [sini](https://support.microsoft.com/en-us/help/3170450/repeated-activation-prompts-occur-after-installing-volume-license-vers)

To resolve this problem, export the following registry keys and delete from computer.

* Close activation screen.
* On the Start menu, click Run.
* Type regedit, and then press Enter.
* Select the following key in the registry.

```
HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Office\16.0\Common\OEM
```

* Right click the OEM value and click File>Export.
* Save the key
* Once the key is backed-up, click on Edit>Delete
* Repeat steps 4-7 with following key

```
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\16.0\Common\OEM
```

* Exit Registry Editor

restart dan selesai.

Semoga bermanfaat.
