---
title: "Glosarium Pengantar TI Part 5"
date: 2026-11-04T22:16:00+07:00
draft: false
tags: ["Glosarium", "Teknologi Informasi", "Basis Data", "DBMS", "Database", "SQL", "NoSQL", "Perancangan Basis Data", "Normalisasi"]
categories: ["Glosarium", "Teknologi"]
summary: "Glosarium istilah basis data dan DBMS, dari tabel, kunci, dan ERD sampai normalisasi, query processor, arsitektur tiga level, serta pilihan antara relasional dan NoSQL."
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

Ada satu momen kecil yang hampir selalu kita lewati tanpa berpikir: menekan tombol **Simpan**.

Kita mengisi formulir pendaftaran, memilih mata kuliah di portal KRS, menambahkan barang ke keranjang, lalu membayarnya. Setelah tombol ditekan, muncul tulisan "Data berhasil disimpan" berwarna hijau, dan kita lanjut ke urusan berikutnya.

Padahal di antara tombol itu dan tulisan tersebut, ada perjalanan yang cukup panjang.

Data yang kita ketik diperiksa dulu formatnya. Setelah itu diperiksa lagi apakah kita memang berhak mengisi kolom itu. Baru kemudian data ditulis ke media penyimpanan, indeksnya diperbarui, dan aktivitasnya dicatat. Semua itu terjadi dalam hitungan milidetik, dan tidak satu pun bagiannya kita lihat.

Karena tidak terlihat, kita cenderung menyederhanakannya: "database itu ya tempat menyimpan data".

Kalimat itu tidak salah, hanya saja terlalu longgar. Dengan pengertian seperti itu, dua puluh file Excel yang dipisah per bulan dan punya susunan kolom berbeda juga bisa disebut database. Padahal dalam rekayasa, itu belum tentu database.

Materi Pertemuan 10 memberi batas yang lebih jelas: basis data adalah kumpulan data yang saling terhubung secara logis dan disimpan bersama dengan cara tertentu, sehingga bisa dipakai kembali oleh organisasi secara cepat dan efisien. Kata kuncinya bukan "banyak", tetapi **terhubung** dan **bisa dipakai bersama**.

Di situ muncul pemeran kedua, yaitu **DBMS**, perangkat lunak yang berdiri antara kita dan media penyimpanan. Basis data adalah datanya, DBMS adalah perangkat lunak yang menjaganya. Dua hal yang sering disebut sebagai satu hal yang sama.

Sebenarnya, basis data dan DBMS sudah muncul sekilas di [part 4](/posts/glosarium-pengantar-ti-part-4/) sebagai dua dari enam komponen sistem informasi. Waktu itu keduanya cuma lewat sebentar, karena ceritanya memang tentang sistem informasi secara keseluruhan. Di part kelima ini, keduanya jadi pusat cerita, jadi saya bahas ulang lebih dalam.

Sama seperti sebelumnya, istilahnya saya susun alfabetis supaya bisa dibaca dari mana saja. Istilah yang berkaitan saya tautkan, jadi teman-teman bisa mengikuti alurnya tanpa harus mencari manual.

Bagi yang baru mampir, [part 1](/posts/glosarium-pengantar-ti-part-1/), [part 2](/posts/glosarium-pengantar-ti-part-2/), dan [part 3](/posts/glosarium-pengantar-ti-part-3/) sudah membahas dasar perangkat keras dan lunak, istilah cloud dan keamanan, serta profesi di bidang TI.

### Mulai membaca dari mana?

Kalau masih bingung mau mulai dari mana, beberapa jalur ini mungkin bisa membantu:

