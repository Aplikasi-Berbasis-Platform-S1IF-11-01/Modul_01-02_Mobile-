<div align="center">

# LAPORAN PRAKTIKUM
# APLIKASI BERBASIS PLATFORM

---

### MODUL 1 & 2
### MOBILE

<br>

<img src="Logo_Telkom.png" alt="Logo Telkom University" width="200"/>

<br>

**Disusun Oleh :**

Reli Gita Nurhidayati

2311102025

S1 IF-11-REG01

<br>

**Dosen Pengampu :**

Dimas Fanny Hebrasianto Permadi, S.ST., M.Kom

<br>

**Asisten Praktikum :**

Apri Pandu Wicaksono
Rangga Pradarrell Fathi

<br>

**LABORATORIUM HIGH PERFORMANCE**
**FAKULTAS INFORMATIKA**
**TELKOM UNIVERSITY PURWOKERTO**
**2026**

---

</div>

---

## 📖 Dasar Teori

Flutter adalah framework UI yang dibangun menggunakan bahasa pemrograman **C, C++, dan Dart**. Framework ini memanfaatkan **Google's Skia Graphics Engine** untuk merender antarmuka pengguna — mesin yang sama digunakan pada Google Chrome, Android, dan Mozilla Firefox.

Flutter beroperasi di atas **Dart Virtual Machine (VM)** pada platform Windows, Linux, maupun macOS. Keunggulan utamanya adalah pemanfaatan kompilasi **Just-In-Time (JIT)** yang memungkinkan fitur **hot-reload**, sehingga proses pengembangan menjadi lebih efisien.

Secara arsitektur, Flutter menggunakan konsep **widget tree**, di mana antarmuka dibangun melalui susunan widget yang saling bersarang (*nested*). Widget dibedakan menjadi dua tipe:

- **Stateless Widget** — tidak menyimpan state/data yang berubah
- **Stateful Widget** — dapat menyimpan dan memperbarui state secara dinamis

---

## 🗂️ Struktur Proyek

```
2311102025_Reli-Gita-Nurhidayati/
├── hello/                  # Flutter project
│   └── lib/
│       └── main.dart
├── Logo_Telkom.png
├── SS HASIL FLUTTER.png
└── README.md
```

---

## Penjelasan Kode (main.dart)

### 1. Import & Entry Point
```dart
import 'package:flutter/material.dart';

void main() {
  runApp(const MyApp());
}
```
`runApp()` menginstruksikan Flutter untuk merender widget akar `MyApp` ke layar perangkat.

---

### 2. Class MyApp (StatelessWidget)
```dart
class MyApp extends StatelessWidget {
  const MyApp({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: "Hello World",
      home: const MyHomePage(title: "Flutter Hello World Page"),
    );
  }
}
```
`MyApp` bersifat **StatelessWidget** karena tidak memerlukan perubahan data secara dinamis. `MaterialApp` mengatur konfigurasi fundamental aplikasi.

---

### 3. Class MyHomePage (StatefulWidget)
```dart
class MyHomePage extends StatefulWidget {
  const MyHomePage({Key? key, required this.title}) : super(key: key);

  final String title;

  @override
  State<MyHomePage> createState() => _MyHomePageState();
}
```
`MyHomePage` menggunakan **StatefulWidget** agar dapat menangani perubahan state. Parameter `title` bersifat `required` dan `final`.

---

### 4. Class _MyHomePageState (State)
```dart
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
`Scaffold` membuat kerangka standar aplikasi dengan `AppBar` dan `body`. Teks "Hello World" ditampilkan tepat di tengah layar menggunakan `Center`.

---

##  Widget Tree

```
main()
└── runApp(MyApp)
    └── MyApp
        └── MaterialApp
            └── MyHomePage
                └── Scaffold
                    ├── AppBar
                    │    └── Text("Flutter Hello World Page")
                    └── Center
                         └── Text("Hello World")
```

---

## Hasil Praktikum

<p align="center">
  <img src="SS HASIL FLUTTER.png" alt="Hasil Flutter Hello World" width="300"/>
</p>

---

## 🛠️ Tools & Environment

- **Framework:** Flutter
- **Bahasa:** Dart
- **IDE:** Visual Studio Code / Android Studio
- **Platform:** Android Emulator / Physical Device
