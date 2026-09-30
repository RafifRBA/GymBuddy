# Proposal Kerangka Kerja Agile

**Campus Fitness & Gym Buddy Matcher**

*Draft — Tugas 1: Proposal Kerangka Kerja Agile, Backlog & Rencana Iterasi*

**Kerangka Kerja Agile Terpilih: **Kanban

## Pendahuluan

Campus Fitness & Gym Buddy Matcher adalah aplikasi berbasis kampus yang membantu mahasiswa menemukan rekan berolahraga (gym buddy) yang cocok berdasarkan kesamaan jadwal, tujuan kebugaran, preferensi jenis olahraga, tingkat pengalaman, dan jam gym yang diinginkan. Kebutuhan fungsional dan non-fungsional sistem ini sudah dirumuskan sebelumnya pada Project 1, dan menjadi dasar penyusunan backlog pada dokumen ini.

Dokumen ini disusun untuk memenuhi Tugas 1: Agile Framework Proposal. Tujuannya adalah menetapkan kerangka kerja agile yang akan dipakai tim untuk mengembangkan sistem secara bertahap, sekaligus mendefinisikan alasan pemilihan model, peran dan tanggung jawab tiap anggota, mekanisme proses kerja, backlog awal beserta acceptance criteria, pengaturan board visual, dan rencana kerja untuk siklus pengembangan pertama.

## 1. Pemilihan Model & Justifikasi

Tim memilih Kanban dibandingkan Scrum atau Scrumban dengan pertimbangan berikut:

- **Ukuran tim: **Tim hanya berisi 5 orang dengan satu peran spesialis masing-masing (SDM/SRM, Frontend, Backend, UI/UX, QA). Overhead ritual Scrum penuh (Sprint Planning, Sprint Backlog terpisah, dedicated Product Owner & Scrum Master) tidak sebanding dengan ukuran tim sekecil ini — Kanban cukup dengan satu fasilitator proses.

- **Cakupan proyek: **Functional Requirement sudah cukup matang dari Project 1 (12 FR di 3 modul), namun detail teknis dan prioritas masih bisa berubah seiring implementasi. Alur kerja kontinu Kanban memungkinkan re-prioritisasi backlog kapan saja tanpa menunggu batas Sprint, sehingga lebih adaptif untuk proyek akademik dengan requirement yang terus disempurnakan.

- **Dinamika alur kerja: **Modul saling bergantung secara longgar (Matching Engine bergantung pada Manajemen Profil selesai lebih dulu). Model pull-based dengan WIP limit lebih cocok mengatur ketergantungan ini dibanding commitment Sprint yang kaku, dan lebih realistis untuk jadwal kuliah anggota tim yang tidak seragam — anggota menarik kartu baru saat benar-benar punya kapasitas.

## 2. Peran & Tanggung Jawab

| **Peran** | **Anggota** | **Tanggung Jawab** |
| --- | --- | --- |
| Service Delivery Manager (SDM) / Service Request Manager (SRM) | Rian Munaji | Mengelola alur kerja & board, memfasilitasi Replenishment Meeting dan Retrospective, menjaga kebijakan WIP limit dan pull-policy berjalan, menjadi penghubung kebutuhan/prioritas dengan tim. |
| Frontend Developer | Rafif | Mengimplementasikan antarmuka pengguna sesuai wireframe dan acceptance criteria tiap kartu. |
| Backend Developer | Adnan | Mengimplementasikan API, logika bisnis, dan penyimpanan data sesuai functional requirement. |
| UI/UX Developer | Rakan | Merancang wireframe, alur pengguna, dan menjaga konsistensi desain antarmuka. |
| QA Tester | Javier | Menyusun test case dari acceptance criteria, memverifikasi kartu, dan memastikan Definition of Done terpenuhi sebelum kartu masuk Done. |

## 3. Penyusunan Proses & Artefak

Karena menggunakan Kanban, tim tidak menetapkan panjang Sprint — struktur alur kerja diatur lewat kolom board, batas WIP, dan kebijakan berikut.

### 3.1 Acara & Kadensi Rapat

