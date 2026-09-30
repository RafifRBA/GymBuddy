# **Campus Fitness & Gym Buddy Matcher**

Anggota Kelompok:

Rakan Hendian	 		24/540158/TK/59909  
Rafif Raihan Bahrul Alam 	24/534432/TK/59237  
Javier Yazid Janadi		24/545752/TK/60737  
Adnan Abdul Majid		24/544058/TK/60471  
Rian Prasetya Munaji		24/545573/TK/60702

1. # **Problem Statement**

Banyak mahasiswa yang ingin berolahraga secara konsisten namun memiliki kesulitan untuk menemukan partner berolahraga yang cocok. Media sosial dan grup chat yang ada saat ini belum mampu mencocokkan mahasiswa secara efisien berdasarkan ketersediaan waktu, kesamaan tujuan dalam berolahraga, preferensi olahraga, dan jam latihan yang diinginkan. Akibatnya mahasiswa banyak yang berolahraga sendirian, kehilangan motivasi, atau gagal konsisten dalam berolahraga. Oleh karena itu, diperlukan sistem yang tepat untuk membantu mahasiswa menemukan partner dalam berolahraga yang cocok dan terpercaya dalam lingkungan kampus.

2. # **Business Goals**

Sistem ini bertujuan untuk:

1. Mempermudah mahasiswa menemukan partner berolahraga (Gym Buddy) yang sesuai.  
2. Meningkatkan konsistensi dan motivasi mahasiswa dalam berolahraga.  
3. Membantu mahasiswa mengatur jadwal olahraga bersama.  
4. Membangun komunitas olahraga di lingkungan kampus yang aman dan terpercaya.  
5. Membantu pengelola gym kampus dengan menyediakan data mengenai waktu ideal dan populer yang diminati mahasiswa.  
   

# **3\.   System Scope**

Campus Fitness & Gym Buddy Matcher adalah aplikasi berbasis kampus yang dirancang untuk membantu mahasiswa menemukan rekan olahraga yang cocok berdasarkan jadwal yang sama, tujuan kebugaran, jenis olahraga yang disukai, tingkat pengalaman, dan waktu gym yang diinginkan. Sistem ini memungkinkan mahasiswa untuk membuat profil kebugaran, memasukkan ketersediaan waktu mereka, menerima rekomendasi rekan berdasarkan peringkat, mengirim dan menerima permintaan pertemanan, berkomunikasi melalui pesan dalam aplikasi, serta menjadwalkan sesi olahraga. Pengelola gym dapat mengelola informasi gym dan melihat statistik waktu latihan yang dikumpulkan, sementara administrator dapat memverifikasi pengguna, mengelola laporan, memoderasi akun, dan mengkonfigurasi data sistem.

# **4\.   System Boundaries**

| In Scope | Out of Scope |
| ----- | ----- |
| Proses verifikasi untuk akun mahasiswa | Pemberian diagnosis maupun konsultasi medis |
| Penyusunan profil kebugaran pengguna | Layanan pelatih pribadi secara profesional |
| Manajemen jadwal serta preferensi gym | Sistem pemrosesan transaksi pembayaran gym |
| Fitur rekomendasi partner olahraga (Gym Buddy) | Monitoring perangkat gym secara real-time |
| Sistem permintaan dan pencocokan buddy | Jaminan keamanan fisik selama aktivitas |
| Fasilitas komunikasi pesan dalam aplikasi | Integrasi dengan fasilitas gym luar kampus |
| Pengaturan jadwal untuk sesi latihan | Pemantauan kondisi kesehatan secara klinis |
| Mekanisme pelaporan dan pemblokiran pengguna | Penyusunan program diet berbasis medis |
| Administrasi data fasilitas gym kampus |  |
| Penyajian statistik penggunaan gym |  |

# **5\.   Primary User Personas**

