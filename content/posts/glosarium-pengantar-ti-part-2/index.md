---
title: "Glosarium Pengantar TI Part 2"
date: 2026-09-23T22:49:08+07:00
draft: false
tags: ["glosarium", "teknologi", "informasi", "teknologi informasi", "komputer"]
categories: ["glosarium", "teknologi"]
summary: "Lanjutan glosarium pengantar teknologi informasi yang membahas istilah seperti Agile, Cloud, DevOps, AI, malware, open source, hingga version control dengan bahasa sederhana dan santai."
ShowToc: true
TocOpen: false
series: ["Glosarium Pengantar TI"]

# cover:
#     image: "<image path/url>"
#     alt: "<alt text>"
#     caption: "<text>"
#     relative: true
---

## Pendahuluan

Di [part sebelumnya](/tags/glosarium/), kita sudah kenalan dengan beberapa istilah dasar di dunia teknologi informasi. Tapi seperti yang mungkin sudah kamu sadari, semakin jauh kita masuk ke dunia teknologi, semakin banyak juga istilah aneh yang muncul.

Ada *compiler*, *container*, *framework*, *DevOps*, sampai *vendor lock-in*. Belum lagi istilah keamanan seperti *malware*, *ransomware*, dan *spyware* yang kedengarannya mirip-mirip, padahal artinya beda.

Masalahnya, banyak istilah teknologi dijelaskan menggunakan istilah teknologi lainnya. Mau cari tahu apa itu *container*, malah ketemu istilah virtualisasi. Cari virtualisasi, ketemu sistem operasi. Cari sistem operasi, ujung-ujungnya buka lima tab baru.

Jadi di part kedua ini kita lanjut membongkar istilah-istilah tersebut satu per satu pakai bahasa yang lebih manusiawi.

Beberapa istilah juga saling berhubungan. Karena itu, di setiap bagian saya kasih tautan ke istilah lain yang masih satu keluarga supaya kamu bisa lompat-lompat tanpa harus nyari manual.

## A

### Agile

Agile itu cara kerja yang lebih fleksibel dan nggak terlalu terpaku sama rencana awal.

Daripada menghabiskan berbulan-bulan bikin produk sampai dianggap "sempurna", tim biasanya membagi pekerjaan menjadi bagian-bagian kecil, mengerjakannya sedikit demi sedikit, lalu rutin mengevaluasi hasilnya.

Jadi kalau di tengah jalan ternyata kebutuhan pengguna berubah, tim masih punya ruang buat menyesuaikan arah tanpa harus membuang semua pekerjaan dari awal.

Agile sendiri bukan satu metode spesifik. Di bawahnya ada berbagai pendekatan seperti Scrum dan Kanban. Ide besarnya kurang lebih sama: kerjakan dalam bagian kecil, dapatkan *feedback*, lalu perbaiki terus.

