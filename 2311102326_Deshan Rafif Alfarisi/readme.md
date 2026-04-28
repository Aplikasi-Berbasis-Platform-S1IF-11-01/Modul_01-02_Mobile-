<div align="center">
  <br />
  <h1>LAPORAN PRAKTIKUM <br>APLIKASI BERBASIS PLATFORM</h1>
  <br />
  <h3>MODUL 1 & 2 <br> Mobile</h3>
  <br />
  <br />
  <img src="assets/logo.png" alt="Logo Universitas Telkom Purwokerto" width="300">
  <br />
  <br />
  <br />
  <h3>Disusun Oleh :</h3>
  <p>
    <strong>Deshan Rafif Alfarisi</strong><br>
    <strong>2311102326</strong><br>
    <strong>S1 IF-11-01</strong>
  </p>
  <br />
  <h3>Dosen Pengampu :</h3>
  <p>
    <strong>Dimas Fanny Hebrasianto Permadi, S.ST., M.Kom</strong>
  </p>
  <br />
  <h4>Asisten Praktikum :</h4>
  <strong>Apri Pandu Wicaksono</strong> <br>
  <strong>Rangga Pradarrell Fathi</strong>
  <br />
  <h3>LABORATORIUM HIGH PERFORMANCE <br>FAKULTAS INFORMATIKA <br>UNIVERSITAS TELKOM PURWOKERTO <br>2026</h3>
</div>

---

## 1. Dasar Teori

### 1.1 Android sebagai Platform Mobile

Android adalah sistem operasi berbasis **Linux** yang dikembangkan oleh Google dan dirancang khusus untuk perangkat mobile seperti smartphone dan tablet. Diluncurkan pertama kali pada tahun 2008, Android kini menjadi sistem operasi mobile dengan pangsa pasar terbesar di dunia. Keterbukaan ekosistemnya (open-source) memungkinkan para pengembang untuk membuat dan mendistribusikan aplikasi dengan bebas melalui Google Play Store maupun jalur distribusi lainnya.

Arsitektur Android terdiri dari beberapa lapisan, yaitu Linux Kernel di bagian paling bawah, Hardware Abstraction Layer (HAL), Android Runtime (ART), Native C/C++ Libraries, Java API Framework, dan lapisan System Apps di bagian paling atas. Pemahaman terhadap arsitektur ini membantu developer dalam memahami bagaimana aplikasi berinteraksi dengan perangkat keras.

### 1.2 Android Studio

**Android Studio** adalah IDE (*Integrated Development Environment*) resmi untuk pengembangan aplikasi Android, dikembangkan oleh Google berbasis IntelliJ IDEA dari JetBrains. Android Studio menyediakan seluruh alat yang dibutuhkan dalam satu paket terpadu, meliputi:

- **Code Editor** yang cerdas dengan fitur *autocomplete*, *refactoring*, dan *syntax highlighting* untuk Kotlin dan Java.
- **Android Emulator** untuk menjalankan dan menguji aplikasi tanpa memerlukan perangkat fisik.
- **Layout Editor** berbasis visual (drag-and-drop) untuk merancang antarmuka pengguna.
- **Gradle Build System** untuk mengotomasi proses kompilasi, pengujian, dan pengemasan aplikasi.
- **Profiler** untuk memantau penggunaan CPU, memori, dan jaringan saat aplikasi berjalan.
- **Logcat** untuk melihat log dari aplikasi yang sedang berjalan.

Android Studio mendukung bahasa pemrograman **Kotlin** sebagai bahasa utama yang direkomendasikan Google sejak 2017, serta **Java** sebagai bahasa alternatif.

### 1.3 Kotlin

**Kotlin** adalah bahasa pemrograman modern yang bersifat *statically typed* dan berjalan di atas **JVM (Java Virtual Machine)**. Dikembangkan oleh JetBrains dan pertama kali dirilis pada tahun 2011, Kotlin dirancang untuk menjadi lebih ringkas, aman, dan ekspresif dibandingkan Java. Beberapa keunggulan Kotlin antara lain:

- **Null Safety**: Sistem tipe Kotlin membedakan antara tipe yang bisa `null` dan yang tidak, sehingga mencegah `NullPointerException` pada *compile time*.
- **Extension Functions**: Memungkinkan penambahan fungsi pada kelas yang sudah ada tanpa harus mewarisinya.
- **Coroutines**: Mendukung pemrograman asinkron yang lebih bersih dan efisien.
- **Interoperabilitas penuh dengan Java**: Kode Kotlin dapat memanggil library Java secara langsung, begitu pula sebaliknya.
- **Sintaks yang ringkas**: Mengurangi *boilerplate code* secara signifikan dibandingkan Java.

