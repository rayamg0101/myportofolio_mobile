#Individual Assignment 7
1. Pohon Widget (Widget Tree): Merupakan struktur hierarki tempat widget-widget disusun. Setiap widget (kecuali root) memiliki satu induk (parent) dan dapat memiliki satu atau beberapa anak (children).
Widget induk mengatur bagaimana anak-anaknya ditempatkan, dirender, dan diberi batasan ukuran (constraints).
2. MaterialApp (berada di main.dart)

Fungsi: Bertindak sebagai root widget yang mengonfigurasi pengaturan dasar aplikasi, seperti judul aplikasi (title), skema warna global (theme menggunakan Material 3 dengan seed color indigo dan sekunder amber), serta menetapkan halaman awal (home) ke MyHomePage.

MyApp (berada di main.dart)

Fungsi: Widget kustom turunan dari StatelessWidget yang menjadi titik masuk (entry point) utama dari struktur pohon widget aplikasi Anda.

MyHomePage (berada di menu.dart)

Fungsi: Widget kustom turunan dari StatelessWidget yang merepresentasikan halaman utama (dashboard) portofolio Anda.

Scaffold (berada di menu.dart)

Fungsi: Menyediakan kerangka tata letak visual dasar Material Design untuk layar, menampung AppBar di bagian atas dan konten utama di bagian body.
AppBar (berada di menu.dart)

Fungsi: Bilah navigasi bagian atas yang menampilkan judul aplikasi ("MyPortfolio") dengan latar belakang warna utama (primary dari tema).

Padding (berada di menu.dart)

Fungsi: Menambahkan ruang kosong (padding) di sekeliling atau di bagian tertentu dari widget anak agar tata letak tidak terlalu menepi.

Column (berada di menu.dart)

Fungsi: Menyusun beberapa widget anak secara vertikal (dari atas ke bawah). Digunakan baik untuk menyusun bagian atas dan bawah layar utama, maupun di dalam kartu.

Row (berada di menu.dart)

Fungsi: Menyusun beberapa widget anak secara horizontal (dari kiri ke kanan). Digunakan untuk mensejajarkan ketiga InfoCard (NPM, Nama, Kelas) secara berdampingan.
InfoCard (berada di menu.dart)

Fungsi: Widget kustom turunan StatelessWidget yang membungkus tampilan informasi ringkas (seperti NPM, Nama, dan Kelas) dalam bentuk kartu terstruktur.

Card (berada di menu.dart)

Fungsi: Menyediakan wadah bergaya material dengan efek bayangan (elevation) untuk menampilkan informasi ringkas.

Container (berada di menu.dart)

Fungsi: Widget serbaguna untuk mengatur ukuran (lebar menggunakan MediaQuery), dekorasi, atau jarak bagian dalam (padding) dari elemen anak.

SizedBox (berada di menu.dart)

Fungsi: Memberikan jarak kosong dengan ukuran tetap (fixed height) secara vertikal antar komponen.

Center (berada di menu.dart)

Fungsi: Menyelaraskan widget anaknya agar berada persis di tengah area yang tersedia.

GridView.count (berada di menu.dart)

Fungsi: Menampilkan daftar elemen dalam bentuk grid (tata letak berbasis kolom silang/crossAxisCount: 3), sangat efisien untuk tombol-tombol menu aksi utama.

ItemCard (berada di menu.dart)

Fungsi: Widget kustom turunan StatelessWidget untuk merender masing-masing tombol menu aksi di dalam grid secara modular.

Material (berada di menu.dart)

Fungsi: Menyediakan dasar material warna latar belakang sekunder (amber) serta sudut lengkung (borderRadius) untuk kartu tombol menu.

InkWell (berada di menu.dart)

Fungsi: Mendeteksi gestur sentuhan (tap) dari pengguna sekaligus memberikan efek visual interaktif berupa ripple effect (gelombang air) saat tombol ditekan.

Icon (berada di menu.dart)

Fungsi: Menampilkan ikon visual grafis (berdasarkan properti item.icon) di dalam tombol menu.

Text (berada di beberapa bagian)

Fungsi: Menampilkan teks string di layar dengan berbagai kustomisasi gaya tipografi (seperti ukuran, ketebalan, dan warna).
3. Tujuan Utama: Mengonfigurasi aplikasi agar sesuai dengan standar desain Material Design dari Google serta menyediakan faytur inti aplikasi seperti sistem navigasi (Navigator), manajemen tema warna global (ThemeData), lokalisasi (localization), dan manajemen rute (routes).

Alasan sebagai Root: MaterialApp bertindak sebagai titik masuk utama (root widget) karena ia menyebarkan (inherit) data konfigurasi penting seperti tema dan status navigasi ke seluruh widget di bawahnya melalui pohon widget. Tanpa MaterialApp (atau CupertinoApp untuk gaya iOS), widget turunan tidak akan memiliki akses ke fungsi navigasi bawaan atau tema material.
4. Stateless Widget Bersifat statis / immutable. Nilai atau tampilannya tidak berubah setelah dirender, Sederhana; hanya memiliki metode build(), dan Teks statis, ikon, tombol sederhana, kartu informasi (card). Stateless Widget digunakan Ketika komponen UI bersifat statis dan hanya bergantung pada data yang diterimanya saat pertama kali dibuat (props/constructor).

Stateful Widget Bersifat dinamis / mutable. Memiliki objek State terpisah yang dapat berubah seiring waktu, Kompleks; memiliki siklus hidup tambahan seperti initState(), setState(), dan dispose(), dan Formulir input, tombol like/toggle, keranjang belanja, counter.
Stateful Widget digunakan ketika komponen UI perlu merespons interaksi pengguna, mengambil data dari API, atau memperbarui tampilan secara dinamis menggunakan setState().
5. BuildContext adalah sebuah pengendali (handle) yang merepresentasikan lokasi sebuah widget di dalam pohon widget (widget tree). BuildContext penting karena Mengapa Penting: Karena widget disusun secara hierarkis, BuildContext memungkinkan sebuah widget untuk mengetahui posisi relatifnya. Dengan context, widget dapat mencari widget leluhur (ancestor) di atasnya untuk mengakses fungsi global seperti tema (Theme.of(context)), media query (MediaQuery.of(context)), atau navigasi (Navigator.push(context, ...)).
6. Saya tidak menggunakan AI ketika mengerjakan mengerjakan tugas main.dart dan menu.dart, tetapi saya menggunakan AI yaitu Gemini untuk membantu saya menjawab pertanyaan ini sekaligus memahami terkait materi tersebut
