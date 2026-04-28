<div align="center">
  <br />
  <h1>LAPORAN PRAKTIKUM</h1>
  <h2>APLIKASI BERBASIS PLATFORM</h2>
  <br />
  <h3>Flutter Hello World</h3>
  <br />
  <br />
  <img src="assets/logo.jpeg" alt="Logo TelU" width="280">
  <br />
  <br />
  <h3>Disusun Oleh :</h3>
  <p>
    <strong>DHEVA DEWA SEPTIANTONI</strong><br>
    <strong>2311102324</strong><br>
    <strong>S1 IF-11-REG01</strong>
  </p>
  <br />
  <h3>Dosen Pengampu :</h3>
  <p>
    <strong>Dimas Fanny Hebrasianto Permadi, S.ST., M.Kom</strong>
  </p>
  <br />
  <h4>Asisten Praktikum :</h4>
  <p>
    <strong>Apri Pandu Wicaksono</strong><br>
    <strong>Rangga Pradarrell Fathi</strong>
  </p>
  <br />
  <h3>
    LABORATORIUM HIGH PERFORMANCE<br>
    FAKULTAS INFORMATIKA<br>
    UNIVERSITAS TELKOM PURWOKERTO<br>
    2026
  </h3>
</div>

---

## 1. Dasar Teori Flutter

**Flutter** adalah framework open-source buatan **Google** untuk membangun aplikasi lintas platform (*cross-platform*) — Android, iOS, Web, dan Desktop — dari satu basis kode (*single codebase*). Flutter menggunakan bahasa pemrograman **Dart**.

### Konsep Utama Flutter

Konsep paling mendasar dalam Flutter adalah **Widget**. Widget merupakan elemen dasar pembentuk UI — segala sesuatu yang tampil di layar, mulai dari teks, tombol, gambar, hingga layout, semuanya adalah widget. Flutter membagi widget menjadi dua jenis utama: **StatelessWidget**, yaitu widget yang tampilannya tidak berubah setelah dibangun dan cocok digunakan untuk UI yang bersifat statis; serta **StatefulWidget**, yaitu widget yang tampilannya dapat berubah sewaktu-waktu karena memiliki *state* (kondisi) internal yang bisa diperbarui.

Selain itu, terdapat beberapa widget struktural penting. **MaterialApp** adalah widget root yang mengaktifkan tema dan desain Material Design dari Google secara global pada seluruh aplikasi. **Scaffold** merupakan kerangka halaman standar yang secara otomatis menyediakan struktur seperti `AppBar`, `body`, dan `FloatingActionButton`. Terakhir, **BuildContext** adalah referensi yang menunjukkan posisi sebuah widget di dalam widget tree, yang digunakan untuk mengakses tema, navigasi, maupun informasi konteks lainnya.

---

## 2. Penjelasan

### Kode
```dart
// ignore_for_file: prefer_const_constructors 
import 'package:flutter/material.dart'; 
void main() { 
runApp(const MyApp()); 
} 
class MyApp extends StatelessWidget { 
const MyApp({Key? key}) : super(key: key); 
// This widget is the root of your application. 
@override 
Widget build(BuildContext context) { 
    return MaterialApp( 
      title: "Hello World", 
      home: const MyHomePage(title: "Flutter Hello World Page"), 
    ); 
  } 
} 
 
class MyHomePage extends StatefulWidget { 
  const MyHomePage({Key? key, required this.title}) : super(key: key); 
 
  final String title; 
 
  @override 
  State<MyHomePage> createState() => _MyHomePageState(); 
} 
 
class _MyHomePageState extends State<MyHomePage> { 
  @override 
  Widget build(BuildContext context) { 
    return Scaffold( 
      appBar: AppBar( 
        title: Text(widget.title), 
      ), 
      body: Center( 
        child: Text( 
          'Hello World', 
        ), 
      ), 
    ); 
  } 
}
```
### Penjelasan Kode


`// ignore_for_file: prefer_const_constructors`:

Ini adalah sebuah komentar khusus untuk linter (alat pemeriksa kode).

Fungsinya adalah untuk memberi tahu linter agar mengabaikan peringatan (warning) terkait penggunaan kata kunci const. Di Flutter, disarankan untuk menggunakan const jika suatu widget tidak akan berubah setelah dibuat, untuk efisiensi. Dalam kode ini, komentar ini digunakan agar linter tidak menampilkan peringatan tersebut, yang seringkali dianggap mengganggu saat baru belajar.

`import 'package:flutter/material.dart';`:

Baris ini adalah pernyataan impor yang penting.

Fungsinya untuk mengimpor paket material.dart, yang berisi berbagai widget dan alat desain standar yang disediakan oleh Flutter. Widget-widget ini mengikuti panduan desain Material Design yang dibuat oleh Google.

