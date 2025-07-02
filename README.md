# Test
website produk




![image](https://github.com/user-attachments/assets/501aa8b2-5680-4600-b10a-4d89e772c8c3)



Dokumentasi Fitur Aplikasi Laravel - Sistem Manajemen Produk
1. Halaman Utama (Landing Page)
Halaman welcome menampilkan dua tombol utama: Login dan Register.
Jika pengguna sudah login, otomatis diarahkan ke halaman daftar produk.
Routing ditangani oleh /routes/web.php dan memeriksa Auth::check().
2. Autentikasi (Login dan Register)
Fitur login dan register menggunakan AuthController:
- Login memverifikasi email dan password, jika berhasil diarahkan ke halaman produk.
- Register menyimpan user baru dan langsung login.
Route login dan register ditentukan di web.php.
View disimpan di resources/views/auth/login.blade.php dan register.blade.php.
3. Daftar Produk (index.blade.php)
Menampilkan daftar produk dalam bentuk tabel.
Fitur:
- Pencarian berdasarkan nama produk.
- Filter berdasarkan kategori (Elektronik, Fashion, Makanan).
- Tombol Aksi: Edit dan Hapus.
Data produk berasal dari controller melalui variabel $produks.
4. Tambah/Edit Produk (form.blade.php)
Form digunakan untuk menambah atau mengedit produk.
Action dan metode disesuaikan berdasarkan kondisi apakah $produk sudah ada (edit) atau belum (tambah).
Field yang disediakan: nama, kategori, harga, stok.
Data divalidasi di ProductController.
5. Routing
Routing utama ditentukan di routes/web.php.
- Route resource untuk produk: Route::resource('/produk', ProductController::class)->middleware('auth');
- Login & Register: route get/post login dan register menggunakan AuthController.
Hanya user yang login bisa mengakses fitur produk.
Dokumentasi Fitur Aplikasi Laravel - Sistem Manajemen Produk
6. Controller
ProductController menangani semua fungsi CRUD produk:
- index(): tampilkan semua produk
- create() & store(): form dan simpan produk baru
- edit() & update(): form edit dan update data
- destroy(): hapus produk
AuthController menangani:
- loginForm(), login()
- registerForm(), register()
Semua menggunakan Laravel Auth dan Validasi.
