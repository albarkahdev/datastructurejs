# Menulis Clean Code \#2

## **Fungsi**

Aturan pertama fungsi adalah mereka harus kecil. Kedua mereka harus lebih kecil dari itu. Ini berarti bahwa blok yang ada pada pernyataan if, else, while, dan seterusnya harus sepanjang satu baris. Dan mungkin baris tersebut harus menjadi pemanggil sebuah fungsi. Ini tidak hanya menjaga fungsi tetap kecil, tetapi juga menambah nilai dokumenter karena fungsi yang dipanggil di dalam blok tersebut dapat memiliki sebuah deskriptif nama yang bagus.

#### **Argument fungsi**

Suatu fungsi tidak boleh memiliki lebih dari 3 argumen. Buat sesedikit mungkin argumen. Ketika suatu fungsi tampaknya membutuhkan lebih dari dua atau tiga argumen, ada kemungkinan bahwa beberapa argumen tersebut harus dibungkus ke dalam kelas mereka sendiri. Mengurangi argumen dengan cara membuat objek dari luar mereka tampaknya curang, tetapi tidak.

Misalnya kamu ingin membuat fungsi yang menghasilkan String pengenalan seseorang. Di dalam String tersebut membutuhkan nama, umur, alamat, hobi, dll. Yang membutuhkan lebih dari tiga argumen. Kamu bisa membuat fungsi itu hanya membutuhkan satu buah argumen saja berupa objek detail user.

Sekarang ketika saya mengatakan untuk mengurangi ukuran fungsi mu, dan kamu sedang membuat fungsi try-catch. Kamu pasti akan berpikir bagaimana cara mengurangi fungsi try-catch karena fungsi tersebut suda membuat kode mu jauh lebih besar. Jawaban saya adalah membuat fungsi yang berisi pernyataan akhirnya saja atau blok yang berfungsi untuk memanggil fungsi yang lainnya. Dan memisahkan body fungsi pada fungsi yang berbeda.

```text
public void delete(Page page) { 
  try {
     deletePageAndAllReferences(page);
  }
  catch (Exception e) { 
    logError(e);
  } 
}

private void deletePageAndAllReferences(Page page) throws Exception { 
    deletePage(page);
    registry.deleteReference(page.name); 
    configKeys.deleteKey(page.name.makeKey());
}

private void logError(Exception e) { 
    logger.log(e.getMessage());
}
```

Ini membuat logikanya lebih jelas. Nama fungsi mudah menggambarkan apa yang ingin kita capai. Penanganan error bisa diabaikan. Ini memberikan pemisahan yang bagus yang membuat kode kita lebih mudah dipahami dan dimodifikasi.

**Penanganan Error adalah satu hal**

Sebuah fungsi harus mengerjakan satu hal. Penanganan error merupakan hal yang lain. Jika suatu fungsi memiliki kata kunci try maka fungsi tersebut harus menjadi kata kunci pertama dan seharusnya tidak ada apa-apa setelah catch atau final blok.