### 1.4 Jetpack Compose

**Jetpack Compose** adalah toolkit UI modern yang bersifat *declarative* untuk membangun antarmuka pengguna Android secara *native*. Diperkenalkan oleh Google dan menjadi *stable* pada tahun 2021, Jetpack Compose menggantikan pendekatan UI tradisional berbasis XML dengan pendekatan berbasis kode Kotlin murni.

Perbedaan mendasar antara pendekatan **imperatif** (XML tradisional) dan **deklaratif** (Jetpack Compose):

| Aspek | XML Tradisional | Jetpack Compose |
|-------|----------------|-----------------|
| Definisi UI | File XML terpisah | Kode Kotlin (fungsi `@Composable`) |
| Pembaruan UI | `findViewById` + setter manual | Rekomposisi otomatis berdasarkan *state* |
| Boilerplate | Banyak | Minimal |
| Preview | Layout Editor visual | Anotasi `@Preview` |
| Performa | Baik | Dioptimalkan dengan *recomposition* cerdas |

### 1.5 Composable Function

Dalam Jetpack Compose, antarmuka pengguna dibangun menggunakan **Composable Functions** — fungsi Kotlin biasa yang diberi anotasi `@Composable`. Setiap composable function mendeskripsikan *seperti apa* tampilan UI, bukan *bagaimana* cara membuatnya. Sistem Compose akan secara otomatis memanggil ulang (*recompose*) fungsi-fungsi ini ketika data (*state*) yang digunakan berubah.

Aturan penting dalam Composable Functions:
- Harus diberi anotasi `@Composable`.
- Tidak boleh mengembalikan nilai (return type `Unit`).
- Nama fungsi menggunakan konvensi *PascalCase* (huruf kapital di awal).
- Dapat dipanggil hanya dari fungsi `@Composable` lain atau dari scope Compose khusus.

### 1.6 Android SDK (Software Development Kit)

**Android SDK** adalah kumpulan alat pengembangan yang diperlukan untuk membangun, menguji, dan men-*debug* aplikasi Android. SDK mencakup berbagai komponen penting seperti:

- **Platform Tools** (`adb`, `fastboot`): Alat komunikasi antara komputer dan perangkat Android.
- **Build Tools**: Kompiler dan alat untuk membangun APK/AAB.
- **SDK Platforms**: Versi API Android tertentu (misalnya API 34 = Android 14).
- **Android Emulator**: Mesin virtual untuk menjalankan perangkat Android di komputer.
- **Intel HAXM / Android Hypervisor Driver**: Akselerasi hardware untuk emulator.

SDK Manager di dalam Android Studio memudahkan instalasi dan pembaruan komponen-komponen SDK secara terpusat.

### 1.7 Gradle Build System

**Gradle** adalah sistem build otomatis yang digunakan Android Studio untuk mengelola dependensi, mengkompilasi kode, menjalankan tes, dan menghasilkan file APK atau AAB. Konfigurasi build didefinisikan dalam file `build.gradle.kts` (Kotlin DSL) atau `build.gradle` (Groovy DSL).

Terdapat dua level file build Gradle dalam proyek Android:
- **Project-level** (`build.gradle`): Konfigurasi yang berlaku untuk seluruh proyek, termasuk repositori plugin.
- **Module-level** (`app/build.gradle`): Konfigurasi spesifik modul, termasuk `compileSdk`, `minSdk`, `targetSdk`, dan daftar dependensi library.

### 1.8 Activity dan Lifecycle

**Activity** adalah komponen fundamental dalam aplikasi Android yang merepresentasikan satu layar dengan antarmuka pengguna. Setiap Activity memiliki *lifecycle* (siklus hidup) yang dikelola oleh sistem Android, mulai dari saat dibuat (`onCreate`), ditampilkan (`onStart`, `onResume`), disembunyikan (`onPause`, `onStop`), hingga dihancurkan (`onDestroy`).

Dalam Jetpack Compose, `ComponentActivity` (atau turunannya) adalah titik masuk utama aplikasi. Method `setContent { }` digunakan untuk menyetel konten UI Compose di dalam Activity tersebut.

---

## 2. Implementasi Sistem

Praktikum ini mencakup dua tahapan utama: **instalasi dan konfigurasi Android Studio** beserta Android SDK (Modul 1), serta **pembuatan proyek Android pertama** dengan menampilkan teks "Hello World" menggunakan Jetpack Compose (Modul 2).

