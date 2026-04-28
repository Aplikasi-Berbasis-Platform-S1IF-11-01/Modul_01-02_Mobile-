<div align="center">
	<br />
	<h1>LAPORAN PRAKTIKUM <br>APLIKASI BERBASIS PLATFORM</h1>
	<br />
	<h3>Flutter Hello World</h3>
	<br />
	<img src="https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2F1.bp.blogspot.com%2F-vb7jyBjK-sM%2FXXfKp51LrjI%2FAAAAAAAACts%2FEjcXzlgZwSswNWXsBHMyX-6aav1mjA77QCPcBGAYYCw%2Fs1600%2FLogo_Telkom_University_potrait.png&f=1&nofb=1&ipt=9d030d54102ea96369d39fe491220e0536195abc8ee443279c1a420302206400" alt="Logo Telkom" width="300">
	<br />
	<br />
	<br />
	<h3>Disusun Oleh :</h3>
	<p>
		<strong>Didik Setiawan</strong><br>
		<strong>2311102030</strong><br>
		<strong>IF-11-REG01</strong>
	</p>
	<br />
	<h3>Dosen Pengampu :</h3>
	<p>
		<strong>Dimas Fanny Hebrasianto Permadi, S.ST., M.Kom</strong>
	</p>
	<br />
	<br />
	<h4>Asisten Praktikum :</h4>
	<strong>Apri Pandu Wicaksono</strong> <br>
	<strong>Rangga Pradarrell Fathi</strong>
	<br />
	<h3>LABORATORIUM HIGH PERFORMANCE
	<br>FAKULTAS INFORMATIKA <br>UNIVERSITAS TELKOM PURWOKERTO <br>2026</h3>
</div>

---

## Dasar Teori Flutter
Flutter adalah framework open-source yang dikembangkan oleh Google untuk membuat aplikasi mobile, web, dan desktop menggunakan satu basis kode yang sama. Framework ini menggunakan bahasa pemrograman Dart dan didukung oleh Skia Graphics Engine untuk menampilkan antarmuka pengguna. Selain itu, Flutter memanfaatkan Dart Virtual Machine (VM) yang memungkinkan proses kompilasi just-in-time (JIT), sehingga fitur hot reload dapat digunakan. Dengan fitur ini, pengembang dapat melihat perubahan kode secara langsung tanpa perlu melakukan build ulang aplikasi secara keseluruhan.

Dalam pembuatan antarmuka, Flutter menerapkan konsep widget tree, yaitu susunan hierarki widget di mana setiap elemen tampilan direpresentasikan sebagai widget. Widget pada Flutter dibedakan menjadi dua jenis, yaitu stateless widget yang bersifat tetap tanpa perubahan state, serta stateful widget yang dapat berubah sesuai interaksi pengguna atau kondisi tertentu. Konsep ini memudahkan pengelolaan tampilan dan state aplikasi secara lebih terstruktur serta modular.

Flutter juga menyediakan arsitektur yang memungkinkan pemisahan antara logika aplikasi dan tampilan, salah satunya melalui pendekatan Business Logic Component (BLoC). Arsitektur ini bekerja dengan menerima event dari aplikasi, kemudian memprosesnya untuk menghasilkan state baru sebagai respons. Dengan memisahkan logika bisnis dari antarmuka, BLoC membantu meningkatkan efisiensi pengembangan, skalabilitas, serta kemudahan dalam proses pengujian aplikasi.

Sebagai tahap awal dalam mempelajari Flutter, biasanya dibuat aplikasi sederhana seperti “Hello World”. Aplikasi ini bertujuan untuk mengenalkan struktur dasar program Flutter, termasuk penggunaan widget utama seperti MaterialApp, Scaffold, dan AppBar, serta pengaturan tampilan melalui widget seperti Text dan Center. Melalui contoh sederhana tersebut, pengembang dapat memahami alur dasar pembuatan aplikasi Flutter mulai dari proses inisialisasi hingga menampilkan antarmuka pengguna..

---



### Penjelasan Kode

```bash
import 'package:flutter/material.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return const MaterialApp(
      home: Scaffold(
        body: Center(
          child: Text(
            'Hello World',
            style: TextStyle(fontSize: 30),
          ),
        ),
      ),
    );
  }
}
```
untuk menampilkan teks “Hello World” di tengah layar. Program diawali dengan mengimpor library material.dart yang menyediakan berbagai widget bawaan Flutter berbasis Material Design. Fungsi main() berperan sebagai titik awal program dan menjalankan widget utama MyApp melalui runApp(). Kelas MyApp merupakan turunan dari StatelessWidget, yaitu widget yang tampilannya bersifat tetap dan tidak berubah. Pada method build(), aplikasi dibangun menggunakan MaterialApp sebagai struktur utama, kemudian Scaffold sebagai kerangka halaman. Bagian isi halaman berada pada properti body, yang menggunakan widget Center agar konten berada tepat di tengah layar. Di dalamnya terdapat widget Text yang menampilkan tulisan “Hello World” dengan ukuran huruf 30. Saat aplikasi dijalankan, pengguna akan melihat teks tersebut tampil di tengah halaman.

### Screenshot Hasil

<img src="https://raw.githubusercontent.com/didiksetia1/asset/refs/heads/main/WhatsApp%20Image%202026-04-28%20at%2017.25.57.jpeg" alt="Logo Telkom" width="300">

