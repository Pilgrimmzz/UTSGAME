srs = r'''# SOFTWARE REQUIREMENTS SPECIFICATION (SRS)
# CLEANSE — Defend. Cleanse. Protect.

## 1. Pendahuluan

### 1.1 Tujuan Dokumen

Dokumen Software Requirements Specification (SRS) ini menjelaskan kebutuhan perangkat lunak untuk prototype game **CLEANSE**. Dokumen digunakan sebagai acuan perancangan, implementasi, dan pengujian fitur game di Unity 2D.

### 1.2 Ruang Lingkup

CLEANSE merupakan game 2D side-scrolling action shooter bertema *Climate Action*. Pemain berperan sebagai anggota Cleanse Division yang bertugas menghadapi organisme yang terbentuk akibat pencemaran dan membantu memulihkan lingkungan.

Prototype direncanakan memiliki pergerakan karakter, lompatan, sistem menembak, bom, musuh, level, Climate Meter, pemulihan lingkungan, antarmuka, serta pertarungan boss. Implementasi dilakukan bertahap; kebutuhan yang tercantum di dokumen ini tidak berarti seluruh fitur sudah tersedia.

### 1.3 Definisi dan Istilah

| Istilah | Definisi |
| --- | --- |
| **CLEANSE** | Nama game yang dikembangkan. |
| **Cleanse Division** | Unit khusus tempat karakter pemain bertugas. |
| **Run-and-Gun** | Genre aksi yang menggabungkan pergerakan karakter dan penggunaan senjata secara real-time. |
| **HUD** | Heads-Up Display, antarmuka yang menampilkan informasi permainan saat gameplay berlangsung. |
| **Climate Meter** | Indikator kondisi atau progres pemulihan lingkungan dalam misi. |
| **Enemy** | Musuh yang menghalangi pemain menyelesaikan misi. |
| **Boss** | Musuh utama dengan tantangan dan pola serangan khusus. |
| **Prototype** | Versi awal game untuk memvalidasi mekanik dan konsep inti. |

### 1.4 Platform Pengembangan

- **Game engine:** Unity dengan template 2D.
- **Bahasa pemrograman:** C#.
- **Platform target:** PC atau laptop.
- **Mode:** Single-player.
- **Input:** Keyboard dan mouse.

Versi Unity dan konfigurasi input final mengikuti project yang digunakan saat implementasi.

## 2. Deskripsi Umum

### 2.1 Perspektif Produk

CLEANSE dikembangkan sebagai game mandiri untuk PC/laptop. Game menggunakan tampilan 2D dari samping, dengan area permainan yang dapat bergulir mengikuti pergerakan pemain.

### 2.2 Fungsi Produk

Fungsi utama yang direncanakan meliputi:

1. Mengendalikan karakter pemain.
2. Membuat pemain dapat melompat dan melewati rintangan.
3. Menyerang musuh menggunakan proyektil.
4. Melempar bom untuk memberikan damage area.
5. Mengelola kondisi pemain dan musuh.
6. Menampilkan informasi gameplay melalui HUD.
7. Menyediakan tujuan misi dan progres level.
8. Menampilkan progres kondisi lingkungan melalui Climate Meter.
9. Menggambarkan pemulihan lingkungan setelah objektif tertentu diselesaikan.
10. Menyediakan kondisi penyelesaian misi dan kekalahan pemain.

### 2.3 Pengguna

Target pengguna adalah pemain yang menyukai game aksi, shooter, sci-fi, dan tema lingkungan. Game dirancang untuk dimainkan secara single-player menggunakan keyboard dan mouse.

### 2.4 Lingkungan Operasi

- Komputer atau laptop yang dapat menjalankan Unity build untuk PC.
- Sistem operasi yang didukung oleh build Unity yang dibuat.
- Keyboard dan mouse.
- Resolusi layar mengikuti konfigurasi build; resolusi minimum belum ditentukan.

### 2.5 Batasan dan Asumsi

- Pengembangan menggunakan Unity 2D dan C#.
- Mekanik utama harus dapat diuji sebelum penambahan polish visual.
- Kontrol lompat menggunakan **W**, bukan Space.
- Fitur lanjutan dapat disesuaikan berdasarkan waktu dan hasil pengembangan.
- Fitur yang belum dibuat tidak boleh dianggap sudah berfungsi.
- Detail performa minimum, resolusi target, dan versi Unity final ditentukan saat konfigurasi project.

## 3. Kebutuhan Antarmuka Eksternal

### 3.1 Antarmuka Pengguna

Antarmuka yang direncanakan:

- **HUD gameplay:** health pemain, jumlah bom, objective, dan Climate Meter.
- **Pause Menu:** opsi melanjutkan permainan dan kembali ke menu atau keluar sesuai implementasi.
- **Game Over:** informasi kekalahan dan opsi mengulang permainan.
- **Mission Complete:** informasi penyelesaian misi.
- **Main Menu:** akses untuk memulai permainan dan keluar dari game; opsi lain dapat ditambahkan sesuai kebutuhan.

### 3.2 Antarmuka Perangkat Keras

Pemain menggunakan keyboard untuk pergerakan, lompatan, bom, dan pause; mouse digunakan untuk menembak.

### 3.3 Antarmuka Perangkat Lunak

- Unity Engine untuk menjalankan game.
- Sistem fisika 2D Unity untuk tabrakan dan deteksi lantai.
- Animator Unity untuk animasi, apabila animasi diterapkan.
- Unity UI untuk HUD dan menu.
- Unity Input System apabila paket tersebut dikonfigurasi sebagai sistem input project.

## 4. Kebutuhan Fungsional

Kebutuhan berikut merupakan target implementasi prototype.

### KF-01 — Pergerakan Pemain

**Deskripsi:** Sistem harus memungkinkan pemain bergerak ke kiri dan kanan.

**Input:** A untuk kiri, D untuk kanan.  
**Hasil yang diharapkan:** Karakter bergerak sesuai input dan tidak terus bergerak ketika input dilepas, kecuali terdapat perilaku khusus yang dirancang.

### KF-02 — Arah Hadap Pemain

**Deskripsi:** Karakter harus menghadap ke arah gerakan atau arah bidik sesuai rancangan kontrol.

**Hasil yang diharapkan:** Tampilan sprite tidak terbalik secara tidak semestinya ketika arah berubah.

### KF-03 — Lompatan

**Deskripsi:** Pemain dapat melompat menggunakan W ketika berada di permukaan yang dianggap sebagai lantai.

**Hasil yang diharapkan:** Pemain tidak dapat melakukan lompatan berulang di udara sebelum mendarat kembali.

### KF-04 — Sistem Menembak

**Deskripsi:** Pemain dapat menembakkan proyektil menggunakan klik kiri mouse.

**Hasil yang diharapkan:** Proyektil bergerak ke arah tembakan dan dapat mengenai target sesuai konfigurasi collision.

### KF-05 — Damage Musuh

**Deskripsi:** Musuh menerima damage ketika terkena serangan yang valid.

**Hasil yang diharapkan:** Nilai health musuh berkurang; ketika health habis, musuh memasuki kondisi mati atau menghilang sesuai implementasi.

### KF-06 — Sistem Bom

**Deskripsi:** Pemain dapat melempar bom menggunakan tombol G.

**Hasil yang diharapkan:** Bom bergerak sesuai mekanik yang ditentukan dan menghasilkan ledakan dengan damage area. Jumlah bom dapat dibatasi jika sistem persediaan bom diterapkan.

### KF-07 — Kondisi Pemain

**Deskripsi:** Sistem harus mengelola health dan kondisi kalah pemain.

**Hasil yang diharapkan:** Pemain menerima damage dari bahaya yang valid. Ketika health habis, gameplay masuk ke kondisi Game Over atau kondisi kalah yang ditentukan.

### KF-08 — Musuh

**Deskripsi:** Game menyediakan musuh dengan perilaku dan ancaman berbeda sesuai rancangan.

**Musuh yang direncanakan:**
- Smogger: serangan jarak jauh dan efek asap.
- Toxiler: daya tahan tinggi dan genangan berbahaya.
- Burner: serangan agresif jarak dekat.
- Spreader: menyebarkan polusi atau menghasilkan unit kecil.
- Germ Core: boss dengan kombinasi pola serangan.

### KF-09 — Kamera dan Level

**Deskripsi:** Kamera mengikuti pemain di area side-scrolling.

**Hasil yang diharapkan:** Pemain dan area gameplay tetap terlihat saat karakter bergerak; batas kamera mengikuti batas level yang dikonfigurasi.

### KF-10 — Objective Misi

**Deskripsi:** Game menyediakan objective yang perlu diselesaikan untuk menuntaskan area.

**Hasil yang diharapkan:** Pemain dapat mengetahui tujuan misi dan menerima status selesai setelah syarat yang ditentukan terpenuhi.

### KF-11 — Climate Meter

**Deskripsi:** Game menampilkan indikator progres kondisi lingkungan.

**Hasil yang diharapkan:** Nilai atau tampilan meter berubah berdasarkan aksi atau objective pemulihan lingkungan yang ditentukan.

### KF-12 — Environmental Restoration

**Deskripsi:** Game menggambarkan perubahan lingkungan setelah sumber polusi atau objective tertentu ditangani.

**Hasil yang diharapkan:** Area dapat menunjukkan perbedaan kondisi tercemar dan kondisi yang telah dipulihkan sesuai aset dan implementasi.

### KF-13 — Pause

**Deskripsi:** Pemain dapat menjeda permainan menggunakan Esc.

**Hasil yang diharapkan:** Gameplay berhenti sementara dan menu pause ditampilkan. Pemain dapat melanjutkan permainan melalui opsi yang tersedia.

### KF-14 — Game Over dan Mission Complete

**Deskripsi:** Game harus membedakan kondisi kalah dan kondisi misi selesai.

**Hasil yang diharapkan:** Layar atau status yang sesuai muncul ketika health pemain habis atau objective misi selesai.

### KF-15 — Animasi dan Feedback

**Deskripsi:** Game menampilkan feedback visual untuk aksi penting sesuai aset yang tersedia.

**Contoh:** Animasi idle, run, jump, shoot, throw, hit, death, serta efek proyektil dan ledakan. Ketersediaan setiap animasi bergantung pada aset dan tahap implementasi.

## 5. Kebutuhan Nonfungsional

### KNF-01 — Respons Kontrol

Input pemain harus diproses secara responsif sehingga pergerakan, lompatan, dan serangan terasa konsisten saat gameplay berlangsung.

### KNF-02 — Stabilitas

Game tidak boleh menghasilkan error yang menghentikan gameplay pada alur normal yang telah diuji.

### KNF-03 — Konsistensi Fisika

Pergerakan, lompatan, tabrakan, dan deteksi lantai harus berjalan konsisten berdasarkan konfigurasi fisika 2D.

### KNF-04 — Keterbacaan UI

Informasi penting seperti health, jumlah bom, objective, dan Climate Meter harus dapat dibedakan dari latar permainan.

### KNF-05 — Kemudahan Pemeliharaan

Script, prefab, scene, animasi, dan aset disusun dalam folder yang jelas serta menggunakan penamaan yang konsisten.

### KNF-06 — Kompatibilitas

Build harus dapat dijalankan pada lingkungan PC/laptop yang didukung versi Unity dan konfigurasi build yang digunakan. Spesifikasi minimum belum ditetapkan.

### KNF-07 — Performa

Gameplay harus berjalan cukup lancar pada perangkat target. Target frame rate dan spesifikasi minimum akan ditentukan dan diuji selama pengembangan.

## 6. Aturan Kontrol

| Aksi | Input |
| --- | --- |
| Bergerak ke kiri | A |
| Bergerak ke kanan | D |
| Melompat | W |
| Menembak | Klik kiri mouse |
| Melempar bom | G |
| Pause | Esc |

**Ketentuan:** Space tidak digunakan sebagai tombol lompat.

## 7. Rancangan Level

Urutan level yang direncanakan:

1. **Prologue** — pengenalan dunia dan misi Cleanse Division.
2. **Infected City** — area perkotaan yang tercemar.
3. **Toxic River** — area dengan ancaman limbah cair.
4. **Burning Forest** — area yang terdampak panas ekstrem dan kerusakan hutan.
5. **The Germ Nest** — area sarang organisme polusi.
6. **The Great Cleanse** — misi akhir untuk menghadapi Germ Core.

Level dapat dikembangkan secara bertahap. Untuk prototype awal, satu area sederhana cukup digunakan untuk memvalidasi mekanik inti sebelum semua level dibuat.

## 8. Skenario Pengujian

| ID | Skenario | Langkah Pengujian | Hasil yang Diharapkan |
| --- | --- | --- | --- |
| UJ-01 | Gerak ke kiri | Tekan A | Pemain bergerak ke kiri. |
| UJ-02 | Gerak ke kanan | Tekan D | Pemain bergerak ke kanan. |
| UJ-03 | Berhenti bergerak | Lepaskan A atau D | Pemain berhenti sesuai konfigurasi gerak. |
| UJ-04 | Lompat dari lantai | Tekan W saat menyentuh lantai | Pemain melompat. |
| UJ-05 | Mencegah lompatan udara | Tekan W berulang ketika masih di udara | Pemain tidak melakukan lompatan baru sebelum mendarat. |
| UJ-06 | Menembak | Klik kiri mouse ketika target tersedia | Proyektil ditembakkan ke arah yang ditentukan. |
| UJ-07 | Musuh terkena peluru | Tembakkan peluru hingga mengenai musuh | Health musuh berkurang. |
| UJ-08 | Musuh kalah | Berikan damage sampai health musuh habis | Musuh masuk kondisi mati sesuai rancangan. |
| UJ-09 | Melempar bom | Tekan G saat bom tersedia | Bom dilempar sesuai mekanik. |
| UJ-10 | Damage ledakan | Ledakkan bom di dekat musuh | Target dalam area ledakan menerima damage sesuai radius. |
| UJ-11 | Pemain menerima damage | Sentuhkan pemain dengan serangan atau bahaya musuh | Health pemain berkurang. |
| UJ-12 | Game Over | Kurangi health pemain hingga habis | Kondisi Game Over ditampilkan. |
| UJ-13 | Kamera mengikuti | Gerakkan pemain melintasi level | Kamera mengikuti pemain tanpa melewati batas yang ditentukan. |
| UJ-14 | Climate Meter | Selesaikan aksi/objective pemulihan yang ditentukan | Indikator Climate Meter berubah sesuai aturan. |
| UJ-15 | Pause | Tekan Esc saat gameplay | Permainan berhenti sementara dan menu pause muncul. |
| UJ-16 | Melanjutkan permainan | Pilih opsi Resume | Gameplay berlanjut. |
| UJ-17 | Misi selesai | Penuhi seluruh syarat objective | Status atau layar Mission Complete muncul. |

### 8.1 Format Catatan Hasil Pengujian

Isi kolom hasil aktual setelah fitur diimplementasikan dan diuji.

| ID Uji | Hasil Aktual | Status (Berhasil/Gagal) | Catatan |
| --- | --- | --- | --- |
| UJ-01 | Belum diuji | Belum diuji | Diisi setelah pengujian. |
| UJ-02 | Belum diuji | Belum diuji | Diisi setelah pengujian. |
| UJ-03 | Belum diuji | Belum diuji | Diisi setelah pengujian. |
| UJ-04 | Belum diuji | Belum diuji | Diisi setelah pengujian. |
| UJ-05 | Belum diuji | Belum diuji | Diisi setelah pengujian. |
| UJ-06 | Belum diuji | Belum diuji | Diisi setelah pengujian. |
| UJ-07 | Belum diuji | Belum diuji | Diisi setelah pengujian. |
| UJ-08 | Belum diuji | Belum diuji | Diisi setelah pengujian. |
| UJ-09 | Belum diuji | Belum diuji | Diisi setelah pengujian. |
| UJ-10 | Belum diuji | Belum diuji | Diisi setelah pengujian. |
| UJ-11 | Belum diuji | Belum diuji | Diisi setelah pengujian. |
| UJ-12 | Belum diuji | Belum diuji | Diisi setelah pengujian. |
| UJ-13 | Belum diuji | Belum diuji | Diisi setelah pengujian. |
| UJ-14 | Belum diuji | Belum diuji | Diisi setelah pengujian. |
| UJ-15 | Belum diuji | Belum diuji | Diisi setelah pengujian. |
| UJ-16 | Belum diuji | Belum diuji | Diisi setelah pengujian. |
| UJ-17 | Belum diuji | Belum diuji | Diisi setelah pengujian. |

## 9. Prioritas Pengembangan

Agar prototype dapat diuji sejak awal, implementasi disarankan mengikuti urutan berikut:

1. Membuat project Unity 2D dan scene gameplay.
2. Membuat pergerakan pemain, deteksi lantai, dan lompatan.
3. Membuat kamera side-scrolling.
4. Membuat sistem menembak dan proyektil.
5. Membuat satu musuh dasar dan sistem damage.
6. Membuat sistem bom.
7. Membuat satu level sederhana dan objective.
8. Menambahkan health UI, jumlah bom, dan pause.
9. Menambahkan Climate Meter dan pemulihan lingkungan.
10. Menambahkan variasi musuh, boss, animasi, audio, dan polish.
11. Menjalankan skenario pengujian dan membuat build.

Urutan ini merupakan rekomendasi pengembangan; fitur lanjutan dapat disesuaikan dengan ruang lingkup dan waktu pengerjaan.

## 10. Kriteria Penerimaan Prototype

Prototype awal dapat dianggap memenuhi tujuan minimum apabila:

- Pemain dapat bergerak ke kiri dan kanan.
- Pemain dapat melompat hanya ketika berada di lantai.
- Pemain dapat menembak dan proyektil berinteraksi dengan target.
- Setidaknya satu musuh dapat menerima damage dan dikalahkan.
- Pemain dan musuh berinteraksi dengan collision secara benar.
- Kamera dapat mengikuti pemain di area uji.
- Kontrol menggunakan A, D, W, klik kiri mouse, G, dan Esc sesuai fitur yang telah diterapkan.
- Hasil pengujian dicatat dan masalah yang ditemukan didokumentasikan.

Fitur Climate Meter, pemulihan lingkungan, seluruh variasi musuh, boss, dan semua level merupakan sasaran pengembangan lanjutan apabila belum termasuk dalam prototype awal.

## 11. Penutup

Dokumen SRS ini menjadi acuan kebutuhan untuk pengembangan prototype CLEANSE. Dokumen dapat diperbarui ketika desain, kontrol, batasan teknis, atau hasil implementasi berubah. Setiap fitur perlu diverifikasi melalui pengujian sebelum dinyatakan selesai.
'''

out = Path("/mnt/data")
(out / "README.md").write_text(readme, encoding="utf-8")
(out / "SRS.md").write_text(srs, encoding="utf-8")
print("Created:", (out / "README.md"), (out / "SRS.md"))
print("README chars:", len(readme), "SRS chars:", len(srs))
