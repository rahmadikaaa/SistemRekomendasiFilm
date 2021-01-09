# UAS_SPK_AlfianAmmar_171011402082
Alfian Ammar / 171011402082 / 04TPLM004 V.107
1. MEMBUAT MATRIX RIWAYAT USER
Content-based menggunakan riwayat user dan profil item sebagai bahan dasar saat merekomendasikan. Untuk movie recommender, pertama-tama kita buat matrix atau tabel yang barisnya merupakan daftar semua film yang telah dirating oleh user, dan kolomnya ada semua “fitur” atau profil dari sebuah film.

“Fitur” atau profil film ini dapat kita tentukan sendiri dengan beragam cara dari yang sederhana hingga rumit. Yang paling sederhana adalah dengan mengekstrak secara manual profil sebuah film yang biasanya menjadi pertimbangan dalam menonton. Misalnya saya contohkan pada tabel di bawah adalah genre sebuah film.

2. DAPATKAN VEKTOR PROFIL USER
Vektor profil user adalah sebuah vektor (array 1 dimensi) yang merangkum matrix riwayatnya. Paling sederhana adalah dengan menjumlahkan semua nilai pada kolom fitur yang sama (tidak termasuk kolom rating).
Tetapi metode menjumlahkan tentu tidak “merangkum” dengan baik. Tampak nilai pada kolom Sci-fi, Thriller, dan Horror adalah sama tanpa menunjukkan mana yang lebih disukai. Metode ini juga bisa menghasilkan bias. Seorang user bisa jadi dianggap menyukai kategori yang sering dia tonton, walaupun dia selalu memberi rating dengan nilai buruk pada kategori tersebut.

3. PREDIKSI RATING FILM BERDASARKAN PROFIL
Setelah diperoleh vektor profil user, kita dapat memprediksi film mana yang akan disukai oleh user. Misalnya jika diketahui dua film berikut, kira-kira mana yang lebih disukai?
Kita bisa hitung perkiraan rating yang akan diberikan oleh user A dengan cara yang mirip dengan sebelumnya. Yakni merata-rata hasil perkalian profil film tersebut dengan profil user.

IMPLEMENTASI
Di kode tersebut saya menggunakan 21 fitur: 19 fitur pertama adalah genre film, dan 2 fitur berikutnya adalah aktor utama pada film tersebut (2 nama ini dipilih dari 2 nama aktor yang filmnya paling sering dirating oleh user pada data train), dapat dilihat pada variabel list `features`.
Lalu inti dari kode tersebut terbagi menjadi tiga bagian (dapat dibaca di comment section kode tersebut):

Memformat dataset, karena dataset yang tersedia bukan one-hotencoded seperti tabel contoh di atas maka perlu penyesuaian terlebih dahulu.
Membuat user profile, sesuai dengan rumus di atas menggunakan rata-rata rating tiap fitur
Memprediksi hasil pada data test, sesuai dengan cara di atas menggunakan rata-rata juga..
Hasil prediksi dapat dilihat di file `result.csv` setelah program dijalankan. Jika diperhatikan hasilnya belum terlalu bagus, tetapi beberapa film yang di rating oleh user dengan hasil yang tinggi juga berhasil terprediksi dengan nilai yang tinggi.
