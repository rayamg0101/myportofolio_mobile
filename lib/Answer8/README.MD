# Individual Assignment 8
1. Navigator.push():Berpindah ke halaman baru.
    Navigation Stack:Menambahkan halaman baru ke atas tumpukan. Halaman sebelumnya tetap tersimpan di bawahnya sehingga pengguna bisa kembali (biasanya lewat tombol back).
    Navigator.pushReplacement():Berpindah ke halaman baru sekaligus mengganti halaman saat ini.
    Navigation Stack:Menghapus halaman yang sedang aktif dari tumpukan, lalu menggantinya dengan halaman baru. Pengguna tidak bisa kembali ke halaman sebelumnya dengan tombol back.
    Navigator.pop():Menutup halaman saat ini.
    Navigation Stack:Mengeluarkan (pop) halaman paling atas dari tumpukan dan mengembalikan pengguna ke halaman yang ada tepat di bawahnya.
2. Peran Scaffold, AppBar, dan Drawer:Scaffold bertindak sebagai kerangka tata letak dasar standar Material Design pada setiap halaman. Dengan menempatkan AppBar di bagian atas dan menyematkan komponen Drawer yang sama ke dalam properti drawer milik Scaffold di tiap halaman, tata letak visualnya tetap seragam—judul halaman selalu berada di posisi yang sama, ikon menu (hamburger icon) selalu muncul di pojok kiri atas, dan menu navigasi samping dapat diakses dari halaman mana pun.
3. Alasan pemilihan tata letak form:
Form umumnya menggunakan tata letak vertikal satu kolom (Column atau ListView) dengan label dan kolom input yang tersusun dari atas ke bawah. Tata letak ini dipilih karena mengikuti arah baca alami pengguna di layar perangkat mobile yang sempit (orientasi portrait), meminimalkan salah ketuk, dan memudahkan pengisian data secara berurutan.

Fungsi widget spacing dan scrolling saat ruang layar terbatas:

Widget Spacing (seperti SizedBox atau Padding): Memberikan jarak napas antar kolom input dan tepi layar agar elemen UI tidak saling menempel, mudah dibaca, dan mencegah pengguna tidak sengaja menekan kolom yang salah.

Widget Scrolling (seperti SingleChildScrollView atau ListView): Sangat krusial ketika keyboard virtual (on-screen keyboard) muncul dari bawah layar dan memakan hampir separuh ruang vertikal. Tanpa widget scrolling, elemen form di bagian bawah akan terpotong dan memunculkan error RenderFlex overflow. Dengan adanya scrolling, pengguna tetap bisa menggulir layar ke atas dan bawah untuk melihat seluruh kolom input serta tombol Save meskipun keyboard sedang terbuka.
4. Peran masing-masing komponen:

GlobalKey<FormState>: Bertindak sebagai pengenal unik (identifier) yang menghubungkan kode logika (seperti fungsi tombol Save) dengan status internal widget Form di dalam pohon widget (widget tree), sehingga state form dapat diakses dari luar.

validator: Fungsi callback yang dipasang pada masing-masing TextFormField. Tugasnya memeriksa isi teks yang diketik pengguna berdasarkan aturan tertentu, lalu mengembalikan pesan error (String) jika tidak valid, atau mengembalikan null jika valid.

validate(): Metode yang dipanggil melalui formKey.currentState!.validate() saat tombol Save ditekan. Metode ini akan memicu seluruh fungsi validator di dalam form secara serentak; jika semuanya mengembalikan null, metode ini menghasilkan true (data siap disimpan), dan jika ada satu saja yang gagal, hasilnya false serta pesan error otomatis muncul di layar.

Contoh nilai yang ditolak dan mengapa keyboard type saja tidak cukup:

Contoh nilai yang ditolak: Input berupa teks huruf (misalnya "abc") atau angka minus/nol (misalnya "-5000") pada kolom harga/jumlah, atau string kosong "" pada kolom wajib isi.

Mengapa widget input / keyboard type saja tidak cukup: Mengatur keyboardType: TextInputType.number hanya mengubah tampilan tombol keyboard di layar ponsel untuk kenyamanan pengguna, tetapi tidak memvalidasi data secara ketat. Pengguna tetap bisa menempelkan (paste) teks huruf dari clipboard, memasukkan simbol yang tidak valid (seperti banyak tanda titik/minus), mengetik lewat keyboard fisik/eksternal, atau membiarkan kolom tetap kosong sama sekali. Oleh karena itu, validasi logika lewat validator tetap wajib dilakukan.
5. 6. Saya tidak menggunakan AI ketika mengerjakan mengerjakan tugas Individu 8, tetapi saya menggunakan AI yaitu Gemini untuk membantu saya menjawab pertanyaan ini sekaligus memahami terkait materi tersebut