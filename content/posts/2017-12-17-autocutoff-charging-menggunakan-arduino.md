---
title: 
date: 2017-04-14T19:39:08+07:00
showDate: true
draft: false
tags: ["blog"]
---
HP menjadi sebuah kebutuhan primer, saya tidak menyangkalnya. Hampir 24 jam setiap hari HP selalu ada di dekat saya. Bicara soal HP, tidak lepas dari baterai dan charging. Biasanya HP saya, biasa hidup dari jam 3 pagi, sampai jam 12 malam. Waktu antara 00:00 - 03:00, saya gunakan untuk charging, karena itu pas dengan jam istirahat. Namun demikian, sering terjadi hal-hal luar biasa, misalnya saya tidur jam 20:00 atau jam 21:00 karena lelah setelah aktivitas siang hari. Pada saat saya tidur, HP harus dicharge, karena saya butuh untuk esok pagi. Bayangkan, jika saya tidur jam 21:00 dan bangun jam 03:00, HP saya charge selama 6 jam. Lama-lama bisa jebol baterainya. Kalau jebol bisa repot, jama sekarang HP model unibody, susah gantinya.

Berangkat dari masalah tsb, saya berinisiatif untuk membuat timer autocutoff charging. Wah keren, beli jadi ada banyak sepertinya. Mmm, kalau beli alat yang sudah jadi, berasa kurang _geek_. Kebetulan saya punya komponen-komponen nganggur bekas mainan jaman dulu. Dimanfaatkan saja.

Secara garis besar, saya butuh:
1. Arduino sebagai kontroler, kebetulan saya punya beberapa Arduino Nano nganggur.
2. RTC DS3231, sekalian aja bikin jam digital.
3. Adaptor 9V 2A, untuk catu daya. 1A juga tidak masalah, kebetulan saja punyanya itu.
4. IC regulator 7805, untuk regulasi tengangan ke uC, LCD, Relay, RTC.
5. Komponen penunjang seperti elco, dc barrel jack, pcb bolong, kabel, push button, dll.
6. LCD 1602, saya punya yang sudah saya tambah I2C, lumayan untuk menghemat pin uC.
7. Modul relay.
8. Stop kontak, yang akan dipotong jalur listriknya.

Apa yang saya pikirkan untuk dibuat:
1. LCD menampilkan hari, tanggal, bulan, tahun, jam, menit, detik, timer.
2. Ada sistem menu sederhana untuk pengaturan poin nomer 1.
3. Fungsi timer ini yang ingin saya pakai untuk cutoff charging. Misalnya HP akan penuh setelah 2 jam 30 menit, tinggal masuk menu, set timer dari jam sekarang ditambah 2 jam 30 menit.

Prototipe jelek ini sudah jadi baik hardware maupun programnya, dan sudah saya coba. Pembahasan lebih lanjut, nantikan artikel berikutnya.

