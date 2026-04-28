<div align="center">

## LAPORAN PRAKTIKUM <br> APLIKASI BERBASIS PLATFORM

<br>

### MODUL 1 & 2
### MOBILE

<br>
<br>

<img src="asset/logo.png" width="150">

<br>
<br>
<br>

**Disusun oleh:**

**Imelda Fajar Awalina Crisyanti**  
**2311102004**

<br>

**KELAS PS1IF-11-REG01**

**Dosen: Dimas Fanny Hebrasianto Permadi, S.ST., M.Kom**

<br><br>

## PROGRAM STUDI S1 TEKNIK INFORMATIKA <br> FAKULTAS INFORMATIKA <br> UNIVERSITAS TELKOM PURWOKERTO <br> 2026 <br><br>

</div>

---

## 1. Dasar Teori

1. Android Studio

Android Studio adalah Integrated Development Environment (IDE) resmi dari Google yang digunakan untuk mengembangkan aplikasi Android. Android Studio menyediakan berbagai fitur seperti editor kode, emulator, serta tools debugging yang memudahkan proses pengembangan aplikasi berbasis Android.

Android Studio juga menyediakan Android SDK (Software Development Kit) yang berisi library, tools, dan API yang diperlukan untuk membuat dan menjalankan aplikasi Android. Dengan adanya emulator, pengembang dapat menjalankan aplikasi tanpa harus menggunakan perangkat fisik.

2. Flutter

Flutter adalah framework open-source yang dikembangkan oleh Google untuk membuat aplikasi berbasis mobile, web, dan desktop menggunakan satu basis kode (single codebase). Flutter menggunakan bahasa pemrograman Dart.

Keunggulan Flutter antara lain:

Cross-platform (Android, iOS, Web, Desktop)
Performa tinggi karena menggunakan rendering engine sendiri
Hot reload yang mempercepat proses pengembangan

---

## 2. Hasil Praktikum

### Langkah-Langkah:

**1.** Buka Visual Studio Code dan pastikan extension **Flutter** dan **Dart** sudah terpasang.

**2.** Buat project Flutter baru melalui menu **View → Command Palette → Flutter: New Project → Application**, pilih folder tujuan, beri nama project, lalu tekan Enter dan tunggu hingga proses selesai.

**3.** Setelah project selesai dibuat, buka file `lib/main.dart`, lalu hapus semua kode yang ada.

**4.** Tambahkan kode berikut pada `main.dart`:

```dart
// ignore_for_file: prefer_const_constructors

import 'package:flutter/material.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: "Hello World",
      debugShowCheckedModeBanner: false,
      theme: ThemeData(primarySwatch: Colors.blue),
      home: const MyHomePage(title: "Halaman Utama"),
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
  int counter = 0;

  void tambah() {
    setState(() {
      counter++;
    });
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text(widget.title),
        centerTitle: true,
        backgroundColor: Colors.blueAccent,
      ),
      body: Container(
        color: Colors.blue[50],
        child: Center(
          child: Column(
            mainAxisAlignment: MainAxisAlignment.center,
            children: [
              Icon(Icons.flutter_dash, size: 100, color: Colors.blue),
              SizedBox(height: 20),
              Text(
                'Hello Flutter!',
                style: TextStyle(fontSize: 24, fontWeight: FontWeight.bold),
              ),
              SizedBox(height: 10),
              Text('Counter: $counter', style: TextStyle(fontSize: 18)),
            ],
          ),
        ),
      ),
      floatingActionButton: FloatingActionButton(
        onPressed: tambah,
        child: Icon(Icons.add),
      ),
    );
  }
}

```

**5.** Jalankan aplikasi dengan perintah `flutter run` di terminal, lalu pilih platform yang diinginkan (web/emulator).

### Output:

![Output Hello World](aset/flutter1.png)