Proyek yang dibuat adalah aplikasi Android sederhana bernama `HelloWorld` dengan spesifikasi:
- **Bahasa**: Kotlin
- **UI Toolkit**: Jetpack Compose
- **Minimum SDK**: API 24 (Android 7.0 Nougat)
- **Target SDK**: API 35 (Android 15)
- **Build System**: Gradle dengan Kotlin DSL

Aplikasi menampilkan teks "Hello World" yang diposisikan tepat di tengah layar menggunakan komponen `Box` dengan `contentAlignment = Alignment.Center`.

---

## 3. Penjelasan Kode Sumber

### 3.1 File `MainActivity.kt`

`MainActivity` adalah *entry point* (titik masuk) utama aplikasi Android. File ini merupakan satu-satunya file Kotlin yang perlu dibuat untuk modul ini. *File Referensi: `app/src/main/java/com/example/helloworld/MainActivity.kt`*

```kotlin
package com.example.helloworld

import android.os.Bundle
import androidx.activity.ComponentActivity
import androidx.activity.compose.setContent
import androidx.activity.enableEdgeToEdge
import androidx.compose.foundation.layout.Box
import androidx.compose.foundation.layout.fillMaxSize
import androidx.compose.foundation.layout.padding
import androidx.compose.material3.Scaffold
import androidx.compose.material3.Text
import androidx.compose.runtime.Composable
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.tooling.preview.Preview
import androidx.compose.ui.unit.sp
import com.example.helloworld.ui.theme.HelloWorldTheme

class MainActivity : ComponentActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        enableEdgeToEdge()
        setContent {
            HelloWorldTheme {
                Scaffold(modifier = Modifier.fillMaxSize()) { innerPadding ->
                    Greeting(
                        modifier = Modifier.padding(innerPadding)
                    )
                }
            }
        }
    }
}

@Composable
fun Greeting(modifier: Modifier = Modifier) {
    Box(
        modifier = modifier.fillMaxSize(),
        contentAlignment = Alignment.Center
    ) {
        Text(
            text = "Hello World",
            fontSize = 24.sp
        )
    }
}

@Preview(showBackground = true)
@Composable
fun GreetingPreview() {
    HelloWorldTheme {
        Greeting()
    }
}
```

---

#### 3.1.1 Deklarasi Package dan Import

```kotlin
package com.example.helloworld
```

Baris pertama mendefinisikan **package** dari file ini. Package berfungsi sebagai namespace untuk mengorganisir kode dan mencegah konflik nama antar kelas. Penamaan package mengikuti konvensi *reverse domain name* (nama domain dibalik), sehingga `com.example.helloworld` merupakan package standar untuk proyek contoh.

Bagian `import` di bawahnya mendatangkan kelas-kelas yang dibutuhkan dari library Jetpack Compose dan Android:
- `ComponentActivity` — kelas dasar Activity yang mendukung Jetpack Compose.
- `setContent` — fungsi ekstensi untuk menyetel konten UI Compose.
- `enableEdgeToEdge` — mengaktifkan tampilan tepi-ke-tepi (*edge-to-edge*) agar UI menggunakan seluruh lebar layar termasuk area notch dan gesture bar.
- `Box`, `fillMaxSize`, `padding` — komponen dan modifier layout Compose.
- `Scaffold`, `Text` — komponen Material Design 3.
- `Composable`, `Preview` — anotasi inti Jetpack Compose.
- `Alignment`, `Modifier` — utilitas tata letak.
- `sp` — satuan ukuran teks (*scale-independent pixels*).

---

#### 3.1.2 Kelas `MainActivity`

```kotlin
class MainActivity : ComponentActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        enableEdgeToEdge()
        setContent {
            HelloWorldTheme {
                Scaffold(modifier = Modifier.fillMaxSize()) { innerPadding ->
                    Greeting(
                        modifier = Modifier.padding(innerPadding)
                    )
                }
            }
        }
    }
}
```

`MainActivity` mewarisi (`:`/extends) `ComponentActivity` yang merupakan kelas dasar Activity dengan dukungan penuh terhadap Jetpack Compose dan ViewModels.

Method `onCreate` adalah callback lifecycle Activity yang dipanggil pertama kali saat Activity dibuat. Tiga hal utama yang dilakukan di dalam `onCreate`:

**`enableEdgeToEdge()`** — Memanggil API bawaan Android untuk mengaktifkan mode *edge-to-edge*, di mana konten aplikasi dapat ditampilkan di belakang system bars (status bar dan navigation bar). Ini adalah praktik terbaik modern untuk tampilan yang lebih imersif.

