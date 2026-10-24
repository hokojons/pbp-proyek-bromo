# pbp-proyek-bromo

Aplikasi Pencari Teman Sparing Voli & Basket

## A. Kelompok
Nama kelompok: Bromo
* Anggota 1: Rafael Valentino Patrick Tantokusumo, 243401001, hokojons
* Anggota 2: Jeremy Christopher, 243401010, J-Chris-14

## B. Ringkasan Usulan Proyek v2
1. Penggunanya adalah individu, komunitas, atau mahasiswa yang ingin mencari teman mabar atau lawan tanding sparing khusus cabang olahraga voli dan basket.
2. Masalah yang mereka alami adalah susah mencari partner atau tim lawan yang pas dari segi lokasi lapangan, jadwal main, dan level permainan (skill level). Contohnya saat tim kekurangan orang untuk main basket/voli di akhir pekan tapi teman-teman dekat sedang tidak bisa ikut.
3. Saat ini mereka masih mencari secara manual lewat grup chat WhatsApp/Telegram yang pesannya cepat tenggelam, atau sekadar ajakan lisan tanpa kepastian kuota pemain.
4. Platform utamanya adalah Android untuk pengujian penuh, ditambah Web dan Desktop dengan tampilan yang menyesuaikan layar. Bedanya ada di fitur foto lapangan: di HP Android langsung memakai kamera HP, sedangkan di Web/Desktop memakai fitur upload file gambar dari komputer.

## C. Kontrak Lima Unsur
1. CRUD: Pengguna bisa menambah, melihat, mengubah, dan menghapus postingan ajakan sparing voli atau basket di daftar kegiatan.
2. API: Data ajakan sparing diambil dan dikirim ke backend kelompok (Dart) lewat endpoint GET /kegiatan, POST /kegiatan, GET /kegiatan/{id}, PUT /kegiatan/{id}, dan DELETE /kegiatan/{id}.
3. Layout Adaptif: Tampilan aplikasi menyesuaikan ukuran layar, baik saat dibuka di layar sempit (HP Android) maupun layar lebar (Web dan Desktop).
4. State Lintas Layar: Status partisipasi atau jumlah kuota pemain yang terisi otomatis berubah secara sinkron antara halaman Beranda/Daftar Kegiatan dan halaman Detail Kegiatan.
5. Penyimpanan Lokal: Aplikasi menyimpan cache data profil pengguna dan pilihan tema tampilan (terang/gelap) di penyimpanan lokal perangkat.

## D. Batasan Ruang Lingkup
Entitas Data:
1. Kegiatan: ID Kegiatan, Judul Kegiatan, Kategori Olahraga (Voli/Basket), Lokasi & Jadwal, Status (Mencari/Penuh/Selesai).
2. Pengguna: ID Pengguna, Nama, Peran (Pencari Teman/Tuan Rumah/Komunitas), Nomor Kontak.
3. Partisipasi: ID Partisipasi, ID Kegiatan, ID Pengguna, Tanggal Bergabung, Status (Menunggu/Diterima/Ditolak).

Layar:
1. Halaman Beranda/Dashboard: Menampilkan ringkasan ajakan sparing voli dan basket terbaru.
2. Halaman Daftar Kegiatan: Menampilkan semua ajakan sparing lengkap dengan pencarian dan filter kategori (Voli/Basket) serta lokasi.
3. Halaman Detail Kegiatan: Menampilkan info lengkap ajakan, syarat pemain/tim, dan sisa slot kuota.
4. Halaman Form Ajakan/Gabung: Berisi form untuk membuat/mengubah ajakan sparing atau form untuk ikut bergabung.
5. Halaman Profil Pengguna: Menampilkan data akun pengguna, olahraga pilihan (voli/basket), dan riwayat sparing yang diikuti.

## E. Backlog Awal
1. Melihat dan memfilter daftar ajakan sparing voli atau basket dari server lewat GET /kegiatan. (Unsur: API, CRUD)
2. Membuat postingan ajakan sparing baru lengkap dengan foto lapangan (kamera di Android, upload file di Web/Desktop) lewat POST /kegiatan. (Unsur: CRUD, API)
3. Mengubah info jadwal/status ajakan lewat PUT /kegiatan/{id} dan menghapus ajakan lewat DELETE /kegiatan/{id}. (Unsur: CRUD, API)
4. Mengajukan ikut sparing di halaman Detail Kegiatan, lalu sisa slot dan status bergabungnya langsung ter-update di halaman Beranda dan Daftar Kegiatan. (Unsur: State lintas layar, CRUD, API)
5. Mengatur tampilan daftar kegiatan menjadi 1 kolom di HP Android dan menjadi tampilan multi-kolom di layar lebar Web/Desktop. (Unsur: Layout adaptif)
6. Menyimpan data profil pengguna yang sedang login dan pengaturan tema aplikasi (gelap/terang) di penyimpanan lokal. (Unsur: Penyimpanan lokal)
7. Menerima atau menolak permintaan gabung dari pemain lain, dan statusnya langsung berubah di halaman Detail Kegiatan maupun Profil Pengguna. (Unsur: CRUD, API, State lintas layar)