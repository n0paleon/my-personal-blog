---
title: "Glosarium Pengantar TI Part 4"
date: 2026-10-29T09:20:00+07:00
draft: false
tags: ["Glosarium", "Teknologi Informasi", "Sistem Informasi", "Organisasi", "Basis Data", "ERP", "Manajemen", "API"]
categories: ["Glosarium", "Teknologi"]
summary: "Glosarium istilah sistem informasi, dari data dan pengetahuan sampai enam komponen, TPS, MIS, ERP, serta tantangan seperti integrasi dan kualitas data."
ShowToc: true
TocOpen: false
series: []

# cover:
#     image: "<image path/url>"
#     alt: "<alt text>"
#     caption: "<text>"
#     relative: true
---

## Pendahuluan

Setiap awal semester, ada satu situs yang hampir pasti dibuka semua mahasiswa: portal KRS.

Di sana kita melihat jadwal, mengisi rencana studi, memantau nilai, dan kadang mengeluh karena halaman tertentu lambat atau tiba-tiba keluar sendiri. Bagi kita, itu "sistem informasi kampus".

Tapi kalau diminta menjelaskan apa itu sistem informasi, jawaban kita sering menyempit menjadi "aplikasi" atau "komputer".

Padahal dalam materi Pertemuan 9, sistem informasi justru didefinisikan sebagai perpaduan teknologi, manusia, dan mekanisme kerja yang mengumpulkan, menyimpan, mengolah, dan mendistribusikan informasi untuk menunjang pengambilan keputusan. Kata "komputer" bahkan tidak muncul di definisi itu.

Komputer cuma salah satu bagiannya. Yang membuat sistem itu benar-benar bekerja adalah basis data yang rapi, jaringan yang menghubungkan, prosedur yang disepakati, dan orang-orang yang mengisi serta memakai datanya.

Contoh kecil: aplikasi kasir di minimarket. Mesinnya ada, aplikasinya jalan. Tapi kalau kasir tidak dilatih, prosedur pembatalan transaksi tidak jelas, dan data barang tidak pernah diperbarui, laporannya tetap tidak bisa dipercaya.

Di part keempat ini, saya merangkum istilah-istilah seputar sistem informasi. Sama seperti sebelumnya, urutannya alfabetis supaya bisa dibaca dari mana saja. Istilah yang saling berkaitan saya tautkan, jadi teman-teman bisa mengikuti alurnya tanpa harus mencari manual.

Bagi yang baru mampir, [part 1](/posts/glosarium-pengantar-ti-part-1/), [part 2](/posts/glosarium-pengantar-ti-part-2/), dan [part 3](/posts/glosarium-pengantar-ti-part-3/) sudah membahas dasar perangkat keras dan lunak, istilah cloud dan keamanan, serta profesi di bidang TI.

### Mulai membaca dari mana?

Kalau masih bingung mau mulai dari mana, beberapa jalur ini mungkin bisa membantu:

