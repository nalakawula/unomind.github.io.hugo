---
title: 
date: 2017-04-14T19:39:08+07:00
showDate: true
draft: false
tags: ["blog"]
---
Hari ini, saya mainan virtualbox dengan setup sebagai berikut:
- Sistem operasi: Ubuntu 16.04
- Network Adapter 1: NAT
- Network Adapter 2: Host-Only adapter
- Host only adapter sudah diset sebagai DHCP Server

## Masalah
Setelah selesai Intsall sistem operasi, ternyata adapter 2 tidak mendapatkan IP Address.

## Solusi
1. Cek apakah network adapater 2 terdeteksi oleh sistem,
```
ip link
```
Catat outputnya, misal adapter 1 terdeteksi sebagai ens0p3 dan adapter 2 tereteksi sebagai ens0p8.
2. Edit `/etc/network/interfaces` dan isi dengan:
```
auto ens0p3
iface ens0p3 inet dhcp
auto ens0p8
iface ens0p8 inet dhcp
```
3. Restart network
```
sudo systemctl restart networking
```
4. Profit