| **Acara** | **Frekuensi** | **Durasi** | **Tujuan** |
| --- | --- | --- | --- |
| Daily Standup | Harian (Sen–Jum) | 15 menit | Tiap anggota menyampaikan progres, rencana berikutnya, dan blocker di board. |
| Kanban Replenishment Meeting | Mingguan (Senin) | 30 menit | Meninjau Backlog, menyusun ulang prioritas, dan menarik batch item berikutnya ke Ready. |
| Board Review & Retrospective | Dua mingguan | 30–45 menit | Meninjau tren cycle time/throughput, menandai kolom yang jadi bottleneck, dan menyepakati penyesuaian proses. |
| Ad-hoc Code Review | Sebelum setiap merge ke Done | Sesuai kebutuhan | Dev Backend/Frontend saling memeriksa kartu terhadap acceptance criteria sebelum dipindah ke Done. |

### 3.2 Aturan & Kebijakan Alur Kerja

**Kolom board: **Backlog → Ready → In Progress → In Review/QA → Done

- **Batas WIP:**

- Ready: maks. 6 kartu (kira-kira satu siklus Replenishment)

- In Progress: maks. 2 kartu per orang

- In Review/QA: maks. 3 kartu total (mencegah tahap review jadi bottleneck)

- **Definisi Siap (Definition of Ready / DoR) — kartu boleh masuk Ready jika:**

  - Sudah punya acceptance criteria tertulis

  - Prioritas sudah ditentukan dan dependensi (jika ada) sudah selesai/dicatat

  - Modul/penanggung jawab sudah teridentifikasi

- **Definisi Selesai (Definition of Done / DoD) — kartu boleh masuk Done jika:**

  - Kode sudah di-merge ke main dan lolos CI/build

  - QA sudah memverifikasi kartu sesuai acceptance criteria

  - Tidak ada regresi yang muncul pada fitur terkait

- **Kebijakan Pull:**

  - Anggota hanya menarik kartu prioritas tertinggi dari Ready jika masih ada kapasitas WIP di In Progress; tidak menarik kartu baru selama kartu yang sedang dikerjakan masih blocked (kartu blocked ditandai, bukan dibiarkan diam).

### 3.3 Pelacakan Progres

| **Metrik** | **Definisi** | **Cara Dipantau** |
| --- | --- | --- |
| Cycle Time | Waktu kartu dari Ready sampai Done | Tercatat otomatis di board tool per kartu; ditinjau saat Retrospective |
| Throughput | Jumlah kartu selesai per minggu | Dihitung setiap Replenishment meeting; ditren minggu ke minggu |
| Flow (opsional) | Distribusi kartu di tiap kolom sepanjang waktu | Cumulative Flow Diagram, dicek dua mingguan untuk melihat kolom bottleneck |

## 4. Backlog Awal

Backlog diturunkan dari Functional Requirement yang sudah didefinisikan di Project 1 (docs/GymBuddy.md), dikelompokkan ke 3 modul fungsional inti yang sama, diprioritaskan, dan dilengkapi acceptance criteria.

### Modul 1 — Manajemen Profil & Preferensi Pengguna

| **ID** | **Kebutuhan Fungsional** | **Prioritas** | **Acceptance Criteria** |
| --- | --- | --- | --- |
| FR-1.1 | Sistem membuat akun mahasiswa dalam maks. 5 detik setelah email kampus valid & data wajib dikirim. | Tinggi | Diberikan email kampus valid dan semua field wajib terisi, Ketika pengguna submit form registrasi, Maka akun dibuat dalam ≤5 detik. |
| FR-1.2 | Sistem memverifikasi akun dalam maks. 10 detik setelah kode OTP valid dikirim. | Tinggi | Diberikan kode verifikasi sekali pakai valid, Ketika pengguna submit kode, Maka akun berstatus verified dalam ≤10 detik. |
| FR-1.3 | Sistem menyimpan tujuan kebugaran, pengalaman, jenis latihan, dan lokasi gym pilihan dalam maks. 3 detik. | Tinggi | Diberikan form profil kebugaran lengkap, Ketika pengguna submit, Maka data tersimpan dalam ≤3 detik dan langsung terlihat di profil. |
| FR-1.4 | Sistem menyimpan minimal satu slot ketersediaan mingguan dalam maks. 3 detik. | Sedang | Diberikan hari, waktu mulai, dan waktu selesai valid, Ketika pengguna submit slot, Maka slot tersimpan dalam ≤3 detik. |

### Modul 2 — Mesin Pencocokan (Matching Engine)