- **Konsep dasar:** [basis data](#basis-data-database) → [baris](#baris-record) → [kolom](#kolom-atribut) → [tabel](#tabel) → [DBMS](#dbms-database-management-system).

- **Menghubungkan tabel:** [kunci primer](#kunci-primer-primary-key) → [kunci asing](#kunci-asing-foreign-key) → [join](#join) → [redundansi data](#redundansi-data).

- **Merancang sebelum membangun:** [perancangan basis data](#perancangan-basis-data) → [analisis kebutuhan data](#analisis-kebutuhan-data) → [ERD](#erd-entity-relationship-diagram) → [perancangan logis](#perancangan-logis) → [normalisasi](#normalisasi) → [perancangan fisik](#perancangan-fisik) → [indeks](#indeks-index).

- **Di dalam mesinnya:** [query](#query) → [query processor](#query-processor) → [optimizer](#optimizer-query-optimizer) → [database engine](#database-engine) → [katalog metadata](#katalog-metadata-data-dictionary) → [arsitektur tiga level](#arsitektur-tiga-level-three-schema-architecture).

- **Menjaga datanya:** [integritas data](#integritas-data) → [konsistensi data](#konsistensi-data) → [transaksi](#transaksi-transaction) → [akses bersamaan](#akses-bersamaan-concurrency) → [backup dan recovery](#backup-dan-recovery).

- **Memilih jenisnya:** [DBMS hierarkis](#hierarkis-dbms-hierarkis) → [DBMS jaringan](#jaringan-dbms-jaringan) → [RDBMS](#rdbms-relational-database-management-system) → [NoSQL](#nosql) → [skalabilitas horizontal](#skalabilitas-horizontal).

## Isi

## A

### Akses Bersamaan (Concurrency)

**Akses bersamaan** adalah kemampuan basis data melayani banyak pengguna yang membaca dan mengubah data pada waktu yang hampir sama.

Contohnya saat pengisian KRS dibuka. Ribuan mahasiswa membuka halaman yang sama, sebagian hanya melihat jadwal, sebagian menekan tombol simpan. Di sisi lain, staf akademik mungkin sedang mengubah kuota kelas yang sedang diperebutkan.

Kalau tidak diatur, muncul masalah yang cukup klasik. Dua petugas membaca stok barang sebanyak 10. Keduanya sama-sama menjual satu barang. Masing-masing menghitung 10 dikurangi 1, lalu menuliskan 9. Padahal seharusnya 8. Satu penjualan hilang begitu saja, tanpa pesan error apa pun.

DBMS menanganinya dengan penguncian atau mekanisme serupa, sehingga perubahan yang bersamaan disusun ulang seolah terjadi satu per satu. Hasil akhirnya harus sama dengan kalau semua permintaan dijalankan berurutan.

Yang menarik, semakin longgar penguncian, semakin cepat sistemnya, tetapi semakin besar risiko konflik. Semakin ketat, semakin aman, tetapi pengguna bisa saling menunggu. Seperti banyak hal lain di basis data, ini soal memilih harga yang mau dibayar.

**Terkait:** [Transaksi](#transaksi-transaction), [Konsistensi Data](#konsistensi-data), [DBMS](#dbms-database-management-system)

### Analisis Kebutuhan Data

**Analisis kebutuhan data** adalah tahap pertama perancangan basis data: menentukan data apa yang benar-benar dibutuhkan, dari mana sumbernya, dan untuk apa data itu nanti dipakai.

Di tahap ini belum ada tabel, belum ada tipe data, belum ada nama kolom yang final. Yang dilakukan justru wawancara dan pengamatan: siapa yang mencatat, kapan, kepada siapa laporannya diserahkan, dan keputusan apa yang dibuat dari laporan itu.

Contohnya perpustakaan kampus. Kalau langsung membuka aplikasi dan mengetik tabel `buku`, pertanyaan penting justru terlewat. Apakah yang dicatat adalah judul atau juga nomor eksemplar? Kalau satu judul punya lima salinan, bagaimana membedakannya? Apakah denda dihitung per hari? Apakah riwayat pinjaman lama perlu disimpan?

Tahap ini terasa lambat karena hasilnya cuma catatan dan daftar pertanyaan. Tapi kesalahan di sini adalah yang paling mahal. Kolom yang tidak pernah dipakai bisa dihapus nanti, sedangkan data yang tidak pernah dicatat sejak awal sering tidak bisa dikembalikan.

**Terkait:** [Perancangan Basis Data](#perancangan-basis-data), [Perancangan Konseptual](#perancangan-konseptual), [ERD](#erd-entity-relationship-diagram)

### Arsitektur Tiga Level (Three-Schema Architecture)

**Arsitektur tiga level** adalah cara DBMS memisahkan bagaimana data disimpan dari bagaimana pengguna melihatnya.

Level pertama, **eksternal**, adalah yang dilihat pengguna dan aplikasi. Setiap orang hanya melihat bagian yang menjadi haknya. Dosen melihat jadwal dan daftar mahasiswa kelasnya, staf keuangan melihat tagihan, dan mahasiswa melihat nilainya sendiri.

Level kedua, **konseptual**, adalah gambaran logis keseluruhan: seluruh tabel, kolom, relasi, dan aturan integritas dalam satu rancangan. Level inilah yang biasanya tergambar sebagai diagram.

Level ketiga, **internal**, adalah kenyataan fisiknya. Bagaimana data disimpan, diindeks, diurutkan, dan dikompresi di media penyimpanan.

Manfaat utamanya bukan sekadar kerapian. Kalau cara penyimpanan di level internal diubah, misalnya memindahkan tabel ke partisi lain atau menambah indeks, tampilan yang dipakai pengguna tidak perlu ikut berubah. Sebaliknya, bagian yang sensitif bisa disembunyikan di level eksternal tanpa mengubah datanya.

Inilah yang disebut kemandirian data, dan inilah yang membuat satu basis data bisa melayani banyak aplikasi dengan kebutuhan berbeda tanpa saling mengganggu.

**Terkait:** [View](#view), [DBMS](#dbms-database-management-system), [Database Engine](#database-engine)

## B

### Backup dan Recovery

**Backup** adalah salinan data yang disimpan terpisah, sedangkan **recovery** adalah proses mengembalikan data dari salinan itu ketika terjadi masalah.

Keduanya adalah fungsi keempat DBMS, dan mungkin fungsi yang paling jarang terasa sampai benar-benar dibutuhkan.

Bayangkan hard disk server rusak pada Jumat sore. Senin pagi sistem sudah berjalan lagi, tetapi datanya hanya sampai Kamis. Artinya seluruh transaksi sehari hilang: penjualan, absensi, pengajuan, dan apa pun yang terjadi di antara keduanya. Organisasi memang selamat, tapi harus membayar dengan kehilangan data dan waktu.

Ada beberapa hal yang sering terlewat. Pertama, backup yang tidak pernah dicoba dipulihkan belum bisa disebut backup, karena kita tidak tahu apakah filenya benar-benar bisa dipakai. Kedua, backup bukan arsip. Backup dibuat untuk mengembalikan keadaan, sedangkan arsip disimpan untuk dirujuk di kemudian hari, dan keduanya punya aturan simpan yang berbeda.

Ketiga, yang paling tidak nyaman: backup harus disimpan di tempat yang tidak ikut rusak ketika server utamanya rusak. Salinan yang menempel di mesin yang sama hanya melindungi dari salah hapus, bukan dari kebakaran atau ransomware.

**Terkait:** [DBMS](#dbms-database-management-system), [Integritas Data](#integritas-data), [Transaksi](#transaksi-transaction)

### Baris (Record)

**Baris** atau *record* adalah satu objek utuh di dalam tabel. Kalau tabelnya daftar mahasiswa, satu baris berarti satu mahasiswa.

Satu baris berisi banyak kolom sekaligus: NPM, nama, program studi, angkatan, dan status. Karena itu, kalimat seperti "saya menambah satu data" sebenarnya berarti "saya menambah satu baris yang berisi beberapa nilai".

Membedakan baris dan kolom terdengar sepele, tetapi menentukan banyak hal. Jumlah baris menunjukkan berapa banyak objek yang tercatat, sedangkan jumlah kolom menunjukkan berapa banyak fakta yang disimpan tentang objek itu.

Kesalahan yang sering terjadi justru di titik ini. Orang menambah kolom baru setiap kali ada mahasiswa baru, misalnya `mahasiswa_1`, `mahasiswa_2`, dan seterusnya. Tabelnya jadi melebar, bukan memanjang. Secara teknis masih bisa dibuka, tetapi pencarian, pelaporan, dan pembaruannya menjadi mimpi buruk.

**Terkait:** [Tabel](#tabel), [Kolom](#kolom-atribut), [Kunci Primer](#kunci-primer-primary-key)

### Basis Data (Database)

**Basis data** adalah kumpulan data yang saling terhubung secara logis dan disimpan bersama dengan cara tertentu, sehingga dapat dimanfaatkan kembali secara cepat, mudah, dan efisien.

Definisi ini muncul di materi dengan dua kutipan yang saling melengkapi. Kadir (2014) menekankan data yang terhubung dan disimpan tanpa redundansi untuk memenuhi kebutuhan pengguna di berbagai aplikasi. Date (2004) menekankan keterorganisasian agar data bisa dipakai oleh berbagai platform aplikasi.

Perhatikan bahwa tidak ada satu pun bagian definisi itu yang menyebut merk perangkat lunak.

Bedanya dengan tumpukan file bukan soal jumlah atau ukuran. Dua puluh file Excel penjualan, satu per bulan, masing-masing dengan susunan kolom sendiri, tetap bukan basis data dalam arti rekayasa. Tidak ada yang menjamin kolomnya sama, tidak ada yang mencegah satu transaksi tercatat dua kali, dan tidak ada yang mengatur apa yang terjadi kalau dua orang membukanya bersamaan.

Basis data menuntut lima hal sekaligus: data yang terhubung secara logis, perangkat keras sebagai tempatnya, perangkat lunak yang mengelolanya, pengguna yang mengisinya, dan prosedur yang mengatur cara kerjanya. Kalau satu bagian hilang, sisanya tetap ada, tetapi tidak lagi menjadi basis data yang bisa dipercaya.

Karena itu, kalimat "kita punya banyak data" belum tentu kabar baik. Pertanyaan yang lebih berguna: data itu terhubung dengan apa, dan siapa yang menjamin isinya tetap konsisten besok?

**Terkait:** [DBMS](#dbms-database-management-system), [Tabel](#tabel), [File Flat](#file-flat-flat-file)

## D

### Data Terstruktur dan Tidak Terstruktur

**Data terstruktur** adalah data yang bentuknya sudah ditentukan sejak awal, seperti tabel dengan kolom dan tipe yang tetap. **Data tidak terstruktur** adalah data yang tidak mengikuti bentuk itu, misalnya teks bebas, gambar, audio, dan video. Di antaranya ada **data semi-terstruktur**, seperti JSON atau log, yang punya penanda tetapi tidak kaku.

Perbedaan ini bukan sekadar istilah, karena menentukan pilihan perangkatnya.

Nilai mahasiswa, absensi, dan transaksi penjualan adalah data terstruktur. Semuanya pas disimpan dalam tabel, dan semuanya menuntut ketepatan. Rekaman konsultasi dosen, komentar di media sosial, atau foto kondisi barang adalah data tidak terstruktur. Bentuknya beragam, ukurannya besar, dan tidak semua bagiannya perlu dipecah menjadi kolom.

Di sinilah pilihan antara [RDBMS](#rdbms-relational-database-management-system) dan [NoSQL](#nosql) mulai masuk akal. Bukan karena salah satunya lebih modern, tetapi karena bentuk datanya berbeda. Memaksa data tidak terstruktur masuk ke tabel biasanya berakhir dengan kolom-kolom kosong dan tabel tambahan yang tidak jelas gunanya.

**Terkait:** [NoSQL](#nosql), [RDBMS](#rdbms-relational-database-management-system), [Model Data](#model-data)

### Database Engine

**Database engine** adalah inti dari DBMS. Bagian inilah yang benar-benar menulis, membaca, dan mengubah data di media penyimpanan, berhubungan langsung dengan sistem file dan perangkat keras.

Kalau DBMS diibaratkan sebuah mobil, engine adalah mesinnya. Pengguna menyentuh kemudi dan pedal, tetapi yang menggerakkan roda ada di dalam.

Karena bekerja paling dekat dengan disk, engine juga yang paling banyak berurusan dengan hal-hal yang tidak terlihat: menyusun data dalam blok, menjaga urutan penulisan, mencatat perubahan sebelum benar-benar diterapkan, dan memastikan tidak ada penulisan setengah jadi ketika listrik tiba-tiba mati.

Di sinilah letak jawaban atas pertanyaan yang sering muncul: kalau proses menyimpan terputus di tengah jalan, apakah datanya rusak? Pada sistem yang dirancang baik, jawabannya tidak, karena engine punya mekanisme untuk menyelesaikan atau membatalkan pekerjaan yang belum tuntas.

**Terkait:** [DBMS](#dbms-database-management-system), [Query Processor](#query-processor), [Transaksi](#transaksi-transaction)

### DBMS (Database Management System)

**DBMS** adalah perangkat lunak yang digunakan untuk membuat, mengelola, dan memelihara basis data. Ia menghubungkan pengguna dengan data fisik yang tersimpan di media penyimpanan.

Kalau tadi basis data adalah datanya, DBMS adalah lapisan perangkat lunaknya. Kita meminta informasi dengan bahasa yang kita pahami, dan DBMS yang memikirkan cara menemukannya di perangkat keras.

Perbedaan ini sering tertukar dalam percakapan sehari-hari. Kalimat "database-nya MySQL" sebenarnya keliru, karena MySQL adalah DBMS, sedangkan basis datanya adalah kumpulan tabel yang kita buat di dalamnya. Kesalahan kecil, tetapi akibatnya cukup jauh ketika berdiskusi soal arsitektur.

DBMS punya empat fungsi utama. Ia menyimpan dan mengambil data secara terstruktur. Ia menjaga keamanan, konsistensi, dan integritas data. Ia mengatur akses banyak pengguna sekaligus beserta hak masing-masing. Dan ia menyediakan pencadangan serta pemulihan ketika terjadi kerusakan.

Di dalamnya ada tiga komponen yang bekerja bersama: [database engine](#database-engine) yang menyentuh penyimpanan, [katalog metadata](#katalog-metadata-data-dictionary) yang menyimpan definisi struktur, dan [query processor](#query-processor) yang menerjemahkan perintah kita.

Ketiganya menjelaskan satu hal sederhana: kita bisa memakai basis data tanpa tahu di mana datanya berada secara fisik. Itu bukan kebetulan, tetapi hasil rancangan.

**Terkait:** [Basis Data](#basis-data-database), [Arsitektur Tiga Level](#arsitektur-tiga-level-three-schema-architecture), [Query Processor](#query-processor)

### Denormalisasi

**Denormalisasi** adalah penggabungan kembali tabel yang sudah dinormalisasi, dilakukan dengan sengaja demi kecepatan.

Contohnya dasbor penjualan yang setiap kali dibuka harus menggabungkan enam tabel: pesanan, pelanggan, produk, kategori, pengiriman, dan pembayaran. Hasilnya benar, tetapi lambat, karena pekerjaan yang sama diulang ribuan kali sehari.

Salah satu jalan keluarnya adalah menyimpan sebagian hasil gabungan itu di satu tabel ringkasan. Ketika dasbor dibuka, datanya sudah siap. Pelaporan jadi jauh lebih cepat.

Harganya juga jelas: redundansi kembali muncul, dan konsistensi harus dijaga dengan cara lain, misalnya diperbarui berkala atau lewat proses tersendiri. Kalau prosesnya lupa dijalankan, angka di dasbor bisa berbeda dari data aslinya.

Karena itu, denormalisasi adalah keputusan sadar setelah normalisasi, bukan jalan pintas karena malas memisahkan tabel. Urutannya penting: pahami dulu bentuk yang benar, baru putuskan di mana kecepatan lebih penting daripada kerapian.

**Terkait:** [Normalisasi](#normalisasi), [Redundansi Data](#redundansi-data), [Indeks](#indeks-index)

## E

### ERD (Entity Relationship Diagram)

**ERD** adalah gambaran konseptual data yang menampilkan entitas, atribut, dan relasi antar data, dibuat sebelum apa pun dibangun.

Entitas adalah hal yang ingin dicatat, misalnya Mahasiswa, Buku, dan Peminjaman. Atribut adalah fakta tentang entitas itu, misalnya judul dan tahun terbit. Relasi menunjukkan bagaimana entitas saling berhubungan, misalnya mahasiswa meminjam buku.

Yang membuat ERD berguna bukan gambarnya, tetapi pertanyaan yang dipaksanya muncul. Apakah satu mahasiswa boleh meminjam buku yang sama dua kali? Kalau satu judul punya banyak salinan, apakah yang dipinjam bukunya atau eksemplarnya? Kalau buku hilang, apakah riwayat pinjamannya ikut terhapus?

Relasi banyak-ke-banyak juga terlihat jelas di sini. Mahasiswa bisa meminjam banyak buku, dan satu buku bisa dipinjam banyak mahasiswa. Bentuk seperti ini tidak bisa ditampung satu tabel saja, sehingga nanti di tahap logis akan muncul tabel penghubung.

Karena itu, ERD sering disebut bahasa bersama. Pustakawan bisa memeriksa apakah aturan peminjaman sudah benar, tanpa perlu tahu apa itu kunci asing.

**Terkait:** [Perancangan Konseptual](#perancangan-konseptual), [Perancangan Logis](#perancangan-logis), [Kunci Asing](#kunci-asing-foreign-key)

## F

### File Flat (Flat File)

**File flat** adalah data yang disimpan dalam satu tabel besar di satu file, tanpa relasi ke file lain.

Ini bentuk paling tua dan paling mudah dipahami. Satu file berisi semua kolom yang dibutuhkan, dan setiap baris berdiri sendiri. Banyak pekerjaan sehari-hari memang dimulai dari sini, dan untuk keperluan kecil cara ini masih memadai.

Masalahnya muncul ketika datanya tumbuh dan dipakai lebih dari satu orang.

Pertama, redundansi. Nama dan nomor telepon dosen diketik ulang di setiap baris mata kuliah yang diampu. Ketika nomornya berubah, ada dua ratus baris yang harus diperbarui, dan satu yang terlewat sudah cukup untuk membuat data saling bertentangan.

Kedua, tidak ada penjagaan. Tidak ada yang mencegah nilai diisi 150, atau tanggal lahir diisi tahun depan, atau satu mahasiswa tercatat dua kali dengan ejaan berbeda.

Ketiga, akses bersamaan. Ketika file dibuka dua orang, salah satu versinya akan menimpa yang lain tanpa peringatan.

File flat tidak salah untuk datanya sendiri. Ia hanya cepat menjadi beban ketika data itu mulai dipakai bersama, dan di situlah basis data mulai punya alasan untuk ada.

**Terkait:** [Basis Data](#basis-data-database), [Redundansi Data](#redundansi-data), [Integritas Data](#integritas-data)

## H

### Hierarkis (DBMS Hierarkis)

**DBMS hierarkis** menyimpan data dalam struktur pohon: satu induk bisa punya banyak anak, tetapi satu anak hanya punya satu induk.

Model ini terasa alami untuk hal-hal yang memang bertingkat. Struktur organisasi, bagan akun keuangan, dan daftar komponen sebuah produk adalah contoh yang mudah dibayangkan. Selama strukturnya tetap, aksesnya sangat cepat.

Kekurangannya muncul ketika struktur itu perlu berubah. Menambah relasi baru di luar pohon bukan pekerjaan mudah, dan hubungan banyak-ke-banyak tidak bisa ditampung secara langsung.

Bayangkan satu mata kuliah yang diampu dua dosen. Dalam pohon, setiap anak hanya punya satu induk, jadi salah satu dosen harus dijadikan induk dan yang lain... ditaruh di mana? Jawabannya biasanya: diduplikasi. Di sinilah masalahnya mulai terasa.

Meski begitu, model ini belum mati. Sistem lama di perbankan dan pemerintahan masih berjalan di atasnya, beberapa di antaranya sudah berusia puluhan tahun. Menggantinya berisiko, sehingga yang dilakukan lebih sering adalah membungkusnya dengan antarmuka yang lebih baru.

Contoh yang disebut di materi adalah IBM IMS.

**Terkait:** [Jaringan (DBMS Jaringan)](#jaringan-dbms-jaringan), [Model Data](#model-data), [RDBMS](#rdbms-relational-database-management-system)

## I

### Indeks (Index)

**Indeks** adalah struktur tambahan yang mempercepat pencarian data, seperti indeks di bagian belakang sebuah buku.

Tanpa indeks, ketika kita mencari satu mahasiswa berdasarkan NPM, DBMS harus memeriksa baris satu per satu dari awal sampai ketemu. Cara ini disebut pemindaian penuh, dan untuk tabel berisi ratusan ribu baris, waktunya terasa.

Dengan indeks, DBMS tahu persis di mana harus melompat. Sama seperti kita tidak membaca seluruh buku untuk menemukan satu istilah, cukup membuka indeksnya.

Tapi indeks bukan gratis. Setiap kali data ditambah, diubah, atau dihapus, indeksnya juga harus diperbarui. Ruang penyimpanannya juga bertambah. Karena itu, tabel yang isinya lebih sering diperbarui daripada dibaca bisa jadi lebih lambat kalau diberi terlalu banyak indeks.

Pelajaran yang sering baru disadari setelah sistem berjalan: indeks yang salah bisa membebani sama seperti tidak punya indeks. Yang perlu diindeks adalah kolom yang benar-benar dipakai untuk mencari dan mengurutkan, bukan semua kolom sekaligus.

**Terkait:** [Perancangan Fisik](#perancangan-fisik), [Optimizer (Query Optimizer)](#optimizer-query-optimizer), [Kunci Primer](#kunci-primer-primary-key)

### Integritas Data

**Integritas data** adalah jaminan bahwa data yang tersimpan tetap sah, sesuai aturan, dan tidak saling bertentangan.

Aturannya bisa sederhana: nilai harus berupa angka antara 0 dan 100, NPM harus unik, tanggal tidak boleh di masa depan, kolom nama tidak boleh kosong. Bisa juga berupa hubungan: baris di tabel KRS tidak boleh menunjuk mata kuliah yang tidak ada.

Yang membedakannya dari validasi di aplikasi adalah tempat aturan itu ditegakkan. Validasi di aplikasi berjalan ketika data masuk lewat aplikasi. Integritas di basis data tetap berlaku walaupun data masuk lewat jalur lain, misalnya skrip impor, perbaikan manual, atau aplikasi lama yang masih dipakai.

Contoh nyata: nilai 150 untuk skala 0–100. Kalau aturannya hanya ada di formulir aplikasi, data tetap bisa masuk lewat unggahan Excel. Kalau aturannya juga ada di basis data, unggahan itu akan ditolak.

Karena itu, integritas bukan soal tegas-tegasan, tetapi soal berlapis. Semakin penting datanya, semakin banyak lapisan yang sebaiknya memeriksanya.

**Terkait:** [Konsistensi Data](#konsistensi-data), [Kunci Asing](#kunci-asing-foreign-key), [Transaksi](#transaksi-transaction)

## J

### Jaringan (DBMS Jaringan)

**DBMS jaringan** memungkinkan satu data memiliki lebih dari satu hubungan, sehingga lebih fleksibel daripada model hierarkis.

Kalau pohon hanya mengizinkan satu induk, model jaringan mengizinkan banyak jalur. Satu mata kuliah bisa terhubung ke dua dosen, satu dosen ke beberapa mata kuliah, dan seterusnya, tanpa harus menduplikasi data.

Untuk data yang hubungannya padat, cara ini memberi akses yang cepat. Contoh penerapannya adalah Integrated Data Store (IDS) dan IDMS.

Tapi fleksibilitas itu dibayar dengan kerumitan. Strukturnya lebih sulit digambarkan, lebih sulit dipelajari, dan pemrogramannya menuntut keahlian khusus. Bagi orang yang baru mengenal basis data, model ini terasa seperti peta jalan yang saling bersilangan tanpa penunjuk arah.

Sejarahnya menarik: model jaringan adalah jawaban atas kekakuan model hierarkis. Yang kemudian menang justru bukan yang paling fleksibel, melainkan yang paling mudah dipahami. Model relasional mengambil jalan tengah, dan itu cukup.

**Terkait:** [Hierarkis (DBMS Hierarkis)](#hierarkis-dbms-hierarkis), [Model Relasional](#model-relasional), [Model Data](#model-data)

### Join

**Join** adalah operasi menggabungkan dua tabel atau lebih berdasarkan kunci yang menghubungkan keduanya.

Contohnya menampilkan daftar mata kuliah yang diambil seorang mahasiswa. Nama mahasiswa ada di tabel mahasiswa, daftar mata kuliah yang diambil ada di tabel KRS, dan nama mata kuliahnya sendiri ada di tabel mata kuliah. Ketiganya perlu disatukan agar hasilnya bisa dibaca manusia.

Tanpa join, pilihan yang tersisa adalah menyalin nama mata kuliah ke setiap baris KRS. Datanya jadi mudah dibaca, tetapi setiap perubahan nama mata kuliah harus diulang di semua baris. Itu kembali ke masalah [redundansi](#redundansi-data).

Join jugalah yang membuat dua tabel terasa seperti satu kesatuan bagi pengguna. Aplikasi cukup mengirim satu perintah, dan DBMS yang menyusun hasilnya.

Menariknya, NoSQL sering tidak menyediakan join. Bukan karena tidak mampu, tetapi karena pilihan rancangannya berbeda: data yang biasanya digabung justru disimpan bersama sejak awal, supaya tidak perlu digabung saat dibaca. Harga yang dibayar adalah duplikasi, dan keputusan seperti ini selalu punya dua sisi.

**Terkait:** [Kunci Asing](#kunci-asing-foreign-key), [RDBMS](#rdbms-relational-database-management-system), [NoSQL](#nosql)

## K

### Katalog Metadata (Data Dictionary)

**Katalog metadata** atau *data dictionary* adalah tempat DBMS menyimpan definisi struktur data: nama tabel, daftar kolom, tipe data, indeks, relasi, kunci primer, kunci asing, dan aturan integritas.

Isinya bukan data mahasiswa, tetapi keterangan tentang data mahasiswa. Semacam daftar isi, kamus, dan denah gudang yang digabung menjadi satu.

Berkat katalog inilah DBMS tahu bagaimana data disusun. Ketika kita menulis `SELECT nama FROM mahasiswa`, DBMS tidak menebak. Ia memeriksa katalog: apakah tabel `mahasiswa` ada, apakah kolom `nama` ada, tipe datanya apa, dan indeks apa yang bisa dipakai.

Katalog juga yang membuat validasi mungkin dilakukan sebelum data ditulis. Menambah kolom dengan nama yang sudah ada, atau menghapus tabel yang masih dirujuk tabel lain, akan ditolak di sini.

Bagi pengguna, bagian ini sepenuhnya tidak terlihat. Bagi yang pernah membuka basis data yang diwarisi dari orang lain tanpa dokumentasi, katalog sering jadi satu-satunya peta yang tersisa.

**Terkait:** [DBMS](#dbms-database-management-system), [Skema](#skema-schema), [Integritas Data](#integritas-data)

### Kolom (Atribut)

**Kolom** atau *atribut* adalah satu jenis fakta yang disimpan untuk setiap baris dalam tabel. Kolom `nama` menyimpan nama, kolom `angkatan` menyimpan tahun masuk.

Setiap kolom punya tipe data, dan pilihan tipe ini bukan urusan teknis semata. Menyimpan tanggal lahir sebagai teks membuat pengurutan dan perhitungan umur menjadi rumit. Menyimpan NPM sebagai angka menghilangkan nol di depan. Menyimpan nomor telepon sebagai angka membuat tanda plus dan strip tidak bisa dipakai.

Keputusan kecil seperti ini punya efek panjang. Tipe yang tepat membantu validasi, menghemat ruang, dan mempercepat pencarian. Tipe yang salah memaksa aplikasi menambal di kemudian hari, biasanya dengan konversi yang berlapis dan mudah salah.

Selain tipe, kolom juga punya aturan: boleh kosong atau tidak, harus unik atau tidak, punya nilai bawaan atau tidak, dan boleh bernilai apa saja.

**Terkait:** [Baris (Record)](#baris-record), [Tabel](#tabel), [Skema](#skema-schema)

### Konsistensi Data

**Konsistensi data** adalah keadaan di mana data tidak saling bertentangan satu sama lain.

Contohnya sederhana. Stok barang tercatat 0, tetapi barangnya masih bisa dipesan. Nilai tercatat untuk mata kuliah yang tidak pernah diambil. Tanggal lahir di satu sistem 1999, di sistem lain 1998, untuk orang yang sama.

Sumbernya bisa macam-macam: redundansi yang tidak terkendali, akses bersamaan yang tidak diatur, kesalahan input, atau integrasi antar sistem yang berjalan tidak serempak.

Basis data membantu menjaga konsistensi lewat aturan, transaksi, dan penguncian. Tapi ada batas yang perlu diakui: basis data hanya bisa menjaga konsistensi bentuk, bukan kebenaran isi. Kalau yang diketik memang salah, sistem bisa menyimpannya dengan sangat rapi.

Karena itu, konsistensi teknis dan kebenaran data adalah dua hal berbeda. Yang pertama bisa dijamin oleh perangkat lunak. Yang kedua tetap menuntut prosedur, pelatihan, dan orang yang teliti.

**Terkait:** [Integritas Data](#integritas-data), [Transaksi](#transaksi-transaction), [Redundansi Data](#redundansi-data)

### Kunci Asing (Foreign Key)

**Kunci asing** adalah kolom yang menunjuk kunci primer di tabel lain.

Contohnya tabel KRS punya kolom `npm` yang menunjuk tabel mahasiswa, dan kolom `kode_mk` yang menunjuk tabel mata kuliah. Dengan begitu, setiap baris KRS tahu ia milik mahasiswa yang mana dan untuk mata kuliah apa.

Fungsinya bukan sekadar penghubung, tetapi penjaga. Basis data akan menolak baris KRS yang menunjuk mahasiswa yang tidak ada. Ia juga bisa menolak penghapusan mahasiswa yang masih punya riwayat KRS, atau menghapus riwayatnya sekaligus kalau aturannya memang begitu.

Di sinilah frasa "terhubung secara logis" pada definisi basis data menjadi konkret. Data tidak hanya disimpan berdekatan, tetapi benar-benar saling merujuk, dan rujukannya dijaga.

Yang perlu diputuskan saat merancang bukan hanya kolom mana yang jadi kunci asing, tetapi apa yang terjadi ketika data induknya berubah atau hilang. Menolak, mengosongkan, atau ikut menghapus, ketiganya punya konsekuensi yang berbeda.

**Terkait:** [Kunci Primer](#kunci-primer-primary-key), [Integritas Data](#integritas-data), [Join](#join)

### Kunci Primer (Primary Key)

**Kunci primer** adalah kolom yang mengenali setiap baris secara unik. Tidak ada dua baris dengan nilai yang sama, dan nilainya tidak boleh kosong.

Pada tabel mahasiswa, NPM bisa menjadi kunci primer karena tidak ada dua mahasiswa dengan NPM yang sama. Pada tabel peminjaman, tidak ada satu kolom pun yang benar-benar unik, sehingga biasanya dibuat kolom `id_pinjam` berisi nomor urut.

Perbedaan ini penting. Kunci alami berasal dari data itu sendiri, seperti NPM atau nomor induk karyawan. Kunci buatan dibuat khusus untuk keperluan basis data.

Kunci alami terasa lebih bermakna, tetapi berisiko ketika nilainya berubah. Kalau kebijakan kampus mengganti format NPM, seluruh tabel yang merujuknya harus ikut diperbarui. Kunci buatan tidak punya masalah itu karena tidak berarti apa-apa selain pengenal.

Karena kunci primer dipakai sebagai rujukan oleh tabel lain, memilihnya adalah keputusan jangka panjang, bukan sekadar kolom pertama yang terlihat unik.

**Terkait:** [Kunci Asing](#kunci-asing-foreign-key), [Tabel](#tabel), [Indeks](#indeks-index)

## M

### Model Data

**Model data** menggambarkan struktur logis basis data: bagaimana data saling berhubungan dan batasan apa yang berlaku.

Model ini bukan format file dan bukan merk perangkat lunak. Ia lebih mirip cara berpikir. Kalau data disusun bertingkat, modelnya hierarkis. Kalau hubungannya bercabang bebas, modelnya jaringan. Kalau disusun sebagai tabel yang dihubungkan kunci, modelnya relasional. Kalau data dan pengolahnya dibungkus sebagai objek, modelnya berorientasi objek.

Materi menyebut empat model ini, dan hampir semuanya masih dipakai di suatu tempat. Yang paling banyak dipakai sekarang adalah relasional, sedangkan yang paling tua masih bertahan di sistem perbankan dan pemerintahan.

Memahami model data membantu kita membaca sistem yang tidak kita bangun sendiri. Ketika melihat aplikasi lama yang datanya tersimpan dalam struktur pohon, kita tahu mengapa menambah relasi baru terasa begitu sulit. Bukan karena programnya malas diperbarui, tetapi karena modelnya memang tidak dirancang untuk itu.

**Terkait:** [Model Relasional](#model-relasional), [Hierarkis (DBMS Hierarkis)](#hierarkis-dbms-hierarkis), [Perancangan Konseptual](#perancangan-konseptual)

### Model Relasional

**Model relasional** menyimpan data dalam bentuk tabel. Setiap baris adalah record, setiap kolom adalah atribut, dan hubungan antar tabel diatur lewat kunci.

Ini model yang paling banyak dipakai saat ini. Hampir semua sistem yang kita pakai sehari-hari, mulai dari portal kampus, aplikasi bank, sampai marketplace, menyimpan datanya dengan cara seperti ini.

Kekuatannya justru karena kesederhanaannya. Satu tabel mewakili satu jenis objek. Hubungan tidak disimpan dengan menumpuk semuanya di satu tempat, tetapi dengan merujuk. Karena bentuknya seragam, pertanyaan apa pun bisa dijawab dengan bahasa yang sama, yaitu SQL.

Kesederhanaan itu bukan karena model ini kurang canggih. Justru sebaliknya: ia sengaja membatasi diri pada satu bentuk, karena bentuk itu ternyata cukup untuk sangat banyak hal.

Yang perlu diingat, "relasional" di sini mengacu pada hubungan antar tabel yang dijaga oleh kunci, bukan pada hubungan sosial antar data. Istilah aslinya berakar pada gagasan tabel sebagai relasi dalam matematika, dan itulah yang membuatnya bisa dijelaskan secara formal.

**Terkait:** [RDBMS](#rdbms-relational-database-management-system), [Tabel](#tabel), [Kunci Primer](#kunci-primer-primary-key)

## N

### Normalisasi

**Normalisasi** adalah proses menyusun tabel agar redundansi berkurang dan anomali pengolahan hilang, dilakukan lewat beberapa tingkatan yang biasa disebut bentuk normal.

Contohnya tabel mata kuliah yang mengulang nama lengkap dan nomor telepon dosen di setiap baris. Secara sekilas tidak masalah. Tapi begitu nomor telepon berubah, ada dua ratus baris yang harus diperbarui, dan satu yang terlewat sudah cukup untuk membuat data saling bertentangan.

Masalah seperti ini disebut anomali. Ada anomali pembaruan, ketika perubahan yang seharusnya satu tempat harus diulang di banyak tempat. Ada anomali penyisipan, ketika kita tidak bisa menambah data baru tanpa memaksa data lain ikut terisi. Ada juga anomali penghapusan, ketika menghapus satu baris tanpa sengaja menghilangkan informasi lain.

Normalisasi menyelesaikannya dengan memisahkan data ke tabel yang tepat. Nama dosen pindah ke tabel dosen, dan tabel mata kuliah cukup menyimpan rujukan ke dosen itu. Hasilnya lebih banyak tabel, tetapi setiap fakta disimpan satu kali.

Tapi normalisasi bukan tujuan akhir. Ia alat untuk menghindari masalah, bukan lomba mencapai bentuk normal tertinggi. Kalau kebutuhan pelaporan menuntut sebaliknya, [denormalisasi](#denormalisasi) yang disengaja bisa jadi pilihan yang lebih masuk akal.

**Terkait:** [Denormalisasi](#denormalisasi), [Redundansi Data](#redundansi-data), [Perancangan Logis](#perancangan-logis)

### NoSQL

**NoSQL** adalah istilah untuk basis data yang tidak mengikuti model relasional ketat. Namanya berasal dari *Not Only SQL*, dan cakupannya cukup luas.

Bentuknya bermacam-macam. Basis data dokumen menyimpan data sebagai dokumen mirip JSON, seperti MongoDB. Basis data key-value menyimpan pasangan kunci dan nilai, seperti Redis. Basis data wide column menyimpan data dalam keluarga kolom yang lebar, seperti Cassandra. Basis data graph menyimpan simpul dan hubungan, seperti Neo4j.

Kelebihannya jelas: fleksibel karena tidak menuntut skema tetap, bisa menambah kapasitas dengan menambah mesin, dan cepat untuk baca-tulis dalam volume besar. Cocok untuk data sensor, log, linimasa media sosial, dan katalog produk yang bentuknya berubah-ubah.

Kekurangannya juga perlu disebut. NoSQL kurang cocok untuk aplikasi yang menuntut konsistensi tinggi dan transaksi kompleks, karena sebagian besar rancangannya memilih ketersediaan dan kecepatan di atas itu. Tidak semua NoSQL mendukung join, dan tidak semua memakai SQL standar.

Karena itu, pertanyaan yang tepat bukan "relasional atau NoSQL, mana yang lebih modern", melainkan "janji apa yang harus ditepati sistem ini". Kalau janjinya ketepatan transaksi, relasional lebih aman. Kalau janjinya menampung data yang terus mengalir, NoSQL lebih masuk akal. Banyak organisasi nyata memakai keduanya sekaligus, masing-masing untuk pekerjaan yang paling cocok.

**Terkait:** [RDBMS](#rdbms-relational-database-management-system), [Data Terstruktur dan Tidak Terstruktur](#data-terstruktur-dan-tidak-terstruktur), [Skalabilitas Horizontal](#skalabilitas-horizontal)

## O

### Optimizer (Query Optimizer)

**Optimizer** adalah bagian dari [query processor](#query-processor) yang mencari cara paling efisien untuk menjalankan sebuah perintah.

Satu query yang sama biasanya bisa dijalankan dengan banyak cara. Misalnya `SELECT nama FROM mahasiswa WHERE prodi = 'Teknologi Informasi'`. DBMS bisa memindai seluruh tabel, bisa memakai indeks pada kolom prodi, dan kalau query-nya melibatkan beberapa tabel, urutan penggabungannya juga bisa berbeda-beda.

Setiap cara punya biaya yang berbeda, dan selisihnya bisa jauh. Pada tabel berisi sepuluh ribu baris, perbedaannya mungkin tidak terasa. Pada tabel berisi sepuluh juta baris, satu pilihan yang salah bisa membuat laporan yang tadinya selesai dalam hitungan detik berubah menjadi menit.

Untuk memilih, optimizer memakai perkiraan biaya berdasarkan statistik data: berapa banyak baris, sebaran nilainya seperti apa, dan indeks apa yang tersedia.

Di sinilah muncul salah satu penyebab query lambat yang paling jarang disadari: statistiknya sudah basi. Datanya bertambah banyak, tetapi perkiraan DBMS masih berdasarkan keadaan enam bulan lalu. Query-nya tidak berubah, rencananya yang berubah. Karena itu, kadang yang perlu diperbarui bukan servernya, melainkan statistiknya.

**Terkait:** [Query Processor](#query-processor), [Indeks](#indeks-index), [Query](#query)

## P

### Perancangan Basis Data

**Perancangan basis data** adalah tahap menyusun struktur data sebelum sistem dibangun, dengan tujuan menghasilkan struktur yang efisien, logis, dan sesuai kebutuhan nyata organisasi.

Materi membaginya menjadi empat tahap yang berurutan: [analisis kebutuhan data](#analisis-kebutuhan-data), [perancangan konseptual](#perancangan-konseptual), [perancangan logis](#perancangan-logis), dan [perancangan fisik](#perancangan-fisik).

Urutannya bukan formalitas. Setiap tahap menetapkan hal yang dipakai tahap berikutnya. Kebutuhan menentukan entitas apa yang perlu digambar. Gambaran itu menentukan tabel apa yang dibuat. Tabel itu menentukan bagaimana penyimpanan fisiknya diatur.

Kalau dua tahap pertama dilewati, akibatnya tidak langsung terlihat. Aplikasi tetap bisa jalan, tabel tetap bisa dibuat. Tapi biayanya muncul di tahap keempat, dan kemudian di setiap laporan yang dibangun sesudahnya: query yang berbelit, data yang terduplikasi, dan kolom yang tidak pernah dipakai tetapi tidak berani dihapus.

Ibarat membangun rumah. Membeli material dulu lalu menyesuaikan denahnya memang mungkin, tetapi setiap perubahan setelah dinding berdiri jauh lebih mahal daripada perubahan di atas kertas.

**Terkait:** [Analisis Kebutuhan Data](#analisis-kebutuhan-data), [Perancangan Logis](#perancangan-logis), [Normalisasi](#normalisasi)

### Perancangan Fisik

**Perancangan fisik** adalah tahap keempat: menentukan bagaimana data benar-benar disimpan di media penyimpanan, termasuk pengaturan indeks, partisi, dan strategi akses.

Di tahap ini pertanyaannya berubah dari "data apa yang dibutuhkan" menjadi "bagaimana data itu dibaca paling cepat". Apakah tabel perlu dipecah berdasarkan tahun? Kolom mana yang perlu indeks? Data lama yang jarang dibuka sebaiknya disimpan di media yang lebih murah?

Keputusan di sini sangat bergantung pada perangkat lunak yang dipakai dan pola pemakaiannya. Query yang paling sering dijalankan menentukan indeks apa yang layak dibuat, dan seberapa sering data diperbarui menentukan indeks apa yang justru membebani.

Yang menarik, ini tahap terakhir tetapi paling sering dijadikan titik awal. Banyak orang langsung membuka DBMS, membuat tabel, lalu bingung ketika aplikasinya membesar dan mulai lambat. Padahal masalahnya sering bukan di pengaturan penyimpanan, melainkan di struktur yang belum pernah dirancang.

**Terkait:** [Perancangan Basis Data](#perancangan-basis-data), [Indeks](#indeks-index), [Denormalisasi](#denormalisasi)

### Perancangan Konseptual

**Perancangan konseptual** adalah tahap kedua: menggambarkan data secara abstrak, biasanya dalam bentuk ERD, sebelum apa pun dibangun.

Di tahap ini belum ada tipe data konkret, belum ada nama tabel yang final, dan belum diputuskan memakai DBMS apa. Yang dibuat adalah gambaran: entitas apa yang ada, atribut apa yang melekat padanya, dan bagaimana entitas itu saling berhubungan.

Justru karena belum terikat produk, tahap ini bisa didiskusikan dengan orang yang tidak mengerti teknologi. Pustakawan bisa memeriksa apakah aturan peminjaman sudah benar. Staf akademik bisa menilai apakah satu mahasiswa boleh mengambil mata kuliah yang sama dua kali.

Di sinilah kesalahan paling murah diperbaiki. Mengubah satu kotak di diagram hanya butuh beberapa menit. Mengubahnya setelah tabel terbentuk, data terisi, dan aplikasi berjalan butuh migrasi, penyesuaian kode, dan keberanian.

**Terkait:** [ERD](#erd-entity-relationship-diagram), [Model Data](#model-data), [Perancangan Logis](#perancangan-logis)

### Perancangan Logis

**Perancangan logis** adalah tahap ketiga: mengubah model konseptual menjadi struktur tabel yang nyata, lengkap dengan kolom, kunci, dan relasi.

Di sini ERD mulai diterjemahkan. Entitas menjadi tabel. Atribut menjadi kolom. Relasi menjadi kunci asing. Hubungan banyak-ke-banyak yang tadinya hanya digambarkan sebagai garis sekarang harus dipecah menjadi tabel penghubung, karena basis data relasional tidak bisa menyimpannya dalam satu kolom.

Tahap ini juga tempat normalisasi dilakukan: memisahkan data ke tabel yang tepat agar redundansi hilang dan anomali berkurang.

Hasilnya belum benar-benar bisa dijalankan, karena tipe data dan nama kolom yang spesifik biasanya baru ditentukan mengikuti produk yang dipakai. Tapi strukturnya sudah cukup konkret untuk ditinjau, diuji dengan contoh data, dan dibandingkan dengan kebutuhan di tahap pertama.

Kalau di tahap ini ada kebutuhan yang ternyata tidak bisa ditampung, lebih baik kembali ke tahap konseptual daripada memaksa menambal di tabel.

**Terkait:** [Perancangan Konseptual](#perancangan-konseptual), [Normalisasi](#normalisasi), [Kunci Asing](#kunci-asing-foreign-key)

## Q

### Query

**Query** adalah perintah untuk meminta, menambah, mengubah, atau menghapus data di basis data.

Bentuknya paling sering berupa SQL. `SELECT` untuk mengambil, `INSERT` untuk menambah, `UPDATE` untuk mengubah, `DELETE` untuk menghapus. Meski namanya sering diartikan sebagai "pertanyaan", cakupannya lebih luas dari itu.

Cara kita menulis query sangat memengaruhi hasilnya. Query yang mengambil seluruh kolom dari tabel besar akan lebih lambat daripada yang hanya mengambil kolom yang dibutuhkan. Query yang menggabungkan terlalu banyak tabel sekaligus lebih sulit dibaca, dan lebih sulit diperbaiki ketika hasilnya salah.

Ada juga hal yang tidak bisa diperbaiki oleh query sebagus apa pun. Kalau strukturnya belum tepat, query yang paling rapi pun akan tetap berbelit, karena ia harus menambal kekurangan di tempat lain.

Karena itu, query yang panjang dan berulang sering bukan tanda programmernya kurang mahir, melainkan tanda datanya disimpan di tempat yang belum benar.

**Terkait:** [Query Processor](#query-processor), [SQL](#sql-structured-query-language), [Join](#join)

### Query Processor

**Query processor** adalah komponen DBMS yang menerjemahkan perintah pengguna, biasanya SQL, menjadi instruksi yang dipahami database engine.

Di dalamnya ada tiga bagian yang bekerja berurutan.

**Parser** memeriksa sintaks perintah untuk memastikan penulisannya benar. Kalau ada yang salah, prosesnya berhenti di sini. Inilah sebabnya pesan seperti "syntax error near WHERE" muncul sebelum data apa pun tersentuh.

**Optimizer** mencari cara terbaik dan paling efisien untuk menjalankan perintah tersebut. Pada titik ini, perintah yang sama bisa punya beberapa rencana eksekusi, dan optimizer memilih yang diperkirakan paling murah.

**Executor** menjalankan perintah sesuai hasil optimasi, mengambil data lewat database engine, lalu mengirimkan hasilnya kembali.

Ketiganya bekerja dalam hitungan milidetik dan hampir tidak pernah kita sadari. Tapi justru di sinilah letak kenyamanan yang kita nikmati: kita tidak perlu tahu di bagian mana data tersimpan secara fisik, dan kita tidak perlu menuliskan langkah-langkah pengambilannya satu per satu.

**Terkait:** [Optimizer (Query Optimizer)](#optimizer-query-optimizer), [Database Engine](#database-engine), [SQL](#sql-structured-query-language)

## R

### RDBMS (Relational Database Management System)

**RDBMS** adalah DBMS yang mengelola data dengan model relasional: tabel, baris, kolom, dan kunci, dikelola menggunakan SQL.

Contoh yang paling sering dijumpai adalah MySQL, PostgreSQL, Oracle, dan SQL Server. Portal kampus, aplikasi kasir, sistem penggajian, dan hampir semua sistem yang menuntut ketepatan angka biasanya berjalan di atas RDBMS.

Kelebihannya banyak: mudah dipakai, fleksibel, mendukung transaksi, menjaga integritas data, dan punya mekanisme keamanan yang matang. Karena sudah dipakai puluhan tahun, dukungan, dokumentasi, dan tenaga terlatihnya juga melimpah.

Kekurangannya bukan pada kemampuannya, tetapi pada batasnya. RDBMS kurang optimal untuk data yang tidak terstruktur atau skala yang sangat besar, terutama kalau tidak dioptimasi. Desain skema yang buruk juga langsung terasa di performa, karena beban perbaikannya jatuh ke query yang harus menambal struktur yang keliru.

Menarik untuk dicatat: RDBMS bukan hanya soal tabel, tetapi soal janji. Ia berjanji bahwa transaksi akan selesai utuh atau tidak sama sekali. Janji itulah yang membuat bank, kampus, dan rumah sakit tetap memilihnya, meskipun ada pilihan yang tampak lebih modern.

**Terkait:** [Model Relasional](#model-relasional), [NoSQL](#nosql), [Transaksi](#transaksi-transaction)

### Redundansi Data

**Redundansi data** adalah keadaan ketika data yang sama disimpan di lebih dari satu tempat tanpa kebutuhan yang jelas.

Contohnya nama dan nomor telepon dosen yang diketik ulang di setiap baris mata kuliah yang diampu. Di satu sisi terasa praktis, karena semua informasi ada dalam satu tabel. Di sisi lain, setiap perubahan menuntut pembaruan di banyak tempat.

Masalahnya bukan sekadar ruang penyimpanan yang terbuang, tetapi risiko ketidakkonsistenan. Ketika nomor telepon berubah dan hanya sebagian baris yang diperbarui, basis data menyimpan dua kebenaran sekaligus. Tidak ada pesan error, tidak ada peringatan. Yang muncul nanti adalah laporan yang angkanya tidak cocok.

Redundansi juga bukan hal yang selalu salah. Salinan cadangan memang sengaja dibuat. [Denormalisasi](#denormalisasi) memang sengaja mengulang sebagian data demi kecepatan. Yang menjadi masalah adalah redundansi yang tidak terkendali, yaitu duplikasi yang tumbuh tanpa ada yang tahu dan tanpa ada yang menjaganya.

**Terkait:** [Normalisasi](#normalisasi), [Denormalisasi](#denormalisasi), [Konsistensi Data](#konsistensi-data)

## S

### Skalabilitas Horizontal

**Skalabilitas horizontal** adalah cara menambah kapasitas sistem dengan menambah jumlah mesin, bukan dengan memperbesar satu mesin.

Bandingkan dengan skalabilitas vertikal, yaitu menambah prosesor, memori, atau penyimpanan pada mesin yang sama. Cara vertikal lebih sederhana, tetapi ada batasnya: pada suatu titik, tidak ada lagi perangkat keras yang cukup besar, dan harganya naik tidak sebanding.

Cara horizontal bekerja dengan membagi beban ke beberapa mesin. Untuk basis data, ini bukan pekerjaan sepele, karena data harus dibagi dan diselaraskan. Di sinilah NoSQL punya keunggulan rancangan, sedangkan RDBMS biasanya lebih nyaman diperbesar secara vertikal, walaupun bisa juga dipecah menjadi beberapa bagian.

Pilihan ini bukan sekadar soal membeli server lebih banyak. Ia menentukan cara aplikasi ditulis, cara data disimpan, dan konsistensi seperti apa yang bisa dijanjikan.

**Terkait:** [NoSQL](#nosql), [RDBMS](#rdbms-relational-database-management-system), [Data Terstruktur dan Tidak Terstruktur](#data-terstruktur-dan-tidak-terstruktur)

### Skema (Schema)

**Skema** adalah rancangan struktur basis data: tabel apa yang ada, kolom apa isinya, tipe datanya apa, dan aturan apa yang berlaku.

Skema adalah cetak biru yang dipakai DBMS untuk memeriksa setiap perubahan. Kalau kolom `angkatan` dideklarasikan sebagai angka, memasukkan teks ke sana akan ditolak.

Pada RDBMS, skema biasanya ditetapkan lebih dulu, sebelum data dimasukkan. Menambah kolom di kemudian hari bukan hal mustahil, tetapi perlu perencanaan, terutama kalau tabelnya sudah besar dan dipakai banyak aplikasi.

Pada NoSQL, istilah "tanpa skema" sering membuat orang membayangkan kebebasan total. Kenyataannya tidak begitu. Yang berubah adalah tempat strukturnya didefinisikan: dari basis data pindah ke aplikasi. Kalau aplikasi tidak konsisten, dokumen-dokumen dalam satu koleksi bisa punya bentuk yang berbeda-beda, dan masalahnya justru lebih sulit dilacak karena tidak ada yang menolaknya di depan.

**Terkait:** [Katalog Metadata](#katalog-metadata-data-dictionary), [Tabel](#tabel), [Kolom (Atribut)](#kolom-atribut)

### SQL (Structured Query Language)

**SQL** adalah bahasa standar untuk mengelola data pada basis data relasional.

Perintahnya cukup sedikit untuk mulai dipakai: `SELECT` untuk mengambil data, `INSERT` untuk menambah, `UPDATE` untuk mengubah, `DELETE` untuk menghapus, `CREATE` untuk membuat tabel, dan `GRANT` untuk memberi hak akses.

Yang membuat SQL bertahan puluhan tahun bukan karena ia sempurna, tetapi karena sifatnya deklaratif. Kita menyebutkan apa yang ingin diperoleh, bukan bagaimana cara memperolehnya. Urusan mencari cara tercepat diserahkan kepada [optimizer](#optimizer-query-optimizer).

SQL juga punya standar, meskipun setiap produk punya dialek sendiri. Perbedaan kecil seperti cara mengambil sebagian baris atau menangani tanggal sering menjadi sumber kebingungan ketika aplikasi dipindahkan dari satu DBMS ke DBMS lain. Prinsipnya portabel, praktiknya tidak selalu.

Bagi yang baru mulai, SQL adalah salah satu keterampilan yang paling cepat memberi hasil. Beberapa baris perintah sudah cukup untuk menjawab pertanyaan yang tadinya harus dikerjakan manual di spreadsheet.

**Terkait:** [Query](#query), [RDBMS](#rdbms-relational-database-management-system), [Query Processor](#query-processor)

## T

### Tabel

**Tabel** adalah kumpulan baris yang memiliki kolom yang sama. Satu tabel biasanya mewakili satu jenis objek, misalnya mahasiswa, mata kuliah, atau peminjaman.

Karena bentuknya seragam, tabel mudah dibaca, mudah diurutkan, dan mudah diolah. Inilah alasan model relasional bertahan lama: bentuk yang sama bisa dipakai untuk hampir semua jenis data yang terstruktur.

Keputusan paling awal dan paling menentukan dalam merancang basis data adalah memilih "satu tabel untuk apa". Kalau terlalu banyak hal dicampur dalam satu tabel, hubungannya menjadi kabur dan redundansi muncul di mana-mana. Kalau terlalu banyak dipecah, setiap pertanyaan sederhana menuntut penggabungan yang panjang.

Contoh yang sering keliru: mencampur data mahasiswa dan data nilai dalam satu tabel. Nilai sebenarnya milik hubungan antara mahasiswa dan mata kuliah, bukan milik mahasiswa saja. Ketika seorang mahasiswa mengambil lima mata kuliah, data dirinya terpaksa diulang lima kali.

Hubungan antar tabel tidak dibuat dengan menyalin data, tetapi dengan kunci. Itulah yang membedakan tabel basis data dari tabel di spreadsheet.

**Terkait:** [Baris (Record)](#baris-record), [Kolom (Atribut)](#kolom-atribut), [Kunci Primer](#kunci-primer-primary-key)

### Transaksi (Transaction)

**Transaksi** adalah rangkaian operasi yang harus selesai seluruhnya atau tidak sama sekali.

Contoh paling jelas adalah transfer uang. Saldo rekening A dikurangi, lalu saldo rekening B ditambah. Kalau listrik mati di antara dua langkah itu, uangnya tidak boleh hilang dari A tanpa pernah sampai ke B, dan juga tidak boleh terhitung dua kali.

Karena itu, transaksi biasanya dijelaskan dengan empat sifat yang disingkat ACID. Atomik, artinya semua langkah selesai atau dibatalkan. Konsisten, artinya data berpindah dari satu keadaan sah ke keadaan sah berikutnya. Terisolasi, artinya transaksi yang berjalan bersamaan tidak saling mengganggu. Tahan lama, artinya yang sudah tersimpan tetap tersimpan walaupun sistem mati setelahnya.

Inilah fitur yang membuat bank, kampus, dan rumah sakit tetap memilih [RDBMS](#rdbms-relational-database-management-system). Bukan karena tabelnya rapi, tetapi karena janji "semua atau tidak sama sekali" itu sulit ditiru.

Pada sistem yang memilih kecepatan dan ketersediaan di atas segalanya, sebagian janji ini sengaja dilonggarkan. Bukan karena lalai, tetapi karena ada harga yang harus dibayar, dan keputusan itu diambil dengan sadar.

**Terkait:** [Akses Bersamaan](#akses-bersamaan-concurrency), [Konsistensi Data](#konsistensi-data), [Integritas Data](#integritas-data)

## V

### View

**View** adalah tampilan virtual dari hasil sebuah query. Ia terlihat seperti tabel, tetapi datanya tidak disimpan sendiri.

Sebuah view bisa menyatukan beberapa tabel, menyaring baris tertentu, atau menyembunyikan kolom yang sensitif. Aplikasi kemudian membaca view itu seolah-olah tabel biasa.

Manfaatnya paling terasa di level eksternal [arsitektur tiga level](#arsitektur-tiga-level-three-schema-architecture). Dosen wali bisa diberi view berisi nilai mahasiswa bimbingannya saja, tanpa harus diberi akses ke seluruh tabel nilai. Staf keuangan bisa melihat tagihan tanpa melihat riwayat medis.

View juga menyederhanakan pekerjaan. Query panjang yang menggabungkan lima tabel bisa disimpan sebagai view, lalu dipakai berulang dengan perintah yang jauh lebih pendek.

Tapi view bukan tabel, dan itu punya konsekuensi. Setiap kali view dibuka, query di baliknya dijalankan lagi. View yang berlapis-lapis di atas view lain bisa membuat query sederhana terasa berat tanpa terlihat penyebabnya. Dan tidak semua view bisa diperbarui langsung, terutama yang menggabungkan banyak tabel.

**Terkait:** [Arsitektur Tiga Level](#arsitektur-tiga-level-three-schema-architecture), [Query](#query), [Skema](#skema-schema)

## Kesimpulan

Setelah membaca semua istilah tadi, mungkin kelihatan bahwa basis data bukan soal tempat menyimpan file.

Di balik tombol Simpan yang kita tekan tanpa berpikir, ada struktur yang dirancang, aturan yang ditegakkan, transaksi yang dijaga, dan mesin yang memutuskan cara tercepat untuk menemukan kembali data itu berbulan-bulan kemudian.

Menariknya, bagian tersulitnya justru bukan teknologinya. Analisis kebutuhan, perancangan, dan normalisasi adalah pekerjaan yang hasilnya tidak terlihat, sementara kesalahannya baru terasa jauh di kemudian hari. Karena itu, banyak proyek melompat langsung ke tahap membangun, lalu membayarnya di setiap laporan yang dibangun sesudahnya.

Materi ini juga membuat saya melihat istilah-istilah yang tadinya terpisah jadi satu rangkaian. Kebutuhan menentukan entitas, entitas menjadi tabel, tabel dihubungkan kunci, kunci memungkinkan join, join dilayani query processor, query processor bekerja di atas penyimpanan yang diatur arsitektur tiga level, dan semuanya dijaga oleh transaksi, integritas, serta backup.

Kalau teman-teman ingin mulai memahami basis data, mulailah dari yang paling dekat: portal kampus, aplikasi bank, atau kasir minimarket yang sering dipakai. Coba tebak dua atau tiga tabel di baliknya, lalu tanyakan satu hal: kunci apa yang menghubungkan tabel-tabel itu?

Karena pada akhirnya, basis data bukan dibangun agar datanya rapi di dalam server. Ia dibangun agar seseorang bisa mempercayai angka yang dibacanya, dan bisa mengambil keputusan tanpa ragu apakah datanya masih benar.