`void main() { ... }`:

Ini adalah fungsi utama (entry point) dari aplikasi Flutter.

Semua program Dart (bahasa yang digunakan Flutter) dimulai dari fungsi main.

`runApp(const MyApp());`: Di dalam fungsi main, kita memanggil fungsi runApp. Fungsi ini adalah kunci untuk menjalankan aplikasi Flutter. Ia menerima sebuah widget utama (dalam hal ini, MyApp) dan menampilkannya di layar perangkat.

`class MyApp extends StatelessWidget { ... }`:

Ini adalah definisi kelas MyApp, yang merupakan widget utama aplikasi kita.

`StatelessWidget` berarti widget ini tidak memiliki state (keadaan) yang berubah setelah dibuat. Isinya statis dan tidak perlu diperbarui berdasarkan input pengguna atau data eksternal.

`const MyApp({Key? key})` : `super(key: key);`: Ini adalah konstruktor kelas. Parameter Key digunakan secara internal oleh Flutter untuk mengidentifikasi widget secara unik.

`@override Widget build(BuildContext context) { ... }`: Metode build adalah jantung dari setiap widget. Di sinilah kita mendefinisikan tampilan widget tersebut. Metode ini akan dipanggil oleh Flutter ketika widget perlu ditampilkan.

`return MaterialApp( ... );`: Di dalam metode build, kita mengembalikan widget MaterialApp. Widget ini adalah wadah tingkat atas untuk aplikasi yang menggunakan Material Design. Ia mengatur tema, rute (navigasi), dan memberikan fondasi untuk widget lainnya.

`title: "Hello World",`: Menetapkan judul aplikasi yang mungkin muncul di bilah tugas atau daftar aplikasi yang baru dibuka.

`home: const MyHomePage(title: "Flutter Hello World Page"),`: Menetapkan widget yang akan ditampilkan pertama kali saat aplikasi dijalankan. Dalam kasus ini, kita menggunakan MyHomePage dan memberikan judul "Flutter Hello World Page" ke konstruktornya.

`class MyHomePage extends StatefulWidget { ... }`:

Ini adalah definisi kelas MyHomePage, yang merupakan halaman utama aplikasi kita.

`StatefulWidget` berarti widget ini dapat memiliki state yang dapat berubah seiring waktu. Ini berguna untuk elemen UI yang responsif terhadap interaksi pengguna atau perubahan data. Meskipun halaman ini sederhana, `StatefulWidget` memberikan fleksibilitas untuk penambahan fitur di masa mendatang.

`const MyHomePage({Key? key, required this.title}) : super(key: key);`: Konstruktor kelas. required this.title berarti parameter title wajib diberikan saat membuat objek MyHomePage.

`final String title;`: Ini adalah properti yang menyimpan judul halaman. Variabel ini diberi tanda final karena nilainya tidak akan berubah setelah objek MyHomePage dibuat.

`@override State<MyHomePage> createState() => _MyHomePageState();`: Metode ini wajib ada di setiap StatefulWidget. Ia bertugas untuk membuat objek state terkait (_MyHomePageState). Objek state inilah yang akan menampung data yang dapat berubah dan mengontrol tampilan widget.

`class _MyHomePageState extends State<MyHomePage> { ... }`:

Ini adalah kelas state untuk MyHomePage.

Kelas ini mewarisi dari `State<MyHomePage>`, yang menghubungkannya dengan widget MyHomePage.

Di sinilah letak logika dan tampilan yang dapat berubah.

`@override Widget build(BuildContext context) { ... }`: Metode build di sini mendefinisikan tampilan halaman utama.

`return Scaffold( ... );`: Kita mengembalikan widget Scaffold. Widget ini menyediakan kerangka dasar untuk halaman Material Design, termasuk app bar (bilah aplikasi), body (konten utama), tombol mengambang, dll.

`appBar: AppBar( title: Text(widget.title), ),`: Kita membuat sebuah AppBar (bilah aplikasi atas). Di dalamnya, terdapat sebuah widget Text yang menampilkan judul halaman. widget.title digunakan untuk mengakses properti title dari kelas MyHomePage yang terkait.

`body: Center( child: Text( 'Hello World', ), ),`: Bagian konten utama halaman. Kita menggunakan widget Center untuk menempatkan kontennya tepat di tengah layar. Di dalam Center, terdapat widget Text yang menampilkan teks `"Hello World"`.


## 5. Referensi

- Flutter Official Docs: [https://docs.flutter.dev](https://docs.flutter.dev)
- Dart Language: [https://dart.dev](https://dart.dev)
- Material Design: [https://m3.material.io](https://m3.material.io)