| **ID** | **Kebutuhan Fungsional** | **Prioritas** | **Acceptance Criteria** |
| --- | --- | --- | --- |
| FR-2.1 | Sistem menampilkan hingga 10 rekomendasi buddy terurut dalam maks. 5 detik. | Tinggi | Diberikan profil & preferensi lengkap, Ketika pengguna request pencarian kecocokan, Maka hingga 10 hasil terurut tampil dalam ≤5 detik. |
| FR-2.2 | Sistem menghitung skor kecocokan berdasarkan waktu, tujuan, preferensi, pengalaman, dan jam gym. | Tinggi | Diberikan dua profil pengguna, Ketika permintaan pencocokan diproses, Maka skor kecocokan dihitung dari kelima faktor tersebut. |
| FR-2.3 | Sistem mengirim permintaan pertemanan latihan dalam maks. 3 detik setelah dikonfirmasi. | Sedang | Diberikan pengguna memilih kandidat buddy, Ketika pengirim konfirmasi request, Maka request terkirim dalam ≤3 detik. |
| FR-2.4 | Sistem membuat kecocokan timbal balik dalam maks. 3 detik setelah request diterima. | Sedang | Diberikan request pending, Ketika penerima menerima request, Maka status berubah jadi matched dalam ≤3 detik. |
| FR-2.5 | Sistem mengaktifkan pesan dalam aplikasi dalam maks. 2 detik setelah matched. | Sedang | Diberikan dua pengguna matched, Ketika status matched terbentuk, Maka fitur chat aktif dalam ≤2 detik. |
| FR-2.6 | Sistem membuat sesi latihan dalam maks. 3 detik setelah lokasi, tanggal, waktu dikonfirmasi kedua pihak. | Rendah | Diberikan kedua pengguna matched menyepakati lokasi/tanggal/waktu, Ketika keduanya konfirmasi, Maka sesi tercatat dalam ≤3 detik. |

### Modul 3 — Komunikasi & Penjadwalan

| **ID** | **Kebutuhan Fungsional** | **Prioritas** | **Acceptance Criteria** |
| --- | --- | --- | --- |
| FR-3.1 | Sistem mencegah interaksi profil & pesan maks. 2 detik setelah diblokir. | Sedang | Diberikan pengguna A memblokir pengguna B, Ketika aksi block dikonfirmasi, Maka B tidak bisa mengirim pesan/melihat profil A dalam ≤2 detik. |
| FR-3.2 | Sistem mencatat laporan pengguna & memberi tahu admin dalam maks. 5 detik setelah alasan valid dikirim. | Sedang | Diberikan alasan dan deskripsi laporan valid, Ketika pelapor submit laporan, Maka laporan tercatat & admin diberi notifikasi dalam ≤5 detik. |

## 5. Pengaturan Board Visual

Board dikonfigurasi dengan kolom dan batas WIP sesuai Bagian 3.2:

| **Kolom** | **Batas WIP** | **Aturan Masuk** |
| --- | --- | --- |
| Backlog | — | Seluruh item backlog yang sudah diprioritaskan masuk ke sini lebih dulu |
| Ready | 6 | Memenuhi Definisi Siap (DoR) |
| In Progress | 2 / orang | Ditarik oleh anggota yang masih punya kapasitas |
| In Review / QA | 3 total | Implementasi selesai, menunggu verifikasi |
| Done | — | Memenuhi Definisi Selesai (DoD) |

*[ Sisipkan screenshot atau link board yang sudah live di sini — misal Trello / Jira / GitHub Projects — yang menampilkan kolom di atas berisi backlog item Modul 1. ]*

## 6. Rencana Iterasi / Kerja — Siklus Pertama

Panjang siklus pertama: 2 minggu. Cakupan: Modul 1 (Manajemen Profil & Preferensi Pengguna) — modul fondasi yang menjadi dependensi modul lainnya.

| **Penanggung Jawab** | **Peran** | **Kartu** | **Kapasitas WIP Awal** |
| --- | --- | --- | --- |
| Rian Munaji | SDM/SRM | Setup board, fasilitasi Replenishment & Standup, susun kartu FR-1.1/1.2 | 1 |
| Rafif | Frontend Developer | UI registrasi (FR-1.1), UI verifikasi (FR-1.2) | 2 |
| Adnan | Backend Developer | API pembuatan akun (FR-1.1), API verifikasi (FR-1.2), penyimpanan profil (FR-1.3) | 2 |
| Rakan | UI/UX Developer | Desain layar profil & preferensi (FR-1.3 / FR-1.4) | 2 |
| Javier | QA Tester | Menulis test case acceptance untuk semua kartu Modul 1; verifikasi terhadap DoD | 2 |

Di akhir siklus, throughput dan cycle time kartu Modul 1 ditinjau saat Board Review & Retrospective, dan batch berikutnya (kartu Modul 2) ditarik ke Ready.
