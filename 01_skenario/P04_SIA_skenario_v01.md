## 1. Identitas Tugas

- **Mata Kuliah:** Praktikum Analisis dan Desain Berorientasi Objek
- **Pertemuan:** 4
- **Studi Kasus:** Sistem Informasi Akademik (SIA)
- **Topik:** Layanan Hasil Studi, Generalization, dan Collaboration
- **Versi:** v01

## 2. Skenario

Sistem Informasi Akademik (SIA) digunakan untuk mendukung kegiatan akademik mahasiswa, dosen, dan Admin Akademik. Mahasiswa dan dosen merupakan bagian dari Civitas Akademika yang memiliki hak untuk melihat kalender akademik institusi, seperti informasi awal semester, batas pengisian KRS, dan masa ujian.

Setelah masa perkuliahan berakhir, dosen dapat menginput nilai mata kuliah yang diampunya. Penginputan nilai hanya boleh dilakukan oleh dosen yang bertanggung jawab terhadap mata kuliah tersebut. Nilai yang belum dipublikasikan belum dapat dilihat oleh mahasiswa.

Mahasiswa dapat melihat Kartu Hasil Studi (KHS) untuk semester yang nilainya sudah dipublikasikan. KHS menampilkan hasil studi mahasiswa berdasarkan nilai yang telah resmi dipublikasikan.

Selain itu, Admin Akademik bertugas mengelola data mahasiswa, meliputi penambahan data mahasiswa baru, perubahan data mahasiswa, dan penghapusan data mahasiswa. Penghapusan hanya diperbolehkan untuk mahasiswa yang tidak memiliki data akademik aktif.

Model SIA pada pertemuan ini merupakan pengembangan dari diagram kumulatif Pertemuan 2 dan Pertemuan 3. Fungsi jadwal kuliah dan pengajuan KRS tetap dipertahankan, kemudian ditambahkan fungsi layanan hasil studi, pengelolaan data mahasiswa, generalization aktor, generalization use case, serta collaboration yang merealisasikan Input Nilai Mata Kuliah dan Lihat KHS.

## 3. Batasan dan Asumsi

1. Kode kebutuhan pada Pertemuan 4 dimulai dari SIA-R07 agar tidak bertabrakan dengan kebutuhan Pertemuan 2 dan Pertemuan 3.
2. Pengguna telah melakukan autentikasi dan mempunyai hak akses sesuai dengan perannya masing-masing.
3. Kalender akademik merupakan agenda resmi institusi, seperti awal semester, batas pengisian KRS, dan masa ujian. Kalender akademik berbeda dari jadwal kuliah.
4. Penginputan nilai hanya dapat dilakukan oleh dosen pengampu mata kuliah yang bersangkutan.
5. Nilai yang belum dipublikasikan tidak ditampilkan pada KHS mahasiswa.
6. Hapus Data Mahasiswa hanya dapat dilakukan jika mahasiswa tidak mempunyai data akademik aktif.
7. Fungsi pengajuan KRS dari Pertemuan 3 tetap menjadi bagian dari diagram kumulatif dan tidak diubah.
8. Pembayaran dan perancangan basis data tidak termasuk dalam ruang lingkup tugas ini.
9. Generalization aktor digunakan untuk menunjukkan bahwa Mahasiswa dan Dosen merupakan jenis khusus dari Civitas Akademika.
10. Generalization use case digunakan untuk menunjukkan bahwa Tambah Data Mahasiswa, Ubah Data Mahasiswa, dan Hapus Data Mahasiswa merupakan bentuk khusus dari Kelola Data Mahasiswa.
11. Collaboration digunakan untuk menunjukkan realisasi dari use case Input Nilai Mata Kuliah dan Lihat KHS.
12. Nama, ID, dan relasi pada diagram harus konsisten dengan katalog use case dan use case description.

## 4. Ruang Lingkup Pemodelan

Pemodelan pada Pertemuan 4 mencakup fungsi lama dan fungsi baru dalam satu diagram kumulatif.

### Fungsi dari Pertemuan Sebelumnya

- SIA-UC01 Lihat Jadwal Kuliah.
- SIA-UC02 Kelola Jadwal Kuliah.
- SIA-UC03 Ajukan KRS.
- SIA-UC04 Validasi KRS.
- SIA-UC05 Unduh Bukti Pengajuan KRS.
- SIA-UC06 Proses Keputusan KRS.

