---
title: "Mudah Dualboot Remix OS dengan Arch Linux" 
date: 2017-07-05T19:39:08+07:00
showDate: true
draft: false
tags: ["blog"]
---
![Remix OS-1](/assets/img/remixos-2.jpg)

Siang tadi, saya sedikit senggang. Kesempatan itu saya gunakan untuk mencoba install Remix OS di Thinkpad x200. Iseng saja sebenarnya, ingin tahu seperti apa rasanya menjalankan Remix OS di laptop tua.

Remix OS merupakan sistem operasi Android yang dimodifikasi sehingga tampilannya mirip dengan sistem operasi besutan Microsoft. Namun sayangnya, Remix OS ini sudah berhenti dikembangkan. Selengkapanya silakan kunjungi [jide.com](http://jide.com).

Thinkpad x200 milik saya, sudah terpasang sistem operasi Arch Linux. Jadi, akan saya dualboot dengan Remix OS. Caranya sangat mudah, sama halnya dengan proses dualboot dengan Android X86. Berikut ini langkah sayang saya ambil:

* Download File Remix OS [disini](https://www.fosshub.com/Remix-OS.html)
* Ekstrak hasil download tadi, maka akan didapat berkas-berkas berikut ini:

```shell
[sumarsono@mesin-arch Remix_OS_for_PC_Android_M_32bit_B2016112201]$ tree
.
├── How_to_launch_Remix_OS_for_PC.txt
├── md5sum.txt
├── Remix_OS_for_PC_Android_M_32bit_B2016112201.iso
└── Remix_OS_for_PC_Installation_Tool-B2016080802.exe
0 directories, 4 files
```
* Siapkan satu partisi `EXT4`, milik saya `sda4` sebesar 10GB. Dijadikan satu dengan partisi `/` milik arch juga boleh. Jangan lupa set `bootable` jika menggunakan partisi terpisah.

```shell
/dev/sda4  *    213958656 234438655  20480000  9,8G 83 Linux
```
* Mount berkas `Remix_OS_for_PC_Android_M_32bit_B2016112201.iso` hasil ekstrak tadi.

```shell
fuseiso /direktori/hasil/ekstrak/Remix_OS_for_PC_Android_M_32bit_B2016112201/Remix_OS_for_PC_Android_M_32bit_B2016112201.iso /lokasi/yg/mau/dijadika/tempat/mount/
```
Dalam hal ini, saya menggunakan `fuseiso`. Boleh menggunakan tool lain. Punya saya, saya mount ke `/home/sumarsono/ISO/`.

* Masuk ke direktori `/dev/sda4` kemudian buat folder dengan `RemixOS/data/`
* Kembali ke `/home/sumarsono/ISO/` kemudian copy file berikut ini kemudian paste ke `/dev/sda4/RemixOS`:
  - initrd.img
  - isolinux.sys
  - kernel
  - ramdisk.img
  - system.sfs,
  Sehingga isi dari `/dev/sda4` adalah sebagai berikut:
 
 ```shell
  .
  └── RemixOS
      ├── data
      ├── initrd.img
      ├── isolinux.sys
      ├── kernel
      ├── ramdisk.img
      └── system.sfs
    3 directories, 5 files
    ```

* Kemudian edit file `/etc/grub.d/40_custom`, tambahkan:

```shell
menuentry "Remix OS" {
        set root='(hd0,4)' #sesuaikan dengan partisi yang disiapkan
        linux /RemixOS/kernel quiet root=/dev/ram0 SERIAL=random logo.showlogo=$
        initrd /RemixOS/initrd.img
}
```

* update `grub.cfg`

```shell
sudo grub-mkconfig -o /boot/grub/grub.cfg
```

* Reboot, and viola ! sudah bisa boot ke Remix OS

Screenshot:

![Remix OS-2](/assets/img/remixos-1.jpg)

![Remix OS-3](/assets/img/remixos-3.jpg)

Mudah bukan? selamat mencoba
