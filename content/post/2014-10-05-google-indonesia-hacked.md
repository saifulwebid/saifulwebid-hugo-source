---
title: Google Indonesia "hacked"?
author: Saiful
layout: post
date: 2014-10-05T05:07:49+00:00
url: /2014/10/google-indonesia-hacked/
dsq_thread_id:
  - 5232724734
categories:
  - Intermezzo
tags:
  - DNS
  - Telkom

---
<img class="alignnone size-full wp-image-23" src="https://saiful.web.id/blog/wp-content/uploads/2014/10/Screenshot-2014-10-05-04.57.31.png" alt="Google Indonesia di-&quot;hack&quot;" width="1366" height="768" srcset="https://saiful.web.id/blog/wp-content/uploads/2014/10/Screenshot-2014-10-05-04.57.31.png 1366w, https://saiful.web.id/blog/wp-content/uploads/2014/10/Screenshot-2014-10-05-04.57.31-300x168.png 300w, https://saiful.web.id/blog/wp-content/uploads/2014/10/Screenshot-2014-10-05-04.57.31-1024x575.png 1024w, https://saiful.web.id/blog/wp-content/uploads/2014/10/Screenshot-2014-10-05-04.57.31-800x449.png 800w" sizes="(max-width: 709px) 85vw, (max-width: 909px) 67vw, (max-width: 1362px) 62vw, 840px" />

Sambil menunggu keluarga di rumah bersiap untuk berangkat shalat Idul Adha, saya membuka laptop untuk _browsing_, sekadar mampir di Facebook, Twitter, Quora, dan beberapa media sosial lainnya. Entah apa yang saya kerjakan hingga kemudian saya membuka tab baru dan mencoba mengakses Google Indonesia.

Dan, tampilan di atas yang saya temui.

_Wait, what?_ Sekelas Google Indonesia pun kena retas juga?

<!--more-->Entahlah. 

_Feeling_ saya mengatakan bahwa tidak wajar perusahaan sekelas Google kena retas. _Something just went off..._ hingga saya menemukan bahwa situs Google di www.google.com masih bisa diakses.

Dengan data seminim itu saya mencoba berdeduksi. Bukan Google-nya yang diretas. Mungkin DNS-nya yang diretas.

Karena sudah mau berangkat ke tempat shalat, jadi saya matikan saja dulu laptop saya. Untuk membuktikan hipotesa tadi, saya coba lakukan dua hal dengan ponsel saya selama masih di rumah:

  1. _Connect_ ke Wi-Fi di rumah (yang menggunakan Telkom Speedy). Coba akses www.google.co.id. Hasil: tampilan Google Indonesia yang sudah berubah jadi warna hitam itu muncul di ponsel saya.
  2. _Disconnect_ dari Wi-Fi di rumah dan coba gunakan koneksi _mobile data_. Saya sempat pesimis karena saya menggunakan Telkomsel dan dugaan saya server DNS yang digunakan pasti sama. Ternyata ... _voila!_ Google Indonesia tidak apa-apa. Baik-baik saja 🙂

Perusahaan sebesar Google rasa-rasanya tidak akan tumbang dengan serangan _deface_ seperti ini. Entah kenapa rasa-rasanya tidak mungkin. Kalaupun iya, tampilan hasil _deface_-nya semestinya lebih keren sedikit. (Entahlah, demikian _feeling_ saya berbicara.)

Sepulang dari shalat Idul Adha saya mencoba akses lagi. Yang saya alami, sekarang selalu muncul galat _connection timed out_ dari Google Chrome saya. Sementara itu, saya coba lakukan _quick search_ di Twitter dan menemukan bahwa tampilan-nya sekarang lebih semarak: di bawah pesan peretas itu malah ada tombol Facebook Like segala. :))

Akhirnya, saya coba laporkan ke @TelkomCare.

<blockquote class="twitter-tweet" data-width="550">
  <p lang="in" dir="ltr">
    <a href="https://twitter.com/TelkomCare">@TelkomCare</a>, apakah DNS Telkom Speedy sedang gangguan? Saya akses <a href="http://t.co/iCV9NNNbL7">http://t.co/iCV9NNNbL7</a> saja tdk bisa. Tadi pagi malah seperti dihack [1/2]
  </p>

  <p>
    &mdash; Muhammad Saiful I. (@saifulwebid) <a href="https://twitter.com/saifulwebid/status/518589143375302656">October 5, 2014</a>
  </p>
</blockquote>



<blockquote class="twitter-tweet" width="550">
  <p lang="in" dir="ltr">
    <a href="https://twitter.com/TelkomCare">@TelkomCare</a> tampilan dihack hanya dari TelkomSpeedy, dari Telkomsel dan ISP lain tidak. Restart modem tdk berefek. Tq <a href="http://t.co/oorAxiK0md">pic.twitter.com/oorAxiK0md</a>
  </p>

  <p>
    &mdash; Muhammad Saiful I. (@saifulwebid) <a href="https://twitter.com/saifulwebid/status/518589377711058945">October 5, 2014</a>
  </p>
</blockquote>



_Long story short_, setelah bertukar informasi di _direct messages_ dan beberapa _mention_, akhirnya dibuatlah pengaduan.

<blockquote class="twitter-tweet" width="550">
  <p lang="in" dir="ltr">
    <a href="https://twitter.com/saifulwebid">@saifulwebid</a> Baik saiful, sudah kami buatkan pelaporan kepada petugas yaa, nomor pelaporan silakan cek DM.^IW
  </p>

  <p>
    &mdash; Telkom Care (@TelkomCare) <a href="https://twitter.com/TelkomCare/status/518613453435461633">October 5, 2014</a>
  </p>
</blockquote>



Saya cukup senang bahwa _customer service_ @TelkomCare ini cukup responsif. Bahkan, di _direct messages_ pun laporan saya ditanggapi oleh tiga orang sekaligus, padahal ini hari libur 🙂 Setahu saya, bahkan ketika ayah saya melapor ke Telkom 147 pun nomor pelaporan semacam itu tidak diinformasikan.

Jadi? Kesimpulannya apa? Google Indonesia tidak diretas. Tidak semudah itu meretas situs Google Indonesia. Yang diretas — mungkin — DNS server yang dipakai Telkom Speedy. Tapi saya penasaran apakah memang semudah itu meretas DNS server? Kalau benar, apakah berarti keamanan kita lemah? Entahlah. Ilmu saya belum sampai ke sana. Saya masih menikmati perjalanan awal di _software engineering_ 😀

(Dan, belakangan, setelah saya coba atur manual DNS server di _router_ saya ke Google Public DNS di 8.8.8.8 dan 8.8.4.4, saya bisa mengakses kembali situs Google Indonesia dengan lancar.)
