---
title: Repositori Lokal Linux Mint 17 Qiana
author: Saiful
layout: post
date: 2014-11-01T15:33:16+00:00
slug: repositori-lokal-linux-mint-17-qiana
disqus_identifier: 5232724638
categories:
  - Linux
tags:
  - linux mint

---
Hal yang saya lakukan ketika baru melakukan instalasi Ubuntu (dan turunannya, seperti Linux Mint yang saya gunakan sekarang) adalah mengganti sumber repositori yang digunakan ke _mirror-mirror_ yang ada di Indonesia (seperti [Kambing UI][1], atau [FTP ITB][2], dan _mirror_ lainnya). Ketika saya sempat mencoba Ubuntu 14.04 LTS beberapa waktu lalu, saya menggunakan _mirror_ ITB.

Ketika saat ini saya menggunakan Linux Mint 17 Qiana, saya menemukan bahwa ITB tidak melakukan _mirror_ terhadap repositori Linux Mint. Hasil Google-_ing_ singkat menunjukkan bahwa Kambing UI dan [repositori UKDW][3]-lah yang melakukan _mirror_ terhadap repositori Linux Mint.

Sehingga, saya membuka Terminal dan mengetikkan ...

```
sudo nano /etc/apt/sources.list
```

Tapi ternyata, hal ini yang saya temui:

![](repo-lokal-1.png)

Lho, ke mana puluhan baris yang biasa saya temui di `/etc/apt/sources.list` milik Ubuntu itu?

<!--more-->Saya mencoba mengakses System Settings bawaan dari Linux Mint 17, kemudian membuka konfigurasi Software Sources di bagian bawah. Setelah memasukkan
_root password_, saya agak kaget dengan tampilan ini — dan langsung berdecak kagum:

![](repo-lokal-2.png)

Ternyata, secara standar, Linux Mint 17 sudah menyediakan opsi untuk merubah sumber repositorinya ke berbagai _mirror_ di seluruh dunia. Kambing UI dan repositori UKDW juga tercantum di sana.

 [1]: http://kambing.ui.ac.id/
 [2]: ftp://ftp.itb.ac.id/pub/
 [3]: http://repo.ukdw.ac.id/
