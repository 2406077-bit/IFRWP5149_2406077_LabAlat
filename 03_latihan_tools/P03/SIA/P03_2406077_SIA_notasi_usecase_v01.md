# VALIDASI KRS
| Elemen                | SIA-R04 — Validasi KRS                                                                 |
| :-------------------- | :------------------------------------------------------------------------------------- |
| Tujuan                | Memeriksa apakah pengajuan KRS sudah sesuai dengan ketentuan.                          |
| Aktor utama           | Mahasiswa                                                                              |
| Sumber kebutuhan      | SIA-R04                                                                                |
| Pemicu                | Mahasiswa mengirim pengajuan KRS.                                                      |
| Prasyarat             | Mahasiswa telah mengisi KRS dan mengirim pengajuan.                                    |
| Pascakondisi berhasil | KRS dinyatakan valid dan dapat disimpan dengan status menunggu persetujuan dosen wali. |
| Pascakondisi gagal    | Pengajuan KRS tidak berhasil disimpan dan sistem menampilkan pesan kesalahan.          |
| Include               | Tidak ada.                                                                             |
| Extension point       | Tidak ada.                                                                             |
| Extend                | Tidak ada.                                                                             |

# AJUKAN KRS
| Elemen                | SIA-R03 — Mengajukan KRS                                                       |
| :-------------------- | :----------------------------------------------------------------------------- |
| Tujuan                | Menghasilkan pengajuan KRS.                                                    |
| Aktor utama           | Mahasiswa                                                                      |
| Sumber kebutuhan      | SIA-R03 dan SIA-R04                                                            |
| Pemicu                | Mahasiswa memilih fungsi pengajuan KRS.                                        |
| Prasyarat             | Mahasiswa telah terautentikasi; data mata kuliah dan jadwal tersedia.          |
| Pascakondisi berhasil | Pengajuan KRS berhasil disimpan dengan status menunggu persetujuan dosen wali. |
| Pascakondisi gagal    | Pengajuan KRS tidak berhasil disimpan jika validasi gagal.                     |
| Include               | SIA-UC04 — Validasi KRS                                                        |
| Extension point       | Konfirmasi pengajuan / bukti pengajuan tersedia.                               |
| Extend                | SIA-UC05 — jika [mahasiswa memilih mengunduh bukti].                           |
|                       |                                                                                |
# UNDUH BUKTI PENGAJUAN KRS
| Elemen                | SIA-R05 — Unduh Bukti Pengajuan KRS                                 |
| :-------------------- | :------------------------------------------------------------------ |
| Tujuan                | Memungkinkan mahasiswa mengunduh bukti pengajuan KRS.               |
| Aktor utama           | Mahasiswa                                                           |
| Sumber kebutuhan      | SIA-R05                                                             |
| Pemicu                | Mahasiswa memilih opsi unduh bukti pada konfirmasi pengajuan KRS.   |
| Prasyarat             | Pengajuan KRS berhasil disimpan dan bukti pengajuan tersedia.       |
| Pascakondisi berhasil | Bukti pengajuan KRS berhasil diunduh oleh mahasiswa.                |
| Pascakondisi gagal    | Bukti tidak berhasil diunduh, tetapi pengajuan KRS tetap tersimpan. |
| Include               | Tidak ada.                                                          |
| Extension point       | Tidak ada.                                                          |
| Extend                | SIA-UC03 — Ajukan KRS, jika [mahasiswa memilih mengunduh bukti].    |

# PROSES KEPUTUSAN KRS
| Elemen                | SIA-R06 — Proses Keputusan KRS                                                               |
| :-------------------- | :------------------------------------------------------------------------------------------- |
| Tujuan                | Memproses persetujuan atau penolakan pengajuan KRS mahasiswa.                                |
| Aktor utama           | Dosen Wali                                                                                   |
| Sumber kebutuhan      | SIA-R06                                                                                      |
| Pemicu                | Dosen wali memilih pengajuan KRS mahasiswa yang akan diperiksa.                              |
| Prasyarat             | Dosen wali telah terautentikasi dan pengajuan KRS mahasiswa tersedia.                        |
| Pascakondisi berhasil | Status KRS diperbarui menjadi disetujui atau ditolak, disertai catatan keputusan dosen wali. |
| Pascakondisi gagal    | Keputusan KRS tidak berhasil disimpan dan status pengajuan tidak berubah.                    |
| Include               | Tidak ada.                                                                                   |
| Extension point       | Tidak ada.                                                                                   |
| Extend                | Tidak ada.                                                                                   |

# TABEL HUBUNGAN 
| Sumber         | Hubungan    | Tujuan   |
| :------------- | :---------- | :------- |
| Mahasiswa      | Asosiasi    | SIA-UC01 |
| Mahasiswa      | Asosiasi    | SIA-UC03 |
| Mahasiswa      | Asosiasi    | SIA-UC05 |
| Admin Akademik | Asosiasi    | SIA-UC02 |
| Dosen Wali     | Asosiasi    | SIA-UC06 |
| SIA-UC03       | <<include>> | SIA-UC04 |
| SIA-UC05       | <<extend>>  | SIA-UC03 |