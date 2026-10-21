# PAYROLL PRO

Aplikasi pengelolaan gaji karyawan. Murni HTML, CSS, dan JavaScript, tanpa framework dan tanpa build. Semua library sudah ada di folder `lib/`, jadi tidak butuh internet saat dipakai.

## Struktur
- `index.html`, `style.css`, `app.js`: aplikasi
- `lib/`: SheetJS (Excel), jsPDF, jsPDF-AutoTable (PDF)

## Jalankan lokal
Klik dua kali `index.html`. Semua fitur berjalan di browser.

## Unggah ke GitHub dan aktifkan GitHub Pages (gratis)
1. Buat repository baru di github.com (disarankan **Private** jika memungkinkan).
2. Unggah seluruh isi folder ini (`Add file` > `Upload files`), lalu `Commit`.
3. Buka `Settings` > `Pages`. Pada `Source` pilih `Deploy from a branch`, branch `main`, folder `/ (root)`, lalu `Save`.
4. Tunggu 1-2 menit; alamat situs muncul di halaman yang sama.

Data gaji TIDAK ikut ke GitHub. Data hanya tersimpan di IndexedDB browser masing-masing perangkat.

## Cara pakai singkat
1. Pilih periode di kanan atas (bulan/tahun).
2. Menu **Data Karyawan**: tambah, edit, hapus, impor CSV (`nama,jabatan,gaji`). Atau muat data demo di **Pengaturan**.
3. Menu **Pengambilan Gaji**: Proses Pengambilan Gaji > konfirmasi > tanda tangan > Simpan dan Konfirmasi. Bukti PDF bisa diunduh.
4. **Rekap Gaji**, **Laporan dan Export** (Excel, CSV, PDF, cetak), **Riwayat Transaksi**.

## Backup dan pemulihan
`Pengaturan` > **Backup data (JSON)** untuk menyimpan, **Pulihkan data** untuk memuat kembali. Lakukan backup rutin, terutama sebelum membersihkan data browser. Backup berisi data gaji dan tanda tangan: simpan di tempat aman, jangan unggah ke GitHub.

## Keamanan
- Penyimpanan browser tidak terenkripsi dan tidak sinkron antar perangkat.
- Tidak ada login karena login yang sungguhan membutuhkan server. Jangan bagikan perangkat ke orang yang tidak berwenang.
- Tanda tangan adalah bukti elektronik internal, bukan tanda tangan elektronik tersertifikasi.

## Migrasi ke database online (nanti)
Untuk multi-perangkat atau multi-admin, pindahkan fungsi `load()` dan `save()` di `app.js` ke layanan dengan autentikasi dan aturan akses per pengguna (misalnya Supabase atau Firebase). Jangan menaruh kunci rahasia server di kode frontend.