* ## **Persona 1 (Student User)**

  Nama		: Javier Abdul Prasetya  
  Umur		: 20 tahun  
  Role		: Mahasiswa / End User  
  Fitness level	: Beginner  
  Background	: Javier ngin mulai berolahraga secara rutin, tetapi merasa kurang percaya diri jika harus pergi ke gym sendirian. Jadwal kuliahnya sering berubah dan ia lebih nyaman berolahraga bersama mahasiswa lain yang memiliki tingkat pengalaman serupa.  
    
  **Goals:**  
* Menemukan workout buddy dengan jadwal yang cocok.  
* Mendapatkan partner dengan tujuan kebugaran dan tingkat pengalaman serupa.  
* Menjadwalkan sesi olahraga bersama.  
* Berkomunikasi dengan calon workout buddy secara aman.  
    
    
  **Permissions:**  
* Membuat dan memperbarui profil kebugaran.  
* Menentukan jadwal, tujuan, dan preferensi latihan.  
* Melihat rekomendasi workout buddy.  
* Mengirim, menerima, atau menolak buddy request.  
* Mengirim pesan kepada matched buddy.  
* Membuat atau membatalkan jadwal latihan.  
* Memblokir dan melaporkan pengguna lain.  
* Mengatur visibilitas profil pribadi.


* ## **Persona 2 (Gym Operator)**

  Nama		: Adnan Raihan Hendian  
  Umur		: 32 tahun  
  Role		:  Staff gym kampus / System Operator  
  Background	: Adnan bertanggung jawab mengelola informasi operasional gym kampus. Ia perlu memastikan bahwa mahasiswa mendapatkan informasi yang benar mengenai jam operasional, fasilitas, dan kapasitas gym.  
    
  **Goals:**  
* Menjaga informasi gym tetap akurat.  
* Mengetahui waktu olahraga yang paling banyak dipilih mahasiswa.  
* Membantu mengurangi kepadatan pada jam tertentu.  
* Menyampaikan perubahan operasional kepada mahasiswa.  
    
  **Permissions:**  
* Menambah dan memperbarui informasi gym.  
* Mengatur jam operasional dan kapasitas gym.  
* Menandai gym sebagai buka, tutup, atau tidak tersedia.  
* Melihat statistik penggunaan gym yang telah diagregasi.  
* Mengirim pengumuman operasional.  
* Tidak dapat membaca pesan pribadi mahasiswa.  
* Tidak dapat melihat data sensitif pengguna.


* ## **Persona 3 (System Administrator)**

  Nama		: Rakan Yazid Munaji  
  Umur		: 28 tahun  
  Role		: System Administrator  
  Background	: Siti mengelola keamanan, keandalan, dan kepatuhan platform. Ia bertugas menangani akun bermasalah, laporan pengguna, dan konfigurasi sistem.

  **Goals:**

* Menjaga keamanan dan kenyamanan pengguna.  
* Memastikan hanya mahasiswa terverifikasi yang menggunakan sistem.  
* Menangani laporan secara konsisten.  
* Menjaga data dan konfigurasi aplikasi tetap valid.  
    
  **Permissions:**  
* Memverifikasi, menangguhkan, dan mengaktifkan akun.  
* Melihat dan menangani laporan pengguna.  
* Mengelola kategori fitness goal dan workout type.  
* Mengelola data gym dan akun operator.  
* Mengakses audit log.  
* Menghapus konten yang melanggar aturan.  
* Tidak dapat mengubah data pribadi tanpa alasan administratif yang tercatat.

# 

6. # **Functional and Non-Functional Requirement**

* ## **Functional Requirement**

  #### Functional Requirements dikelompokkan ke dalam **3 modul fungsional inti** :

  #### **Manajemen Profil & Preferensi Pengguna**

| ID | Kebutuhan Fungsional |
| ----- | ----- |
| FR-1.1 | Sistem harus membuat akun mahasiswa dalam waktu maksimal 5 detik setelah pengguna mengirimkan alamat email kampus yang valid dan seluruh data pendaftaran wajib. |
| FR-1.2 | Sistem harus memverifikasi akun mahasiswa dalam waktu maksimal 10 detik setelah pengguna mengirimkan kode verifikasi sekali pakai yang valid. |
| FR-1.3 | Sistem harus menyimpan tujuan kebugaran, tingkat pengalaman, jenis latihan yang disukai, dan lokasi gym pilihan pengguna dalam waktu maksimal 3 detik setelah pengguna mengirimkan formulir profil. |
| FR-1.4 | Sistem harus menyimpan setidaknya satu slot waktu ketersediaan mingguan dalam waktu maksimal 3 detik setelah pengguna mengirimkan hari, waktu mulai, dan waktu selesai yang valid. |

