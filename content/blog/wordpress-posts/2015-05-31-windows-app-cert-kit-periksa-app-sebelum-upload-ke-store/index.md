---
title: 'Windows App Cert Kit: Periksa App Sebelum Upload ke Store'
author: Saiful
date: 2015-05-31T04:38:50+00:00
slug: windows-app-cert-kit-periksa-app-sebelum-upload-ke-store
categories:
  - Microsoft Ecosystem
blackfriday:
  sourceRelativeLinksEval: false

---
Salah satu tahapan yang akan dilalui App kita sebelum ditayangkan oleh Microsoft di Store (baik Windows Store maupun Windows Phone Store) adalah pengujian. Semua aplikasi yang akan ditayangkan pasti diuji dulu secara otomatis. Beberapa aplikasi akan diuji secara manual, tapi mayoritas tidak akan melalu pengujian manual lagi.

Nah ... kayaknya repot ya kalau misalnya buat App yang ukurannya besar, terus sudah upload lama-lama (apalagi kalau pakai koneksi umum di Indonesia — lain hal kalau misalnya pakai koneksi di kampus :D), terus ternyata hasil pengujiannya gagal?

Untungnya, Microsoft punya aplikasi Windows App Certification Kit. Aplikasi ini sudah include dengan Windows Development Kit yang bisa diinstal bersama Visual Studio. Dengan aplikasi ini, kita bisa menguji App yang sudah dibuat secara lokal. Konon katanya, kalau sudah lolos pengujian di sini, kemungkinan besar akan lolos juga di Store karena metode pengujiannya sama.

<!--more-->Item test yang dilakukan oleh Windows App Certification Kit ini adalah:

  * App capabilities test
  * App manifest resources test
  * Crashes and hangs test (tidak termasuk untuk Phone App)
  * Debug configuration test
  * Direct3D feature test (tidak termasuk untuk Phone App)
  * File encoding test
  * Package compliance test
  * Package sanity test
  * Performance test (tidak termasuk untuk Phone App)
  * Resource usage test
  * Supported API test
  * Windows Runtime metadata validation
  * Windows security features test

Penggunaannya pun sangat mudah. Wizard-nya user friendly (bahkan untuk user biasa sekalipun!). Tidak banyak jargon-jargon aneh yang terdapat pada aplikasi ini. Tinggal pilih jenis App yang ingin diuji, lalu pilih App-nya, lalu tunggu beberapa saat, dan hasil tes pun keluar.

![](/blog/from-wp/2015-app-cert-kit/Screenshot-2015-05-31-11.35.22.png)

Microsoft sangat merekomendasikan semua App yang kita buat untuk diuji dengan aplikasi ini sebelum meng-upload-nya ke Store. Saya sendiri sangat terbantu dengan aplikasi ini: aplikasi ini mengingatkan saya untuk melakukan Build dengan mode Release ketika pengujian, mengingatkan untuk menambah logo aplikasi dan splash screen, dan hal-hal trivial lainnya.

Kalau Anda ingin melihat contoh report yang dihasilkan, Anda bisa lihat [contoh report yang berhasil][1], [yang gagal][2], dan [report untuk Windows Phone App][3].

 [1]: /blog/from-wp/2015-app-cert-kit/app-test-success.htm
 [2]: /blog/from-wp/2015-app-cert-kit/app-test-failed.html
 [3]: /blog/from-wp/2015-app-cert-kit/phone-test-success.html
