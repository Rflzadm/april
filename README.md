# UAS_Algoritma_Kelompok-5
# Sistem Pemesanan Tiket Konser & Manajemen Admin (C++)
> Aplikasi berbasis CLI (Command Line Interface) untuk mengelola antrean pembeli, pemesanan tiket konser, pencatatan riwayat transaksi secara real-time, serta dilengkapi modul kontrol manajemen data khusus dari sisi Admin.

---

## 👥 Anggota Kelompok & Pembagian Tugas
Pengembangan kode program ini dibagi secara kolaboratif dan dipantau secara terstruktur:

| Nama Anggota | Peran / Tugas yang Dikerjakan | File Source Code / Modul | Status |
| :--- | :--- | :--- | :--- |
| **Refliza** | - **Ketua Kelompok**<br>- Memantau progres pekerjaan anggota tim<br>- Manajemen repositori GitHub | *Management & Monitoring* | ✅ Aktif |
| **Andin** | - Inisialisasi jadwal & ketersediaan informasi tiket<br>- **[BARU]** Autentikasi akses & pembaruan data konser oleh Admin | `FiturJadwal.cpp`<br>`FiturAdmin.cpp` | ✅ Selesai |
| **Rezia** | - Implementasi **Queue** untuk antrean pembeli<br>- Validasi kuota & proses pemotongan stok<br>- Implementasi **Stack** untuk riwayat transaksi | `FiturTransaksi.cpp` | ✅ Selesai |
| **Riyyan** | - Integrasi seluruh modul file program ke master file<br>- Pembuatan alur menu utama (*Main Workflow*)<br>- Validasi pilihan menu utama pengguna | `main1.cpp` | ✅ Selesai |

---

## 🚀 Fitur Utama Sistem

### 👤 Fitur Sisi Pengguna (User/Pembeli):
* **Manajemen Jadwal & Stok (Array of Struct):** Menyimpan data konser (ID, Nama Artis, Stok, dan Harga) dengan kapasitas maksimal 5 konser aktif.
* **Sistem Antrean Pembeli (Queue / FIFO):** Calon pembeli wajib masuk ke dalam baris antrean terlebih dahulu sebelum bertransaksi (*First-In, First-Out*).
* **Riwayat Transaksi Terakhir (Stack / LIFO):** Mencatat log transaksi sukses dan menampilkan maksimal 3 riwayat transaksi terbaru (*Last-In, First-Out*).
* **Validasi Stok Otomatis:** Menolak proses *checkout* jika tiket yang dipesan melebihi sisa kapasitas kursi di sistem.

### 🔐 Fitur Sisi Manajemen (Admin):
* **Sistem Proteksi Otentikasi (Password Gate):** Mengamankan menu manajemen menggunakan password khusus. Akses otomatis ditolak jika input tidak sesuai.
* **Modifikasi Data Dinamis (Real-Time Update):** Mengizinkan Admin mencari jadwal konser berdasarkan ID (Linear Search), melihat data lama, kemudian memperbarui nama artis, menambahkan/mengurangi stok, hingga mengubah harga tiket secara instan di memori program.

---

## 🛠️ Struktur Data & Konsep C++ yang Diterapkan
Program ini memanfaatkan beberapa konsep fundamental dan lanjutan dari mata kuliah Struktur Data:
1. **`struct` (`tiketkonser` & `Transaksi`):** Digunakan untuk membungkus tipe data objek kompleks menjadi satu kesatuan.
2. **Array of Struct (`jadwalkonser[5]`):** Untuk menampung daftar jadwal konser yang bersifat statis namun isinya dapat diubah secara dinamis oleh admin.
3. **`std::queue` (STL):** Digunakan untuk mengelola antrean pembeli (`antreanPembeli`) dengan fungsi `.push()`, `.pop()`, dan `.front()`.
4. **`std::stack` (STL):** Digunakan untuk mencatat memori riwayat transaksi (`riwayatTransaksi`) dengan fungsi `.push()`, `.pop()`, dan `.top()`.
5. **Searching & Linear Control:** Algoritma pencarian data berdasarkan ID konser untuk menemukan indeks data target yang ingin dimodifikasi oleh admin.

---
