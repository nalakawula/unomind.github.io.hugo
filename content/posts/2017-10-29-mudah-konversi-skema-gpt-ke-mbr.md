---
title: 
date: 2017-04-14T19:39:08+07:00
showDate: true
draft: false
tags: ["blog"]
---
Apa itu GPT?
Apa itu MBR?
Silakan _surfing_ saja untuk mencari tahu tentang GPT dan MBR.

### Kronologi
Si A membeli HDD 500GB seken, untuk mengganti HDD laptopnya yang rusak. Setelah dipasang, mau diinstall Windows 7. Ternyata ditengah jalan muncul error yang intinya Windows tidak dapat diinstall di HDD tersebut. Usut punya usut, pemilik sebelumnya memformat HDD tsb. dengan skema GPT. Kalau begitu, harus di konversi ke MBR.

### Kendala
1. Tidak ada komputer lain
2. Tidak punya bootable OS selain installer Windows 7

### Solusi
1. Di Wizard installer window 7, tekan <kbd>shift</kbd> + <kbd>F10</kbd>
2. Jalankan diskpart
```
diskpart
```
3. List disk
```
list disk
```
4. Pilih disk yang mau dikonversi
```
select disk 0
```
5. Clean untuk menghapus semua partisi dan dari disk yang terpilih
```
clean
```
6. Konversi ke MBR
```
convert mbr
```
7. Reboot
8. Profit

Sudah gitu aja