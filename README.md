
## Tentang Game

**CLEANSE** adalah prototype game **2D side-scrolling action shooter** bertema *Climate Action*. Pemain berperan sebagai anggota **Cleanse Division**, unit khusus yang bertugas menghadapi organisme berbahaya yang terbentuk akibat pencemaran lingkungan.

Dalam dunia masa depan yang tercemar oleh limbah industri, polusi udara, dan kerusakan hutan, pencemaran telah bermutasi menjadi makhluk hidup yang mengancam manusia dan lingkungan. Pemain harus bergerak melewati area berbahaya, menembak musuh, menggunakan bom, menyelesaikan objektif, dan memulihkan lingkungan.

Game ini mengadaptasi mekanik permainan *run-and-gun* 2D dengan identitas cerita, musuh, dan tema lingkungan milik CLEANSE sendiri.

## Fitur Utama

- **2D Side-Scrolling Action Shooter** — gameplay aksi dari perspektif samping dengan pergerakan kiri, kanan, dan lompatan.
- **Player Movement** — pemain dapat bergerak, melompat, dan berhadapan dengan musuh.
- **Shooting System** — pemain menembakkan proyektil untuk menyerang musuh.
- **Bomb System** — pemain dapat melempar bom untuk memberikan damage area.
- **Enemy System** — rancangan musuh dengan karakteristik serangan yang berbeda.
- **Climate Meter** — indikator progres kondisi lingkungan selama misi.
- **Environmental Restoration** — sistem pemulihan lingkungan sebagai bagian dari tujuan permainan.
- **Level Progression** — rencana misi dari area kota tercemar hingga sarang organisme polusi.
- **Boss Battle** — pertarungan melawan Germ Core sebagai tantangan akhir.
- **HUD dan Menu** — rencana tampilan health, jumlah bom, objective, Climate Meter, pause, game over, dan mission complete.

> **Catatan status:** Daftar di atas merupakan cakupan fitur yang direncanakan untuk CLEANSE. Fitur dianggap selesai setelah diimplementasikan dan diuji di dalam project Unity.

## Kontrol Permainan

| **Aksi** | **Tombol** |
| --- | --- |
| Bergerak ke kiri | A |
| Bergerak ke kanan | D |
| Melompat | W |
| Menembak | Klik kiri mouse |
| Melempar bom | G |
| Pause | Esc |

**Catatan:** Tombol **Space tidak digunakan**. Kontrol di atas merupakan rancangan kontrol prototype dan dapat disesuaikan saat implementasi.

## Cara Menjalankan Project

### Persyaratan

- Unity Hub
- Unity Editor versi yang digunakan untuk membuat project
- Sistem operasi yang mendukung Unity Editor
- Git (opsional, jika project diambil dari repository)

### Langkah Menjalankan

1. Clone atau unduh repository CLEANSE.
2. Buka Unity Hub.
3. Pilih **Add** atau **Add project from disk**.
4. Pilih folder utama project CLEANSE.
5. Buka project menggunakan versi Unity yang sesuai.
6. Tunggu proses import asset dan kompilasi script selesai.
7. Buka scene gameplay yang telah dikonfigurasi sebagai scene utama.
8. Tekan tombol **Play** pada Unity Editor.
9. Gunakan kontrol permainan untuk menguji mekanik yang sudah tersedia.

> **Penting:** Nama scene, lokasi scene, versi Unity, dan konfigurasi Build Settings harus diperbarui sesuai kondisi project yang sebenarnya. Informasi tersebut belum ditetapkan dalam dokumentasi awal ini.

## Gambaran Alur Permainan

1. Pemain memasuki area yang terdampak pencemaran.
2. Pemain bergerak melewati platform dan rintangan.
3. Pemain mendeteksi dan menghadapi organisme polusi.
4. Pemain menggunakan senjata dan bom untuk mengalahkan musuh.
5. Pemain menyelesaikan objektif misi.
6. Pemain memulihkan kondisi lingkungan melalui sistem CLEANSE.
7. Pemain melanjutkan ke area atau misi berikutnya.

Alur ini merupakan rancangan gameplay dan akan disesuaikan dengan fitur yang telah diimplementasikan.

## Rancangan Musuh

| **Musuh** | **Karakteristik** |
| --- | --- |
| **Smogger** | Mewakili polusi udara; menyerang dari jarak jauh dan menghasilkan asap yang mengganggu pandangan. |
| **Toxiler** | Mewakili limbah cair atau beracun; bergerak lambat, memiliki daya tahan tinggi, dan meninggalkan genangan berbahaya. |
| **Burner** | Mewakili panas ekstrem; agresif dan menyerang dari jarak dekat. |
| **Spreader** | Menyebarkan polusi dan dapat menghasilkan unit kecil sebagai bantuan. |
| **Germ Core** | Boss utama yang menggabungkan pola serangan dari ancaman sebelumnya. |

## Rancangan Progres Misi

1. **Prologue** — pengenalan dunia dan tugas Cleanse Division.
2. **Level 1: Infected City** — menghadapi pencemaran di kawasan kota.
3. **Level 2: Toxic River** — menghadapi pencemaran limbah cair.
4. **Level 3: Burning Forest** — menghadapi ancaman panas ekstrem dan kerusakan hutan.
5. **Level 4: The Germ Nest** — memasuki sarang organisme polusi.
6. **Final Mission: The Great Cleanse** — menghadapi ancaman utama dan menyelesaikan misi.

Daftar ini adalah rencana progres permainan; jumlah level dan urutannya dapat berubah selama pengembangan.


## 🛠️ Teknologi yang Digunakan

| **Teknologi** | **Kegunaan** |
| --- | --- |
| Unity 2D | Engine dan lingkungan pengembangan game |
| C# | Bahasa pemrograman gameplay |
| Unity Input System | Pengelolaan input pemain, jika digunakan pada project |
| Unity 2D Physics | Rigidbody2D, Collider2D, dan deteksi tabrakan |
| Unity Animator | Pengaturan animasi karakter dan musuh |
| Unity UI | HUD, menu, dan layar informasi permainan |

## 📌 Cakupan Prototype

Prototype CLEANSE berfokus pada pengalaman **single-player** dalam format 2D side-scrolling action shooter. Pengembangan dilakukan bertahap, dimulai dari mekanik inti—pergerakan, lompatan, menembak, dan interaksi dengan musuh—sebelum dilanjutkan ke sistem bom, level, Climate Meter, pemulihan lingkungan, UI, dan boss.

Fitur yang belum diimplementasikan tidak dianggap sebagai fitur aktif. Status akhir setiap fitur perlu dikonfirmasi melalui pengujian di Unity.

## 📄 Dokumentasi

- https://github.com/Pilgrimmzz/UTSGAME/blob/main/srs.md — kebutuhan fungsional, nonfungsional, kontrol, dan skenario pengujian prototype.

## 👥 Informasi Project

**Nama:** CLEANSE  
**Tagline:** Defend. Cleanse. Protect.  
**Genre:** 2D Side-Scrolling Action Shooter / Run-and-Gun  
**Tema:** Climate Action dan Pemulihan Lingkungan  
**Status:** Prototype dalam pengembangan  
**Platform Target:** PC / Laptop  
**Mode Permainan:** Single-player  
**Engine:** Unity 2D


