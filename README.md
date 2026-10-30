# Dashboard Kolaborasi — GitHub Pages

Paket statis dari Dashboard Kolaborasi (Matriks Import dan Export).

## Isi paket

- `index.html`: aplikasi lengkap beserta data, gambar, font, dan pembaca Excel.
- `.nojekyll`: menayangkan file sebagai situs statis tanpa pemrosesan Jekyll.
- `README.md`: panduan ini.

Tidak membutuhkan Node.js, instalasi paket, atau proses build.

## Mengunggah melalui browser

1. Ekstrak ZIP ini di komputer. Jangan mengunggah file ZIP langsung sebagai situs.
2. Buka repository GitHub tujuan, atau buat repository baru.
3. Pilih **Add file → Upload files**.
4. Unggah `index.html`, `.nojekyll`, dan `README.md` langsung ke bagian paling atas repository. Jangan menaruhnya di dalam folder tambahan.
5. Klik **Commit changes**.
6. Buka **Settings → Pages**.
7. Pada **Build and deployment → Source**, pilih **Deploy from a branch**.
8. Pilih branch **main** dan folder **/(root)**, lalu klik **Save**. Bila branch repository memakai nama lain, pilih branch tempat file diunggah.
9. Tunggu proses publikasi selesai, lalu buka tautan situs yang ditampilkan pada halaman Pages.

Alamat umumnya berbentuk `https://USERNAME.github.io/NAMA-REPOSITORY/`. Gunakan tautan yang benar-benar ditampilkan GitHub untuk repository Anda.

Panduan resmi: https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site

## Menggunakan dan memperbarui data

- Buka situs melalui tautan GitHub Pages, lalu gunakan akun dashboard yang tersedia.
- Data & Import menyediakan tujuh sumber data dengan tombol Upload dan Export.
- Upload membuka pop up unggah, dan Export mengunduh seluruh data aktif untuk sumber tersebut.
- File Excel yang diunggah tidak otomatis ditulis ke repository GitHub.
- Pengaturan dan pembaruan lokal mengikuti penyimpanan browser yang sudah digunakan aplikasi. Data tidak otomatis dibagikan ke perangkat atau pengguna lain.
- Domain GitHub Pages memiliki penyimpanan browser yang terpisah dari file HTML lokal. Ekspor/cadangkan data dari penggunaan sebelumnya sebelum berpindah, lalu impor di situs bila diperlukan.
- Untuk memperbarui kode aplikasi, gantikan `index.html` pada repository dengan versi baru dan commit perubahan. Jika tampilan lama masih muncul, muat ulang dengan Ctrl+F5.

## Akses dan data wajib pajak

HTML ini memuat data wajib pajak di dalam kode sumbernya. Orang yang dapat mengakses situs dapat mengunduh file HTML beserta data tertanam tersebut. Role dan login pada aplikasi statis ini bekerja di browser dan tidak menjadi pengamanan data pada server.

Paket ini mempertahankan mode aplikasi yang ada (`internal`, tanpa backend). Paket tidak menambahkan autentikasi server, sinkronisasi antarperangkat, penyimpanan Google Drive, atau database bersama. Pastikan lokasi publikasi dan pihak yang dapat mengaksesnya sesuai dengan penggunaan data Anda.

Paket ini disiapkan untuk unggah manual. Situs belum dipublikasikan oleh pembuat paket.

## Perubahan versi 133

Label identitas pegawai menggunakan NIP. Password baru dan reset password minimal 4 karakter. Identitas akun dan data yang sudah tersimpan tetap kompatibel.