**`setContent { ... }`** — Fungsi ekstensi dari Jetpack Compose yang menyetel pohon komposisi UI. Seluruh kode di dalam lambda `{ }` ini adalah konteks Compose.

Di dalam `setContent`, terdapat:
- **`HelloWorldTheme { ... }`** — Membungkus seluruh UI dengan tema Material Design kustom yang telah dibuat otomatis oleh Android Studio. Tema ini mendefinisikan palet warna, tipografi, dan bentuk yang konsisten.
- **`Scaffold { ... }`** — Komponen Material Design yang menyediakan struktur tata letak dasar (slot untuk TopBar, BottomBar, FAB, dll.). `modifier = Modifier.fillMaxSize()` membuatnya mengisi seluruh ukuran layar. `Scaffold` secara otomatis menghitung `innerPadding` (padding dalam) agar konten tidak tertimpa oleh system bars.
- **`Greeting(modifier = Modifier.padding(innerPadding))`** — Memanggil composable `Greeting` dengan padding dari `Scaffold`, memastikan konten tidak tertimpa oleh status bar atau navigation bar.

---

#### 3.1.3 Composable Function `Greeting`

```kotlin
@Composable
fun Greeting(modifier: Modifier = Modifier) {
    Box(
        modifier = modifier.fillMaxSize(),
        contentAlignment = Alignment.Center
    ) {
        Text(
            text = "Hello World",
            fontSize = 24.sp
        )
    }
}
```

`Greeting` adalah sebuah **Composable Function** — unit terkecil pembangunan UI dalam Jetpack Compose. Anotasi `@Composable` memberitahu compiler Compose bahwa fungsi ini mendeskripsikan bagian dari UI.

Parameter `modifier: Modifier = Modifier` adalah pola standar dalam Compose. `Modifier` adalah objek yang merangkai berbagai transformasi pada composable (ukuran, padding, klik, dll.). Memberikan nilai *default* `= Modifier` memastikan fungsi tetap dapat dipanggil tanpa argumen.

Di dalam `Greeting`:

**`Box`** — Composable layout yang menumpuk anak-anaknya (*children*) satu di atas yang lain (mirip `FrameLayout` di View System). Dua properti yang digunakan:
- `modifier = modifier.fillMaxSize()` — `modifier` di sini adalah modifier yang diteruskan dari pemanggil (sudah berisi padding dari `Scaffold`), kemudian dirantai (`.`) dengan `fillMaxSize()` yang membuatnya mengisi seluruh ruang yang tersedia.
- `contentAlignment = Alignment.Center` — Menentukan perataan *default* untuk semua anak di dalam `Box`. `Alignment.Center` menempatkan `Text` tepat di tengah-tengah `Box` secara horizontal maupun vertikal.

**`Text`** — Composable untuk menampilkan teks. Dua properti yang digunakan:
- `text = "Hello World"` — Konten string yang ditampilkan.
- `fontSize = 24.sp` — Ukuran font 24 *scale-independent pixels* (sp). Satuan `sp` direkomendasikan untuk teks karena otomatis menyesuaikan dengan pengaturan ukuran font sistem pengguna.

---

#### 3.1.4 Preview Function `GreetingPreview`

```kotlin
@Preview(showBackground = true)
@Composable
fun GreetingPreview() {
    HelloWorldTheme {
        Greeting()
    }
}
```

`GreetingPreview` adalah fungsi khusus yang hanya digunakan oleh Android Studio untuk menampilkan pratinjau UI di panel **Design Preview** tanpa perlu menjalankan emulator atau perangkat fisik.

Dua anotasi yang digunakan:
- `@Preview(showBackground = true)` — Menandai fungsi ini sebagai fungsi pratinjau. Parameter `showBackground = true` menambahkan latar belakang putih di belakang pratinjau agar tampilan terlihat jelas.
- `@Composable` — Diperlukan karena fungsi ini memanggil composable lain (`HelloWorldTheme` dan `Greeting`).

Fungsi ini membungkus `Greeting()` di dalam `HelloWorldTheme` agar pratinjau mencerminkan tampilan yang sebenarnya, termasuk tema warna dan tipografi. Fungsi preview **tidak dipanggil saat runtime** dan tidak diikutsertakan dalam APK akhir pada *release build*.

---

## 4. Hasil Tampilan (Screenshots)

### 4.1 Proses Instalasi Android Studio

Proses instalasi Android Studio dilakukan dengan mengunduh installer dari situs resmi `developer.android.com/studio` dan menjalankan wizard instalasi. Installer secara otomatis menyertakan Android SDK dasar, AVD Manager, dan emulator yang diperlukan.

