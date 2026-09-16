---
title: "Glosarium: Pengantar TI Part 1"
date: 2026-09-16T19:23:35+07:00
draft: false
tags: ["glosarium", "teknologi", "informasi", "teknologi informasi", "komputer", "chip", "ai"]
categories: ["glosarium", "teknologi"]
summary: "Dari hardware sampai AI, tulisan ini merangkum istilah-istilah penting TI dengan gaya santai supaya lebih enak dibaca dan mudah diingat hubungannya."
ShowToc: true
TocOpen: false
series: []
# cover:
#   image: "<image path/url>"
#   alt: "<alt text>"
#   caption: "<text>"
#   relative: true
---

## Pendahuluan

CPU, RAM, SSD, mungkin teman-teman sudah sering dengar nama-nama ini waktu lihat spesifikasi laptop atau ponsel. Kita tahu semuanya ada di dalam perangkat yang kita pakai, tapi belum tentu tahu apa tugas masing-masing dan bagaimana mereka bisa bekerja bersama.

Dari situ, saya menyusun glosarium ini sebagai bagian dari proses belajar teknologi informasi. Saya ingin merangkum istilah yang saya pelajari dengan bahasa yang lebih gampang dipahami, lalu menghubungkan istilah-istilah yang ternyata punya kaitan satu sama lain.

Tulisan ini bisa dipakai teman-teman yang baru mengenal komputer, atau yang sudah terbiasa memakainya dan ingin tahu lebih jauh apa yang terjadi di dalamnya. Nggak perlu langsung paham semuanya. Istilahnya saya susun menurut abjad, dan nama istilah yang bisa diklik akan membawa teman-teman ke penjelasan terkait. Mulai saja dari yang bikin penasaran, lalu ikuti hubungannya.

### Mulai membaca dari mana?

Kalau masih bingung mau mulai dari mana, teman-teman bisa mengikuti beberapa jalur ini:

- **Cara komputer bekerja:** [perangkat keras](#perangkat-keras-hardware) → [perangkat masukan](#perangkat-masukan-input-device) → [perangkat pemrosesan](#perangkat-pemrosesan-processing-device) → [perangkat keluaran](#perangkat-keluaran-output-device). [Perangkat lunak](#perangkat-lunak-software) mengatur pekerjaan komponen-komponen tersebut.

- **Bagian dalam prosesor:** [CPU](#cpu-central-processing-unit), [CU](#cu-control-unit), [ALU](#alu), dan [register](#register) bekerja bersama untuk menjalankan [instruksi](#instruksi).

- **Tempat data disimpan:** bandingkan [RAM](#ram-random-access-memory), [cache](#cache), dan [penyimpanan sekunder](#penyimpanan-sekunder), lalu kenali [penyimpanan cadangan](#penyimpanan-cadangan).

- **Perangkat yang saling terhubung:** mulai dari [protokol](#protokol), [Ethernet](#ethernet), dan [Bluetooth](#bluetooth), lalu lanjut ke [IoT](#internet-of-things-iot) dan [edge computing](#edge-computing).

- **Dasar kecerdasan buatan:** pahami hubungan [AI](#artificial-intelligence-ai) dengan [machine learning](#machine-learning), kemudian kenali peran [GPU](#gpu-graphics-processing-unit), [NPU](#npu-neural-processing-unit), dan [TPU](#tpu-tensor-processing-unit).

## A

### Aktuator

Aktuator adalah [perangkat keras](#perangkat-keras-hardware) yang mengubah energi menjadi gerakan. Contoh yang gampang dibayangkan adalah motor pada pintu otomatis. Saat pengendali mengirim perintah, motor bergerak dan pintunya terbuka. Dalam [sistem tertanam](#sistem-tertanam-embedded-system) atau IoT, aktuator inilah yang melakukan tindakan fisik berdasarkan perintah dari pengendali seperti [mikrokontroler](#mikrokontroler).

### ALU

ALU (*Arithmetic Logic Unit*) adalah bagian [CPU](#cpu-central-processing-unit) yang mengerjakan operasi aritmetika dan logika. Mulai dari menjumlahkan angka, membandingkan nilai, sampai operasi AND dan OR. [CU](#cu-control-unit) mengatur operasi yang perlu dijalankan, sementara [register](#register) menampung data yang sedang dipakai. Untuk operasi tertentu, prosesor juga bisa memakai unit khusus lainnya.

### Arsitektur Komputer

Arsitektur komputer bisa dibayangkan sebagai rancangan dasar cara kerja komputer. Rancangan ini menjelaskan bagaimana [instruksi](#instruksi) dijalankan, bagaimana [memori](#memori) diakses, dan bagaimana komponen saling berkomunikasi. Nanti kita akan bertemu beberapa konsep yang berkaitan, seperti [arsitektur Von Neumann](#von-neumann-arsitektur), [arsitektur Harvard](#harvard-arsitektur), serta pendekatan set instruksi [RISC](#risc-reduced-instruction-set-computing) dan [CISC](#cisc-complex-instruction-set-computing).

### Artificial Intelligence (AI)

Artificial Intelligence atau kecerdasan buatan adalah bidang yang mengembangkan sistem komputer untuk melakukan tugas seperti mengenali gambar, memahami bahasa, dan mengambil keputusan. Salah satu pendekatannya adalah [machine learning](#machine-learning), yang menggunakan data untuk belajar mengenali pola. Jadi, cakupan AI itu luas, dan belajar dari data hanyalah salah satu cara yang digunakan di dalamnya.

## B

### Bandwidth

Bandwidth menggambarkan berapa banyak data yang bisa dibawa sebuah jalur komunikasi per satuan waktu. Satuannya biasanya bit per detik, seperti Mbps atau Gbps. Bayangkan lebar jalan, makin lebar jalannya, makin banyak kendaraan yang bisa lewat bersama. Tapi jumlah kendaraan yang benar-benar lewat tetap bergantung pada kondisi jalannya. Begitu juga dengan transfer data. Istilah ini dipakai pada jaringan seperti [Ethernet](#ethernet) maupun koneksi komponen seperti [PCIe](#pcie-peripheral-component-interconnect-express).

### Bluetooth

Bluetooth adalah teknologi komunikasi tanpa kabel untuk menghubungkan perangkat dalam jarak relatif dekat. Misalnya, mouse ke laptop atau headphone ke ponsel. Supaya kedua perangkat bisa saling memahami data yang dikirim, Bluetooth memakai [protokol](#protokol) komunikasi. Teknologi ini sering kita temui pada [perangkat periferal](#perangkat-periferal-peripheral-device).

### Bus Sistem

Komponen komputer perlu jalur untuk saling mengirim informasi. Jalur yang menghubungkan [CPU](#cpu-central-processing-unit), [memori](#memori), dan perangkat [I/O](#inputoutput-io) ini disebut bus sistem. Dalam model dasar komputer, yang dibawa bukan cuma data, tetapi juga alamat tujuan dan sinyal kontrol. Pada komputer modern, komunikasinya bisa dibagi ke beberapa jalur khusus.

## C

### Cache

Cache menyimpan salinan data atau [instruksi](#instruksi) supaya bisa diakses lagi dengan lebih cepat. Di dalam atau dekat [CPU](#cpu-central-processing-unit), cache membantu prosesor agar nggak perlu terus mengambil data yang sama dari [RAM](#ram-random-access-memory). Aplikasi dan peramban juga memakai konsep cache untuk menyimpan data yang bisa digunakan kembali. Tujuannya mirip, walaupun lokasi dan cara kerjanya berbeda.

### Chipset

Chipset adalah satu atau beberapa chip pada [motherboard](#motherboard) yang membantu mengatur komunikasi dengan komponen lain, seperti perangkat penyimpanan dan port [USB](#usb-universal-serial-bus). Dulu, lebih banyak urusan komunikasi ditangani chipset. Pada banyak komputer modern, sebagian tugas tersebut sudah pindah ke [CPU](#cpu-central-processing-unit), termasuk pengendali [RAM](#ram-random-access-memory).

### CISC (Complex Instruction Set Computing)

CISC adalah pendekatan desain set [instruksi](#instruksi) yang menyediakan beragam operasi, termasuk instruksi yang bisa menggabungkan beberapa langkah pekerjaan. Misalnya, mengambil data dari [memori](#memori) lalu melakukan perhitungan terhadapnya. CISC sering dibahas bersama [RISC](#risc-reduced-instruction-set-computing). Tapi untuk menentukan prosesor mana yang lebih cepat, kita perlu melihat desain prosesor dan pekerjaan yang dijalankannya juga.

### Cloud Storage

Cloud storage memungkinkan kita menyimpan berkas di server milik penyedia layanan dan mengaksesnya lewat internet. Jadi, berkas yang disimpan dari laptop bisa dibuka lagi lewat perangkat lain. Layanan ini juga bisa dipakai untuk [penyimpanan cadangan](#penyimpanan-cadangan). Yang perlu diperhatikan, sinkronisasi saja belum tentu cukup untuk pencadangan, karena berkas yang terhapus di satu perangkat bisa ikut terhapus di tempat lain.

### CPU (Central Processing Unit)

CPU adalah prosesor utama yang menjalankan [instruksi](#instruksi) program dan mengatur banyak pekerjaan komputer. Di dalamnya ada bagian-bagian seperti [CU](#cu-control-unit), [ALU](#alu), dan [register](#register) yang punya tugas masing-masing. CPU memakai [RAM](#ram-random-access-memory) untuk mengakses data yang sedang dibutuhkan, dan bisa membagi pekerjaan dengan prosesor khusus seperti [GPU](#gpu-graphics-processing-unit) atau [NPU](#npu-neural-processing-unit).

### CU (Control Unit)

CU adalah bagian [CPU](#cpu-central-processing-unit) yang mengatur jalannya [instruksi](#instruksi). Setelah menafsirkan instruksi, CU mengirim sinyal kontrol ke bagian yang perlu bekerja. Misalnya, kapan data harus diambil dan kapan [ALU](#alu) perlu melakukan perhitungan. Dengan pengaturan ini, komponen-komponen di dalam prosesor bisa menjalankan tugasnya sesuai urutan yang diperlukan.

## E

### Edge Computing

Edge computing berarti mengolah data di dekat tempat data itu dihasilkan. Misalnya, kamera pintar memproses rekamannya sendiri atau dibantu komputer lokal di dekatnya. Dengan begitu, nggak semua data mentah harus dikirim ke server yang jauh. Ini bisa mengurangi waktu tunggu dan penggunaan [bandwidth](#bandwidth). Pendekatan ini sering dipakai dalam IoT, dan hasil pengolahannya tetap bisa dikirim ke [cloud storage](#cloud-storage).

### Ethernet

Ethernet adalah keluarga standar jaringan yang biasa dipakai untuk menghubungkan perangkat lewat kabel, baik kabel tembaga maupun serat optik. Standar ini mengatur cara data dikirim dalam jaringan lokal. [Bandwidth](#bandwidth) yang tersedia bergantung pada standar dan perangkatnya. Jadi, saat laptop sudah terhubung lewat Ethernet, akses internetnya tetap bergantung pada jaringan yang digunakan.

## G

### Gateway

Gateway menjadi penghubung dari satu jaringan atau sistem ke jaringan atau sistem lain. Di rumah, router biasanya berperan sebagai *default gateway*, yaitu tempat data dikirim ketika tujuannya berada di luar jaringan lokal. Pada kebutuhan tertentu, gateway juga bisa menerjemahkan [protokol](#protokol), misalnya supaya perangkat IoT dapat berkomunikasi dengan sistem lain.

### GPU (Graphics Processing Unit)

GPU dirancang untuk mengerjakan banyak operasi secara paralel, terutama saat mengolah grafis. Kemampuan [komputasi paralel](#komputasi-paralel) ini ternyata juga berguna untuk sebagian pekerjaan [machine learning](#machine-learning). GPU bekerja bersama [CPU](#cpu-central-processing-unit) dan ikut menghasilkan tampilan yang kita lihat, termasuk lingkungan tiga dimensi pada [Virtual Reality](#virtual-reality-vr).

## H

### Harvard (arsitektur)

Pada arsitektur Harvard, [memori](#memori) dan jalur untuk [instruksi](#instruksi) dipisahkan dari memori dan jalur untuk data. Dengan pemisahan ini, komputer bisa mengambil instruksi sambil mengakses data. Ini salah satu pendekatan dalam [arsitektur komputer](#arsitektur-komputer). Kita bisa membandingkannya dengan [Von Neumann](#von-neumann-arsitektur) yang memakai memori bersama, atau [Modified Harvard Architecture](#modified-harvard-architecture) yang menggabungkan sebagian karakteristik keduanya.

### HDD (Hard Disk Drive)

Di dalam HDD ada piringan magnetik yang berputar dan kepala baca-tulis yang bergerak untuk mengakses data. Komponen mekanis inilah yang membedakannya dari [SSD](#ssd-solid-state-drive). HDD termasuk [penyimpanan sekunder](#penyimpanan-sekunder), jadi datanya tetap tersimpan saat komputer dimatikan. Pada komputer pribadi, HDD umum dihubungkan lewat [SATA](#sata-serial-ata).

### HDMI

HDMI (*High-Definition Multimedia Interface*) adalah standar koneksi untuk mengirim video dan audio digital. Kalau teman-teman pernah menyambungkan laptop ke monitor atau televisi dengan kabel HDMI, itulah salah satu penggunaannya. Monitor dan televisi berperan sebagai [perangkat keluaran](#perangkat-keluaran-output-device). Resolusi, laju penyegaran, dan fitur audio yang bisa digunakan bergantung pada perangkat serta kabelnya.

## I

### Input/Output (I/O)

I/O adalah pertukaran data antara komputer dan perangkat atau lingkungan di luarnya. *Input* berarti data masuk, sementara *output* berarti data keluar. Keyboard termasuk [perangkat masukan](#perangkat-masukan-input-device), sedangkan monitor termasuk [perangkat keluaran](#perangkat-keluaran-output-device). Cakupannya juga sampai ke komunikasi dengan penyimpanan dan jaringan, jadi nggak terbatas pada apa yang kita ketik atau lihat di layar.

### Instruksi

Instruksi adalah perintah dasar dalam bahasa mesin yang memberi tahu [CPU](#cpu-central-processing-unit) apa yang harus dikerjakan. Contohnya memindahkan data, menjumlahkan nilai, atau melompat ke bagian program lain. [CU](#cu-control-unit) menafsirkan perintah tersebut agar bisa dijalankan. Instruksi yang didukung sebuah prosesor berkaitan dengan [arsitektur komputer](#arsitektur-komputer), termasuk pendekatan [RISC](#risc-reduced-instruction-set-computing) dan [CISC](#cisc-complex-instruction-set-computing).

### Internet of Things (IoT)

IoT menghubungkan benda fisik ke jaringan supaya bisa mengirim data, menerima perintah, atau bekerja bersama layanan lain. Contohnya lampu pintar yang bisa dinyalakan lewat ponsel. Di dalam perangkat IoT, kita bisa menemukan sensor, [aktuator](#aktuator), dan [mikrokontroler](#mikrokontroler). Perangkatnya dapat terhubung melalui [gateway](#gateway), sementara sebagian datanya bisa diolah di dekat sumbernya dengan [edge computing](#edge-computing).

## K

### Komputasi Paralel

Komputasi paralel membagi pekerjaan menjadi beberapa bagian yang dikerjakan pada waktu yang sama. Bagian-bagian ini bisa dijalankan oleh beberapa inti prosesor [multicore](#multicore), banyak unit pada [GPU](#gpu-graphics-processing-unit), atau bahkan beberapa komputer. Hasilnya bisa lebih cepat kalau pekerjaannya memang bisa dibagi dengan baik. Kalau satu langkah harus menunggu hasil langkah sebelumnya, pembagiannya jadi lebih terbatas.

## M

### Machine Learning

Machine learning adalah cabang AI yang menggunakan data untuk membentuk model yang bisa mengenali pola dan membuat prediksi atau keputusan. Misalnya, model belajar dari contoh surel untuk mengenali spam. Manusia tetap menyiapkan data dan merancang proses belajarnya, tetapi nggak perlu menulis aturan untuk setiap kemungkinan kasus. Untuk pekerjaan tertentu, prosesnya bisa dipercepat dengan [GPU](#gpu-graphics-processing-unit), [NPU](#npu-neural-processing-unit), atau [TPU](#tpu-tensor-processing-unit).

### Memori

Memori menyimpan data dan [instruksi](#instruksi) yang digunakan komputer. Saat membahas cara kerja prosesor, kita akan bertemu [register](#register), [cache](#cache), dan [RAM](#ram-random-access-memory). Ada memori yang isinya hilang ketika listrik mati, disebut *volatile*. Ada juga yang tetap menyimpan isinya, disebut *non-volatile*. Dalam percakapan sehari-hari, memori kerja biasanya dibedakan dari [penyimpanan sekunder](#penyimpanan-sekunder) seperti [SSD](#ssd-solid-state-drive) dan [HDD](#hdd-hard-disk-drive).

### Mikrokontroler

Mikrokontroler bisa dibayangkan sebagai komputer kecil dalam satu chip. Di dalamnya sudah ada prosesor, [memori](#memori), dan antarmuka [I/O](#inputoutput-io) untuk mengendalikan perangkat tertentu. Misalnya pada mesin cuci, mikrokontroler membaca tombol yang ditekan lalu mengatur kerja motor. Komponen ini banyak dipakai dalam [sistem tertanam](#sistem-tertanam-embedded-system) dan IoT, termasuk untuk memberi perintah ke [aktuator](#aktuator).

### Modified Harvard Architecture

Modified Harvard Architecture adalah variasi [arsitektur Harvard](#harvard-arsitektur) yang melonggarkan pemisahan [instruksi](#instruksi) dan data pada bagian tertentu. Salah satu contohnya memakai [cache](#cache) instruksi dan cache data yang terpisah, tetapi [memori](#memori) utamanya tetap digunakan bersama. Jadi, pada tingkat cache aksesnya terpisah, sementara pada memori utama ada kesamaan dengan pendekatan [Von Neumann](#von-neumann-arsitektur).

### Motherboard

Motherboard adalah papan sirkuit utama tempat komponen komputer terhubung. [CPU](#cpu-central-processing-unit), [RAM](#ram-random-access-memory), [chipset](#chipset), dan konektor penyimpanan terpasang atau terhubung melalui papan ini. Motherboard juga menyediakan koneksi untuk komponen tambahan, misalnya lewat [PCIe](#pcie-peripheral-component-interconnect-express), serta port untuk perangkat luar seperti [USB](#usb-universal-serial-bus). Dari sinilah banyak hubungan antarkomponen komputer bisa kita lihat secara fisik.

### Multicore

Multicore berarti satu prosesor punya lebih dari satu inti pemrosesan atau *core*. Beberapa inti ini bisa mengerjakan tugas berbeda atau membagi satu pekerjaan secara paralel. Ini mendukung [komputasi paralel](#komputasi-paralel), tetapi manfaatnya tetap bergantung pada bagaimana perangkat lunaknya dibuat. Multicore membahas jumlah inti pada [perangkat keras](#perangkat-keras-hardware), sedangkan [multithreading](#multithreading) membahas alur eksekusi program.

### Multithreading

Multithreading memungkinkan satu proses memiliki beberapa alur eksekusi yang disebut *thread*. Contohnya, aplikasi tetap merespons tombol saat thread lain sedang memuat data. Pada satu inti [CPU](#cpu-central-processing-unit), thread bisa berjalan bergantian. Kalau prosesornya [multicore](#multicore), sebagian thread bisa benar-benar berjalan bersamaan. Itu sebabnya multithreading tidak selalu berarti [komputasi paralel](#komputasi-paralel).

## N

### NPU (Neural Processing Unit)

NPU adalah unit pemrosesan khusus untuk mempercepat operasi jaringan saraf dalam [machine learning](#machine-learning). Salah satu pekerjaan utamanya adalah menghitung matriks, yaitu susunan angka dalam baris dan kolom. NPU membantu menjalankan beban kerja AI tertentu secara efisien dan bisa melengkapi [CPU](#cpu-central-processing-unit) serta [GPU](#gpu-graphics-processing-unit). Nama *neural* merujuk pada jaringan saraf buatan, jadi nggak berarti chip ini meniru seluruh cara kerja otak manusia. Contoh cara kerjanya bisa dibaca dalam [dokumentasi NPU Intel](https://intel.github.io/intel-npu-acceleration-library/npu.html).

### NVMe (Non-Volatile Memory Express)

NVMe adalah [protokol](#protokol) untuk mengakses penyimpanan non-volatile yang dirancang dengan mempertimbangkan kemampuan media seperti [SSD](#ssd-solid-state-drive). Pada SSD internal komputer, NVMe biasanya memakai koneksi [PCIe](#pcie-peripheral-component-interconnect-express). Ada satu istilah lain yang sering muncul bersama NVMe, yaitu M.2. M.2 menjelaskan format modulnya, jadi SSD berbentuk M.2 bisa memakai [SATA](#sata-serial-ata) atau PCIe/NVMe sesuai jenisnya.

## P

### PCIe (Peripheral Component Interconnect Express)

PCIe adalah standar koneksi berkecepatan tinggi untuk komponen seperti kartu [GPU](#gpu-graphics-processing-unit), [SSD](#ssd-solid-state-drive) [NVMe](#nvme-non-volatile-memory-express), dan kartu jaringan. Koneksi ini punya jalur yang disebut *lane*. Jumlah lane dan generasi PCIe memengaruhi [bandwidth](#bandwidth) yang tersedia. Pada komputer pribadi, slot atau konektornya bisa kita temukan di [motherboard](#motherboard).

### Penyimpanan Cadangan

Penyimpanan cadangan dipakai untuk menyimpan salinan data agar bisa dipulihkan kalau data aslinya hilang, rusak, atau terhapus. Medianya bisa berupa [HDD](#hdd-hard-disk-drive) eksternal atau [cloud storage](#cloud-storage) yang diatur untuk pencadangan. Salinannya sebaiknya disimpan terpisah dari data utama. Kalau cuma dipindah ke folder lain pada drive yang sama, kedua salinan tetap bisa hilang saat drive itu rusak.

### Penyimpanan Sekunder

Penyimpanan sekunder menyimpan data dan program untuk jangka panjang, termasuk saat komputer mati. Contohnya [SSD](#ssd-solid-state-drive) dan [HDD](#hdd-hard-disk-drive). Ketika program dijalankan, data dan [instruksi](#instruksi) yang dibutuhkan biasanya dimuat ke [RAM](#ram-random-access-memory) terlebih dahulu sebagai ruang kerja. Sifatnya disebut non-volatile karena data bertahan tanpa listrik, walaupun tetap bisa hilang akibat kerusakan atau penghapusan.

### Penyimpanan Utama

Dalam glosarium ini, penyimpanan utama merujuk pada [memori](#memori) utama, terutama [RAM](#ram-random-access-memory), yang menampung data dan [instruksi](#instruksi) yang sedang dipakai [CPU](#cpu-central-processing-unit). Bayangkan meja kerja tempat kita menaruh bahan yang sedang dikerjakan. [Penyimpanan sekunder](#penyimpanan-sekunder) seperti lemari untuk menyimpan bahan itu lebih lama. Kalau teman-teman menemukan cakupan istilah yang sedikit berbeda di buku lain, perhatikan konteks pembahasannya juga.

### Perangkat Keras (Hardware)

Perangkat keras adalah bagian fisik komputer yang bisa kita lihat dan sentuh. Contohnya [motherboard](#motherboard), [CPU](#cpu-central-processing-unit), [RAM](#ram-random-access-memory), keyboard, dan monitor. Masing-masing punya tugas, mulai dari menerima [masukan](#perangkat-masukan-input-device) sampai menampilkan hasil. Supaya pekerjaan itu sesuai dengan yang kita inginkan, perangkat keras mengikuti arahan [perangkat lunak](#perangkat-lunak-software).

### Perangkat Keluaran (Output Device)

Perangkat keluaran menyampaikan hasil pemrosesan komputer. Bentuknya bisa berupa tampilan di monitor, suara dari speaker, atau cetakan dari printer. Semuanya termasuk [perangkat keras](#perangkat-keras-hardware). Dalam sistem kendali, keluarannya juga bisa berupa gerakan melalui [aktuator](#aktuator). Inilah sisi *output* dalam [I/O](#inputoutput-io).

### Perangkat Lunak (Software)

Perangkat lunak adalah program beserta data pendukung yang mengarahkan kerja [perangkat keras](#perangkat-keras-hardware). Contohnya sistem operasi, aplikasi pengolah kata, dan driver yang membantu sistem berkomunikasi dengan perangkat. Saat program dijalankan, pekerjaannya pada akhirnya melibatkan [instruksi](#instruksi) yang bisa dieksekusi prosesor.

### Perangkat Masukan (Input Device)

Perangkat masukan mengirim data atau sinyal ke komputer. Keyboard mengirim teks yang kita ketik, mikrofon menangkap suara, dan sensor suhu membaca kondisi lingkungan. Semuanya merupakan [perangkat keras](#perangkat-keras-hardware) yang memberikan masukan untuk ditangani [perangkat pemrosesan](#perangkat-pemrosesan-processing-device). Dari contoh sensor tadi, kita bisa melihat bahwa masukan juga bisa datang tanpa tindakan langsung dari manusia.

### Perangkat Pemrosesan (Processing Device)

Perangkat pemrosesan mengolah data dengan menjalankan operasi tertentu. [CPU](#cpu-central-processing-unit) menangani pekerjaan umum, [GPU](#gpu-graphics-processing-unit) cocok untuk banyak perhitungan paralel, sementara [NPU](#npu-neural-processing-unit) menangani beban kerja AI tertentu. Saat bekerja, komponen-komponen ini membutuhkan [memori](#memori) untuk menyimpan dan mengakses data yang digunakan.

### Perangkat Periferal (Peripheral Device)

Perangkat periferal menambah kemampuan komputer, misalnya keyboard untuk mengetik, printer untuk mencetak, atau drive eksternal untuk menyimpan berkas. Fungsinya bisa berupa [I/O](#inputoutput-io) maupun penyimpanan. Periferal dapat terpasang di dalam atau di luar komputer, dengan koneksi seperti [USB](#usb-universal-serial-bus), [Bluetooth](#bluetooth), dan antarmuka lainnya.

### Protokol

Protokol adalah aturan agar perangkat atau sistem bisa saling bertukar informasi. Aturannya mencakup bentuk pesan dan urutan komunikasi, sehingga pengirim dan penerima sama-sama memahami apa yang dikirim. Penggunaannya luas, sampai ke komunikasi di dalam komputer. [NVMe](#nvme-non-volatile-memory-express), misalnya, mengatur komunikasi dengan perangkat penyimpanan.

## R

### RAM (Random Access Memory)

RAM adalah [memori](#memori) kerja yang menampung data dan program yang sedang digunakan. RAM utama pada komputer umumnya bersifat *volatile*, jadi isinya hilang saat daya terputus. Itu sebabnya berkas perlu disimpan ke [penyimpanan sekunder](#penyimpanan-sekunder) agar tetap tersedia setelah komputer dimatikan. Saat prosesor membutuhkan data tertentu berulang kali, [cache](#cache) bisa membantu menyediakan salinannya lebih cepat daripada mengambilnya dari RAM.

### Real-time

Real-time berarti sistem harus memberikan respons dalam batas waktu yang ditentukan. Jadi, yang diperhatikan adalah apakah responsnya datang tepat waktu untuk kebutuhan tersebut. Pada [sistem tertanam](#sistem-tertanam-embedded-system) seperti pengendali rem, respons yang terlambat bisa membuat hasilnya tidak lagi berguna. Istilah ini nggak berarti semuanya terjadi tanpa jeda. Penjelasan berbasis batas waktu ini juga dipakai oleh [FreeRTOS](https://freertos.org/).

### Register

Register adalah tempat penyimpanan kecil dan sangat cepat di dalam [CPU](#cpu-central-processing-unit). Isinya bisa berupa data, alamat, atau hasil operasi yang sedang digunakan. [ALU](#alu), misalnya, memakai nilai dalam register untuk melakukan perhitungan. Kapasitasnya jauh lebih kecil daripada [RAM](#ram-random-access-memory), dan tugasnya berbeda dari [cache](#cache) yang menyimpan salinan data atau [instruksi](#instruksi).

### RISC (Reduced Instruction Set Computing)

RISC adalah pendekatan desain set [instruksi](#instruksi) yang menekankan operasi dasar yang relatif sederhana dan teratur. Pada banyak desain RISC, instruksi untuk mengakses [memori](#memori) dipisahkan dari operasi perhitungan pada [register](#register). RISC sering dibahas bersama [CISC](#cisc-complex-instruction-set-computing). Satu hal yang perlu diingat, instruksi RISC nggak selalu selesai dalam satu siklus clock. Waktunya bergantung pada instruksi dan desain prosesor, seperti yang bisa dilihat pada [dokumentasi waktu instruksi Arm](https://developer.arm.com/documentation/ddi0337/e/Instruction-Timing/Processor-instruction-timings).

## S

### SATA (Serial ATA)

SATA adalah standar antarmuka untuk menghubungkan perangkat penyimpanan, seperti [HDD](#hdd-hard-disk-drive), sebagian [SSD](#ssd-solid-state-drive), dan drive optik. Pada komputer pribadi, koneksinya umum tersedia di [motherboard](#motherboard). Karena SSD bisa memakai SATA maupun [PCIe](#pcie-peripheral-component-interconnect-express)/[NVMe](#nvme-non-volatile-memory-express), nama SSD saja belum memberi tahu kita jenis koneksi yang dipakainya.

### Sistem Tertanam (Embedded System)

Sistem tertanam adalah sistem komputer yang menjadi bagian dari perangkat lain untuk menjalankan tugas tertentu. Contohnya pengatur siklus mesin cuci atau pengendali suhu AC. Sistem ini sering memakai [mikrokontroler](#mikrokontroler) untuk membaca sensor dan mengendalikan [aktuator](#aktuator). Sebagian perlu memberikan respons secara [real-time](#real-time). Koneksi internet bersifat terpisah dari itu, jadi sistem tertanam nggak harus menjadi perangkat IoT.

### SSD (Solid State Drive)

SSD adalah media [penyimpanan sekunder](#penyimpanan-sekunder) yang umumnya memakai [memori](#memori) flash dan tidak memiliki bagian mekanis bergerak. Kalau [HDD](#hdd-hard-disk-drive) perlu menggerakkan kepala baca-tulis ke posisi data, SSD mengakses datanya secara elektronik. SSD umumnya punya waktu akses lebih singkat dan lebih tahan guncangan saat digunakan. Koneksinya bisa memakai [SATA](#sata-serial-ata) atau [PCIe](#pcie-peripheral-component-interconnect-express) dengan [protokol](#protokol) [NVMe](#nvme-non-volatile-memory-express).

## T

### TPU (Tensor Processing Unit)

TPU adalah akselerator buatan Google untuk mempercepat operasi pada tensor dalam [machine learning](#machine-learning). Untuk gambaran awal, tensor bisa dipahami sebagai susunan angka, misalnya dalam bentuk daftar atau tabel. TPU dipakai untuk melatih model dan menjalankan inferensi, yaitu menggunakan model yang sudah dilatih. TPU dan [NPU](#npu-neural-processing-unit) sama-sama ditujukan untuk pekerjaan AI, sementara [GPU](#gpu-graphics-processing-unit) juga banyak dipakai untuk grafis dan komputasi lainnya.

## U

### USB (Universal Serial Bus)

USB adalah standar koneksi untuk mengirim data dan menyalurkan daya antarperangkat. Kita sering memakainya untuk menghubungkan [perangkat periferal](#perangkat-periferal-peripheral-device) seperti keyboard dan flash drive, atau menyambungkan ponsel ke komputer. Yang perlu diperhatikan, bentuk konektor seperti USB-C belum menjelaskan semua kemampuannya. Kecepatan dan fitur yang didukung tetap perlu dilihat dari spesifikasi perangkat serta kabelnya.

## V

### Virtual Reality (VR)

Virtual Reality menghadirkan lingkungan digital yang membuat pengguna merasa berada di dalamnya, biasanya lewat headset khusus. Sensor membaca gerakan sebagai [masukan](#perangkat-masukan-input-device), lalu layar dan speaker menyampaikan [keluaran](#perangkat-keluaran-output-device). [GPU](#gpu-graphics-processing-unit) membantu menghasilkan tampilan tiga dimensinya. Supaya nyaman digunakan, tampilan perlu mengikuti gerakan pengguna dengan waktu respons yang singkat.

### Von Neumann (arsitektur)

Dalam arsitektur Von Neumann, [instruksi](#instruksi) program dan data ditempatkan dalam [memori](#memori) yang sama. [CPU](#cpu-central-processing-unit) mengambil keduanya dari memori bersama tersebut. Pendekatan [arsitektur komputer](#arsitektur-komputer) ini bisa dibandingkan dengan [arsitektur Harvard](#harvard-arsitektur) yang memisahkan jalur dan memori instruksi dari data. Pada komputer modern, gagasan memori bersama juga bisa dipadukan dengan [cache](#cache) terpisah seperti pada [Modified Harvard Architecture](#modified-harvard-architecture).

## Kesimpulan

Sekarang mulai kelihatan bagaimana istilah-istilah tadi saling terhubung. [Perangkat keras](#perangkat-keras-hardware) menjalankan arahan [perangkat lunak](#perangkat-lunak-software), prosesor mengolah data dengan bantuan memori, lalu hasilnya bisa disimpan atau ditampilkan ke pengguna. Dari kegiatan sederhana seperti mengetik saja, sudah ada beberapa komponen yang bekerja bersama.

Hubungan inilah yang ingin saya pahami lewat glosarium ini. RAM dan SSD sama-sama menyimpan data, tapi dipakai untuk kebutuhan yang berbeda. Multicore berkaitan dengan inti prosesor, sementara multithreading berkaitan dengan alur eksekusi. Saat kaitannya mulai dipahami, istilah-istilah itu jadi lebih mudah dibayangkan daripada sekadar dihafal namanya.

Catatan ini tentu masih bisa berkembang seiring materi yang saya pelajari. Kalau ada istilah yang belum langsung dipahami, coba hubungkan dengan perangkat yang teman-teman pakai sehari-hari, lalu baca lagi konsep yang berkaitan. Pelan-pelan saja, kita bisa mulai dari satu istilah dan menemukan banyak hal lain dari sana.
