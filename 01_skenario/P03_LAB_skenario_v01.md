# DESKRIPSI SKENARIO

Mahasiswa mengajukan peminjaman peralatan dengan memilih alat, jumlah, dan rentang waktu. Sistem memeriksa ketersediaan peralatan. Jika peralatan tersedia dan data lengkap, sistem menyimpan pengajuan dengan status menunggu keputusan. Pada tampilan konfirmasi, mahasiswa dapat memilih untuk mencetak bukti pengajuan. Petugas mengelola data peralatan serta menyetujui atau menolak pengajuan. Kepala laboratorium dapat melihat laporan peminjaman.

# TABEL KEBUTUHAN

| ID | Kebutuhan |
|---|---|
| LAB-R01 | Mahasiswa dapat melihat ketersediaan peralatan. |
| LAB-R02 | Petugas dapat mengelola data peralatan. |
| LAB-R03 | Mahasiswa dapat mengajukan peminjaman; sistem memeriksa ketersediaan sebelum menyimpan pengajuan. |
| LAB-R04 | Mahasiswa dapat mencetak bukti pada konfirmasi pengajuan jika memilihnya. |
| LAB-R05 | Petugas dapat menetapkan persetujuan atau penolakan pengajuan. |
| LAB-R06 | Kepala laboratorium dapat melihat laporan peminjaman. |

# BATAS SISTEM DAN ATURAN

- Sistem mencatat dan menyediakan informasi; perpindahan fisik alat tidak terjadi di dalam perangkat lunak.
- Pengguna telah terautentikasi dan memiliki hak akses sesuai peran.
- Pengajuan yang diterima sistem berstatus Menunggu Keputusan, bukan otomatis Disetujui.
- Pengajuan dengan peralatan tidak tersedia tidak disimpan sebagai pengajuan berhasil.
- Pencetakan bukti tidak menjadi syarat keberhasilan pengajuan.
- Persetujuan petugas belum dimodelkan sebagai reservasi teknis stok.
- Pengambilan, pengembalian, kondisi alat, dan denda belum dianalisis pada potongan model ini.

# TABEL IDENTIFIKASI AKTOR

| No. | Aktor | Tujuan terhadap Sistem |
|---|---|---|
| 1 | Mahasiswa | Melihat ketersediaan peralatan, mengajukan peminjaman, dan mencetak bukti pengajuan. |
| 2 | Petugas Laboratorium | Mengelola data peralatan serta memproses persetujuan atau penolakan pengajuan. |
| 3 | Kepala Laboratorium | Melihat laporan peminjaman. |

# TABEL KATALOG USE CASE

| No. | ID Use Case | Nama Use Case | Peran dalam Model |
|---|---|---|---|
| 1 | LAB-UC01 | Lihat Ketersediaan Peralatan | Fungsi utama mahasiswa. |
| 2 | LAB-UC02 | Kelola Data Peralatan | Fungsi utama petugas laboratorium. |
| 3 | LAB-UC03 | Ajukan Peminjaman | Fungsi utama mahasiswa. |
| 4 | LAB-UC04 | Periksa Ketersediaan | Perilaku yang disertakan dalam UC03. |
| 5 | LAB-UC05 | Cetak Bukti Pengajuan | Fungsi tambahan bersyarat pada UC03. |
| 6 | LAB-UC06 | Proses Keputusan Peminjaman | Fungsi utama petugas laboratorium. |
| 7 | LAB-UC07 | Lihat Laporan Peminjaman | Fungsi utama kepala laboratorium. |

# RELASI INCLUDE

**LAB-UC03 Ajukan Peminjaman** `<<include>>` **LAB-UC04 Periksa Ketersediaan**

Alasan: Pemeriksaan ketersediaan merupakan bagian wajib dari proses pengajuan peminjaman agar sistem dapat memastikan peralatan tersedia sebelum pengajuan berhasil disimpan.

# RELASI EXTEND

**LAB-UC05 Cetak Bukti Pengajuan** `<<extend>>` **LAB-UC03 Ajukan Peminjaman**

- **Extension point:** Bukti pengajuan tersedia.
- **Kondisi:** Mahasiswa memilih opsi cetak.
- **Alasan:** Pengajuan peminjaman tetap berhasil meskipun mahasiswa tidak mencetak bukti.