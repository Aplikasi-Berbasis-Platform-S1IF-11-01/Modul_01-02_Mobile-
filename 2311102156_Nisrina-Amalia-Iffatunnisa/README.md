<div align="center">
  <br />
  <h1>LAPORAN PRAKTIKUM <br>APLIKASI BERBASIS PLATFORM</h1>
  <br />
  <h3> Modul 01-02 Mobile <br> Hello World</h3>
  <br />
  <img src="./assets/logo.png" alt="Logo" width="300"> 
  <br />
  <br />
  <br />
  <h3>Disusun Oleh :</h3>
  <p>
    <strong>Nisrina Amalia Iffatunnisa</strong><br>
    <strong>2311102156</strong><br>
    <strong>S1 IF-11-01</strong>
  </p>
  <br />
  <h3>Dosen Pengampu :</h3>
  <p>
    <strong>Dimas Fanny Hebrasianto Permadi, S.ST., M.Kom</strong>
  </p>
  <br />
  <br />
    <h4>Asisten Praktikum :</h4>
    <strong> Apri Pandu Wicaksono </strong> <br>
    <strong>Rangga Pradarrell Fathi</strong>
  <br />
  <h3>LABORATORIUM HIGH PERFORMANCE
 <br>FAKULTAS INFORMATIKA <br>UNIVERSITAS TELKOM PURWOKERTO <br>2026</h3>
</div>


## 1. Penjelasan Lengkap Pembuatan Proyek

### A. Flutter
Flutter adalah kerangka kerja sumber terbuka yang dikembangkan dan didukung oleh Google. Developer frontend dan full-stack menggunakan Flutter untuk membangun antarmuka pengguna (UI) aplikasi untuk beberapa platform dengan kode program tunggal. Saat Flutter diluncurkan pada tahun 2018, Flutter terutama mendukung pengembangan aplikasi seluler. Flutter kini mendukung pengembangan aplikasi di enam platform, yaitu iOS, Android, web, Windows, MacOS, dan Linux

Keuntungan Flutter
- Performa yang mendekati aslinya. Flutter menggunakan bahasa pemrograman Dart dan dikompilasi menjadi kode mesin. Perangkat host memahami kode ini sehingga memastikan performa yang cepat dan efektif.
- Rendering yang cepat, konsisten, dan dapat disesuaikan. Alih-alih mengandalkan alat rendering khusus platform, Flutter menggunakan pustaka grafis Skia sumber terbuka milik Google untuk me-render UI. Keuntungan ini memberi pengguna visual yang konsisten, apa pun platform yang digunakan untuk mengakses aplikasi. 
- Alat yang ramah developer. Google membuat Flutter dengan mengutamakan pada kemudahan penggunaan. Dengan alat seperti hot reload, developer dapat melihat seperti apa perubahan kode tanpa kehilangan status. Alat lain seperti pemeriksa widget memudahkan dalam memvisualisasikan dan memecahkan masalah tata letak UI.

Flutter menggunakan bahasa pemrograman sumber terbuka Dart, yang juga dikembangkan oleh Google. Dart dioptimalkan untuk membangun UI. Flutter berjalan menggunakan Dart Virtual Machine (VM) di sistem operasi Windows, Linux, dan macOS. Dart VM menggunakan kompilasi kode just-in-time (JIT) yang menyediakan fitur hot-reload untuk menghemat waktu pengembangan. Di Flutter, developer membuat tata letak UI dengan menggunakan widget. Widget Flutter didesain agar developer dapat dengan mudah menyesuaikannya. Flutter mencapai tujuan ini melalui pendekatan komposisi. Artinya, sebagian besar widget terbuat dari widget yang lebih kecil, dan sebagian besar widget dasar memiliki tujuan tertentu. Hal ini memungkinkan developer untuk menggabungkan atau mengedit widget untuk membuat widget yang baru

### Hasil Penugasan
![Tampilan](./assets/2311102156_Praktikum%20Dart%20Hello%20World.jpg)

## 2. Sourcecode 

### Sourcecode main.dart
``` Dart
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
      title: "Hello World, Nisrin",
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
          'Hello World, Nisrin!',
        ),
      ),
    );
  }
}
```

## Penjelasan dan Kesimpulan
Kode tersebut merupakan struktur dasar aplikasi Flutter yang menggunakan bahasa pemrograman Dart untuk menampilkan antarmuka sederhana berupa teks "Hello World, Nisrin!". Program ini dimulai dari fungsi main() yang menjalankan MyApp sebagai akar aplikasi berbasis MaterialApp, yang kemudian memanggil MyHomePage sebagai halaman utama. Di dalam halaman tersebut, terdapat penggunaan widget Scaffold untuk mengatur tata letak standar aplikasi, yang terdiri dari AppBar (bilah navigasi atas) yang menampilkan judul dan body yang menempatkan teks tepat di tengah layar menggunakan widget Center. Kode ini juga mengilustrasikan perbedaan antara StatelessWidget, yang bersifat statis, dan StatefulWidget, yang memungkinkan adanya perubahan status atau logika interaktif di dalam komponen antarmuka tersebut.

Secara keseluruhan, pada bagian Flutter, source code main.dart berhasil menampilkan antarmuka sederhana namun fungsional: sebuah halaman dengan AppBar dan teks “hello world, nisrin!” di tengah layar. Ini membuktikan bahwa pengembangan mobile dasar telah berjalan dengan baik dan hasilnya tampil konsisten di platform Flutter.