Fungsi lama beserta relasi yang sudah ditetapkan tetap dipertahankan sesuai model sebelumnya.

### Fungsi Baru Pertemuan 4

- SIA-UC07 Lihat Kalender Akademik.
- SIA-UC08 Input Nilai Mata Kuliah.
- SIA-UC09 Lihat KHS.
- SIA-UC10 Kelola Data Mahasiswa.
- SIA-UC11 Tambah Data Mahasiswa.
- SIA-UC12 Ubah Data Mahasiswa.
- SIA-UC13 Hapus Data Mahasiswa.

### Aktor

Aktor yang digunakan dalam model kumulatif adalah:

- **Civitas Akademika:** aktor umum untuk fungsi melihat kalender akademik.
- **Mahasiswa:** aktor khusus dari Civitas Akademika yang dapat melihat kalender akademik dan KHS serta menjalankan fungsi pengajuan KRS.
- **Dosen:** aktor khusus dari Civitas Akademika yang dapat melihat kalender akademik dan menginput nilai mata kuliah yang diampunya.
- **Admin Akademik:** aktor yang mengelola data mahasiswa.
- **Dosen Wali:** aktor yang tetap dipertahankan dari model Pertemuan 3 sesuai fungsi sebelumnya.

## 5. Aturan Pemodelan

1. Generalization aktor ditunjukkan dengan panah bergaris utuh dan segitiga kosong yang mengarah ke aktor umum, yaitu Civitas Akademika.
2. Asosiasi untuk fungsi melihat kalender akademik digambar satu kali dari Civitas Akademika, sehingga tidak perlu dibuat ulang dari Mahasiswa dan Dosen.
3. Generalization use case ditunjukkan dengan panah bergaris utuh dan segitiga kosong yang mengarah ke use case umum Kelola Data Mahasiswa.
4. Ketiga use case khusus pengelolaan data mahasiswa memiliki perilaku masing-masing sesuai fungsinya.
5. Collaboration digambarkan menggunakan elips bergaris putus-putus dan diberi nama yang sama persis dengan use case yang direalisasikan.
6. Relasi realization digambarkan menggunakan garis putus-putus dengan segitiga kosong yang mengarah ke use case.
7. Collaboration tidak dihubungkan secara langsung dengan aktor.
8. Diagram akhir harus memuat fungsi jadwal kuliah, pengajuan KRS, dan layanan hasil studi tanpa mengubah identitas kebutuhan sebelumnya.

## 6. Hasil Pemeriksaan Konsistensi

### Situasi A: Mahasiswa Melihat Kalender Akademik

**Hasil:** Mahasiswa tetap dapat melihat kalender akademik meskipun tidak memiliki garis asosiasi langsung ke use case Lihat Kalender Akademik. Hal ini karena Mahasiswa merupakan aktor khusus dari Civitas Akademika dan mewarisi fungsi yang terhubung dengan aktor umum tersebut.

### Situasi B: Dosen Bukan Pengampu Menginput Nilai

**Hasil:** Sistem harus menolak penginputan nilai karena dosen tersebut bukan pengampu mata kuliah yang bersangkutan. Nilai tidak boleh tersimpan sebagai hasil penginputan yang berhasil.

### Situasi C: Admin Akademik Menghapus Mahasiswa yang Masih Memiliki Data Akademik Aktif

**Hasil:** Sistem harus menolak penghapusan data mahasiswa karena tidak memenuhi ketentuan penghapusan. Data mahasiswa tetap dipertahankan.

## 7. Kesimpulan

Pada Pertemuan 4, mengembangkan diagram Sistem Informasi Akademik dengan menambahkan fitur untuk melihat KHS, input nilai mata kuliah, dan mengelola data mahasiswa. Saya juga menambahkan generalisasi untuk menunjukkan hubungan antara aktor umum dan aktor khusus serta antara use case umum dan use case khusus. Selain itu, collaboration digunakan untuk menggambarkan realisasi proses input nilai dan melihat KHS. Fitur-fitur dari pertemuan sebelumnya tetap dipertahankan agar diagram menjadi satu model yang lengkap.