![Instalasi Android Studio](assets/Install%20Android%20Studio.png)

---

### 4.2 Instalasi SDK dan Konfigurasi Awal

Setelah Android Studio terinstal, SDK Manager digunakan untuk mengunduh komponen SDK yang diperlukan, termasuk Android SDK Platform, SDK Build-Tools, dan Android Emulator. Proses ini memastikan seluruh alat yang dibutuhkan tersedia sebelum memulai pengembangan.

![SDK Installer](assets/SDK%20Installer.png)

---

### 4.3 Pembuatan Proyek Baru

Proyek Android baru dibuat melalui menu **File → New → New Project** di Android Studio. Template yang dipilih adalah **Empty Activity** dengan Jetpack Compose. Konfigurasi proyek meliputi nama aplikasi (`HelloWorld`), nama package (`com.example.helloworld`), lokasi penyimpanan, bahasa (Kotlin), dan minimum SDK (API 24).

![New Project](assets/New%20Project.png)

---

### 4.4 Hasil Aplikasi Hello World

Aplikasi berhasil dijalankan pada Android Emulator dan menampilkan teks "Hello World" yang diposisikan tepat di tengah layar. Teks ditampilkan menggunakan composable `Text` dengan ukuran font 24sp di dalam `Box` yang memiliki `contentAlignment = Alignment.Center`.

![Hello World](assets/hello%20world.png)

---

## 5. Kesimpulan

Dari praktikum Modul 1 dan 2 ini dapat disimpulkan beberapa hal sebagai berikut:

Pertama, **Android Studio** merupakan IDE yang komprehensif dan lengkap untuk pengembangan aplikasi Android. Proses instalasi yang terpandu dan konfigurasi SDK yang terintegrasi membuat setup awal pengembangan menjadi relatif mudah dilakukan bahkan oleh pemula.

Kedua, **Jetpack Compose** menghadirkan paradigma baru dalam pengembangan UI Android yang bersifat *declarative*. Dibandingkan pendekatan XML tradisional, Compose memungkinkan penulisan kode UI yang lebih ringkas, mudah dibaca, dan lebih mudah diuji karena UI didefinisikan sebagai fungsi Kotlin biasa dengan anotasi `@Composable`.

Ketiga, konsep **Composable Function** adalah inti dari Jetpack Compose. Dengan memahami cara kerja `modifier`, `Alignment`, dan komponen-komponen dasar seperti `Box`, `Text`, dan `Scaffold`, developer dapat membangun antarmuka yang kompleks secara bertahap dari komponen-komponen kecil yang dapat digunakan ulang.

Keempat, penggunaan **Kotlin** sebagai bahasa utama pengembangan Android memberikan keunggulan berupa sintaks yang bersih dan *null safety* yang membantu mencegah bug umum pada *compile time*, bukan *runtime*.

Kelima, proyek HelloWorld yang berhasil dibuat dan dijalankan ini membuktikan bahwa ekosistem Android modern (Android Studio + Kotlin + Jetpack Compose) sudah siap digunakan dan memberikan pengalaman pengembangan yang produktif sejak tahap awal.

---

## 6. Daftar Pustaka

Google. (2024). *Android Studio Documentation*. Android Developers. Diakses dari https://developer.android.com/studio

Google. (2024). *Jetpack Compose — Android Developers*. Android Developers. Diakses dari https://developer.android.com/jetpack/compose

Google. (2024). *Composable Functions — Jetpack Compose*. Android Developers. Diakses dari https://developer.android.com/jetpack/compose/composables

Google. (2024). *Layouts in Compose — Jetpack Compose*. Android Developers. Diakses dari https://developer.android.com/jetpack/compose/layouts

Google. (2024). *Activity Lifecycle — Android Developers*. Android Developers. Diakses dari https://developer.android.com/guide/components/activities/activity-lifecycle

Google. (2024). *Kotlin for Android — Android Developers*. Android Developers. Diakses dari https://developer.android.com/kotlin

JetBrains. (2024). *Kotlin Documentation*. JetBrains. Diakses dari https://kotlinlang.org/docs/home.html

Google. (2024). *Android SDK — Android Developers*. Android Developers. Diakses dari https://developer.android.com/tools

Phillips, B., Stewart, C., & Marsicano, K. (2019). *Android Programming: The Big Nerd Ranch Guide* (4th ed.). Big Nerd Ranch Guides.

Griffiths, D., & Griffiths, D. (2021). *Head First Android Development: A Brain-Friendly Guide* (3rd ed.). O'Reilly Media.
