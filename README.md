
# Sistem Voting Pemilihan Ketua Umum Asrama 2025

**Sumber:** `index.html` (file yang Anda unggah). fileciteturn0file0

---

## Ringkasan
Aplikasi front-end sederhana untuk penyelenggaraan voting pemilihan Ketua Umum Asrama (Asrama Mahasiswa Bumi Siliwangi UPI — Kabinet Adhyayana). Dibangun sebagai single-page static HTML + JavaScript dengan styling Tailwind CSS. Data (calon, angkatan, suara, waktu voting, status admin) disimpan di `localStorage` pada browser.

---

## Fitur Utama
- Halaman voting bagi pemilih (masuk berdasarkan angkatan dan nama).
- Manajemen calon (tambah/hapus calon, upload foto, visi/misi/program kerja).
- Manajemen angkatan (tambah/edit/hapus angkatan; dukungan input massal).
- Pengaturan waktu voting (mulai / selesai, mulai sekarang selama 24 jam, hentikan).
- Tampilan hasil real-time dengan peringkat dan progress bar.
- Export hasil ke CSV.
- Otentikasi admin berbasis kredensial hard-coded (untuk akses fitur manajemen).

---

## Teknologi
- HTML5 (single file `index.html`)
- Vanilla JavaScript (no build tools)
- Tailwind CSS (via CDN)
- Penyimpanan: `localStorage` (browser)

---

## Cara Menjalankan (lokal)
1. Pastikan Anda memiliki `index.html` di folder.
2. Buka `index.html` di browser (double-click atau `File > Open`).
3. Aplikasi langsung berjalan tanpa server.  
   (Catatan: untuk fitur upload foto dan `localStorage`, gunakan browser modern.)

---

## Struktur Data (localStorage)
Nama-nama kunci yang digunakan:
- `ketua_umum_candidates` — array objek calon
- `ketua_umum_classes` — array objek angkatan `{ name, studentCount, votedCount }`
- `ketua_umum_votes` — object mapping `voterId -> candidateId`
- `ketua_umum_voting_time` — object `{ start, end }`
- `ketua_umum_admin_logged_in` — `'true'` / `'false'`

---

## Alur Penggunaan Singkat
### Sebagai Admin
1. Klik tombol **Admin** → masukkan username & password.
2. Setelah login, menu **Kelola Calon**, **Kelola Kelas**, **Waktu Voting**, **Hasil** akan tersedia.
3. Tambah calon / angkatan, atur waktu voting, atau mulai voting sekarang (opsi 24 jam).

### Sebagai Pemilih
1. Di halaman Voting: pilih angkatan, masukkan nama lengkap, klik *Masuk untuk Voting*.
2. Jika voting aktif, pilih salah satu calon (konfirmasi akan diminta).
3. Suara disimpan ke `localStorage` dan pemilih tidak dapat mengubah suara.

---

## Export & Backup
- Hasil voting dapat diexport ke CSV via tombol **Export Hasil ke CSV** (format: Nama Calon, Program Studi/Fakultas, Jumlah Suara, Persentase).
- Untuk backup manual: buka DevTools → Application → Local Storage → ekspor kunci-kunci di atas.

## Lisensi
Gunakan sesuai kebutuhan