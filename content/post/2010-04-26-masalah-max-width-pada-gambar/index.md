---
title: Masalah max-width Pada Gambar
date: 2010-04-26T17:28:00+07:00
slug: masalah-max-width-pada-gambar
category:
  - Arsip Lama
oldblog: http://saiful.web.id/post/18/masalah-max-width-pada-gambar/
---

Anda seorang web designer, mendesain sebuah website dengan CSS dan menerapkan pembatasan lebar gambar dengan menggunakan max-width. Anda mengetikkan kode-kode berikut dan berharap gambar-gambar yang lebih besar dari 500 pixel dapat dikecilkan ke ukuran 500 pixel dengan proporsional.

    #content img { max-width: 500px; }

Lalu Anda memasukkan gambar berukuran 1.024×768 pixel dan berharap ia mengecil dengan proporsional. Tapi yang Anda temui adalah sebuah gambar yang dikecilkan paksa lebarnya sebesar 500 pixel, sementara tingginya tetap 768 pixel. Dan Anda berkata, "Bukan ini yang saya inginkan!"

<!--more-->

## Solusi

Gunakan saja kode berikut:

    #content img { max-width: 500px; height: auto; }

Dan buatlah diri Anda tersenyum melihat gambar yang Anda tampilkan kini mengecil dengan proporsional. Selamat bermain CSS!
