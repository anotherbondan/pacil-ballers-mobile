# pacil_ballers

A new Flutter project.

## Getting Started

This project is a starting point for a Flutter application.

A few resources to get you started if this is your first Flutter project:

- [Lab: Write your first Flutter app](https://docs.flutter.dev/get-started/codelab)
- [Cookbook: Useful Flutter samples](https://docs.flutter.dev/cookbook)

For help getting started with Flutter development, view the
[online documentation](https://docs.flutter.dev/), which offers tutorials,
samples, guidance on mobile development, and a full API reference.

---
- [Tugas 7](#tugas-7)
---

## Tugas 7
- Jelaskan apa itu widget tree pada Flutter dan bagaimana hubungan parent-child (induk-anak) bekerja antar widget.
  - Widget tree pada Flutter adalah struktur hierarki yang menggambarkan bagaimana setiap elemen dalam antarmuka pengguna saling berhubungan. Setiap tampilan yang terlihat di layar dibangun dari widget, dan widget-widget tersebut tersusun secara berlapis seperti pohon. Hubungan parent-child (induk-anak) berarti bahwa widget induk bertanggung jawab untuk menampung, mengatur tata letak, serta menentukan bagaimana widget anak ditampilkan. Misalnya, widget Column bisa menjadi parent dari beberapa widget Text atau Button di dalamnya. Perubahan pada widget anak dapat memengaruhi tampilan keseluruhan yang dikendalikan oleh widget induk.
- Sebutkan semua widget yang kamu gunakan dalam proyek ini dan jelaskan fungsinya.
  - Dalam proyek Flutter yang saya kerjakan, beberapa widget yang digunakan antara lain MaterialApp, Scaffold, AppBar, Text, Container, Column, Row, ElevatedButton, dan Image. Widget MaterialApp berfungsi sebagai titik awal (root) aplikasi berbasis Material Design dan mengatur tema, navigasi, serta rute aplikasi. Scaffold digunakan untuk menyediakan struktur dasar halaman seperti app bar, body, dan floating action button. AppBar menampilkan bagian atas aplikasi seperti judul atau ikon navigasi. Text menampilkan teks, sedangkan Container digunakan untuk mengatur ukuran, warna, dan margin elemen. Widget Column dan Row digunakan untuk menata widget secara vertikal dan horizontal. ElevatedButton berfungsi sebagai tombol interaktif, dan Image menampilkan gambar dari aset atau internet.
- Apa fungsi dari widget MaterialApp? Jelaskan mengapa widget ini sering digunakan sebagai widget root.
  - Widget MaterialApp berfungsi sebagai wadah utama yang menginisialisasi struktur dan tema aplikasi berbasis Material Design. Widget ini sering digunakan sebagai root karena menyediakan fitur penting seperti manajemen rute (navigasi antar halaman), tema global, dan dukungan terhadap komponen Material Design. Dengan menggunakan MaterialApp, pengembang dapat memastikan konsistensi tampilan dan interaksi di seluruh halaman aplikasi.
- Jelaskan perbedaan antara StatelessWidget dan StatefulWidget. Kapan kamu memilih salah satunya?
  - StatelessWidget dan StatefulWidget merupakan dua jenis widget utama di Flutter. StatelessWidget digunakan ketika tampilan tidak bergantung pada perubahan data, misalnya untuk menampilkan teks statis atau ikon. Sebaliknya, StatefulWidget digunakan ketika tampilan perlu berubah seiring waktu atau ketika pengguna berinteraksi, seperti pada form input atau animasi. Pemilihan di antara keduanya tergantung pada kebutuhan data — jika data bersifat tetap, gunakan StatelessWidget, sedangkan jika data dapat berubah, gunakan StatefulWidget.
- Apa itu BuildContext dan mengapa penting di Flutter? Bagaimana penggunaannya di metode build?
  - BuildContext adalah objek yang merepresentasikan posisi suatu widget dalam widget tree. Objek ini penting karena digunakan untuk mengakses informasi tentang lokasi widget, tema aplikasi, dan elemen lain di atasnya. Di dalam metode build, BuildContext digunakan untuk memanggil widget lain atau melakukan navigasi, misalnya dengan Navigator.push(context, ...). Dengan konteks ini, Flutter dapat memahami dari mana suatu widget dipanggil dan bagaimana ia berinteraksi dengan widget lain di sekitarnya.
- Jelaskan konsep "hot reload" di Flutter dan bagaimana bedanya dengan "hot restart".
  - Konsep hot reload di Flutter memungkinkan pengembang memperbarui kode aplikasi tanpa harus memulai ulang seluruh aplikasi. Hot reload hanya memperbarui bagian yang berubah sehingga sangat cepat dan efisien untuk pengujian tampilan atau logika kecil. Sedangkan hot restart akan me-restart seluruh aplikasi dan menghapus semua state yang tersimpan. Hot restart lebih lambat karena seluruh aplikasi dibangun ulang dari awal, namun berguna ketika ada perubahan besar yang memengaruhi inisialisasi program.
- Jelaskan bagaimana kamu menambahkan navigasi untuk berpindah antar layar di aplikasi Flutter.
  - Untuk menambahkan navigasi antar layar, Flutter menggunakan sistem Navigator dan Route. Misalnya, ketika pengguna menekan tombol untuk berpindah halaman, kita dapat memanggil ```Navigator.push(context, MaterialPageRoute(builder: (context) => HalamanTujuan()))```. Metode ini menambahkan rute baru ke tumpukan navigasi. Untuk kembali ke halaman sebelumnya, digunakan Navigator.pop(context). Dengan sistem ini, Flutter memudahkan pengembang mengatur transisi dan alur antar halaman secara terstruktur.
