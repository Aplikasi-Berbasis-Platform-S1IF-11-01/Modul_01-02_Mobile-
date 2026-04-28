<div align="center">

## LAPORAN PRAKTIKUM <br> APLIKASI BERBASIS PLATFORM

<br>

### MODUL 1 & 2
### MOBILE

<br>
<br>

<img src="aset/logo.png" width="150">

<br>
<br>
<br>

**Disusun oleh:**

**Syafanida Khakiki**  
**2311102006**

<br>

**KELAS PS1IF-11-REG01**

**Dosen: Dimas Fanny Hebrasianto Permadi, S.ST., M.Kom**

<br><br>

## PROGRAM STUDI S1 TEKNIK INFORMATIKA <br> FAKULTAS INFORMATIKA <br> UNIVERSITAS TELKOM PURWOKERTO <br> 2026 <br><br>

</div>

---

## 1. Dasar Teori

Flutter ditulis menggunakan bahasa C, C++, dan Dart dengan Google's Skia Graphics Engine untuk user interface. Flutter berjalan menggunakan Dart Virtual Machine (VM) di sistem operasi Windows, Linux, dan macOS. Dart VM menggunakan kompilasi kode just-in-time (JIT) yang menyediakan fitur hot-reload untuk menghemat waktu pengembangan.

Flutter API menggabungkan beberapa widget sesuai kebutuhan aplikasi. Widget bisa **stateless** atau **stateful** tergantung pada status widget itu sendiri, yang berguna untuk membantu mengelola status aplikasi.

Flutter juga memiliki arsitektur dasar yang disebut **Business Logic Component (BLOC)**, yaitu pendekatan untuk memisahkan logika bisnis dari antarmuka dengan ide inti berupa *simplicity*, *scalability*, dan *testability*.

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