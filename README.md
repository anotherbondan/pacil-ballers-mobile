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
- [Tugas 8](#tugas-8)
- [Tugas 9](#tugas-9)
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

## Tugas 8
- Jelaskan perbedaan antara Navigator.push() dan Navigator.pushReplacement() pada Flutter. Dalam kasus apa sebaiknya masing-masing digunakan pada aplikasi Football Shop kamu?
  - Dalam Flutter, Navigator.push() digunakan untuk menambahkan halaman baru di atas stack navigasi tanpa menghapus halaman sebelumnya. Artinya, ketika pengguna menekan tombol _back_, aplikasi akan kembali ke halaman sebelumnya. Sebaliknya, Navigator.pushReplacement() akan mengganti halaman yang sedang ditampilkan dengan halaman baru, sehingga halaman lama dihapus dari stack dan tidak bisa dikembalikan dengan tombol _back_. Dalam aplikasi Pacil Ballers, Navigator.push() cocok digunakan ketika pengguna berpindah ke halaman detail produk dari daftar produk. Pengguna mungkin ingin kembali ke halaman sebelumnya untuk melihat produk lain, sehingga navigasi bertumpuk adalah pilihan yang tepat. Sedangkan Navigator.pushReplacement() lebih sesuai digunakan saat transisi besar seperti berpindah dari halaman login ke halaman beranda setelah berhasil masuk. Pada tahap itu, pengguna tidak perlu kembali ke halaman login lagi, sehingga halaman sebelumnya bisa dihapus dari stack untuk menjaga alur aplikasi yang lebih efisien.

- Bagaimana kamu memanfaatkan hierarchy widget seperti Scaffold, AppBar, dan Drawer untuk membangun struktur halaman yang konsisten di seluruh aplikasi?
  - Dalam membangun Pacil Ballers, hierarchy widget dimanfaatkan untuk menciptakan struktur halaman yang konsisten di seluruh aplikasi. Widget Scaffold berperan sebagai kerangka utama setiap halaman, menyediakan area dasar untuk elemen-elemen seperti AppBar, Drawer, Body, dan FloatingActionButton. AppBar digunakan untuk menampilkan judul halaman serta tombol navigasi atau pencarian produk, sehingga pengguna selalu memiliki konteks tentang posisi mereka di aplikasi. Sementara itu, Drawer dimanfaatkan sebagai navigasi samping yang memudahkan pengguna berpindah antarhalaman seperti ke halaman profil, daftar produk, atau riwayat pesanan. Dengan menerapkan struktur hierarki ini secara konsisten, tampilan dan pengalaman pengguna menjadi lebih teratur serta mudah dikenali di setiap halaman.
- Dalam konteks desain antarmuka, apa kelebihan menggunakan layout widget seperti Padding, SingleChildScrollView, dan ListView saat menampilkan elemen-elemen form? Berikan contoh penggunaannya dari aplikasi kamu.
  - Dalam desain antarmuka Pacil Ballers, penggunaan layout widget seperti Padding, SingleChildScrollView, dan ListView memberikan fleksibilitas dalam mengatur tampilan elemen form agar tetap rapi dan responsif. Widget Padding digunakan untuk memberikan jarak antar elemen form, seperti antara kolom input “Nama Produk” dan “Harga Produk”, sehingga tampilan tidak terlihat menumpuk. SingleChildScrollView sangat berguna ketika form yang ditampilkan panjang dan melebihi tinggi layar, pengguna dapat menggulirkan tampilan tanpa terpotong. Sedangkan ListView digunakan untuk menampilkan daftar produk secara vertikal, di mana setiap item produk dapat digulir dengan lancar. Contohnya, pada halaman tambah produk, struktur form dibungkus dengan SingleChildScrollView agar semua input dapat diakses tanpa terganggu oleh ukuran layar, sementara setiap kolom input memiliki Padding yang cukup agar mudah dibaca dan digunakan oleh pengguna.
- Bagaimana kamu menyesuaikan warna tema agar aplikasi Football Shop memiliki identitas visual yang konsisten dengan brand toko?
  - Agar aplikasi Pacil Ballers memiliki identitas visual yang konsisten dengan brand toko, penyesuaian warna tema dilakukan melalui properti ThemeData di root aplikasi. Warna utama atau primaryColor dipilih berdasarkan palet khas brand. Warna ini diterapkan secara konsisten pada elemen seperti AppBar, tombol utama (ElevatedButton), dan ikon navigasi. Selain itu, warna teks dan latar belakang juga disesuaikan agar tetap serasi dan mudah dibaca. Dengan menerapkan skema warna yang konsisten, Football Shop tidak hanya terlihat profesional, tetapi juga memperkuat identitas merek yang mudah dikenali oleh pengguna setiap kali mereka membuka aplikasi.

## Tugas 9
#### Step-by-step melengkapi checklist
- Mengimplementasikan fitur registrasi akun pada proyek tugas Flutter.
  - Siapkan modul auth di proyek django
  - Buat function pada views.py
  ```
  @csrf_exempt
  def login(request):
      username = request.POST['username']
      password = request.POST['password']
      user = authenticate(username=username, password=password)
      if user is not None:
          if user.is_active:
              auth_login(request, user)
              # Login status successful.
              return JsonResponse({
                  "username": user.username,
                  "user_id": user.id, 
                  "status": True,
                  "message": "Login successful!"
                  # Add other data if you want to send data to Flutter.
              }, status=200)
          else:
              return JsonResponse({
                  "status": False,
                  "message": "Login failed, account is disabled."
              }, status=401)
  
      else:
          return JsonResponse({
              "status": False,
              "message": "Login failed, please check your username or password."
          }, status=401)
        

  @csrf_exempt
  def register(request):
      if request.method == 'POST':
          data = json.loads(request.body)
          username = data['username']
          password1 = data['password1']
          password2 = data['password2']
  
          # Check if the passwords match
          if password1 != password2:
              return JsonResponse({
                  "status": False,
                  "message": "Passwords do not match."
              }, status=400)
          
          # Check if the username is already taken
          if User.objects.filter(username=username).exists():
              return JsonResponse({
                  "status": False,
                  "message": "Username already exists."
              }, status=400)
          
          # Create the new user
          user = User.objects.create_user(username=username, password=password1)
          user.save()
          
          return JsonResponse({
              "username": user.username,
              "status": 'success',
              "message": "User created successfully!"
          }, status=200)
      
      else:
          return JsonResponse({
              "status": False,
              "message": "Invalid request method."
          }, status=400)
  
  @csrf_exempt
  def logout(request):
      username = request.user.username
      try:
          auth_logout(request)
          return JsonResponse({
              "username": username,
              "status": True,
              "message": "Logged out successfully!"
          }, status=200)
      except:
          return JsonResponse({
              "status": False,
              "message": "Logout failed."
          }, status=401)
          
  def get_current_user(request):
      return JsonResponse({
          "user_id": request.user.id,
          "username": request.user.username,
      })
  ```
  - Set url untuk tiap function
  ```
  app_name = 'authentication'
  urlpatterns = [
      path('login/', login, name='login'),
      path('register/', register, name='register'),
      path('logout/', logout, name='logout'),
      path('current-user/', get_current_user, name='current_user'),
  ]
  ```
  - Membuat halaman register pada proyek Flutter
  ```
  import 'dart:convert';
  import 'package:flutter/material.dart';
  import 'package:pacil_ballers/screens/login.dart';
  import 'package:pbp_django_auth/pbp_django_auth.dart';
  import 'package:provider/provider.dart';
  
  class RegisterPage extends StatefulWidget {
    const RegisterPage({super.key});
  
    @override
    State<RegisterPage> createState() => _RegisterPageState();
  }
  
  class _RegisterPageState extends State<RegisterPage> {
    final _usernameController = TextEditingController();
    final _passwordController = TextEditingController();
    final _confirmPasswordController = TextEditingController();
  
    @override
    Widget build(BuildContext context) {
      final request = context.watch<CookieRequest>();
      return Scaffold(
        appBar: AppBar(
          title: const Text('Register'),
          leading: IconButton(
            icon: const Icon(Icons.arrow_back),
            onPressed: () {
              Navigator.pop(context);
            },
          ),
        ),
        body: Center(
          child: SingleChildScrollView(
            padding: const EdgeInsets.all(16.0),
            child: Card(
              elevation: 8,
              shape: RoundedRectangleBorder(
                borderRadius: BorderRadius.circular(12.0),
              ),
              child: Padding(
                padding: const EdgeInsets.all(20.0),
                child: Column(
                  mainAxisSize: MainAxisSize.min,
                  children: <Widget>[
                    const Text(
                      'Register',
                      style: TextStyle(
                        fontSize: 24.0,
                        fontWeight: FontWeight.bold,
                      ),
                    ),
                    const SizedBox(height: 30.0),
                    TextFormField(
                      controller: _usernameController,
                      decoration: const InputDecoration(
                        labelText: 'Username',
                        hintText: 'Enter your username',
                        border: OutlineInputBorder(
                          borderRadius: BorderRadius.all(Radius.circular(12.0)),
                        ),
                        contentPadding: EdgeInsets.symmetric(
                          horizontal: 12.0,
                          vertical: 8.0,
                        ),
                      ),
                      validator: (value) {
                        if (value == null || value.isEmpty) {
                          return 'Please enter your username';
                        }
                        return null;
                      },
                    ),
                    const SizedBox(height: 12.0),
                    TextFormField(
                      controller: _passwordController,
                      decoration: const InputDecoration(
                        labelText: 'Password',
                        hintText: 'Enter your password',
                        border: OutlineInputBorder(
                          borderRadius: BorderRadius.all(Radius.circular(12.0)),
                        ),
                        contentPadding: EdgeInsets.symmetric(
                          horizontal: 12.0,
                          vertical: 8.0,
                        ),
                      ),
                      obscureText: true,
                      validator: (value) {
                        if (value == null || value.isEmpty) {
                          return 'Please enter your password';
                        }
                        return null;
                      },
                    ),
                    const SizedBox(height: 12.0),
                    TextFormField(
                      controller: _confirmPasswordController,
                      decoration: const InputDecoration(
                        labelText: 'Confirm Password',
                        hintText: 'Confirm your password',
                        border: OutlineInputBorder(
                          borderRadius: BorderRadius.all(Radius.circular(12.0)),
                        ),
                        contentPadding: EdgeInsets.symmetric(
                          horizontal: 12.0,
                          vertical: 8.0,
                        ),
                      ),
                      obscureText: true,
                      validator: (value) {
                        if (value == null || value.isEmpty) {
                          return 'Please confirm your password';
                        }
                        return null;
                      },
                    ),
                    const SizedBox(height: 24.0),
                    ElevatedButton(
                      onPressed: () async {
                        String username = _usernameController.text;
                        String password1 = _passwordController.text;
                        String password2 = _confirmPasswordController.text;
  
                        // Check credentials
                        // To connect Android emulator with Django on localhost, use URL http://10.0.2.2/
                        // If you using chrome,  use URL http://localhost:8000
                        final response = await request.postJson(
                          "http://localhost:8000/auth/register/",
                          jsonEncode({
                            "username": username,
                            "password1": password1,
                            "password2": password2,
                          }),
                        );
                        if (context.mounted) {
                          if (response['status'] == 'success') {
                            ScaffoldMessenger.of(context).showSnackBar(
                              const SnackBar(
                                content: Text('Successfully registered!'),
                              ),
                            );
                            Navigator.pushReplacement(
                              context,
                              MaterialPageRoute(
                                builder: (context) => const LoginPage(),
                              ),
                            );
                          } else {
                            ScaffoldMessenger.of(context).showSnackBar(
                              const SnackBar(
                                content: Text('Failed to register!'),
                              ),
                            );
                          }
                        }
                      },
                      style: ElevatedButton.styleFrom(
                        foregroundColor: Colors.white,
                        minimumSize: Size(double.infinity, 50),
                        backgroundColor: Theme.of(context).colorScheme.primary,
                        padding: const EdgeInsets.symmetric(vertical: 16.0),
                      ),
                      child: const Text('Register'),
                    ),
                    const SizedBox(height: 36.0),
                    GestureDetector(
                      onTap: () {
                        Navigator.push(
                          context,
                          MaterialPageRoute(
                            builder: (context) => const LoginPage(),
                          ),
                        );
                      },
                      child: Text(
                        'Already have an account? Login',
                        style: TextStyle(
                          color: Theme.of(context).colorScheme.primary,
                          fontSize: 16.0,
                        ),
                      ),
                    ),
                  ],
                ),
              ),
            ),
          ),
        ),
      );
    }
  }
  ```
- Membuat halaman login pada proyek tugas Flutter.
  ```
  import 'package:flutter/material.dart';
  import 'package:pbp_django_auth/pbp_django_auth.dart';
  import 'package:provider/provider.dart';
  import 'package:pacil_ballers/screens/register.dart';
  import 'package:pacil_ballers/screens/menu.dart';
  
  void main() {
    runApp(const LoginApp());
  }
  
  class LoginApp extends StatelessWidget {
    const LoginApp({super.key});
  
    @override
    Widget build(BuildContext context) {
      return MaterialApp(
        title: 'Login',
        theme: ThemeData(
          useMaterial3: true,
          colorScheme: ColorScheme.fromSwatch(
            primarySwatch: Colors.blue,
          ).copyWith(secondary: Colors.blueAccent[400]),
        ),
        home: const LoginPage(),
      );
    }
  }
  
  class LoginPage extends StatefulWidget {
    const LoginPage({super.key});
  
    @override
    State<LoginPage> createState() => _LoginPageState();
  }
  
  class _LoginPageState extends State<LoginPage> {
    final TextEditingController _usernameController = TextEditingController();
    final TextEditingController _passwordController = TextEditingController();
  
    @override
    Widget build(BuildContext context) {
      final request = context.watch<CookieRequest>();
  
      return Scaffold(
        appBar: AppBar(title: const Text('Login')),
        body: Center(
          child: SingleChildScrollView(
            padding: const EdgeInsets.all(16.0),
            child: Card(
              elevation: 8,
              shape: RoundedRectangleBorder(
                borderRadius: BorderRadius.circular(12.0),
              ),
              child: Padding(
                padding: const EdgeInsets.all(20.0),
                child: Column(
                  mainAxisSize: MainAxisSize.min,
                  children: [
                    const Text(
                      'Login',
                      style: TextStyle(
                        fontSize: 24.0,
                        fontWeight: FontWeight.bold,
                      ),
                    ),
                    const SizedBox(height: 30.0),
                    TextField(
                      controller: _usernameController,
                      decoration: const InputDecoration(
                        labelText: 'Username',
                        hintText: 'Enter your username',
                        border: OutlineInputBorder(
                          borderRadius: BorderRadius.all(Radius.circular(12.0)),
                        ),
                        contentPadding: EdgeInsets.symmetric(
                          horizontal: 12.0,
                          vertical: 8.0,
                        ),
                      ),
                    ),
                    const SizedBox(height: 12.0),
                    TextField(
                      controller: _passwordController,
                      decoration: const InputDecoration(
                        labelText: 'Password',
                        hintText: 'Enter your password',
                        border: OutlineInputBorder(
                          borderRadius: BorderRadius.all(Radius.circular(12.0)),
                        ),
                        contentPadding: EdgeInsets.symmetric(
                          horizontal: 12.0,
                          vertical: 8.0,
                        ),
                      ),
                      obscureText: true,
                    ),
                    const SizedBox(height: 24.0),
                    ElevatedButton(
                      onPressed: () async {
                        String username = _usernameController.text;
                        String password = _passwordController.text;
  
                        // Check credentials
                        // To connect Android emulator with Django on localhost, use URL http://10.0.2.2/
                        // If you using chrome,  use URL http://localhost:8000
                        final response = await request.login(
                          "http://localhost:8000/auth/login/",
                          {'username': username, 'password': password},
                        );
  
                        if (request.loggedIn) {
                          String message = response['message'];
                          String uname = response['username'];
                          if (context.mounted) {
                            Navigator.pushReplacement(
                              context,
                              MaterialPageRoute(
                                builder: (context) => MyHomePage(),
                              ),
                            );
                            ScaffoldMessenger.of(context)
                              ..hideCurrentSnackBar()
                              ..showSnackBar(
                                SnackBar(
                                  content: Text("$message Welcome, $uname."),
                                ),
                              );
                          }
                        } else {
                          if (context.mounted) {
                            showDialog(
                              context: context,
                              builder: (context) => AlertDialog(
                                title: const Text('Login Failed'),
                                content: Text(response['message']),
                                actions: [
                                  TextButton(
                                    child: const Text('OK'),
                                    onPressed: () {
                                      Navigator.pop(context);
                                    },
                                  ),
                                ],
                              ),
                            );
                          }
                        }
                      },
                      style: ElevatedButton.styleFrom(
                        foregroundColor: Colors.white,
                        minimumSize: Size(double.infinity, 50),
                        backgroundColor: Theme.of(context).colorScheme.primary,
                        padding: const EdgeInsets.symmetric(vertical: 16.0),
                      ),
                      child: const Text('Login'),
                    ),
                    const SizedBox(height: 36.0),
                    GestureDetector(
                      onTap: () {
                        Navigator.push(
                          context,
                          MaterialPageRoute(
                            builder: (context) => const RegisterPage(),
                          ),
                        );
                      },
                      child: Text(
                        'Don\'t have an account? Register',
                        style: TextStyle(
                          color: Theme.of(context).colorScheme.primary,
                          fontSize: 16.0,
                        ),
                      ),
                    ),
                  ],
                ),
              ),
            ),
          ),
        ),
      );
    }
  }
  ```
- Mengintegrasikan sistem autentikasi Django dengan proyek tugas Flutter.
  - Konfigurasi settings.py
    ```
    CORS_ALLOW_ALL_ORIGINS = True
    CORS_ALLOW_CREDENTIALS = True
    CSRF_COOKIE_SECURE = True
    SESSION_COOKIE_SECURE = True
    CSRF_COOKIE_SAMESITE = 'None'
    SESSION_COOKIE_SAMESITE = 'None'
    ```
  - Install library django-cors-headers pada proyek django
  - Pada settings.py, tambahkan 'corsheaders' di INSTALLED_APPS dan 'corsheaders.middleware.CorsMiddleware' di MIDDLEWARE
  - Install library provider dan pbp_django_auth pada proyek flutter
  - Modifikasi lib/main.dart
    ```
    import 'package:flutter/material.dart';
    import 'package:pacil_ballers/screens/menu.dart';
    import 'package:pacil_ballers/screens/login.dart';
    import 'package:pbp_django_auth/pbp_django_auth.dart';
    import 'package:provider/provider.dart';
    
    void main() {
      runApp(const MyApp());
    }
    
    class MyApp extends StatelessWidget {
      const MyApp({super.key});
    
      // This widget is the root of your application.
      @override
      Widget build(BuildContext context) {
        return Provider(
          create: (_) {
            CookieRequest request = CookieRequest();
            return request;
          },
          child: MaterialApp(
            title: 'Pacil Ballers',
            theme: ThemeData(
              // This is the theme of your application.
              //
              // TRY THIS: Try running your application with "flutter run". You'll see
              // the application has a purple toolbar. Then, without quitting the app,
              // try changing the seedColor in the colorScheme below to Colors.green
              // and then invoke "hot reload" (save your changes or press the "hot
              // reload" button in a Flutter-supported IDE, or press "r" if you used
              // the command line to start the app).
              //
              // Notice that the counter didn't reset back to zero; the application
              // state is not lost during the reload. To reset the state, use hot
              // restart instead.
              //
              // This works for code too, not just values: Most code changes can be
              // tested with just a hot reload.
                colorScheme: ColorScheme.fromSwatch(primarySwatch: Colors.blue)
              .copyWith(secondary: Colors.blueAccent[400]),
            ),
            home: const LoginPage(),
          ),
        );
      }
    }
    ```
  - Pada android/app/src/main/AndroidManifest.xml, tambahkan 
  ```
  <uses-permission android:name="android.permission.INTERNET" />
  ```
  di bawah </application>
- Membuat model kustom sesuai dengan proyek aplikasi Django.
  - Copy paste json yang terima dari API ke quicktype.io
  - Isi file lib/models/product_entry.dart
  ```
  // To parse this JSON data, do
  //
  //     final productEntry = productEntryFromJson(jsonString);
  
  import 'dart:convert';
  
  List<ProductEntry> productEntryFromJson(String str) => List<ProductEntry>.from(
    json.decode(str).map((x) => ProductEntry.fromJson(x)),
  );
  
  String productEntryToJson(List<ProductEntry> data) =>
      json.encode(List<dynamic>.from(data.map((x) => x.toJson())));
  
  class ProductEntry {
    String id;
    String name;
    int price;
    String description;
    String category;
    String thumbnail;
    bool isFeatured;
    int? userId;
  
    ProductEntry({
      required this.id,
      required this.name,
      required this.price,
      required this.description,
      required this.category,
      required this.thumbnail,
      required this.isFeatured,
      required this.userId,
    });
  
    factory ProductEntry.fromJson(Map<String, dynamic> json) => ProductEntry(
      id: json["id"],
      name: json["name"],
      price: json["price"],
      description: json["description"],
      category: json["category"],
      thumbnail: json["thumbnail"] ?? "",
      isFeatured: json["is_featured"],
      userId: json["user_id"],
    );
  
    Map<String, dynamic> toJson() => {
      "id": id,
      "name": name,
      "price": price,
      "description": description,
      "category": category,
      "thumbnail": thumbnail,
      "is_featured": isFeatured,
      "user_id": userId,
    };
  }
  ```
- Membuat halaman yang berisi daftar semua item yang terdapat pada endpoint JSON di Django yang telah kamu deploy.
  - Buat file lib/screens/product_entry_list.dart
  ```
  import 'package:flutter/material.dart';
  import 'package:pacil_ballers/models/product_entry.dart';
  import 'package:pacil_ballers/widgets/left_drawer.dart';
  import 'package:pacil_ballers/screens/product_detail.dart';
  import 'package:pacil_ballers/widgets/product_entry_card.dart';
  import 'package:provider/provider.dart';
  import 'package:pbp_django_auth/pbp_django_auth.dart';
  
  class ProductEntryListPage extends StatefulWidget {
    final bool showOnlyMyProduct;
  
    const ProductEntryListPage({super.key, this.showOnlyMyProduct = false});
  
    @override
    State<ProductEntryListPage> createState() => _ProductEntryListPageState();
  }
  
  class _ProductEntryListPageState extends State<ProductEntryListPage> {
    Future<List<ProductEntry>> fetchProduct(CookieRequest request) async {
      final response = await request.get('http://localhost:8000/json/');
      final userData = await request.get(
        'http://localhost:8000/auth/current-user/',
      );
  
      int currentUserId = userData['user_id'];
  
      List<ProductEntry> listProduct = [];
  
      for (var d in response) {
        if (d != null) {
          final product = ProductEntry.fromJson(d);
  
          if (widget.showOnlyMyProduct) {
            if (product.userId == currentUserId) {
              listProduct.add(product);
            }
          } else {
            listProduct.add(product);
          }
        }
      }
  
      return listProduct;
    }
  
    @override
    Widget build(BuildContext context) {
      final request = context.watch<CookieRequest>();
      return Scaffold(
        appBar: AppBar(title: const Text('Product Entry List')),
        drawer: const LeftDrawer(),
        body: FutureBuilder(
          future: fetchProduct(request),
          builder: (context, AsyncSnapshot<List<ProductEntry>> snapshot) {
            if (snapshot.connectionState == ConnectionState.waiting) {
              return const Center(child: CircularProgressIndicator());
            } else if (snapshot.hasError) {
              return Center(child: Text('Error: ${snapshot.error.toString()}'));
            } else if (snapshot.hasData) {
              if (snapshot.data!.isEmpty) {
                return const Center(
                  child: Column(
                    mainAxisAlignment: MainAxisAlignment.center,
                    children: [
                      Text(
                        'There are no product yet.',
                        style: TextStyle(fontSize: 20, color: Color(0xff59A5D8)),
                        textAlign: TextAlign.center,
                      ),
                      SizedBox(height: 8),
                    ],
                  ),
                );
              } else {
                return ListView.builder(
                  itemCount: snapshot.data!.length,
                  itemBuilder: (_, index) => ProductEntryCard(
                    product: snapshot.data![index],
                    onTap: () {
                      Navigator.push(
                        context,
                        MaterialPageRoute(
                          builder: (context) =>
                              ProductDetailPage(product: snapshot.data![index]),
                        ),
                      );
                    },
                  ),
                );
              }
            } else {
              return const Center(child: Text('No data received from server.'));
            }
          },
        ),
      );
    }
  }
  ```
- Tampilkan name, price, description, thumbnail, category, dan is_featured dari masing-masing item pada halaman ini (Dapat disesuaikan dengan field yang kalian buat sebelumnya).
  - Buat file lib/widgets/product_entry_card.dart
    ```
    import 'package:flutter/material.dart';
    import 'package:pacil_ballers/models/product_entry.dart';
    
    class ProductEntryCard extends StatelessWidget {
      final ProductEntry product;
      final VoidCallback onTap;
    
      const ProductEntryCard({
        super.key,
        required this.product,
        required this.onTap,
      });
    
      @override
      Widget build(BuildContext context) {
        return Container(
          margin: const EdgeInsets.symmetric(horizontal: 16, vertical: 12),
          child: InkWell(
            onTap: onTap,
            child: Card(
              shape: RoundedRectangleBorder(
                borderRadius: BorderRadius.circular(8.0),
                side: BorderSide(color: Colors.grey.shade300),
              ),
              elevation: 2,
              child: Padding(
                padding: const EdgeInsets.all(16.0),
                child: Column(
                  mainAxisAlignment: MainAxisAlignment.start,
                  crossAxisAlignment: CrossAxisAlignment.start,
                  children: [
                    // Thumbnail
                    ClipRRect(
                      borderRadius: BorderRadius.circular(6),
                      child: Image.network(
                        'http://localhost:8000/proxy-image/?url=${Uri.encodeComponent(product.thumbnail)}',
                        height: 150,
                        width: double.infinity,
                        fit: BoxFit.cover,
                        errorBuilder: (context, error, stackTrace) => Container(
                          height: 150,
                          color: Colors.grey[300],
                          child: const Center(child: Icon(Icons.broken_image)),
                        ),
                      ),
                    ),
                    const SizedBox(height: 8),
    
                    // Title
                    Text(
                      product.name,
                      style: const TextStyle(
                        fontSize: 18.0,
                        fontWeight: FontWeight.bold,
                      ),
                    ),
                    const SizedBox(height: 6),
    
                    // Category
                    Container(
                      padding: const EdgeInsets.symmetric(
                        horizontal: 10.0,
                        vertical: 4.0,
                      ),
                      decoration: BoxDecoration(
                        color: Colors.indigo.shade100,
                        borderRadius: BorderRadius.circular(12.0),
                      ),
                      child: Text(
                        product.category.toUpperCase(),
                        style: TextStyle(
                          fontSize: 12,
                          fontWeight: FontWeight.bold,
                          color: Colors.indigo.shade700,
                        ),
                      ),
                    ),
                    const SizedBox(height: 6),
    
                    Text('Rp${product.price},-'),
                    const SizedBox(height: 6),
    
                    // Content preview
                    Text(
                      product.description.length > 100
                          ? '${product.description.substring(0, 100)}...'
                          : product.description,
                      maxLines: 2,
                      overflow: TextOverflow.ellipsis,
                      style: const TextStyle(color: Colors.black54),
                    ),
                    const SizedBox(height: 6),
    
                    // Featured indicator
                    if (product.isFeatured)
                      const Text(
                        'Featured',
                        style: TextStyle(
                          color: Colors.amber,
                          fontWeight: FontWeight.bold,
                        ),
                      ),
                  ],
                ),
              ),
            ),
          ),
        );
      }
    }
    ```
- Membuat halaman detail untuk setiap item yang terdapat pada halaman daftar Item.
  - Buat file lib/screens/product_detail.dart
  ```
  import 'package:flutter/material.dart';
  import 'package:pacil_ballers/models/product_entry.dart';
  
  class ProductDetailPage extends StatelessWidget {
    final ProductEntry product;
  
    const ProductDetailPage({super.key, required this.product});
  
    String _formatDate(DateTime date) {
      final months = [
        'Jan',
        'Feb',
        'Mar',
        'Apr',
        'May',
        'Jun',
        'Jul',
        'Aug',
        'Sep',
        'Oct',
        'Nov',
        'Dec',
      ];
      return '${date.day} ${months[date.month - 1]} ${date.year}, ${date.hour.toString().padLeft(2, '0')}:${date.minute.toString().padLeft(2, '0')}';
    }
  
    @override
    Widget build(BuildContext context) {
      return Scaffold(
        appBar: AppBar(
          title: const Text('Product Detail'),
          backgroundColor: Colors.indigo,
          foregroundColor: Colors.white,
        ),
        body: SingleChildScrollView(
          child: Column(
            crossAxisAlignment: CrossAxisAlignment.start,
            children: [
              if (product.thumbnail.isNotEmpty)
                Image.network(
                  'http://localhost:8000/proxy-image/?url=${Uri.encodeComponent(product.thumbnail)}',
                  width: double.infinity,
                  height: 250,
                  fit: BoxFit.cover,
                  errorBuilder: (context, error, stackTrace) => Container(
                    height: 150,
                    color: Colors.grey[300],
                    child: const Center(child: Icon(Icons.broken_image)),
                  ),
                ),
  
              Padding(
                padding: const EdgeInsets.all(16.0),
                child: Column(
                  crossAxisAlignment: CrossAxisAlignment.start,
                  children: [
                    if (product.isFeatured)
                      Container(
                        padding: const EdgeInsets.symmetric(
                          horizontal: 12.0,
                          vertical: 6.0,
                        ),
                        margin: const EdgeInsets.only(bottom: 12.0),
                        decoration: BoxDecoration(
                          color: Colors.amber,
                          borderRadius: BorderRadius.circular(20.0),
                        ),
                        child: const Text(
                          'Featured',
                          style: TextStyle(
                            fontWeight: FontWeight.bold,
                            fontSize: 12,
                          ),
                        ),
                      ),
  
                    Text(
                      product.name,
                      style: const TextStyle(
                        fontSize: 24.0,
                        fontWeight: FontWeight.bold,
                      ),
                    ),
                    const SizedBox(height: 12),
  
                    Row(
                      children: [
                        Container(
                          padding: const EdgeInsets.symmetric(
                            horizontal: 10.0,
                            vertical: 4.0,
                          ),
                          decoration: BoxDecoration(
                            color: Colors.indigo.shade100,
                            borderRadius: BorderRadius.circular(12.0),
                          ),
                          child: Text(
                            product.category.toUpperCase(),
                            style: TextStyle(
                              fontSize: 12,
                              fontWeight: FontWeight.bold,
                              color: Colors.indigo.shade700,
                            ),
                          ),
                        ),
                        const SizedBox(width: 12),
                      ],
                    ),
                    const SizedBox(height: 8),
  
                    Text(
                      'Rp${product.price},-',
                      style: const TextStyle(fontSize: 20.0),
                    ),
                    const SizedBox(height: 6),
  
                    const Divider(height: 20),
  
                    Text(
                      product.description,
                      style: const TextStyle(fontSize: 12.0, height: 1.6),
                      textAlign: TextAlign.justify,
                    ),
                    const SizedBox(height: 24),
                  ],
                ),
              ),
            ],
          ),
        ),
      );
    }
  }
  ```
- Melakukan filter pada halaman daftar item dengan hanya menampilkan item yang terasosiasi dengan pengguna yang login.
  - Set argumen pada drawer
  ```
          ListTile(
            leading: const Icon(Icons.sports_soccer_rounded),
            title: const Text('See Football Product'),
            onTap: () {
              Navigator.push(
                context,
                MaterialPageRoute(
                  builder: (context) => const ProductEntryListPage(showOnlyMyProduct: false,),
                ),
              );
            },
          ),
          ListTile(
            leading: const Icon(Icons.add_reaction_rounded),
            title: const Text('My Product'),
            onTap: () {
              Navigator.push(
                context,
                MaterialPageRoute(
                  builder: (context) => const ProductEntryListPage(showOnlyMyProduct: true,),
                ),
              );
            },
          ),
  ```
- Jelaskan mengapa kita perlu membuat model Dart saat mengambil/mengirim data JSON? Apa konsekuensinya jika langsung memetakan Map<String, dynamic> tanpa model (terkait validasi tipe, null-safety, maintainability)?
  - Model pada Dart berfungsi sebagai kontrak data yang jelas dan aman. Ketika menggunakan model, setiap field memiliki tipe yang tegas, sehingga kesalahan tipe dapat terdeteksi sejak awal melalui mekanisme compile-time dan null-safety milik Dart. Model juga memusatkan proses parsing JSON ke dalam satu tempat, sehingga jika API berubah, perbaikan hanya perlu dilakukan pada satu file. Selain itu, penggunaan model mempermudah dokumentasi, autocompletion, refactoring, serta meningkatkan maintainability jangka panjang. Sebaliknya, jika langsung memakai Map<String, dynamic>, struktur data menjadi tidak jelas, validasi harus dilakukan manual di banyak tempat, risiko kesalahan tipe meningkat, null-safety hilang, dan kesalahan baru akan muncul pada runtime. Pendekatan ini membuat kode lebih rentan error, sulit dirawat, serta tidak scalable untuk aplikasi besar.
- Apa fungsi package http dan CookieRequest dalam tugas ini? Jelaskan perbedaan peran http vs CookieRequest.
  - Package http menyediakan fungsi dasar untuk melakukan request HTTP seperti GET, POST, dan DELETE, tetapi sifatnya stateless dan tidak otomatis menyimpan atau mengirim cookie. Artinya, jika backend menggunakan session-based authentication seperti Django, developer harus menangani cookie, header, dan CSRF token secara manual. Berbeda dengan itu, CookieRequest dirancang untuk mengelola sesi secara otomatis. Ia menyimpan cookie yang diberikan oleh server, mengirimkannya kembali pada request berikutnya, serta mengatur CSRF token tanpa perlu campur tangan manual. Dengan demikian, http berperan sebagai klien HTTP generik, sementara CookieRequest berperan sebagai klien HTTP yang sadar terhadap sesi (session-aware) dan cocok untuk autentikasi berbasis Django.
- Jelaskan mengapa instance CookieRequest perlu untuk dibagikan ke semua komponen di aplikasi Flutter.
  - Satu instance CookieRequest perlu dibagikan ke seluruh komponen aplikasi karena autentikasi berbasis sesi membutuhkan konsistensi cookie dan CSRF token di setiap request. Jika setiap widget atau halaman membuat instance sendiri, maka masing-masing akan memiliki cookie yang berbeda sehingga sebagian aplikasi akan menganggap pengguna login sementara bagian lain tidak. Dengan berbagi satu instance yang sama, seluruh bagian aplikasi dapat memakai state login yang sama, cookie yang sama, dan session yang sama. Selain itu, pendekatan ini membuat arsitektur lebih mudah diatur, efisien dari sisi resource, serta mempermudah testing dan dependency injection menggunakan Provider, Riverpod, atau state management lainnya.
- Jelaskan konfigurasi konektivitas yang diperlukan agar Flutter dapat berkomunikasi dengan Django. Mengapa kita perlu menambahkan 10.0.2.2 pada ALLOWED_HOSTS, mengaktifkan CORS dan pengaturan SameSite/cookie, dan menambahkan izin akses internet di Android? Apa yang akan terjadi jika konfigurasi tersebut tidak dilakukan dengan benar?
  - Agar Flutter dapat berkomunikasi dengan Django, beberapa konfigurasi perlu disiapkan. Android emulator mengakses komputer host melalui alamat khusus 10.0.2.2, sehingga Django harus menambahkan alamat ini ke dalam ALLOWED_HOSTS untuk menghindari error Invalid Host Header. Selain itu, bila aplikasi dijalankan melalui browser (misalnya Flutter Web), Django perlu mengaktifkan CORS agar browser mengizinkan frontend melakukan request ke backend. Pengaturan cookie seperti SameSite=None dan Secure=True juga diperlukan jika aplikasi menggunakan session-based authentication dan melakukan request lintas domain, karena tanpa konfigurasi tersebut cookie session tidak akan dikirim oleh browser. Di sisi Android, aplikasi mobile membutuhkan permission INTERNET agar dapat mengakses jaringan. Jika salah satu konfigurasi ini tidak benar, maka request bisa diblokir, session tidak terkirim, login gagal, atau aplikasi tidak dapat terhubung ke server sama sekali.
- Jelaskan mekanisme pengiriman data mulai dari input hingga dapat ditampilkan pada Flutter.
  - Ketika pengguna memasukkan data melalui form di Flutter, aplikasi akan melakukan validasi nilai input dan kemudian mengubah data tersebut menjadi JSON melalui model Dart. Setelah itu, Flutter mengirimkan request HTTP ke Django menggunakan CookieRequest atau http, lengkap dengan cookie, CSRF token, dan header yang diperlukan. Django kemudian menerima data tersebut, melakukan validasi server-side, dan jika valid, menyimpannya ke database sebelum mengembalikan response dalam bentuk JSON. Flutter men-decode JSON tersebut, mengubahnya kembali menjadi objek model, lalu memperbarui state aplikasi. Hasil akhirnya, data baru akan muncul di UI setelah proses render ulang dilakukan oleh Flutter.
- Jelaskan mekanisme autentikasi dari login, register, hingga logout. Mulai dari input data akun pada Flutter ke Django hingga selesainya proses autentikasi oleh Django dan tampilnya menu pada Flutter.
  - Proses autentikasi dimulai ketika pengguna memasukkan username dan password pada Flutter, lalu aplikasi mengirimkannya ke endpoint login Django. Django memverifikasi kredensial, dan jika benar, ia membuat session di server dan mengirim cookie sessionid (serta csrftoken jika diperlukan). CookieRequest menyimpan cookie ini sehingga request berikutnya otomatis membawa session yang sama, memungkinkan Django mengenali pengguna tanpa harus login ulang. Untuk pendaftaran (register), prosesnya mirip: Flutter mengirim data pengguna baru ke Django, dan Django membuat akun tersebut. Pada proses logout, Flutter mengirim request ke endpoint logout Django, yang kemudian menghapus session di server dan menginstruksikan klien untuk menghapus cookie session. Setelah logout, Flutter menghapus session yang tersimpan secara lokal dan menampilkan kembali tampilan login atau menu awal. Mechanisme ini memastikan bahwa Flutter dan Django tetap sinkron dalam hal status autentikasi pengguna.
