# DESKRIPSI SKENARIO

Mahasiswa mengajukan KRS dengan memilih mata kuliah. Setiap pengajuan menjalankan validasi KRS yang memeriksa kelengkapan, prasyarat mata kuliah, dan benturan jadwal. Jika validasi berhasil, sistem menyimpan pengajuan dengan status menunggu persetujuan dosen wali. Pada konfirmasi penyimpanan, mahasiswa dapat memilih untuk mengunduh bukti pengajuan. Dosen wali menyetujui atau menolak KRS dan memberikan catatan keputusan.

# TABEL KEBUTUHAN

| ID | Kebutuhan Tugas |
|---|---|
| SIA-R01 | Mahasiswa dapat melihat jadwal kuliah. |
| SIA-R02 | Admin akademik dapat mengelola jadwal kuliah. |
| SIA-R03 | Mahasiswa dapat mengajukan KRS. |
| SIA-R04 | Sistem memvalidasi KRS sebagai bagian dari pengajuan. |
| SIA-R05 | Mahasiswa dapat mengunduh bukti jika memilihnya pada konfirmasi pengajuan. |
| SIA-R06 | Dosen wali dapat memproses persetujuan atau penolakan KRS. |

# BATAS DAN ASUMSI

- Pengguna telah terautentikasi.
- Data mata kuliah, prasyarat, dan jadwal tersedia.
- Validasi gagal menyebabkan pengajuan belum berhasil tersimpan.
- Mengunduh bukti bukan syarat keberhasilan pengajuan.
- KRS yang tersimpan belum berarti sudah disetujui.
- Pembayaran, pengisian nilai, dan implementasi basis data berada di luar tugas.

# TABEL IDENTIFIKASI AKTOR

| No. | Nama Aktor | Deskripsi |
|---|---|---|
| 1 | Mahasiswa | Pengguna yang dapat melihat jadwal kuliah, mengajukan KRS, dan mengunduh bukti pengajuan KRS. |
| 2 | Dosen Wali | Pengguna yang bertugas memeriksa pengajuan KRS, memberikan persetujuan atau penolakan, serta menambahkan catatan keputusan. |
| 3 | Admin Akademik | Pengguna yang bertugas mengelola jadwal kuliah, seperti menambah, mengubah, dan menghapus data jadwal. |

# TABEL KATALOG USE CASE

| No. | ID Use Case | Nama Use Case | Aktor | Deskripsi |
|---|---|---|---|---|
| 1 | SIA-UC01 | Lihat Jadwal Kuliah | Mahasiswa | Mahasiswa melihat informasi jadwal kuliah yang tersedia. |
| 2 | SIA-UC02 | Kelola Jadwal Kuliah | Admin Akademik | Admin akademik menambah, mengubah, dan menghapus data jadwal kuliah. |
| 3 | SIA-UC03 | Ajukan KRS | Mahasiswa | Mahasiswa memilih mata kuliah dan mengajukan KRS untuk diperiksa oleh sistem. |
| 4 | SIA-UC04 | Validasi KRS | Sistem | Sistem memeriksa kelengkapan KRS, prasyarat mata kuliah, dan benturan jadwal. |
| 5 | SIA-UC05 | Unduh Bukti Pengajuan KRS | Mahasiswa | Mahasiswa mengunduh bukti pengajuan KRS jika memilih opsi unduh setelah pengajuan berhasil. |
| 6 | SIA-UC06 | Proses Keputusan KRS | Dosen Wali | Dosen wali memeriksa pengajuan KRS, memberikan persetujuan atau penolakan, dan menambahkan catatan keputusan. |

# RELASI INCLUDE

**SIA-UC03 Ajukan KRS** `<<include>>` **SIA-UC04 Validasi KRS**

Relasi ini digunakan karena setiap pengajuan KRS wajib melalui proses validasi. Validasi meliputi pemeriksaan kelengkapan data, prasyarat mata kuliah, dan benturan jadwal.

# RELASI EXTEND