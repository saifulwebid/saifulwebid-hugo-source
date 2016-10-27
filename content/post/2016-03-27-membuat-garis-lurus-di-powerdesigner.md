---
title: Membuat Garis Lurus di PowerDesigner
author: Saiful
layout: post
date: 2016-03-27T10:19:23+00:00
url: /2016/03/membuat-garis-lurus-di-powerdesigner/
dsq_thread_id:
  - 5232724529
categories:
  - PowerDesigner

---
Di semester 4 ini salah satu mata kuliah yang saya pelajari adalah Analisis dan Perancangan Perangkat Lunak 1 (APPL-1). Pada mata kuliah ini, kami menggunakan _software_ PowerDesigner untuk membuat _use case diagram_ dan kawan-kawannya.

Salah satu masalah yang muncul adalah ketika membuat asosiasi dari _actor_ ke _use case_, garis yang muncul tidak bisa lurus. Bentuknya garis patah-patah, seperti ini:

<img class="alignnone size-full wp-image-107 aligncenter" src="https://saiful.web.id/blog/wp-content/uploads/2016/03/garis-lurus-powerdesigner-1.png" alt="garis-lurus-powerdesigner-1" width="329" height="259" srcset="https://saiful.web.id/blog/wp-content/uploads/2016/03/garis-lurus-powerdesigner-1.png 329w, https://saiful.web.id/blog/wp-content/uploads/2016/03/garis-lurus-powerdesigner-1-300x236.png 300w" sizes="(max-width: 329px) 85vw, 329px" />

Padahal, notasi yang umum digunakan, garis asosiasi dari _actor_ ke _use case_ itu wujudnya berupa garis lurus.

<!--more-->Bukan hanya satu-dua orang yang mencoba, tapi kami sekelas mencoba meluruskan garis bengkok ini sulitnya minta ampun. (Lain halnya kalau "membengkokkan garis lurus" yang kami pelajari di mata kuliah Aljabar Linear. Lebih mudah itu.)

Ternyata, setelah mencari-cari di _search engine_ agak dalam, ketemulah _[thread ini][1]_. Di sana ada _statement_ seperti ini:

> What line mode have you selected? There are a number of different modes. [...] First is the jagged line (lightening bolt). This mode is all straight lines with elbows. **No attempt is made to keep the lines horizontal or vertical.**

Membaca _statement_ itu saya mendapat _feeling _bahwa ini adalah jawaban yang saya (dan kawan-kawan) cari. Setelah mencoba beberapa kali, akhirnya garis bengkok itu berhasil diluruskan.

<img class="alignnone size-full wp-image-112 aligncenter" src="https://saiful.web.id/blog/wp-content/uploads/2016/03/garis-lurus-powerdesigner-6.png" alt="garis-lurus-powerdesigner-6" width="362" height="280" srcset="https://saiful.web.id/blog/wp-content/uploads/2016/03/garis-lurus-powerdesigner-6.png 362w, https://saiful.web.id/blog/wp-content/uploads/2016/03/garis-lurus-powerdesigner-6-300x232.png 300w" sizes="(max-width: 362px) 85vw, 362px" />

Caranya ternyata mudah: **gunakan mode Corners "jagged line/lightning bolt" pada format asosiasi yang dibentuk**.

Lengkapnya seperti ini:

Pertama, klik kanan pada garis asosiasi. Pilih menu Format.

<img class="alignnone size-full wp-image-108 aligncenter" src="https://saiful.web.id/blog/wp-content/uploads/2016/03/garis-lurus-powerdesigner-2.png" alt="garis-lurus-powerdesigner-2" width="478" height="362" srcset="https://saiful.web.id/blog/wp-content/uploads/2016/03/garis-lurus-powerdesigner-2.png 478w, https://saiful.web.id/blog/wp-content/uploads/2016/03/garis-lurus-powerdesigner-2-300x227.png 300w" sizes="(max-width: 478px) 85vw, 478px" />

Pada _window_ "Symbol Format" yang muncul, pada _tab_ "Line Style", pilih opsi pertama (bergambar _jagged line_ atau seperti garis kilat) pada pilihan "Corners".

<img class="alignnone size-full wp-image-109 aligncenter" src="https://saiful.web.id/blog/wp-content/uploads/2016/03/garis-lurus-powerdesigner-3.png" alt="garis-lurus-powerdesigner-3" width="580" height="408" srcset="https://saiful.web.id/blog/wp-content/uploads/2016/03/garis-lurus-powerdesigner-3.png 580w, https://saiful.web.id/blog/wp-content/uploads/2016/03/garis-lurus-powerdesigner-3-300x211.png 300w" sizes="(max-width: 580px) 85vw, 580px" />

Selanjutnya, tekan tombol Ctrl di _keyboard_, lalu klik kiri pada sudut yang ingin dihilangkan.

<img class="alignnone size-full wp-image-110 aligncenter" src="https://saiful.web.id/blog/wp-content/uploads/2016/03/garis-lurus-powerdesigner-4.png" alt="garis-lurus-powerdesigner-4" width="329" height="259" srcset="https://saiful.web.id/blog/wp-content/uploads/2016/03/garis-lurus-powerdesigner-4.png 329w, https://saiful.web.id/blog/wp-content/uploads/2016/03/garis-lurus-powerdesigner-4-300x236.png 300w" sizes="(max-width: 329px) 85vw, 329px" />

Voila!

<img class="alignnone size-full wp-image-111 aligncenter" src="https://saiful.web.id/blog/wp-content/uploads/2016/03/garis-lurus-powerdesigner-5.png" alt="garis-lurus-powerdesigner-5" width="337" height="262" srcset="https://saiful.web.id/blog/wp-content/uploads/2016/03/garis-lurus-powerdesigner-5.png 337w, https://saiful.web.id/blog/wp-content/uploads/2016/03/garis-lurus-powerdesigner-5-300x233.png 300w" sizes="(max-width: 337px) 85vw, 337px" />

Garis yang bengkok sudah bisa diluruskan. Dengan cara yang sama, kita bisa "membengkokkan" garis lurus dengan menambah sudut-sudut lain pada garis yang ada.

Semoga bermanfaat. (Khususnya untuk saya sendiri — hal-hal begini, kalau tidak dicatat di suatu tempat, pasti akan mudah terlupakan.)

 [1]: http://codeverge.com/sybase.powerdesigner.general/lines-with-angles/832901
