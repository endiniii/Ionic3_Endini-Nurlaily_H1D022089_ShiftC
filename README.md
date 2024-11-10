# Ionic3_Endini-Nurlaily_H1D022089_ShiftC
# 1. Create (Tambah Data)
- Fungsi ini memungkinkan pengguna untuk menambahkan data mahasiswa baru ke dalam sistem.
- Saat pengguna menekan tombol Tambah Mahasiswa, modal untuk menambah data mahasiswa akan terbuka.
- Pengguna mengisi nama dan jurusan mahasiswa yang ingin ditambahkan.
- Saat tombol Tambah Mahasiswa di modal ditekan, fungsi tambahMahasiswa() akan dipanggil.
- tambahMahasiswa():
  - Mengecek apakah kedua field (nama dan jurusan) sudah terisi.
  - Jika terisi, fungsi membuat objek data mahasiswa baru yang akan dikirim ke endpoint API (tambah.php) menggunakan layanan ApiService.
  - Setelah data berhasil dikirim dan ditambahkan ke server, modal akan ditutup, input akan di-reset, dan daftar mahasiswa akan diperbarui dengan memanggil getMahasiswa().
  - Jika terdapat error, pesan gagal akan dicetak di console.
#2. Read (Lihat Data)
- Fitur ini berfungsi untuk mengambil dan menampilkan semua data mahasiswa dari server.
- Ketika halaman pertama kali dimuat (pada fungsi ngOnInit), atau setiap kali data diperbarui, fungsi getMahasiswa() akan dipanggil.
- getMahasiswa():
  - Mengirim permintaan GET ke endpoint API (tampil.php) melalui ApiService.
  - Jika data berhasil diterima, respons tersebut akan disimpan dalam variabel dataMahasiswa, dan data akan ditampilkan pada tampilan HTML dengan menggunakan *ngFor.
  - Jika terjadi error, pesan error akan dicetak di console.
# 3. Update (Edit Data)
- Fitur ini digunakan untuk mengedit data mahasiswa yang sudah ada.
- Ketika pengguna memilih mahasiswa tertentu dan menekan tombol Edit, fungsi openModalEdit() akan dipanggil untuk membuka modal edit.
- openModalEdit(isOpen: boolean, idget: any):
  - Fungsi ini akan membuka modal edit, mengisi nilai id, dan memanggil fungsi ambilMahasiswa(id) untuk mendapatkan data mahasiswa dari server berdasarkan id yang dipilih.
- ambilMahasiswa(id: any):
  - Mengirim permintaan GET ke endpoint API (lihat.php?id=) untuk mengambil data spesifik mahasiswa tersebut.
  - Jika berhasil, nilai data mahasiswa (nama dan jurusan) akan disimpan dalam variabel lokal untuk ditampilkan di modal edit.
- editMahasiswa():
  - Setelah pengguna memperbarui data di modal, mereka dapat menekan tombol Edit Mahasiswa untuk menyimpan perubahan.
  - Fungsi ini membuat objek data yang berisi id, nama, dan jurusan, kemudian mengirim permintaan POST ke endpoint API (edit.php) untuk memperbarui data mahasiswa di server.
  - Jika berhasil, modal akan ditutup, input akan di-reset, dan daftar mahasiswa akan diperbarui.
  - Jika terjadi error, pesan gagal akan dicetak di console.
# 4. Delete (Hapus Data)
- Fitur ini memungkinkan pengguna untuk menghapus data mahasiswa.
- Ketika pengguna menekan tombol Hapus pada data mahasiswa, fungsi confirmHapus() akan memunculkan alert konfirmasi yang menanyakan apakah pengguna yakin ingin menghapus data (Ya atau Tidak0.
- confirmHapus(id: any):
  - Menggunakan AlertController untuk menampilkan pesan konfirmasi sebelum menghapus.
  - Jika pengguna menekan "Ya", maka fungsi hapusMahasiswa(id) akan dipanggil untuk menghapus data dari server.
- hapusMahasiswa(id: any):
  - Mengirim permintaan DELETE ke endpoint API (hapus.php?id=) untuk menghapus data mahasiswa dari server berdasarkan id.
  - Jika berhasil, daftar mahasiswa akan diperbarui dengan memanggil getMahasiswa().
  - Jika terjadi error, pesan gagal akan dicetak di console.


# a. Gambar tampilan awal website
![Tampilan awal](https://raw.githubusercontent.com/endiniii/Ionic3_Endini-Nurlaily_H1D022089_ShiftC/main/awal.png)

# b. Gambar tampilan Tambah Data Mahasiswa
![Tampilan Tambah Mahasiswa](https://raw.githubusercontent.com/endiniii/Ionic3_Endini-Nurlaily_H1D022089_ShiftC/main/tambah_mahasiswa.png) 

# c. Gambar tampilan Edit Data Makasiswa
![Tampilan Edit Data](https://raw.githubusercontent.com/endiniii/Ionic3_Endini-Nurlaily_H1D022089_ShiftC/main/edit_mahasiswapng)

# b. Gambar tampilan Hapus Data Mahasiswa
![Tampilan Hapus Data Mahasiswa](https://raw.githubusercontent.com/endiniii/Ionic3_Endini-Nurlaily_H1D022089_ShiftC/main/konfirmasia_hapus.png) 

