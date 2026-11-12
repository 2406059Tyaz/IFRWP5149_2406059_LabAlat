<!-- Ajukan KRS -->
| Elemen                | SIA                                                        |
|-----------------------|------------------------------------------------------------|
| Tujuan                | Menghasilkan pengajuan KRS yang tersimpan                  |
| Aktor                 | Utama Mahasiswa                                            |
| Sumber                | Kebutuhan SIA-R03 dan SIA-R04                              |
| Pemicu                | Mahasiswa memilih fungsi pengajuan KRS                     |
| Prasyarat             | Mahasiswa telah login; data mata kuliah tersedia           |
| Pascakondisi berhasil | Pengajuan tersimpan dengan status Menunggu persetujuan     |
| Pascakondisi gagal    | Tidak ada pengajuan baru yang berhasil tersimpan           |
| Include               | SIA-UC04 — Validasi KRS                                    |
| Extension point       | Konfirmasi pengajuan ditampilkan                           |
| Extend                | SIA-UC05 jika mahasiswa memilih unduh bukti                |

<!-- Validasi KRS -->
| Elemen                | SIA                                                        |
|-----------------------|------------------------------------------------------------|
| Tujuan                | Memeriksa kelayakan pengajuan KRS                          |
| Aktor                 | Sistem                                                     |
| Sumber                | Kebutuhan SIA-R04                                          |
| Pemicu                | Mahasiswa mengajukan KRS                                   |
| Prasyarat             | Mahasiswa telah memilih mata kuliah                        |
| Pascakondisi berhasil | KRS memenuhi kelengkapan, prasyarat, dan jadwal            |
| Pascakondisi gagal    | Sistem menampilkan kesalahan validasi                      |
| Include               | Tidak ada                                                  |
| Extension point       | Tidak ada                                                  |
| Extend                | Tidak ada                                                  |

<!-- Unduh Bukti Pengajuan KRS -->
| Elemen                | SIA                                                        |
|-----------------------|------------------------------------------------------------|
| Tujuan                | Menyediakan bukti pengajuan KRS                            |
| Aktor                 | Mahasiswa                                                  |
| Sumber                | Kebutuhan SIA-R05                                          |
| Pemicu                | Mahasiswa memilih unduh bukti                              |
| Prasyarat             | Pengajuan KRS berhasil disimpan                            |
| Pascakondisi berhasil | Bukti pengajuan tersedia untuk diunduh                     |
| Pascakondisi gagal    | Pengajuan tetap berhasil meskipun bukti tidak diunduh      |
| Include               | Tidak ada                                                  |
| Extension point       | Bukti pengajuan tersedia                                   |
| Extend                | SIA-UC03 jika mahasiswa memilih unduh bukti                |

<!-- Proses Keputusan KRS -->
| Elemen                | SIA                                                        |
|-----------------------|------------------------------------------------------------|
| Tujuan                | Menentukan persetujuan atau penolakan KRS                  |
| Aktor                 | Utama Dosen wali                                           |
| Sumber                | Kebutuhan SIA-R06                                          |
| Pemicu                | Dosen wali memeriksa pengajuan KRS                         |
| Prasyarat             | Pengajuan KRS berstatus Menunggu persetujuan               |
| Pascakondisi berhasil | Keputusan dan catatan dosen wali tersimpan                 |
| Pascakondisi gagal    | Keputusan belum berhasil disimpan                          |
| Include               | Tidak ada                                                  |
| Extension point       | Tidak ada                                                  |
| Extend                | Tidak ada                                                  |