- **Konsep dasar:** [sistem](#sistem) → [data](#data) → [informasi](#informasi) → [pengetahuan](#pengetahuan) → [sistem informasi](#sistem-informasi).

- **Enam komponen:** [komponen sistem informasi](#komponen-sistem-informasi) → [basis data](#basis-data-database) → [DBMS](#dbms-database-management-system) → [jaringan dan TI](#jaringan-dan-ti) → [prosedur](#prosedur) → [manusia](#manusia).

- **Jenis sistem:** [TPS](#tps-transaction-processing-system) → [MIS](#mis-management-information-system) → [SPK](#spk-sistem-pendukung-keputusan) → [EIS](#eis-executive-information-system) → [ERP](#erp-enterprise-resource-planning). [OAS](#oas-office-automation-system) dan [KMS](#kms-knowledge-management-system) melengkapi pekerjaan sehari-hari.

- **Tantangan:** [keamanan dan privasi](#keamanan-dan-privasi) → [integrasi sistem](#integrasi-sistem) → [kualitas data](#kualitas-data) → [manusia](#manusia) → [biaya sistem informasi](#biaya-sistem-informasi) → [perubahan teknologi](#perubahan-teknologi) → [etika dan hukum](#etika-dan-hukum).

## Isi

## A

### API (Application Programming Interface)

**API** adalah kesepakatan tentang bagaimana dua perangkat lunak saling meminta dan mengirim data.

Bayangkan kita memesan makanan di restoran. Kita tidak masuk ke dapur dan mengambil sendiri bahan makanannya. Kita menyampaikan pesanan lewat pelayan, lalu pelayan membawa hasilnya. API bekerja kurang lebih seperti itu: satu aplikasi meminta sesuatu, aplikasi lain menyiapkan jawabannya.

Dalam sistem informasi, API sering dipakai untuk menghubungkan aplikasi yang berbeda. Misalnya aplikasi absensi kampus dengan portal kepegawaian, atau marketplace dengan jasa pengiriman. Data tidak perlu diketik ulang di dua tempat.

Tapi API bukan tombol ajaib. Kedua sistem tetap harus sepakat soal format data, siapa yang boleh mengakses, dan apa yang terjadi kalau salah satu pihak gagal merespons.

**Terkait:** [Integrasi Sistem](#integrasi-sistem), [Arsitektur Perusahaan](#arsitektur-perusahaan-enterprise-architecture), [DBMS](#dbms-database-management-system)

### Arsitektur Perusahaan (Enterprise Architecture)

**Arsitektur perusahaan** adalah rancangan menyeluruh tentang bagaimana proses bisnis, data, aplikasi, dan teknologi dalam sebuah organisasi saling terhubung.

Namanya terdengar seperti urusan gedung, padahal yang dimaksud adalah "gedung" dalam bentuk sistem. Ketika organisasi punya banyak aplikasi dari berbagai generasi, tanpa rancangan menyeluruh mudah sekali ada tumpang tindih: dua aplikasi menyimpan data yang sama, atau sistem baru tidak bisa bicara dengan sistem lama.

Contohnya rumah sakit yang bergabung dengan rumah sakit lain. Masing-masing sudah punya sistem pasien sendiri, dibangun sepuluh tahun terpisah, di platform yang berbeda. Arsitektur perusahaan membantu memetakan mana yang disatukan, mana yang cukup dijembatani, dan mana yang tetap dibiarkan berjalan sementara.

Hasilnya bukan cuma diagram rapi. Yang lebih penting, keputusan teknologi jadi punya alasan yang bisa dijelaskan, bukan sekadar "kata vendor begitu".

**Terkait:** [Integrasi Sistem](#integrasi-sistem), [API](#api-application-programming-interface), [Data Silo](#data-silo)

### Autentikasi

**Autentikasi** adalah proses memastikan bahwa seseorang benar-benar orang yang ia klaim.

Saat kita memasukkan nama pengguna dan kata sandi di portal kampus, di situlah autentikasi bekerja. Bentuknya bisa macam-macam: kata sandi, kode OTP, sidik jari, wajah, atau *single sign-on* yang membuat satu akun bisa dipakai untuk beberapa layanan.

Autentikasi berbeda dari otorisasi. Autentikasi menjawab "siapa kamu?", sedangkan otorisasi menjawab "apa yang boleh kamu lakukan?". Seorang mahasiswa bisa berhasil login, tetapi tetap tidak boleh membuka nilai mahasiswa lain.

Karena itu, autentikasi yang lemah bukan cuma masalah satu akun. Kalau akun admin bocor, seluruh data di belakangnya ikut berisiko.

**Terkait:** [Keamanan dan Privasi](#keamanan-dan-privasi), [Enkripsi](#enkripsi), [Phishing](#phishing)

## B

### Basis Data (Database)

**Basis data** adalah kumpulan data yang disimpan secara sistematis agar mudah diakses, dikelola, dan diperbarui.

Data mahasiswa, mata kuliah, Kartu Rencana Studi, dan nilai bisa tinggal dalam satu basis data yang saling berhubungan. Karena terhubung, perubahan di satu tempat bisa tercermin di tempat lain tanpa menyalin manual.

Bedanya dengan tumpukan file Excel bukan cuma soal ukuran. Basis data dirancang untuk menangani banyak pengguna sekaligus, menjaga konsistensi, dan membatasi siapa yang boleh melihat atau mengubah apa.

Kalau basis datanya berantakan, aplikasi sebagus apa pun akan menghasilkan laporan yang salah. Ibarat dapur: bahan makanannya sama, tapi kalau disimpan sembarangan, memasak jadi lambat dan mudah keliru.

**Terkait:** [DBMS](#dbms-database-management-system), [Kualitas Data](#kualitas-data), [Komponen Sistem Informasi](#komponen-sistem-informasi)

### Biaya Sistem Informasi

**Biaya sistem informasi** bukan hanya harga lisensi atau harga perangkat kerasnya.

Ada biaya pengadaan, implementasi, penyesuaian proses, pelatihan, pemeliharaan, pembaruan, dan penambahan kapasitas. Ada juga biaya yang lebih sulit dihitung: waktu pegawai yang harus belajar sistem baru, gangguan operasional saat migrasi, dan kesempatan yang hilang ketika proyeknya tertunda.

Sering bagian termahal justru muncul setelah sistem berjalan. Server perlu dirawat, data perlu dicadangkan, keamanan perlu dipantau, dan pengguna perlu didampingi.

Karena itu, keputusan membeli sistem tidak cukup berhenti di pertanyaan "fiturnya lengkap tidak?". Pertanyaan lain yang sama penting: siapa yang akan merawatnya, berapa biaya lima tahun ke depan, dan apakah manfaatnya benar-benar sebanding?

**Terkait:** [Manusia](#manusia), [Perubahan Teknologi](#perubahan-teknologi), [ERP](#erp-enterprise-resource-planning)

### Big Data

**Big Data** bukan sekadar "data yang banyak". Istilah ini biasanya merujuk pada data yang volumenya besar, datang dengan cepat, dan bentuknya beragam, sehingga sulit ditangani dengan cara biasa.

Contohnya log klik di marketplace, rekaman transaksi harian, unggahan media sosial, atau data lokasi kendaraan. Data seperti ini bisa dipakai untuk menemukan pola: kapan orang paling sering berbelanja, produk apa yang sering dilihat tetapi jarang dibeli, atau rute mana yang paling padat.

Tapi banyak data tidak otomatis berarti banyak pengetahuan. Kalau datanya kotor, tidak lengkap, atau tidak jelas asal-usulnya, analisisnya bisa tetap menyesatkan. Kualitas tetap lebih penting daripada jumlah.

**Terkait:** [Data](#data), [Kualitas Data](#kualitas-data), [Transformasi Digital](#transformasi-digital)

## C

### CRM (Customer Relationship Management)

**CRM** adalah sistem untuk mengelola hubungan organisasi dengan pelanggan.

Di dalamnya tersimpan riwayat kontak, keluhan, pembelian, dan interaksi lain. Ketika seorang pelanggan menghubungi lagi, petugas bisa melihat konteks sebelumnya tanpa harus bertanya dari awal.

CRM sering disandingkan dengan [ERP](#erp-enterprise-resource-planning), tapi fokusnya berbeda. ERP lebih banyak mengurus sumber daya internal seperti keuangan, stok, dan SDM. CRM lebih dekat ke sisi pelanggan: siapa mereka, apa yang mereka butuhkan, dan bagaimana hubungannya dijaga.

Datanya juga bisa naik ke [EIS](#eis-executive-information-system) sebagai ringkasan, misalnya berapa banyak pelanggan baru atau seberapa cepat keluhan diselesaikan.

**Terkait:** [ERP](#erp-enterprise-resource-planning), [EIS](#eis-executive-information-system), [Informasi](#informasi)

## D

### Data

**Data** adalah fakta mentah yang belum diberi makna.

Angka "120", tanggal "12 Desember", atau nama "Budi" adalah data. Tanpa konteks, kita belum tahu 120 itu apa: jumlah penjualan, jumlah mahasiswa, atau harga barang.

Data adalah bahan baku. Setelah diolah dan diberi konteks, ia berubah menjadi [informasi](#informasi). Setelah informasi ditafsirkan dengan pengalaman, ia bisa menjadi [pengetahuan](#pengetahuan).

Di kampus, daftar nilai mentah bisa jadi contoh. Deretan angka 75, 80, dan 90 adalah data. Setelah diolah menjadi rata-rata kelas atau jumlah mahasiswa yang lulus, barulah muncul informasi. Setelah dosen menghubungkannya dengan pola kehadiran dan tingkat kesulitan materi, itu berubah menjadi pengetahuan.

Karena itu, kalimat seperti "kita punya banyak data" belum tentu kabar baik. Yang menentukan bukan jumlahnya, tetapi apakah data itu akurat, relevan, dan cukup untuk menjawab pertanyaan yang kita punya.

**Terkait:** [Informasi](#informasi), [Pengetahuan](#pengetahuan), [Kualitas Data](#kualitas-data)

### Data Cleansing

**Data cleansing** adalah proses membersihkan data dari duplikat, format yang tidak seragam, nilai kosong, salah ketik, dan berbagai ketidakkonsistenan lain.

Contoh sederhananya nomor telepon. Satu bagian menulis "0812...", bagian lain menulis "+62812...", dan bagian ketiga menulis "0812-...". Ketiganya mungkin orang yang sama, tapi bagi sistem mereka bisa terlihat seperti tiga pelanggan berbeda.

Contoh lain: nama perusahaan "PT ABC", "PT. A.B.C.", dan "ABC, PT". Kalau digabungkan tanpa dibersihkan, laporan bisa menghitung satu perusahaan beberapa kali.

Data cleansing biasanya dilakukan sebelum data dianalisis atau dipindahkan ke sistem baru. Pekerjaannya tidak selalu terlihat keren, tapi dampaknya besar. Laporan yang rapi sering kali dimulai dari data yang dibersihkan lebih dulu.

**Terkait:** [Kualitas Data](#kualitas-data), [Validasi Data](#validasi-data), [Data Silo](#data-silo)

### Data Silo

**Data silo** adalah data yang terkunci di satu bagian atau aplikasi sehingga sulit diakses dan digabungkan dengan data dari bagian lain.

Bukan karena datanya tidak ada. Datanya ada, bahkan mungkin lengkap. Masalahnya, ia tinggal di sistem yang berdiri sendiri, dengan format dan aturan sendiri, lalu tidak terhubung ke mana-mana.

Akibatnya, bagian akademik punya satu versi data mahasiswa, bagian keuangan punya versi lain, dan ketika pimpinan meminta laporan menyeluruh, semua orang sibuk mencocokkan angka.

Data silo sering muncul bukan karena kesalahan teknis, tetapi karena cara organisasi tumbuh: setiap bagian membeli atau membangun sistemnya sendiri tanpa rancangan bersama. Di sinilah [arsitektur perusahaan](#arsitektur-perusahaan-enterprise-architecture) dan [integrasi sistem](#integrasi-sistem) mulai dibutuhkan.

**Terkait:** [Integrasi Sistem](#integrasi-sistem), [Arsitektur Perusahaan](#arsitektur-perusahaan-enterprise-architecture), [Kualitas Data](#kualitas-data)

### DBMS (Database Management System)

**DBMS** adalah perangkat lunak yang mengelola basis data.

Kalau [basis data](#basis-data-database) adalah tempat datanya, DBMS adalah alat yang mengatur bagaimana data itu disimpan, diambil, diubah, dan dilindungi. Contohnya MySQL, PostgreSQL, Oracle, dan SQL Server.

Tugasnya bukan cuma menyimpan. DBMS mengatur hak akses, menjaga transaksi tetap konsisten ketika banyak pengguna mengakses bersamaan, dan menyediakan mekanisme backup serta pemulihan.

Jadi ketika ada yang bertanya "datanya disimpan di mana?", jawabannya bisa dua lapis: di basis data, dan dikelola oleh DBMS. Keduanya berkaitan, tapi bukan hal yang sama.

**Terkait:** [Basis Data](#basis-data-database), [Komponen Sistem Informasi](#komponen-sistem-informasi), [Keamanan dan Privasi](#keamanan-dan-privasi)

## E

### EIS (Executive Information System)

**EIS** adalah sistem informasi untuk manajemen puncak. Isinya ringkasan, bukan detail transaksi.

Bayangkan seorang rektor ingin melihat penerimaan mahasiswa, kondisi keuangan, dan kinerja riset dalam satu layar. Ia tidak perlu membuka satu per satu aplikasi bagian. EIS menyajikan data yang sudah diringkas, terkini, dan terintegrasi.

Bentuknya sering berupa dasbor dengan grafik dan indikator. Tujuannya membantu pimpinan melihat arah organisasi dan mendeteksi hal yang perlu diperhatikan lebih cepat.

Tapi EIS tetap bergantung pada data dari sistem lain, terutama [TPS](#tps-transaction-processing-system), [MIS](#mis-management-information-system), dan [ERP](#erp-enterprise-resource-planning). Kalau data di bawahnya kacau, dasbor di atasnya cuma terlihat meyakinkan.

**Terkait:** [MIS](#mis-management-information-system), [Piramida Manajemen](#piramida-manajemen), [ERP](#erp-enterprise-resource-planning)

### Enabler Strategis (Strategic Enabler)

**Enabler strategis** adalah cara pandang yang menempatkan sistem informasi bukan sekadar sebagai alat operasional, tetapi sebagai sarana mencapai tujuan organisasi.

Dalam pandangan ini, sistem informasi bisa membuka pasar baru, mempercepat layanan, mengurangi biaya, atau mengubah cara organisasi bersaing. Bukan cuma mengganti kertas dengan layar.

Contohnya bank yang dulu mengharuskan nasabah datang ke cabang, lalu bisa membuka rekening lewat aplikasi. Yang berubah bukan hanya medianya, tetapi jangkauan dan cara bank melayani nasabah.

Tapi label "strategis" jangan dipakai sebagai pembenaran otomatis. Sistem baru tetap perlu proses yang jelas, orang yang terlatih, dan keputusan yang mendukung. Tanpa itu, teknologi hanya jadi biaya tambahan yang rapi secara visual.

**Terkait:** [Transformasi Digital](#transformasi-digital), [Perubahan Teknologi](#perubahan-teknologi), [Sistem Informasi](#sistem-informasi)

### Enkripsi

**Enkripsi** adalah proses mengubah data menjadi bentuk yang tidak bisa dibaca tanpa kunci tertentu.

Tujuannya melindungi data, baik saat dikirim maupun saat disimpan. Ketika kita membuka situs dengan HTTPS, data perjalanan antara browser dan server ikut dienkripsi. Ketika ponsel menyimpan data dalam keadaan terenkripsi, isinya tidak mudah dibaca kalau perangkatnya hilang.

Enkripsi penting, tapi bukan solusi tunggal. Kunci enkripsi harus dijaga, akses harus diatur, dan pengguna tetap perlu dilindungi dari [phishing](#phishing) atau kelalaian lain.

Ibarat pintu berlapis: enkripsi membuat isi ruangan sulit dibaca, tetapi kalau kuncinya ditempel di pintu, lapisan itu kehilangan gunanya.

**Terkait:** [Keamanan dan Privasi](#keamanan-dan-privasi), [Autentikasi](#autentikasi), [Validasi Data](#validasi-data)

### ERP (Enterprise Resource Planning)

**ERP** adalah sistem terpadu yang menyatukan berbagai proses bisnis dalam satu platform.

Keuangan, SDM, produksi, logistik, dan inventori biasanya punya aplikasi masing-masing. ERP berusaha menggabungkannya supaya data tidak perlu dimasukkan berulang kali dan semua bagian melihat versi yang sama.

Contohnya ketika bagian penjualan mencatat pesanan, bagian gudang bisa langsung melihat kebutuhan stok, dan bagian keuangan bisa menyiapkan tagihan dari data yang sama. Contoh produknya SAP, Oracle ERP, dan Microsoft Dynamics.

Tapi ERP adalah proyek besar. Ia bukan hanya soal memasang software, melainkan menyesuaikan dan kadang mengubah proses kerja organisasi. Semakin banyak penyesuaian khusus, semakin besar biaya dan risikonya.

Kalau organisasinya belum siap, ERP yang lengkap bisa terasa seperti rumah besar yang ruangannya belum dipakai.

**Terkait:** [CRM](#crm-customer-relationship-management), [EIS](#eis-executive-information-system), [Biaya Sistem Informasi](#biaya-sistem-informasi)

### Etika dan Hukum

**Etika dan hukum** dalam sistem informasi adalah rambu-rambu tentang apa yang boleh dan tidak boleh dilakukan terhadap data serta teknologi.

Hukum memberi batas yang tertulis. Di Indonesia ada UU ITE yang mengatur informasi dan transaksi elektronik, serta UU Pelindungan Data Pribadi yang mengatur cara data pribadi dikumpulkan, disimpan, dan digunakan. Etika melengkapi hukum ketika aturannya belum jelas atau ketika sesuatu memang legal tetapi terasa tidak pantas.

Contohnya menyebarkan data pelanggan ke grup WhatsApp, memakai foto orang tanpa izin, atau membuka akses sistem hanya karena "kebetulan bisa". Secara teknis mungkin mudah, tetapi secara etis dan hukum bisa bermasalah.

Organisasi perlu kebijakan, pelatihan, dan sanksi yang jelas. Bukan karena takut dihukum saja, tetapi karena kepercayaan pengguna adalah bagian dari fondasi sistem itu sendiri.

**Terkait:** [Keamanan dan Privasi](#keamanan-dan-privasi), [UU ITE](#uu-ite), [Manusia](#manusia)

## I

### Informasi

**Informasi** adalah data yang sudah diolah dan diberi konteks sehingga punya makna.

Data penjualan berupa deretan angka bisa berubah menjadi informasi ketika disusun menjadi laporan: "penjualan naik 20% pada bulan Desember". Angka yang sama, tetapi sekarang kita tahu apa artinya.

Informasi yang baik biasanya akurat, tepat waktu, relevan, dan cukup ringkas untuk dipakai. Informasi yang terlambat atau salah bisa lebih berbahaya daripada tidak ada informasi, karena orang tetap mengambil keputusan berdasarkan itu.

Informasi juga bukan kebenaran otomatis. Ia bergantung pada kualitas data dan cara pengolahannya. Kalau datanya keliru, laporannya bisa terlihat rapi tetapi menyesatkan.

**Terkait:** [Data](#data), [Pengetahuan](#pengetahuan), [Kualitas Data](#kualitas-data)

### Integrasi Sistem

**Integrasi sistem** adalah upaya menyambungkan sistem atau aplikasi yang berbeda agar data bisa mengalir di antaranya.

Caranya bisa lewat [API](#api-application-programming-interface), pertukaran file, koneksi langsung ke basis data, atau perangkat perantara. Tujuannya satu: mengurangi input ganda dan memastikan semua bagian memakai data yang konsisten.

Tantangannya jarang cuma soal teknologi. Sistem yang dibangun pada tahun berbeda, oleh vendor berbeda, dengan format data berbeda, harus dipaksa bicara. Belum lagi soal siapa yang memiliki data, siapa yang boleh mengubah, dan apa yang terjadi kalau salah satu sistem mati.

Integrasi yang baik tidak selalu berarti semua sistem dilebur menjadi satu. Kadang cukup dijembatani dengan aturan yang jelas, seperti pada pembahasan [arsitektur perusahaan](#arsitektur-perusahaan-enterprise-architecture).

**Terkait:** [API](#api-application-programming-interface), [Data Silo](#data-silo), [Arsitektur Perusahaan](#arsitektur-perusahaan-enterprise-architecture)

## J

### Jaringan dan TI

**Jaringan** adalah komponen sistem informasi yang memungkinkan data berpindah antar pengguna dan antarsistem.

Tanpa jaringan, sebuah aplikasi hanya hidup di satu komputer. Dengan jaringan, data bisa diakses dari ruang lain, gedung lain, bahkan dari perangkat yang berbeda. Internet, intranet, dan [komputasi awan](/posts/glosarium-pengantar-ti-part-2/#cloud) memperluas jangkauan itu.

Tapi jaringan bukan hanya soal "ada wifi". Di dalamnya ada server, perangkat jaringan, alamat, hak akses, dan jalur komunikasi yang harus diatur. Kalau salah konfigurasi, data bisa tidak sampai, atau malah sampai ke pihak yang tidak berhak.

Jaringan juga memperbesar permukaan serangan. Semakin banyak pintu yang terbuka, semakin penting siapa yang memegang kuncinya.

**Terkait:** [Komponen Sistem Informasi](#komponen-sistem-informasi), [Keamanan dan Privasi](#keamanan-dan-privasi), [Basis Data](#basis-data-database)

## K

### Keamanan dan Privasi

**Keamanan** adalah upaya melindungi sistem dan data dari akses, perubahan, atau perusakan yang tidak sah. **Privasi** adalah hak orang atas data pribadinya: apa yang boleh dikumpulkan, untuk apa, dan siapa yang boleh melihatnya.

Ancamannya bermacam-macam. Ada [phishing](#phishing) yang menipu pengguna, [malware](/posts/glosarium-pengantar-ti-part-2/#malware) yang menyusup, [ransomware](/posts/glosarium-pengantar-ti-part-2/#ransomware) yang mengunci data dan meminta tebusan, sampai kebocoran data yang terjadi karena akses terlalu longgar.

Penanggulangannya juga berlapis: kebijakan keamanan, [autentikasi](#autentikasi) yang kuat, [enkripsi](#enkripsi), audit berkala, backup, dan pelatihan pengguna. Tidak ada satu alat yang cukup.

Yang sering terlupakan, keamanan bukan tugas satu bagian TI saja. Kalau pengguna mengklik tautan sembarangan atau menuliskan kata sandi di tempat yang salah, sistem sekuat apa pun bisa tetap jebol.

**Terkait:** [Phishing](#phishing), [Enkripsi](#enkripsi), [Etika dan Hukum](#etika-dan-hukum)

### KMS (Knowledge Management System)

**KMS** adalah sistem untuk menangkap, menyimpan, dan membagikan pengetahuan yang dimiliki organisasi.

Bentuknya bisa portal internal, wiki, basis kasus, atau repositori dokumen. Isinya bukan cuma laporan resmi, tetapi juga pengalaman: cara menangani masalah tertentu, catatan proyek, dan praktik baik yang biasanya cuma diingat orang.

Tujuannya supaya pengetahuan tidak hilang ketika pegawai berpindah atau berhenti. Kalau semuanya hanya ada di kepala satu orang, organisasi kehilangan bagian dari dirinya setiap kali orang itu pergi.

Tapi KMS tidak bekerja sendiri. Kalau tidak ada kebiasaan menulis dan mengkurasi, isinya bisa berubah menjadi tumpukan file yang tidak pernah dibuka. Sistemnya ada, pengetahuannya tetap sulit ditemukan.

**Terkait:** [Pengetahuan](#pengetahuan), [OAS](#oas-office-automation-system), [Manusia](#manusia)

### Komponen Sistem Informasi

**Komponen sistem informasi** ada enam: perangkat keras, perangkat lunak, basis data, jaringan, prosedur, dan manusia.

Empat komponen pertama berkaitan dengan teknologi. Perangkat keras adalah bagian fisiknya, perangkat lunak adalah instruksinya, basis data adalah tempat datanya, dan jaringan adalah penghubungnya. Empat komponen ini bisa dibeli.

Dua komponen terakhir justru menentukan apakah uangnya tidak sia-sia. [Prosedur](#prosedur) adalah aturan kerja yang disepakati, sementara [manusia](#manusia) adalah orang yang memakai, mengelola, dan mengembangkan sistem.

Coba petakan portal KRS. Perangkat kerasnya server dan laptop; perangkat lunaknya aplikasi web serta sistem operasi; basis datanya menyimpan data mahasiswa, mata kuliah, dan KRS; jaringannya internet kampus; prosedurnya aturan pengisian dan batas SKS; manusianya mahasiswa, dosen wali, dan admin akademik. Hilangkan salah satunya, sistemnya berhenti berguna.

Perangkat keras dan perangkat lunak sudah dibahas lebih jauh di [part pertama](/posts/glosarium-pengantar-ti-part-1/#perangkat-keras-hardware).

**Terkait:** [Basis Data](#basis-data-database), [Jaringan dan TI](#jaringan-dan-ti), [Prosedur](#prosedur), [Manusia](#manusia)

### Kualitas Data

**Kualitas data** adalah seberapa jauh data bisa dipercaya untuk dipakai: akurat, lengkap, konsisten, dan tepat waktu.

Data yang salah menghasilkan [informasi](#informasi) yang salah. Kalau stok barang di sistem menulis 50 padahal di gudang tinggal 5, keputusan pembelian berikutnya ikut salah. Kalau alamat pelanggan sudah kedaluwarsa, pengiriman gagal meskipun sistemnya berjalan normal.

Masalah kualitas data sering tidak terasa sampai seseorang membutuhkan laporan. Baru kemudian ketahuan ada duplikat, kolom kosong, format tanggal campur aduk, atau kode barang yang sudah tidak dipakai.

Perbaikannya bisa lewat [validasi data](#validasi-data) di titik input, [data cleansing](#data-cleansing), standar pengisian, dan audit berkala. Yang paling penting, kualitas data bukan proyek sekali selesai. Ia lebih mirip kebiasaan yang harus dijaga.

**Terkait:** [Data](#data), [Data Cleansing](#data-cleansing), [Validasi Data](#validasi-data)

## M

### Manusia

**Manusia** adalah komponen sistem informasi yang memakai, mengelola, dan mengembangkan sistem.

Cakupannya luas. Ada pengguna harian yang mengisi data, manajer yang membaca laporan, analis yang merancang proses, teknisi yang menjaga server, sampai pimpinan yang mengambil keputusan dari informasi yang dihasilkan.

Sistem tercanggih bisa gagal karena komponen ini. Contohnya kantor yang membeli aplikasi inventaris mahal, tetapi setengah tahun kemudian pegawainya masih mencatat stok di buku tulis. Bisa jadi aplikasinya tidak cocok, bisa jadi tidak ada pelatihan, atau bisa jadi prosedurnya tidak pernah disepakati.

Karena itu, investasi pada manusia bukan pelengkap. Pelatihan, dokumentasi, dan keterlibatan pengguna sejak awal sering lebih menentukan daripada spesifikasi teknis.

Dalam glosarium sebelumnya, manusia juga dibahas sebagai [brainware](/posts/glosarium-pengantar-ti-part-3/#brainware).

**Terkait:** [Pelatihan Pengguna](#pelatihan-pengguna), [Prosedur](#prosedur), [Komponen Sistem Informasi](#komponen-sistem-informasi)

### MIS (Management Information System)

**MIS** adalah sistem informasi untuk manajer menengah, biasanya berupa laporan berkala dari data yang dihasilkan sistem transaksi.

Isinya ringkasan kinerja: laporan penjualan bulanan, absensi, pengendalian produksi, atau penggunaan anggaran. Manajer memakainya untuk memantau apakah pekerjaan berjalan sesuai target dan di mana perlu perbaikan.

MIS berbeda dari [TPS](#tps-transaction-processing-system) yang mencatat transaksi harian, dan dari [EIS](#eis-executive-information-system) yang menyajikan ringkasan untuk pimpinan puncak. MIS berada di tengah: cukup ringkas untuk melihat pola, cukup rinci untuk menelusuri masalah.

Karena itu, MIS sangat bergantung pada data dari TPS. Kalau transaksi di bawahnya tidak rapi, laporan manajerialnya juga tidak bisa dipercaya.

**Terkait:** [TPS](#tps-transaction-processing-system), [EIS](#eis-executive-information-system), [Piramida Manajemen](#piramida-manajemen)

## O

### OAS (Office Automation System)

**OAS** adalah sistem yang mempermudah administrasi dan komunikasi harian: surel, dokumen digital, penjadwalan, dan rapat daring.

Contohnya Google Workspace, Microsoft 365, atau alat rapat daring. Hampir semua orang memakainya, bukan cuma bagian tertentu. Karena itu OAS sering dianggap remeh: "ah, cuma email".

Padahal justru di sinilah banyak pekerjaan organisasi berjalan. Dokumen bersama, kalender tim, dan komunikasi lintas bagian adalah bagian dari sistem informasi, meskipun bentuknya tidak seperti aplikasi kasir yang punya layar khusus.

OAS juga bisa menjadi pintu masuk ke [KMS](#kms-knowledge-management-system), karena banyak pengetahuan organisasi bermula dari dokumen dan percakapan yang tersimpan di sana.

**Terkait:** [KMS](#kms-knowledge-management-system), [Otomatisasi](#otomatisasi), [Manusia](#manusia)

### Otomatisasi

**Otomatisasi** adalah menggantikan langkah manual yang berulang dengan proses yang dijalankan sistem.

Contohnya absensi yang otomatis mencatat kehadiran, laporan yang dihasilkan tanpa menyusun tabel dari nol, atau sistem yang memberi peringatan ketika stok menipis. Hasilnya bisa lebih cepat, konsisten, dan murah.

Tapi otomatisasi bukan selalu jawaban. Kalau prosesnya sejak awal berantakan, mengotomatiskan proses itu hanya membuat kesalahan berjalan lebih cepat dan lebih rapi. Sebelum bertanya "bisa diotomatiskan tidak?", ada baiknya bertanya dulu "prosesnya sudah benar belum?".

Otomatisasi juga mengubah pekerjaan manusia. Sebagian tugas rutin berkurang, tetapi kebutuhan untuk memeriksa, menafsirkan, dan menangani pengecualian tetap ada.

**Terkait:** [Prosedur](#prosedur), [TPS](#tps-transaction-processing-system), [Transformasi Digital](#transformasi-digital)

## P

### Pelatihan Pengguna

**Pelatihan pengguna** adalah kegiatan membekali orang agar mampu memakai sistem sesuai kebutuhan.

Bentuknya bisa pelatihan awal, panduan tertulis, video singkat, pendampingan, atau penyegaran berkala. Yang dilatih bukan cuma tombol-tombolnya, tetapi juga alur kerja, aturan pengisian data, dan hal-hal yang harus dilakukan ketika ada masalah.

Tanpa pelatihan, sistem yang mahal bisa berubah menjadi pajangan. Pengguna akan kembali ke cara lama karena cara baru terasa merepotkan, atau tetap memakai sistem tetapi dengan data yang tidak konsisten.

Pelatihan juga berkaitan dengan keamanan. Banyak insiden terjadi bukan karena sistemnya jebol, tetapi karena seseorang tidak tahu bahwa tautan yang diklik atau kata sandi yang dibagikan itu berbahaya.

**Terkait:** [Manusia](#manusia), [Prosedur](#prosedur), [Keamanan dan Privasi](#keamanan-dan-privasi)

### Pengetahuan

**Pengetahuan** adalah pemahaman yang terbentuk dari pengalaman dan penafsiran atas informasi.

Kalau [informasi](#informasi) memberi tahu bahwa penjualan naik setiap Desember, pengetahuan mencoba menjawab mengapa hal itu terjadi dan apa yang sebaiknya dilakukan berikutnya. Di situ ada pengalaman, konteks, dan pertimbangan yang tidak selalu tertulis di laporan.

Pengetahuan bisa bersifat *tacit*, tersimpan di kepala orang, atau *explicit*, sudah didokumentasikan. Banyak pengetahuan organisasi justru bersifat tacit: cara menangani pelanggan tertentu, langkah kecil saat sistem bermasalah, atau keputusan yang dulu pernah diambil beserta alasannya.

Karena itu, [KMS](#kms-knowledge-management-system) berusaha mengubah sebagian pengetahuan tacit menjadi explicit. Bukan untuk menggantikan orang, tetapi supaya pengalaman tidak hilang begitu saja ketika orangnya tidak lagi ada.

**Terkait:** [Informasi](#informasi), [KMS](#kms-knowledge-management-system), [Manusia](#manusia)

### Perubahan Teknologi

**Perubahan teknologi** adalah tantangan organisasi karena teknologi berkembang lebih cepat daripada kemampuan beradaptasi.

Cloud, Big Data, AI, dan IoT datang silih berganti. Di atas kertas, semuanya terdengar menjanjikan. Di lapangan, organisasi masih harus menghadapi proses yang belum rapi, pegawai yang belum terlatih, dan anggaran yang terbatas.

Yang gagal menyesuaikan diri bisa tertinggal. Tapi yang mengejar semua teknologi sekaligus juga bisa kehabisan tenaga dan biaya. Karena itu, transformasi biasanya lebih berhasil kalau bertahap, punya prioritas, dan disertai perubahan proses serta kompetensi.

Teknologi baru bukan tujuan akhir. Ia alat. Pertanyaan yang lebih penting: masalah apa yang ingin diselesaikan, dan apakah organisasi siap menjalankannya?

**Terkait:** [Transformasi Digital](#transformasi-digital), [Biaya Sistem Informasi](#biaya-sistem-informasi), [Enabler Strategis](#enabler-strategis-strategic-enabler)

### Phishing

**Phishing** adalah upaya menipu orang agar menyerahkan data sensitif dengan menyamar sebagai pihak yang tepercaya.

Contohnya surel yang mengaku dari bagian TI dan meminta kita mengonfirmasi kata sandi, atau pesan yang mengatakan "akun Anda akan diblokir, klik tautan ini". Tampilannya bisa sangat meyakinkan: logo asli, bahasa resmi, dan tautan yang mirip dengan situs asli.

Yang diserang bukan cuma sistem, tetapi manusia. Karena itu, pertahanannya juga melibatkan manusia: memeriksa alamat pengirim, tidak buru-buru mengklik tautan, memakai [autentikasi](#autentikasi) berlapis seperti OTP atau kode aplikasi, dan melaporkan pesan mencurigakan.

Prinsipnya sederhana: pihak resmi biasanya tidak meminta kata sandi lewat surel. Kalau ada yang memintanya, itu justru alasan untuk curiga.

**Terkait:** [Keamanan dan Privasi](#keamanan-dan-privasi), [Autentikasi](#autentikasi), [Enkripsi](#enkripsi)

### Piramida Manajemen

**Piramida manajemen** menggambarkan tiga tingkat pengambilan keputusan dalam organisasi: operasional, manajerial, dan strategis.

Di tingkat operasional, pertanyaannya sederhana dan berulang: "apakah transaksi ini berhasil?". Sistem yang dipakai biasanya [TPS](#tps-transaction-processing-system) dan [OAS](#oas-office-automation-system).

Di tingkat manajerial, pertanyaannya mulai tentang kinerja: "apakah kuartal ini sesuai target, dan mengapa?". Di sini [MIS](#mis-management-information-system) dan [SPK](#spk-sistem-pendukung-keputusan) lebih berperan.

Di tingkat strategis, pertanyaannya makin terbuka: "lima tahun lagi kita harus ada di mana?". [EIS](#eis-executive-information-system) dan [ERP](#erp-enterprise-resource-planning) membantu menyajikan gambaran menyeluruh.

Semakin ke atas, masalahnya makin tidak terstruktur. Karena itu, sistem di tingkat atas seharusnya menunjang pertimbangan manusia, bukan menggantikannya.

**Terkait:** [TPS](#tps-transaction-processing-system), [MIS](#mis-management-information-system), [EIS](#eis-executive-information-system), [SPK](#spk-sistem-pendukung-keputusan)

### Prosedur

**Prosedur** adalah aturan dan langkah yang disepakati untuk mengumpulkan, mengolah, menyimpan, dan menyebarkan data.

Contohnya siapa yang boleh mengubah nilai, kapan data harus diperbarui, bagaimana format penulisan alamat, dan apa yang harus dilakukan ketika ada data ganda. Prosedur membuat pekerjaan orang berbeda menghasilkan data yang bisa digabungkan.

Tanpa prosedur yang jelas, sistem mudah jatuh ke inkonsistensi. Dua bagian mengisi format berbeda, atau satu bagian mengubah data tanpa memberi tahu bagian lain. Secara teknis sistemnya berjalan, tetapi datanya perlahan menjadi tidak bisa dipercaya.

Prosedur tidak harus tebal dan rumit. Yang penting jelas, diketahui, dan benar-benar dijalankan. Prosedur yang hanya tersimpan di dokumen tetapi tidak dipakai sama saja dengan tidak ada.

**Terkait:** [Komponen Sistem Informasi](#komponen-sistem-informasi), [Kualitas Data](#kualitas-data), [Manusia](#manusia)

## S

### Sistem

**Sistem** adalah kumpulan elemen yang saling terhubung dan terorganisasi untuk menghasilkan output dari input yang diterimanya.

Kata aslinya, *systema*, berasal dari bahasa Yunani dan berarti kesatuan atas bagian-bagian yang saling terhubung. Ada tiga syarat sederhana: punya lebih dari satu bagian, bagian-bagiannya saling berinteraksi, dan semuanya mengarah ke satu tujuan bersama.

Contohnya sistem akademik. Ada data mahasiswa, aturan kurikulum, dosen, ruang kelas, dan aplikasi yang menyatukannya. Kalau salah satu bagian dihilangkan, hasilnya berubah. Tanpa aturan, jadwal bisa bentrok. Tanpa data, aplikasi tidak tahu harus menampilkan apa.

Cara berpikir sistem membantu kita melihat hubungan, bukan cuma bagian. Pertanyaan seperti "komponen mana yang gagal?" sering lebih berguna daripada "aplikasi mana yang salah?".

**Terkait:** [Sistem Informasi](#sistem-informasi), [Komponen Sistem Informasi](#komponen-sistem-informasi), [Prosedur](#prosedur)

### Sistem Informasi

**Sistem informasi** adalah perpaduan teknologi, manusia, dan mekanisme kerja yang mengumpulkan, menyimpan, mengolah, dan mendistribusikan informasi untuk menunjang pengambilan keputusan.

Perhatikan bahwa definisi itu tidak menyebut kata "komputer". Komputer hanyalah salah satu bagian dari teknologi yang dipakai. Yang membuatnya menjadi sistem informasi adalah kombinasi semua komponen yang bekerja bersama.

Contohnya portal KRS, aplikasi kasir minimarket, mobile banking, dan rekam medis rumah sakit. Semuanya punya data yang dikumpulkan, diolah, lalu disajikan kepada orang yang membutuhkan.

Tujuannya bukan sekadar menyimpan data. Sistem informasi dibangun agar organisasi bekerja lebih efisien, arus informasinya lebih cepat, dan perencanaannya berdasar bukti, bukan tebakan.

Dalam organisasi modern, perannya cukup luas: menunjang operasional harian, membantu manajemen memantau kinerja, mendukung keputusan strategis, membuka kolaborasi, menjadi pusat pengetahuan, dan membantu mengawasi serta mengendalikan penyimpangan.

Karena itu, menilai sistem informasi tidak cukup dari tampilannya. Perlu dilihat juga apakah datanya akurat, prosedurnya jelas, dan orang-orangnya mampu memakainya.

**Terkait:** [Komponen Sistem Informasi](#komponen-sistem-informasi), [Enabler Strategis](#enabler-strategis-strategic-enabler), [Piramida Manajemen](#piramida-manajemen)

### SPK (Sistem Pendukung Keputusan)

**SPK** atau *Decision Support System* adalah sistem yang membantu manajer menghadapi masalah semi-terstruktur.

Masalah semi-terstruktur adalah masalah yang sebagian bisa dihitung, tetapi sebagian lagi butuh pertimbangan. Contohnya memilih lokasi cabang baru: ada data biaya, jumlah penduduk, dan lalu lintas, tetapi tetap ada faktor yang tidak bisa sepenuhnya diukur.

SPK menggabungkan data, model analisis, dan antarmuka untuk mencoba berbagai skenario "bagaimana-jika". Manajer bisa membandingkan beberapa pilihan sebelum memutuskan.

SPK tidak memberi jawaban mutlak. Ia membantu melihat konsekuensi dari pilihan yang berbeda. Keputusan akhirnya tetap ada di tangan manusia, karena tidak semua hal bisa diterjemahkan menjadi angka.

**Terkait:** [MIS](#mis-management-information-system), [EIS](#eis-executive-information-system), [Piramida Manajemen](#piramida-manajemen)

## T

### TPS (Transaction Processing System)

**TPS** adalah sistem yang mencatat transaksi rutin harian dan memasok data untuk sistem lain.

Contohnya sistem kasir di minimarket, pemesanan tiket, absensi, dan pencatatan inventori. Setiap penjualan, setiap barang masuk, dan setiap kehadiran dicatat sebagai transaksi.

Karena dipakai terus-menerus, TPS menuntut kecepatan, akurasi, dan keandalan. Kalau kasir lambat, antrean panjang. Kalau pencatatan salah, laporan di atasnya ikut salah.

TPS adalah fondasi. [MIS](#mis-management-information-system), [SPK](#spk-sistem-pendukung-keputusan), dan [EIS](#eis-executive-information-system) mengambil data dari sini. Kalau fondasinya tidak rapi, bangunan di atasnya hanya terlihat kokoh.

**Terkait:** [MIS](#mis-management-information-system), [Otomatisasi](#otomatisasi), [Piramida Manajemen](#piramida-manajemen)

### Transformasi Digital

**Transformasi digital** adalah perubahan cara organisasi bekerja dengan memanfaatkan teknologi secara menyeluruh.

Ini bukan sekadar memindahkan formulir kertas ke PDF, atau membuat akun media sosial untuk perusahaan. Transformasi mencakup proses, budaya, kompetensi, dan kadang model bisnis.

Contohnya bank yang berpindah dari layanan cabang ke aplikasi, atau UMKM yang beralih dari catatan buku ke sistem kasir yang terhubung dengan stok. Yang berubah bukan cuma alatnya, tetapi cara orang bekerja dan mengambil keputusan.

Transformasi bisa gagal kalau dianggap proyek pembelian alat. Teknologi baru tanpa proses yang jelas dan orang yang siap hanya menambah beban. Karena itu, perubahan biasanya lebih berhasil kalau bertahap dan melibatkan mereka yang akan memakainya.

**Terkait:** [Perubahan Teknologi](#perubahan-teknologi), [Enabler Strategis](#enabler-strategis-strategic-enabler), [Manusia](#manusia)

## U

### UU ITE

**UU ITE** adalah Undang-Undang Informasi dan Transaksi Elektronik, aturan hukum di Indonesia yang membahas informasi elektronik, transaksi elektronik, dan tindak pidana yang berkaitan dengannya.

Cakupannya luas: tanda tangan elektronik, penyelenggaraan sistem elektronik, akses ilegal, pencemaran nama baik, sampai penyebaran konten. UU ini juga menjadi salah satu dasar bagaimana organisasi harus memperlakukan data dan sistem yang dikelolanya.

Dalam praktik, UU ITE sering dilengkapi dengan aturan lain, seperti UU Pelindungan Data Pribadi. Bagi organisasi, keduanya bukan cuma urusan bagian hukum. Pengembang yang membangun sistem, admin yang mengelola akses, dan pengguna yang mengunggah data perlu tahu batasannya.

Yang perlu dihindari adalah anggapan bahwa "di internet bebas". Jejak digital bisa tersimpan lama, dan aturan tetap berlaku di ruang digital.

**Terkait:** [Etika dan Hukum](#etika-dan-hukum), [Keamanan dan Privasi](#keamanan-dan-privasi), [Data](#data)

## V

### Validasi Data

**Validasi data** adalah pemeriksaan agar data yang masuk sesuai aturan yang ditentukan.

Aturannya bisa berupa format, rentang, kewajiban isi, atau konsistensi. Contohnya NIM harus sepuluh digit, tanggal lahir tidak boleh di masa depan, email harus mengandung tanda @, dan jumlah SKS tidak boleh melebihi batas.

Validasi dilakukan di titik input, saat data dimasukkan. Tujuannya mencegah kesalahan sejak awal, bukan membersihkannya setelah bertumpuk. Karena itu, validasi lebih murah dan lebih cepat daripada [data cleansing](#data-cleansing).

Tapi validasi juga perlu dirancang dengan akal sehat. Aturan yang terlalu ketat bisa membuat pengguna mencari jalan pintas, misalnya mengisi kolom dengan data asal agar formulir bisa dikirim. Validasi yang baik membantu, bukan menghalangi.

**Terkait:** [Kualitas Data](#kualitas-data), [Data Cleansing](#data-cleansing), [Prosedur](#prosedur)

## Kesimpulan

Setelah membaca semua istilah tadi, mungkin kelihatan bahwa sistem informasi bukan soal komputer semata.

Di balik portal KRS yang kita buka setiap semester, ada basis data yang menyimpan data, jaringan yang menghubungkan, prosedur yang mengatur, dan orang-orang yang memastikan semuanya berjalan. Kalau salah satu bagian itu lemah, yang kita rasakan di layar mungkin cuma "error" atau "lambat", padahal masalahnya bisa jauh di belakang.

Menariknya, tantangan terbesar sering bukan teknologinya. Integrasi, kualitas data, pelatihan, biaya, dan etika lebih sering menentukan apakah sebuah sistem benar-benar dipakai atau hanya jadi proyek yang diresmikan lalu perlahan ditinggalkan.

Materi ini juga membuat saya melihat istilah-istilah yang tadinya terdengar terpisah jadi saling terhubung. TPS memasok data ke MIS, MIS membantu manajer, EIS meringkas untuk pimpinan, ERP mencoba menyatukan semuanya, dan keamanan harus menjaga di setiap lapisan.

Kalau teman-teman ingin mulai memahami sistem informasi, mulailah dari yang paling dekat: portal kampus, aplikasi bank, atau marketplace yang sering dipakai. Coba petakan enam komponennya, lalu tanyakan satu hal: informasi apa yang sebenarnya ingin dihasilkan sistem ini?

Karena pada akhirnya, sistem informasi bukan dibangun agar datanya rapi di dalam server. Ia dibangun agar seseorang bisa mengambil keputusan yang lebih baik.
