---
title: Universal Apps, Write-Once-(Almost)-Run-Everywhere
author: Saiful
layout: post
date: 2015-05-10T11:25:09+00:00
url: /2015/05/universal-apps-write-once-almost-run-everywhere/
categories:
  - Life Notes
  - Microsoft Ecosystem

---
Seumur-umur membuat software ([kecil-kecilan][1]), saya baru tahu beberapa waktu terakhir kalau di ekosistem Windows Apps saat ini ada konsep Universal Apps. Pertama kali mendengar istilah ini, saya pikir dengan Universal Apps kita dapat membuat suatu aplikasi Windows Apps dan aplikasi yang sama juga berjalan di Windows Phone.

Well, setelah baca-baca di berbagai sumber (terutama MSDN), asumsi saya [ternyata &#8220;benar&#8221; untuk Windows 10][2]. (Yeay! Write once, run everywhere!) Apalagi santer dibicarakan di berbagai rilis-rilis yang kita baca kalau Windows 10 ini memang akan jadi [one OS to rule them all][3]. Di Windows 10, ada suatu konsep bernama Universal Windows Platform yang intinya setiap device yang berbeda (desktop, mobile, ..., bahkan Xbox) memiliki implementasi Windows Core yang sama, sehingga aplikasi yang dikembangkan dapat memanfaatkan core tersebut untuk mampu berjalan di berbagai device.

Nah, bagaimana untuk adiknya, Windows 8.1?

<!--more-->Universal Apps di adiknya tidak se-sakti itu, apparently. Dari berbagai referensi, saya menyimpulkan bahwa Universal Apps generasi sebelumnya tetap menuntut ada dua project terpisah (masing-masing untuk Windows dan Windows Phone, jika dilihat dari perspektif Visual Studio). Namun kode dasarnya bisa tetap sama. Misalnya, metode untuk pull data dari public API tetap sama, hanya implementasi penampilan UI-nya saja yang berbeda antara Windows dan Windows Phone.

**Terus, jadi tetap develop dua aplikasi dong?**

(Sepertinya) betul. (Saya sedang coba.) Tapi effortnya tidak sebesar murni membuat dua aplikasi, karena selain banyak kode yang bisa dibagi antar dua project tersebut, hal-hal lain seperti user controls, assets, atau localization strings (terjemahan aplikasi — jika membuat aplikasi multi-bahasa) pun bisa dibagi.

**Sedang coba?**

Ya. Saya masuk ke ekosistem Windows Apps ini juga karena sedang mengajukan diri untuk menjadi Microsoft Student Partner Indonesia tahun 2015. Salah satu commitment review-nya adalah membuat sebuah Universal Apps. (Mohon doanya ya!)

Hasilnya bagaimana? Tunggu post selanjutnya ...

 [1]: https://id.linkedin.com/in/saifulwebid
 [2]: https://msdn.microsoft.com/library/dn975273.aspx
 [3]: http://gizmodo.com/heres-how-windows-10-apps-will-run-across-pcs-tablets-1680830108
