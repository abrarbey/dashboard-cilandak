# Dashboard SAKTI — versi 137

Ketujuh sumber otomatis sekarang menggunakan file Excel dari Google Drive. Halaman mengambil data saat selesai dimuat dan menampilkan data terakhir selama proses pengunduhan. File tidak perlu diunggah manual setiap kali membuka dashboard.

## Memasang di GitHub Pages

1. Ekstrak ZIP ini di komputer.
2. Buka repository GitHub yang digunakan untuk dashboard.
3. Pilih Add file → Upload files.
4. Unggah index.html, .nojekyll, README.md dan VALIDASI_SUMBER.txt ke direktori paling atas repository. Jangan mengunggah file ZIP sebagai halaman situs.
5. Commit changes. Jika index.html sudah ada, gantikan file lama.
6. Settings → Pages → Source: Deploy from a branch → branch main → folder /(root) → Save. Jika repository menggunakan branch lain, pilih branch tempat file diunggah.
7. Buka alamat yang ditampilkan GitHub Pages. Bila masih terlihat versi lama, tekan Ctrl+F5.

## Sumber yang terhubung

- Overview.xlsx
- DHKP_Unduhan_SPPT.xlsx
- Pembayaran_PBB.xlsx
- Riwayat_Pembayaran.xlsx
- Prioritas_Himbauan.xlsx
- Rincian_Piutang_Tahunan.xlsx
- Jatuh_Tempo_PBB.xlsx

URL sumber berada di SAKTI_HYBRID_SOURCES pada index.html. Seluruh type bernilai xlsx. Unduhan menggunakan fetch + arrayBuffer, lalu XLSX.read melalui Web Worker jika tersedia. Dua sumber diunduh secara paralel agar penggunaan memori terkendali. Mekanisme pembaca CSV tetap tersedia di kode untuk kompatibilitas, tetapi tidak dipakai oleh ketujuh sumber otomatis ini.

## Memperbarui data

Perbarui isi file Google Drive yang sama agar ID tautannya tetap. Jangan menghapus file lama dan membuat file baru jika ingin mempertahankan tautan. Nama sheet dan header tetap mengikuti format yang sudah diuji.

Setelah pembaruan tersimpan di Drive, buka ulang dashboard atau pilih Data & Import → Sinkronkan Ulang. Waktu Google menyiapkan hasil ekspor dapat memengaruhi kapan perubahan terlihat.

Upload manual dan Export tetap tersedia sesuai hak akses. Bila sumber diunggah manual saat sinkronisasi berjalan, pembaruan otomatis sumber itu dilewati agar unggahan baru tidak tertimpa.

## Validasi dan kegagalan

NOPD wajib teks 18 digit lengkap. Kolom, angka dan tanggal diperiksa sebelum sumber diterapkan. Riwayat penyampaian, catatan operasional dan pengaturan hak akses tetap dipertahankan. Data prioritas diperbarui/ditambah menurut NOPD; objek lain tidak dihapus otomatis.

Sumber gagal karena izin, jaringan, CORS, format, atau data tidak valid akan ditandai Gagal dalam matriks Data & Import. Data terakhir sumber tersebut tetap dipakai. Buka status untuk melihat penjelasannya. Rincian pemeriksaan awal ada di VALIDASI_SUMBER.txt.

Data aktif disimpan melalui penyimpanan browser yang sudah ada. Jika penyimpanan gagal, peringatan ditampilkan. Login akun SAKTI tetap lokal; tidak menambahkan autentikasi Google atau backend. Unduhan memakai URL yang dapat diakses tanpa cookie Google. Perubahan izin Drive dapat menghentikan pengambilan otomatis.

## Akses data

HTML memuat data wajib pajak dan tautan sumber. Orang yang dapat mengakses situs dapat membaca kode/data tersebut. Role dan login lokal bukan pengamanan server. Pastikan akses publikasi sesuai penggunaan data.

Tidak perlu Node.js, npm, atau proses build. Situs belum dipublikasikan oleh pembuat paket.
