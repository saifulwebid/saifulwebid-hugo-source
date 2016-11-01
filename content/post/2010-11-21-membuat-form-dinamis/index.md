---
title: Membuat Form Dinamis
date: 2010-11-21T00:00:00+07:00
slug: membuat-form-dinamis
categories:
  - Arsip Lama
oldblog: http://muhammad.saiful.web.id/2010/11/membuat-form-dinamis/
---

Form dinamis yang saya maksud di atas adalah, form yang bisa menambah jumlah field yang ia miliki, tergantung permintaan dari user. Form ini akan menambah fieldnya menggunakan JavaScript, yang hasilnya: no-refresh needed! 😊

Langsung saja:

<!--more-->

```
<script type="text/JavaScript">
function add_new_field() {
     document.getElementById("fields").innerHTML =
          document.getElementById("fields").innerHTML +
          document.getElementById("additionalfield").innerHTML;
}
</script>

<form id="formkita">
     <div id="fields">
          <input type="text" name="data[]" />
     </div>
     <div id="additionalfield" style="display: none;">
          <input type="text" name="data[]" />
     </div>
     <a href="javascript:add_new_field();">Tambah Field</a>
</form>
```

(Apakah ada cara lebih baik untuk menambahkan string tambahan pada suatu variabel di JavaScript? Di PHP, ini bisa dilakukan dengan mudah dengan `$variabel .= $tambahan` yang hasilnya sama dengan `$variabel = $variabel . $tambahan`.)