#### 

#### 

#### **Mesin Pencocokan (Matching Engine)**

| ID | Kebutuhan Fungsional |
| ----- | ----- |
| FR-2.1 | Sistem harus menampilkan hingga 10 rekomendasi teman latihan yang telah diurutkan dalam waktu maksimal 5 detik setelah pengguna meminta pencarian kecocokan baru. |
| FR-2.2 | Sistem harus menghitung setiap skor kecocokan menggunakan kesamaan waktu ketersediaan, tujuan kebugaran, preferensi latihan, tingkat pengalaman, dan jam gym pilihan dalam setiap permintaan pencocokan. |
| FR-2.3 | Sistem harus mengirimkan permintaan pertemanan latihan kepada mahasiswa yang dipilih dalam waktu maksimal 3 detik setelah pengirim mengonfirmasi permintaan tersebut. |
| FR-2.4 | Sistem harus membuat kecocokan timbal balik dalam waktu maksimal 3 detik setelah mahasiswa penerima menerima permintaan teman latihan yang masih tertunda. |
| FR-2.5 | Sistem harus mengaktifkan fitur pesan dalam aplikasi dalam waktu maksimal 2 detik setelah dua mahasiswa menjadi pasangan yang saling cocok. |
| FR-2.6 | Sistem harus membuat sesi latihan dalam waktu maksimal 3 detik setelah kedua mahasiswa yang cocok mengonfirmasi lokasi gym, tanggal, dan waktu. |

#### **Komunikasi & Penjadwalan**

| ID | Kebutuhan Fungsional |
| ----- | ----- |
| FR-3.1 | Sistem harus segera mencegah interaksi profil dan pengiriman pesan lebih lanjut dalam waktu maksimal 2 detik setelah seorang mahasiswa memblokir pengguna lain. |
| FR-3.2 | Sistem harus mencatat laporan pengguna dan memberi tahu administrator dalam waktu maksimal 5 detik setelah mahasiswa pelapor mengirimkan alasan dan deskripsi yang valid. |

## **Non-Functional Requirement**

| ID | Kategori | Kebutuhan Non-Fungsional |
| ----- | ----- | ----- |
| NFR-1.1 | Performance | Sistem harus mengembalikan hasil rekomendasi kecocokan dalam waktu maksimal 3 detik untuk 95% permintaan ketika melayani 1000 pengguna aktif secara bersamaan |
| NFR-1.2 | Security | Sistem harus mengenkripsi seluruh data pribadi dan pesan chat yang tersimpan menggunakan enkripsi AES-256 serta melindungi data yang dikirimkan antara aplikasi dan server |
| NFR-1.3 | Usability | Sistem harus memungkinkan pengguna baru menyelesaikan pengaturan profil dan melihat saran kecocokan pertamanya dalam waktu maksimal 5 menit tanpa bantuan eksternal. |
| NFR-1.4 | Availability | Sistem harus mempertahankan waktu aktif (*uptime*) minimal 99,5% per bulan, tidak termasuk jadwal pemeliharaan yang telah direncanakan. |
| NFR-1.5 | Scalability | Sistem harus mendukung minimal 5.000 pengguna aktif secara bersamaan tanpa penurunan waktu respons yang melebihi 20%. |
| NFR-1.6 | Privacy/Compliance | Sistem harus menghapus akun pengguna dan seluruh data pribadi terkait secara permanen dalam waktu maksimal 7 hari setelah permintaan penghapusan yang terverifikasi serta menghapus salinan data tersebut dari sistem cadangan dalam waktu maksimal 30 hari. |

