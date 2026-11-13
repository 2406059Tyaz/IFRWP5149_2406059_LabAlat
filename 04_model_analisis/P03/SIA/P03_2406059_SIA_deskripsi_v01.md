## a. SIA-UC08 - Input Nilai Mata Kuliah

| Elemen                 |                       Isi                                                                                                                  |
|------------------------|--------------------------------------------------------------------------------------------------------------------------------------------|
| ID dan nama            | SIA-UC08 - Input Nilai Mata Kuliah                                                                                                         |
| Sumber kebutuhan       | SIA-R08, SIA-R12                                                                                                                           |
| Tujuan                 | Nilai mata kuliah yang diampu dosen tersimpan pada data akademik mahasiswa                                                                 |
| Aktor utama            | Dosen                                                                                                                                      |
| Aktor pendukung        | -                                                                                                                                          |   
| Pemicu                 | Dosen memilih fungsi input nilai setelah masa perkuliahan berakhir                                                                         |
| Prasyarat              | Dosen telah terautentikasi dan memiliki hak akses; dosen adalah dosen pengampu mata kuliah yang dipilih                                    |
| Generalization         | Tidak ada. Aktor Dosen adalah bentuk khusus dari Civitas Akademika, tetapi asosiasi ke use case ini milik Dosen sendiri dan tidak diwarisi |
| Collaboration          | SIA-CO01: Input Nilai Mata Kuliah                                                                                                          |
| Pascakondisi berhasil  | Nilai tersimpan pada data mata kuliah dan mahasiswa dengan status belum dipublikasikan                                                     |
| Pascakondisi gagal     | Tidak ada nilai baru yang tersimpan; data nilai tidak berubah                                                                              | 
| Aturan bisnis/asumsi   | Hanya dosen pengampu yang dapat menginput nilai. Nilai yang diinput belum terpublikasi sebelum dinyatakan resmi (proses publikasi tidak dimodelkan). Rentang nilai yang sah tidak ditetapkan angkanya oleh tugas ini |

**Alur utama**

||Langkah|       Tindakan_dosen       |  Respons  |                                  sistem                                    |
||-------|----------------------------|-----------|----------------------------------------------------------------------------|
||  ---  |            ---             |    ---    |                                                                            |
||   1   | Memilih_fungsi_input_nilai |Menampilkan|               daftar mata kuliah yang diampu dosen tersebut                |
||   2   |    Memilih_mata_kuliah     |Menampilkan|                 daftar mahasiswa peserta dan isian nilai                   |
||   3   |Mengisi_nilai_tiap_mahasiswa| Menampung |                                   isian                                    |
||   4   |       Mengirim_nilai       | Memeriksa |bahwa dosen adalah pengampu dan setiap nilai berada dalam rentang yang sah  |
||   5   |             -              | Menyimpan |                 nilai dengan status belum dipublikasikan                   |
||   6   |     Melihat_konfirmasi     |Menampilkan|                      ringkasan nilai yang tersimpan                        |


**Alur alternatif / pengecualian**
- **A1. Nilai di luar rentang yang sah (langkah 4):** sistem menolak nilai tersebut, menampilkan mahasiswa dan nilai yang bermasalah, dan tidak menyimpan nilai. Pascakondisi gagal berlaku. Dosen dapat memperbaiki isian lalu kembali ke langkah 3.
- **A2. Dosen bukan pengampu mata kuliah (langkah 2 atau 4):** sistem menolak input, menampilkan pesan bahwa mata kuliah bukan milik dosen tersebut, dan tidak ada nilai yang tersimpan. Pascakondisi gagal berlaku.
- **A3. Penyimpanan gagal (langkah 5):** sistem menampilkan pesan gagal dan nilai tidak tersimpan. Pascakondisi gagal berlaku (asumsi, tidak ada di skenario).

---

## b. SIA-UC09 - Lihat KHS (deskripsi ringkas)

| Elemen                  | Isi                                                                                                             |
|-------------------------|-----------------------------------------------------------------------------------------------------------------|
| ID dan nama             | SIA-UC09-Lihat KHS                                                                                              |
| Sumber kebutuhan        | SIA-R09, SIA-R12                                                                                                |
| Tujuan                  | Mahasiswa melihat KHS untuk semester yang nilainya sudah dipublikasikan                                         |
| Aktor utama             | Mahasiswa                                                                                                       |
| Aktor pendukung         | -                                                                                                               |
| Pemicu                  | Mahasiswa memilih fungsi lihat KHS dan menentukan semester                                                      |
| Prasyarat               | Mahasiswa telah terautentikasi; mahasiswa memiliki data akademik pada semester yang dipilih                     |
| Generalization          | Tidak ada. Asosiasi Mahasiswa ke use case ini milik Mahasiswa sendiri                                           |
| Collaboration           | SIA-CO02: Lihat KHS                                                                                             |
| Pascakondisi berhasil   | KHS semester terpilih ditampilkan, hanya memuat nilai yang sudah dipublikasikan                                 |
| Pascakondisi gagal      | KHS tidak ditampilkan; data nilai tidak berubah                                                                 |
| Aturan bisnis/asumsi    | Hanya nilai yang sudah dipublikasikan yang ditampilkan. Nilai berstatus belum dipublikasikan tidak ditampilkan  |

**Alur utama**

| Langkah | Tindakan_mahasiswa       | Respons_sistem                                                               |
|---------|--------------------------|------------------------------------------------------------------------------|
| 1       | Memilih_fungsi_lihat_KHS | Menampilkan_daftar_semester                                                  |
| 2       | Memilih semester         | Mengambil_nilai_semester_tersebut, menyaring hanya yang sudah dipublikasikan |
| 3       | -                        | Menampilkan_KHS_berisi_mata_kuliah_dan_nilai_yang_dipublikasikan             |

**Alur alternatif / pengecualian**
- **A1. Belum ada nilai yang dipublikasikan pada semester itu (langkah 2):** sistem menampilkan pesan bahwa nilai belum tersedia dan tidak menampilkan KHS. Pascakondisi gagal berlaku.

---

## c. SIA-UC13 - Hapus Data Mahasiswa (ringkas, untuk Situasi C)

| Elemen | Isi |
|---|---|
| ID dan nama | SIA-UC13 - Hapus Data Mahasiswa |
| Sumber kebutuhan | SIA-R11 |
| Tujuan | Data mahasiswa yang tidak lagi diperlukan terhapus |
| Aktor utama | Admin Akademik |
| Pemicu | Admin Akademik memilih hapus pada data mahasiswa |
| Prasyarat | Admin Akademik telah terautentikasi; mahasiswa terpilih tidak memiliki data akademik aktif |
| Generalization | Bentuk khusus dari SIA-UC10 Kelola Data Mahasiswa |
| Collaboration | - |
| Pascakondisi berhasil | Data mahasiswa terhapus |
| Pascakondisi gagal | Data mahasiswa tidak berubah |

**Alur utama:** Admin memilih mahasiswa, memilih hapus; sistem memeriksa data akademik aktif (tidak ada); sistem menghapus data dan menampilkan konfirmasi.
**Alur alternatif A1:** mahasiswa masih memiliki data akademik aktif, sistem menolak penghapusan, menampilkan alasan, dan data tetap ada.
