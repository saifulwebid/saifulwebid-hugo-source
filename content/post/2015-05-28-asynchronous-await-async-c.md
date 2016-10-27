---
title: 'Asynchronous dengan “await” dan “async” pada C#'
author: Saiful
layout: post
date: 2015-05-27T22:24:50+00:00
url: /2015/05/asynchronous-await-async-c/
categories:
  - Microsoft Ecosystem

---
Dulu, saat saya sering membuat halaman-halaman web sederhana, saya beberapa kali memanfaatkan asynchronous programming untuk beberapa keperluan. Secara sederhana, asynchronous programming adalah teknik di mana suatu fungsi berjalan dengan thread yang berbeda dengan thread utama, sehingga bisa menjalankan dua atau lebih fungsi dalam waktu yang bersamaan.

Sebagai contoh, jika saya memiliki fungsi `getData()` yang berfungsi mengambil data siswa dari <http://mhs.polban.ac.id/> misalnya, maka waktu prosesnya akan bervariasi pada berbagai kondisi. Jika kondisinya stabil (baik pada client maupun pada server) maka delay yang dirasakan mungkin tidak signifikan.

Namun, bagaimana jika kondisinya tidak stabil? <!--more-->Misalnya, client hanya dapat jaringan EDGE, kemudian server juga sedang berat diakses? Bagaimana jika fungsi 

`getData()` sedang berjalan lalu user ternyata berubah pikiran dan ingin mengakses fitur lain? Kemungkinan besar yang terjadi: muncullah tulisan “(Not Responding)” di samping tulisan “Mozilla Firefox”.

Nah, teknik asynchronous programming dapat mengatasi hal seperti ini. Namun biasanya implementasinya agak rumit. Ketika kita menjalankan `getData()` secara asynchronous, kita harus menyediakan fungsi yang akan dipanggil sebagai callback. Misalnya, setelah `getData()` dipanggil, callbacknya adalah: hasil dari `getData()` akan ditampilkan dalam sebuah container.

Pada teknologi Microsoft sendiri, sejak Visual Studio 2012 diluncurkan, implementasi asynchronous dapat sangat mudah dilakukan dengan dua buah keyword baru: `await` dan `async`. Dan, subhanallah, ini gampang banget! Saat mengimplementasikan ini untuk [tugas Microsoft Student Partner saya][1], saya tidak merasa membuat sebuah asynchronous call seribet zaman dahulu!

Coba Anda lihat kode program berikut [1]:

<pre class="lang:c# decode:true ">private async void ButtonClick(object sender, EventArgs e)
{
	var client = new WebClient();
	var imageData = await client.DownloadDataTaskAsync("http://image-url");
	pictureBox.Image = Image.FromStream(new MemoryStream(imageData));
}</pre>

Lihatlah: sekilas, seperti tidak membuat asynchronous call yang ribet! Baris kelima otomatis menjadi callback dari asynchronous call pada baris keempat.

Perhatikan bahwa pada baris pertama, ada keyword async. Keyword ini menunjukkan bahwa method ButtonClick() akan memiliki pemanggilan yang bersifat asynchronous. Pemanggilan ini ditunjukkan pada keyword await pada baris 4.

Ya, memang pemanggilan asynchronous call ini bukan berarti membuat sebuah thread baru. Kalau ada thread baru, berarti bisa jadi ada dua proses yang berjalan bersamaan ya? (CMIIW). Tapi kalau ini tidak [2].

### 

### Getting Started

Pada .NET Framework 4.5, banyak method baru yang memanfaatkan fitur ini, ditandai dengan akhiran &#8220;Async&#8221; pada nama method-nya dan nilai kembali berupa Task atau Task<T>. Sebagai contoh, [WebClient][2] memiliki method [DownloadDataTaskAsync()][3] sebagai komplemen dari [DownloadData()][4] [1].

Pada Windows Runtime (WinRT), hampir semua operasi berjalan secara asynchronous. Semua operasi yang kemungkinan dapat berjalan di atas 50 ms diimplementasikan sebagai fungsi asynchronous. Operasi-operasi seperti networking, file access, API sensor, dan operasi lain yang terkait dengan I/O [1].

### Referensi

[1] Marukovich, Andrei. 2013. &#8220;[C# async and await: Why Do We Need Them?][5]&#8221; MSDN Canadian Developer Connection.

[2] &#8220;[Asynchronous Programming with Async and Await (C# and Visual Basic)][6]&#8220;. MSDN.

 [1]: https://github.com/saifulwebid/polban-news-reader
 [2]: http://msdn.microsoft.com/en-ca/library/system.net.webclient%28v=vs.110%29.aspx
 [3]: http://msdn.microsoft.com/en-ca/library/hh138334(v=vs.110).aspx
 [4]: http://msdn.microsoft.com/en-ca/library/ms144188(v=vs.110).aspx
 [5]: http://blogs.msdn.com/b/cdndevs/archive/2013/12/18/c-async-and-await-why-do-we-need-them-part-1.aspx
 [6]: https://msdn.microsoft.com/en-us/library/hh191443.aspx