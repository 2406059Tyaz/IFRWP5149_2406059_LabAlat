<!-- Deskripsi Skenario -->
Mahasiswa mengajukan KRS dengan memilih mata kuliah. Setiap
pengajuan menjalankan validasi KRS yang memeriksa kelengkapan,
prasyarat mata kuliah, dan benturan jadwal. Jika validasi berhasil,
sistem menyimpan pengajuan berstatus menunggu persetujuan dosen
wali. Pada konfirmasi penyimpanan, mahasiswa dapat memilih
mengunduh bukti pengajuan. Dosen wali menyetujui atau menolak KRS
dan memberikan catatan keputusan.

<!-- Tabel kebutuhan -->
|  ID   |                             Kebutuhan_tugas                                |
|-------|----------------------------------------------------------------------------|
|SIA-R01|  Mahasiswa dapat melihat jadwal kuliah                                     |
|SIA-R02|  Admin akademik dapat mengelola jadwal kuliah                              |
|SIA-R03|  Mahasiswa dapat mengajukan KRS                                            |
|SIA-R04|  Sistem memvalidasi KRS sebagai bagian pengajuan                           |
|SIA-R05|  Mahasiswa dapat mengunduh bukti jika memilihnya pada konfirmasi pengajuan |
|SIA-R06|  Dosen wali dapat memproses persetujuan atau penolakan KRS                 |


<!-- batas sistem dan aturan -->
• Pengguna telah terautentikasi.
• Data mata kuliah, prasyarat, dan jadwal tersedia.
• Validasi gagal menyebabkan pengajuan belum berhasil tersimpan.
• Unduh bukti tidak menjadi syarat keberhasilan pengajuan.
• KRS tersimpan belum berarti disetujui.
• Pembayaran, pengisian nilai, dan implementasi basis data berada di luar
tugas

<!-- tabel identifikasi aktor -->
|  Aktor  |                                       Tujuan_terhadap_sistem                                           |
|---------|--------------------------------------------------------------------------------------------------------|
|Mahasiswa|   Mengajukan KRS dengan memilih mata kuliah dan mengunduh bukti pengajuan jika memilihnya.             |
|  Dosen  |   Wali memproses pengajuan KRS dengan memberikan persetujuan atau penolakan beserta catatan keputusan. |

<!-- Tabel katalog use case -->

| ID       | Nama Use Case             | Peran dalam Model                            |
| -------- | ------------------------- | -------------------------------------------- |
| SIA-UC01 | Lihat Jadwal Kuliah       | Fungsi utama mahasiswa                       |
| SIA-UC02 | Kelola Jadwal Kuliah      | Fungsi utama admin akademik                  |
| SIA-UC03 | Ajukan KRS                | Fungsi utama mahasiswa                       |
| SIA-UC04 | Validasi KRS              | Perilaku yang disertakan dalam pengajuan KRS |
| SIA-UC05 | Unduh Bukti Pengajuan KRS | Tambahan bersyarat pada pengajuan KRS        |
| SIA-UC06 | Proses Keputusan KRS      | Fungsi utama dosen wali                      |
Keterangan relasi:
1. SIA-UC03 include SIA-UC04, karena setiap pengajuan KRS harus divalidasi.
2. SIA-UC05 extend SIA-UC03, karena mahasiswa dapat memilih untuk mengunduh bukti pengajuan.
3. SIA-UC06 digunakan dosen wali untuk menyetujui atau menolak KRS dan memberikan catatan keputusan.

<!-- relasi include -->
Ajukan KRS terhubung ke Validasi KRS. Setiap pengajuan KRS harus melalui proses validasi data, prasyarat mata kuliah, dan benturan jadwal.

<!-- relasi extend -->
Unduh Bukti Pengajuan KRS terhubung ke Ajukan KRS. Mahasiswa dapat memilih untuk mengunduh bukti pengajuan setelah KRS berhasil diajukan.