**Terkait:** [DevOps](#devops), [Developer](#developer), [Version Control](#version-control)

### Antivirus

Antivirus adalah software keamanan yang tugasnya mendeteksi, mencegah, dan menangani program berbahaya yang masuk ke perangkat kita.

Dulu antivirus identik dengan mencari "virus komputer". Sekarang tugasnya jauh lebih luas karena ancamannya juga sudah macam-macam, mulai dari [malware](#malware), [spyware](#spyware), sampai [ransomware](#ransomware).

Cara kerjanya juga nggak cuma mencocokkan file dengan daftar virus yang sudah dikenal. Antivirus modern biasanya ikut memperhatikan perilaku program. Kalau tiba-tiba ada aplikasi yang mencoba mengenkripsi ribuan file dalam beberapa detik, misalnya, itu jelas patut dicurigai.

Tapi antivirus juga bukan jimat sakti. Kalau penggunanya tetap asal download file, pakai password `123456`, atau menonaktifkan fitur keamanan, ya tetap bisa kena masalah.

**Terkait:** [Malware](#malware), [Ransomware](#ransomware), [Spyware](#spyware), [Sistem Operasi](#sistem-operasi)

### Algoritma

Algoritma sederhananya adalah urutan langkah untuk menyelesaikan suatu masalah.

Misalnya kamu mau bikin teh:

1. Panaskan air.
2. Masukkan teh ke gelas.
3. Tuangkan air panas.
4. Tunggu beberapa menit.
5. Tambahkan gula kalau suka.

Itu sebenarnya sudah bisa disebut algoritma.

Bedanya, dalam komputer setiap langkah harus dibuat jauh lebih jelas karena komputer nggak punya kemampuan buat menebak maksud kita. Kalau instruksinya salah atau urutannya keliru, hasil akhirnya juga bisa salah.

Konsep algoritma ini ada hampir di mana-mana, mulai dari pencarian Google, navigasi Maps, rekomendasi video, sampai [kecerdasan buatan](#kecerdasan-buatan-ai).

**Terkait:** [Kecerdasan Buatan (AI)](#kecerdasan-buatan-ai), [Developer](#developer)

## C

### Compiler

Compiler itu bisa kita bayangkan sebagai penerjemah antara kode yang ditulis programmer dengan bentuk yang lebih mudah dijalankan komputer.

Misalnya kita menulis program menggunakan C atau C++. Kode tersebut belum tentu bisa langsung dieksekusi prosesor. Compiler akan membaca kode kita, memeriksa sebagian kesalahannya, lalu menerjemahkannya menjadi bentuk lain seperti *machine code*, *bytecode*, atau representasi perantara tertentu.

Jadi sebenarnya compiler nggak selalu sekadar mengubah kode menjadi "angka nol dan satu". Proses di baliknya bisa jauh lebih panjang.

Biasanya compiler juga sudah terintegrasi dengan [IDE](#ide), jadi kita tinggal pencet tombol *build* atau *run* tanpa harus menjalankan semuanya manual lewat terminal.

**Terkait:** [Developer](#developer), [IDE](#ide), [Sistem Operasi](#sistem-operasi)

### Cloud

Cloud itu sebenarnya komputer milik orang lain yang kita akses lewat jaringan.

Terdengar terlalu sederhana? Ya memang kurang lebih begitu.

Daripada beli server sendiri, nyari ruangan, pasang pendingin, mikirin listrik, lalu begadang kalau hard disk-nya mati, kita bisa menyewa sumber daya komputer dari penyedia cloud.

Kita bisa pakai cloud buat nyimpan file, menjalankan website, database, aplikasi, sampai melatih model AI.

Google Drive dan iCloud adalah contoh cloud yang dekat dengan pengguna biasa. Kalau di dunia developer, ada layanan seperti AWS, Google Cloud, dan Microsoft Azure yang menyediakan infrastruktur dalam skala jauh lebih besar.

Enaknya fleksibel. Tapi semakin dalam kita memakai layanan khusus milik satu penyedia, semakin besar juga kemungkinan terkena [vendor lock-in](#vendor-lock-in).

**Terkait:** [Container](#container), [Microservices](#microservices), [Vendor Lock-in](#vendor-lock-in), [DevOps](#devops)

### Container

Container adalah cara mengemas aplikasi beserta kebutuhan-kebutuhannya supaya bisa dijalankan dengan lebih konsisten di berbagai tempat.

Pernah dengar kalimat legendaris developer:

> "Lho, di laptop saya jalan kok."

Nah, container mencoba mengurangi masalah seperti itu.

Aplikasi bisa dibungkus bersama library, konfigurasi, dan dependensi yang dibutuhkannya. Hasilnya, lingkungan aplikasi di laptop developer bisa dibuat mirip dengan lingkungan yang nantinya dipakai di server.

Container juga biasanya lebih ringan dibanding menjalankan satu mesin virtual penuh karena beberapa container bisa berbagi kernel [sistem operasi](#sistem-operasi) yang sama.

Docker mungkin nama yang paling sering kamu dengar ketika ngomongin teknologi ini.

**Terkait:** [Cloud](#cloud), [DevOps](#devops), [Microservices](#microservices), [Sistem Operasi](#sistem-operasi)

## D

### Developer

Developer adalah orang yang membuat atau mengembangkan software.

Kerjaannya memang banyak berkaitan dengan menulis kode, tapi bukan berarti seharian cuma duduk sambil mengetik simbol aneh di layar hitam.

Developer juga harus memahami masalah, merancang solusi, membaca dokumentasi, mencari bug, melakukan pengujian, berdiskusi dengan tim, sampai mempertanyakan kenapa kode yang tadi malam masih jalan tiba-tiba rusak pagi ini.

Mereka biasanya dibantu berbagai alat seperti [IDE](#ide), [framework](#framework), [library](#library), dan [version control](#version-control).

Jadi kemampuan developer bukan cuma soal seberapa cepat dia mengetik kode, tapi juga seberapa baik dia bisa memecahkan masalah.

**Terkait:** [IDE](#ide), [Framework](#framework), [Library](#library), [Version Control](#version-control)

### DevOps

DevOps berasal dari gabungan kata *Development* dan *Operations*.

Sebelumnya, tim developer dan tim operasi sering bekerja seperti dua dunia berbeda. Developer bikin aplikasi, lalu menyerahkannya ke tim operasi buat dipasang ke server.

Kalau aplikasinya error?

Tim operasi bilang kodenya bermasalah.

Developer bilang servernya yang bermasalah.

Mulailah perang dingin.

DevOps mencoba mengurangi tembok tersebut dengan membuat proses pengembangan, pengujian, deployment, dan operasional menjadi lebih terintegrasi.

Makanya di dunia DevOps kamu sering ketemu istilah otomatisasi, CI/CD, monitoring, [container](#container), [cloud](#cloud), dan [version control](#version-control).

Tujuan akhirnya sederhana: perubahan software bisa sampai ke pengguna dengan lebih cepat tanpa bikin sistem jadi berantakan.

**Terkait:** [Agile](#agile), [Cloud](#cloud), [Container](#container), [Version Control](#version-control)

## F

### Framework

Framework itu bisa kita anggap seperti kerangka rumah yang sebagian strukturnya sudah dibuat.

Daripada developer membangun semuanya dari nol, framework menyediakan struktur, aturan, dan berbagai komponen umum yang tinggal kita gunakan.

Misalnya saat bikin website, kita hampir selalu membutuhkan routing, pengelolaan request, validasi data, dan berbagai fitur dasar lainnya. Framework biasanya sudah menyediakan pola untuk menangani hal-hal tersebut.

Makanya bikin aplikasi menggunakan framework sering lebih cepat dan lebih terstruktur dibanding benar-benar mulai dari halaman kosong.

Tapi framework juga biasanya lebih "ngatur" dibanding [library](#library). Kalau library kita panggil ketika dibutuhkan, framework justru sering menentukan bagaimana aplikasi kita harus disusun.

**Terkait:** [Library](#library), [Developer](#developer), [Low-code](#low-code)

## G

### GDPR

GDPR atau *General Data Protection Regulation* adalah aturan perlindungan data pribadi yang berlaku di Uni Eropa dan Wilayah Ekonomi Eropa.

Intinya, perusahaan nggak boleh memperlakukan data pribadi pengguna seenaknya.

Pengguna punya sejumlah hak terhadap datanya, sementara organisasi yang mengumpulkan data punya kewajiban untuk menjelaskan data apa yang dikumpulkan, kenapa data itu dibutuhkan, dan bagaimana data tersebut digunakan.

GDPR juga mengatur bagaimana organisasi menangani insiden kebocoran data. Dalam kondisi tertentu, pelanggaran data harus dilaporkan kepada otoritas terkait dalam waktu maksimal 72 jam setelah organisasi mengetahuinya.

Jadi ketika sebuah website tiba-tiba punya *cookie consent* sepanjang formulir pendaftaran CPNS, salah satu penyebabnya bisa jadi karena mereka sedang berusaha memenuhi aturan privasi seperti GDPR.

**Terkait:** [Cloud](#cloud), [Spyware](#spyware)

### GPL

GPL atau *GNU General Public License* adalah salah satu lisensi *open source* yang punya konsep *copyleft*.

Kamu boleh menggunakan, mempelajari, memodifikasi, dan mendistribusikan software berlisensi GPL.

Tapi ada syarat pentingnya.

Kalau kamu mendistribusikan versi modifikasi dari software GPL, pada umumnya kode sumber yang relevan juga harus tersedia menggunakan lisensi GPL yang sesuai.

Jadi bukan berarti setiap kali kamu mengubah kode GPL di laptop sendiri kamu wajib langsung mengunggahnya ke internet. Kewajiban tersebut terutama menjadi penting ketika software tersebut didistribusikan.

Karakter ini berbeda dengan lisensi yang lebih permisif seperti [MIT License](#mit-license).

**Terkait:** [Open Source](#open-source), [MIT License](#mit-license), [Lisensi Perangkat Lunak](#lisensi-perangkat-lunak)

## I

### IDE

IDE atau *Integrated Development Environment* adalah aplikasi yang mengumpulkan berbagai alat coding dalam satu tempat.

Kalau pakai editor teks biasa, mungkin kamu harus buka editor, terminal, debugger, dan berbagai alat lain secara terpisah.

IDE mencoba menyatukan semuanya.

Biasanya sudah ada editor kode, autocomplete, integrasi [compiler](#compiler), debugger, terminal, sampai integrasi [version control](#version-control).

Contohnya ada Visual Studio, IntelliJ IDEA, Android Studio, dan berbagai aplikasi sejenis.

Tujuannya bukan bikin developer jadi malas, tapi mengurangi pekerjaan berulang supaya lebih banyak waktu bisa dipakai buat hal yang lebih penting: mencari tahu kenapa fungsi yang cuma lima baris tetap nggak jalan.

**Terkait:** [Developer](#developer), [Compiler](#compiler), [Version Control](#version-control)

### Internet of Things (IoT)

Internet of Things atau IoT adalah konsep menghubungkan benda-benda fisik ke jaringan supaya benda tersebut bisa mengirim, menerima, atau memproses data.

Contohnya banyak banget.

Jam tangan bisa mengirim data aktivitas ke HP. CCTV bisa dipantau dari luar rumah. Sensor di pabrik bisa kasih peringatan kalau suhu mesin terlalu tinggi. Lampu rumah bahkan bisa dimatikan sambil rebahan dari kasur.

Biasanya perangkat IoT nggak bekerja sendirian. Data dari sensor bisa dikirim ke [cloud](#cloud), lalu dianalisis menggunakan berbagai [algoritma](#algoritma) atau bahkan sistem [AI](#kecerdasan-buatan-ai).

Semakin banyak perangkat tersambung ke internet, tentu semakin besar juga perhatian yang dibutuhkan soal keamanan. Kita jelas nggak mau kulkas pintar ikut bergabung dengan pasukan botnet.

**Terkait:** [Cloud](#cloud), [Kecerdasan Buatan (AI)](#kecerdasan-buatan-ai), [Malware](#malware)

## K

### Kecerdasan Buatan (AI)

Kecerdasan Buatan atau AI adalah bidang teknologi yang mencoba membuat komputer mampu melakukan tugas yang biasanya membutuhkan kemampuan seperti mengenali pola, memahami bahasa, membuat prediksi, atau mengambil keputusan berdasarkan data.

AI bukan berarti komputer tiba-tiba punya pikiran sendiri seperti manusia.

Banyak sistem AI bekerja dengan mempelajari pola dari data menggunakan [algoritma](#algoritma) tertentu. Dari pola tersebut, sistem kemudian bisa menghasilkan prediksi atau respons terhadap data baru.

Contohnya dekat banget dengan kehidupan sehari-hari: rekomendasi video YouTube, filter spam email, pengenal wajah di HP, penerjemah otomatis, sampai chatbot.

Semakin besar sistem AI, biasanya semakin besar juga kebutuhan komputasinya. Makanya [cloud](#cloud) punya peran besar dalam perkembangan AI modern.

**Terkait:** [Algoritma](#algoritma), [Cloud](#cloud), [Internet of Things (IoT)](#internet-of-things-iot)

## L

### Library

Library adalah kumpulan kode yang sudah dibuat orang lain supaya kita nggak perlu menyelesaikan masalah yang sama dari nol.

Misalnya kamu butuh membaca file PDF, melakukan enkripsi, memproses gambar, atau mengirim request HTTP.

Daripada menulis semua algoritmanya sendiri, biasanya sudah ada library yang menyediakan fungsi tersebut.

Tinggal pakai.

Tapi tentu bukan berarti asal install semuanya. Setiap library menjadi tambahan dependensi yang harus kita rawat, update, dan periksa keamanannya.

Library juga sering tertukar dengan [framework](#framework). Bedanya secara sederhana: kalau library biasanya kita yang memanggil kodenya, framework sering kali justru menjadi kerangka utama yang memanggil kode kita.

**Terkait:** [Framework](#framework), [Developer](#developer), [Lisensi Perangkat Lunak](#lisensi-perangkat-lunak)

### Lisensi Perangkat Lunak

Lisensi perangkat lunak adalah aturan yang menentukan apa yang boleh dan nggak boleh kita lakukan terhadap suatu software.

Punya salinan software bukan berarti otomatis punya semua hak atas software tersebut.

Lisensinya bisa menentukan apakah software boleh dimodifikasi, dibagikan ulang, dipakai secara komersial, atau bahkan dilihat kode sumbernya.

Ada lisensi [open source](#open-source) seperti [GPL](#gpl) dan [MIT License](#mit-license). Ada juga software [proprietary](#proprietary-software) yang biasanya memberikan hak penggunaan jauh lebih terbatas.

Makanya tombol "I Agree" yang biasanya kita klik dalam 0,2 detik itu sebenarnya punya arti hukum yang lumayan panjang.

**Terkait:** [GPL](#gpl), [MIT License](#mit-license), [Open Source](#open-source), [Proprietary Software](#proprietary-software)

### Low-code

Low-code adalah pendekatan membuat aplikasi dengan mengurangi sebanyak mungkin kode yang harus ditulis secara manual.

Biasanya platform low-code menyediakan editor visual, komponen siap pakai, konektor database, sampai sistem *drag-and-drop*.

Tapi sesuai namanya, **low-code bukan berarti no-code**.

Developer masih bisa menulis kode ketika butuh logika khusus yang nggak disediakan platform.

Tujuannya adalah mempercepat proses pengembangan, terutama untuk aplikasi bisnis yang banyak polanya berulang seperti formulir, dashboard, approval, atau sistem internal perusahaan.

**Terkait:** [No-code](#no-code), [Developer](#developer), [Cloud](#cloud)

## M

### Malware

Malware berasal dari istilah *malicious software*, alias software yang sengaja dibuat untuk melakukan sesuatu yang merugikan.

Malware itu istilah payung.

Jadi virus komputer sebenarnya cuma salah satu jenis malware. Di dalam keluarga besarnya masih ada worm, trojan, [spyware](#spyware), [ransomware](#ransomware), dan berbagai jenis lainnya.

Tujuannya juga beda-beda. Ada yang ingin merusak sistem, mencuri password, memata-matai korban, mengambil alih komputer, sampai memeras uang.

Karena itu, bilang "komputer kena malware" kurang lebih seperti bilang "orang itu kena penyakit". Benar, tapi kita belum tahu penyakit yang mana.

**Terkait:** [Antivirus](#antivirus), [Ransomware](#ransomware), [Spyware](#spyware)

### Microservices

Microservices adalah pendekatan membuat aplikasi dengan membaginya menjadi banyak layanan kecil yang masing-masing punya tanggung jawab tertentu.

Misalnya kita punya aplikasi e-commerce.

Daripada semua fitur pembayaran, akun pengguna, katalog barang, notifikasi, dan pengiriman ditumpuk menjadi satu aplikasi raksasa, setiap bagian bisa dipisahkan menjadi layanan sendiri.

Keuntungannya, setiap layanan bisa dikembangkan dan diperbarui dengan lebih independen.

Tapi jangan salah, microservices juga bukan tombol ajaib yang otomatis bikin aplikasi lebih bagus. Semakin banyak layanan, semakin banyak juga jaringan, monitoring, deployment, dan komunikasi antarsistem yang harus dipikirkan.

Makanya microservices sering berjalan bareng [container](#container), [cloud](#cloud), dan praktik [DevOps](#devops).

**Terkait:** [Container](#container), [Cloud](#cloud), [DevOps](#devops)

### MIT License

MIT License adalah salah satu lisensi *open source* yang terkenal sangat permisif.

Secara sederhana, kamu boleh menggunakan, menyalin, memodifikasi, bahkan menjual software yang menggunakan MIT License.

Syarat utamanya relatif ringan: pemberitahuan hak cipta dan teks lisensinya harus tetap disertakan pada salinan atau bagian penting software tersebut.

Berbeda dengan [GPL](#gpl), MIT License tidak mewajibkan software turunan yang kamu distribusikan untuk ikut dibuka menggunakan lisensi yang sama.

Karena aturannya sederhana dan fleksibel, lisensi ini sangat populer di berbagai proyek open source.

**Terkait:** [GPL](#gpl), [Open Source](#open-source), [Lisensi Perangkat Lunak](#lisensi-perangkat-lunak)

## N

### No-code

No-code adalah pendekatan membuat aplikasi tanpa harus menulis kode pemrograman secara langsung.

Kita biasanya tinggal menyusun komponen visual, mengatur alur kerja, menyambungkan database, lalu menentukan apa yang terjadi ketika pengguna menekan tombol tertentu.

Platform seperti ini cocok buat orang yang punya ide atau memahami proses bisnis tetapi nggak punya pengalaman programming mendalam.

Tentu saja no-code tetap punya batas.

Kalau kebutuhan aplikasinya semakin aneh, kompleks, atau sangat spesifik, kita mungkin akan sampai pada titik ketika platformnya nggak menyediakan fitur yang dibutuhkan.

Di situlah pendekatan [low-code](#low-code) atau pengembangan software biasa mulai punya keuntungan.

**Terkait:** [Low-code](#low-code), [Cloud](#cloud), [Developer](#developer)

## O

### Open Source

Open source adalah model pengembangan software di mana kode sumbernya tersedia supaya bisa dipelajari, dimodifikasi, dan didistribusikan sesuai aturan lisensinya.

Jadi *open source* bukan sekadar "kode yang bisa dilihat".

Hak apa saja yang kita punya tetap ditentukan oleh [lisensi perangkat lunak](#lisensi-perangkat-lunak) yang digunakan.

Ada proyek yang menggunakan [MIT License](#mit-license) dan memberikan kebebasan sangat luas. Ada juga yang menggunakan [GPL](#gpl) dengan aturan *copyleft*.

Karena source code-nya tersedia, orang lain bisa mempelajari cara kerjanya, menemukan bug, memperbaiki fitur, atau membuat versi mereka sendiri selama tetap mengikuti lisensi.

Kebalikannya biasanya disebut [proprietary software](#proprietary-software).

**Terkait:** [GPL](#gpl), [MIT License](#mit-license), [Lisensi Perangkat Lunak](#lisensi-perangkat-lunak), [Proprietary Software](#proprietary-software)

## P

### Proprietary Software

Proprietary software adalah software yang kendali utamanya tetap berada di tangan pemilik atau perusahaan pembuatnya.

Kode sumbernya biasanya nggak dibuka ke publik, dan pengguna mendapatkan hak penggunaan berdasarkan lisensi tertentu.

Kita mungkin boleh memakai aplikasinya, tapi belum tentu boleh melihat source code, memodifikasi program, atau membagikannya kembali.

Contohnya banyak banget dalam software komersial.

Model seperti ini sebenarnya nggak otomatis buruk atau bagus. Itu cuma model distribusi yang berbeda dengan [open source](#open-source).

Masalah mulai terasa ketika kita sudah terlalu bergantung pada satu produk dan pindah ke alternatif lain menjadi sangat sulit. Situasi seperti itu biasanya disebut [vendor lock-in](#vendor-lock-in).

**Terkait:** [Open Source](#open-source), [Lisensi Perangkat Lunak](#lisensi-perangkat-lunak), [Vendor Lock-in](#vendor-lock-in)

## R

### Ransomware

Ransomware adalah jenis [malware](#malware) yang dirancang untuk memeras korbannya.

Salah satu caranya adalah mengenkripsi file korban sehingga file tersebut nggak bisa dibuka tanpa kunci tertentu. Pelaku kemudian meminta uang tebusan supaya akses dikembalikan.

Tapi ransomware modern nggak selalu berhenti di enkripsi.

Ada pelaku yang lebih dulu mencuri data korban, kemudian mengancam akan menyebarkannya kalau tebusan nggak dibayar. Jadi korbannya bisa kena dua masalah sekaligus: data terkunci dan data bocor.

Dan membayar tebusan juga nggak menjamin file bakal kembali. Kita tetap sedang berurusan dengan penjahat, bukan customer service.

Makanya backup, update keamanan, kontrol akses, dan [antivirus](#antivirus) tetap penting sebagai bagian dari pertahanan.

**Terkait:** [Malware](#malware), [Antivirus](#antivirus), [Spyware](#spyware)

## S

### Sistem Operasi

Sistem operasi atau *operating system* adalah software utama yang mengatur hubungan antara hardware, aplikasi, dan pengguna.

Windows, Linux, macOS, Android, dan iOS adalah contoh sistem operasi.

Bayangkan kalau setiap aplikasi harus tahu sendiri cara berkomunikasi langsung dengan setiap jenis CPU, RAM, layar, keyboard, SSD, Wi-Fi, dan perangkat lainnya.

Developer mungkin sudah pensiun sebelum aplikasinya selesai.

Sistem operasi menyediakan lapisan standar supaya aplikasi nggak perlu mengurus semua detail hardware tersebut secara langsung.

Dia juga mengatur penggunaan memori, proses yang sedang berjalan, file, perangkat, jaringan, sampai izin akses.

Bahkan teknologi seperti [container](#container) juga sangat bergantung pada kemampuan yang disediakan sistem operasi.

**Terkait:** [Container](#container), [Antivirus](#antivirus), [Malware](#malware), [Compiler](#compiler)

### Spyware

Spyware adalah jenis [malware](#malware) yang dibuat untuk memata-matai pengguna tanpa sepengetahuan atau tanpa persetujuan yang semestinya.

Informasi yang dikumpulkan bisa macam-macam: aktivitas browsing, informasi perangkat, lokasi, kredensial, sampai input tertentu yang dilakukan pengguna.

Beberapa spyware bahkan dirancang untuk berjalan diam-diam supaya korbannya nggak sadar sedang dipantau.

Data yang berhasil dikumpulkan kemudian bisa dipakai untuk penipuan, pencurian akun, pemerasan, atau tujuan lainnya.

Makanya spyware termasuk ancaman privasi sekaligus keamanan.

**Terkait:** [Malware](#malware), [Antivirus](#antivirus), [GDPR](#gdpr)

## V

### Vendor Lock-in

Vendor lock-in adalah kondisi ketika kita sudah terlalu bergantung pada satu produk atau penyedia layanan sampai pindah ke tempat lain terasa sangat sulit atau mahal.

Misalnya perusahaan sudah menyimpan data selama bertahun-tahun menggunakan format khusus milik satu vendor.

Secara teori bisa pindah.

Tapi begitu dihitung, ternyata harus migrasi puluhan terabyte data, menulis ulang aplikasi, melatih ulang karyawan, dan mengubah seluruh infrastrukturnya.

Akhirnya kalimatnya berubah menjadi:

> "Ya udahlah, lanjut bayar aja."

Situasi ini cukup sering dibahas di dunia [cloud](#cloud), karena setiap penyedia punya layanan dan teknologi khususnya sendiri.

Penggunaan teknologi standar dan [open source](#open-source) kadang bisa membantu mengurangi ketergantungan, meskipun nggak otomatis menghilangkannya.

**Terkait:** [Cloud](#cloud), [Open Source](#open-source), [Proprietary Software](#proprietary-software)

### Version Control

Version control adalah sistem yang menyimpan riwayat perubahan file dari waktu ke waktu.

Di dunia software, alat yang paling terkenal tentu Git.

Bayangkan kamu sedang mengerjakan aplikasi, lalu sore ini semuanya masih normal. Besok pagi setelah mengubah 17 file, aplikasinya tiba-tiba rusak total.

Tanpa version control:

> "Kemarin saya ubah apaan ya?"

Dengan version control, kita bisa melihat perubahan satu per satu, membandingkan versi, dan kembali ke kondisi sebelumnya kalau dibutuhkan.

Version control juga memungkinkan banyak [developer](#developer) mengerjakan proyek yang sama secara bersamaan melalui *branch* tanpa harus kirim file seperti:

`project-final.zip`

`project-final-beneran.zip`

`project-final-beneran-fix-2.zip`

Dalam praktik modern, version control juga menjadi bagian penting dari proses [DevOps](#devops) dan pengembangan [Agile](#agile).

**Terkait:** [Developer](#developer), [DevOps](#devops), [Agile](#agile), [IDE](#ide)

## Kesimpulan

Kalau diperhatikan, hampir semua istilah di atas sebenarnya saling nyambung.

[Developer](#developer) menulis kode menggunakan [IDE](#ide), dibantu [framework](#framework) dan [library](#library), lalu menyimpan perubahannya menggunakan [version control](#version-control).

Aplikasinya mungkin dikemas memakai [container](#container), dijalankan di [cloud](#cloud), dipecah menjadi [microservices](#microservices), kemudian proses deployment-nya diotomatisasi menggunakan praktik [DevOps](#devops).

Di sisi lain, kita juga harus mikirin keamanan karena ada [malware](#malware), [spyware](#spyware), dan [ransomware](#ransomware). Belum selesai sampai sana, masih ada urusan [lisensi perangkat lunak](#lisensi-perangkat-lunak), privasi, sampai risiko [vendor lock-in](#vendor-lock-in).

Itulah kenapa belajar teknologi kadang terasa seperti buka satu pintu lalu menemukan sepuluh pintu baru di belakangnya.

Tapi nggak perlu memahami semuanya sekaligus.

Yang penting kita tahu gambaran besarnya dulu: istilah itu ngomongin apa, hubungannya dengan teknologi lain apa, dan kapan biasanya istilah tersebut muncul.

Nanti ketika benar-benar ketemu di dunia nyata, barulah kita gali lebih dalam.

Karena ujung-ujungnya, sebagian besar istilah teknologi yang terdengar rumit sebenarnya cuma nama keren untuk sebuah masalah dan cara manusia mencoba menyelesaikannya.