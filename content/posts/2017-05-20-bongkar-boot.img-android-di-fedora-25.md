---
title: "Bongkar boot.img Android di Fedora 25" 
date: 2017-05-20T21:39:08+07:00
showDate: true
draft: false
tags: ["blog"]
---
Hari ini saya mendapati custom ROM Android yang `/system` nya termount `ro` atau *read only*. Padahal saya mau edit file [ini]({{ site.baseurl }}{% post_url 2017-05-20-disable-tombol-kapasitip-hp-android-rom-cm13-google-seed %}) di `system`.

Usut punya usut, agar `/system` termount dalam mode `rw` harus bongkar `boot.img`. Untungnya sudah ada yang membuat `bash script` untuk *unpack* dan *repack* `boot.img`

* Unduh [disini](https://github.com/GameTheory-/mktool.git) lalu ekstrak
* Copy paste file boot.img ke dalam folder mktool
* jalankan ./mktool
![Fedora_winten](/assets/img/ss-mktool.png)

* Pilih **2** dan masukan nama file boot.img nya.
* Edit file `/mktool/extracted/ramdisk/fstab.qcom`
* Ubah baris:

```shell-script
/dev/block/bootdevice/by-name/system    /system     ext4    ro,barrier=1    wait
```
menjadi:

```shell-script
/dev/block/bootdevice/by-name/system    /system     ext4    rw,barrier=1    wait
```
Simpan

* kembali ke jendela mktool, pilih repack. Nanti akan menghasilkan file `new-boot.img`
* File tersebut siap di flash via fastboot flash

Selesai.
Next time, kita bahas cara flash file tadi pakai fastboot :+1:

