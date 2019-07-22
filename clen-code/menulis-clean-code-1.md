# Menulis Clean Code \#1

## **Nama yang bermakna**

Gunakan maksud yang jelas ketika menulis nama. Menentukan nama yang baik membutuhkan waktu tapi itu akan lebih menghemat waktu kedepannya. Kenapa bisa lebih menghemat waktu? karena ketika kamu kembali pada kode yang kamu buat, kamu akan mudah mengetahui apa yang terjadi pada kodemu dengan penamaan yang baik. Nama variabel, fungsi, atau kelas, harus menjawab semua pertanyaan besar. Nama tersebut **harus memberitahumu kenapa fungsi/kelas/variabel itu ada, dan apa yang dilakukannya, dan bagaimana cara menggunakannya.** Jika suatu nama membutuhkan sebuah komen, maka nama itu tidak menampakkan maksudnya.  


Misalnya **- int d; // elapsed time in days**

Kita harus memilih nama yang menentukan apa yang diukur dan unit pengukuran itu.

Nama yang lebih baik dari contoh diatas adalah: - int elapsedTimeInDays, Karena nama tersebut menampakkan kenapa dia ada, apa yang dia lakukan, dan bagaimana cara menggunakannya.

#### Nama kelas

Kelas atau object harus memiliki kata benda atau frasa kata benda seperti Customer, WikiPage, Account, dan AddressParser. Hindari kata-kata seperti Manager, Processor, Data, atau Info atas nama kelas. Nama kelas tidak boleh berupa kata kerja.

#### **Nama metode**

Metode nama kata kerja atau frasa kata kerja seperti postPayment, deletePage, atau save. Mengakses \(get\), merubah \(put\), predicates harus dinamai sesuai nilainya dan diawali dengan get, set.

Ketika constructors itu overloaded, gunakan metode static factory dengan nama yang mendefinisikan argumennya. Contoh,

Complex fulcrumPoint = Complex.FromRealNumber\(23.0\); umumnya lebih baik dari Complex fulcrumPoint = new Complex\(23.0\);

#### **Pilih satu kata setiap konsep**

Pilih satu kata untuk satu konsep abstrak dan pertahankan itu. Misalnya, kadang kita menamai fetch di satu bagian kadang retrieve, kadang juga get sebagai metode yang sama dengan kelas berbeda. Sangat membingungkan bukan? Bagaimana caranya kamu mengingat metode mana untuk kelas yang mana? Juga, sangat membingungkan ketika kita mempunyai sebuah controller  dan sebuah manager dan sebuah driver di satu kode basis yang sama. Apa sih perbedaan penting antara DeviceManager dan Protocol-Controller?



