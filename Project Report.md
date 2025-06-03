# Laporan Proyek Machine Learning - Sistem Rekomendasi Destinasi Wisata Indoensia
### Oleh Muhammad Syafiq Irzaky

# 🌍 Project Overview (Ulasan Proyek)

Bagian ini memberikan gambaran umum mengenai proyek sistem rekomendasi tempat wisata di Indonesia. Ini mencakup latar belakang, justifikasi pentingnya proyek, serta tinjauan terhadap penelitian terkait yang menjadi dasar pengembangan.

## 1. Latar Belakang

Indonesia, dengan kekayaan alam dan keragaman budayanya, merupakan destinasi pariwisata yang sangat beragam dan terus menunjukkan pertumbuhan signifikan sebagai sektor vital bagi perekonomian nasional. Data terbaru dari Badan Pusat Statistik (BPS) per 3 Juni 2024 menunjukkan bahwa pada April 2024, kunjungan wisatawan mancanegara (wisman) ke Indonesia mencapai 1,07 juta kunjungan. Jumlah ini menandai kenaikan sebesar 23,23 persen dibandingkan dengan periode yang sama pada tahun sebelumnya (y-on-y), dengan wisman mayoritas berasal dari Malaysia, Australia, dan Tiongkok. Lebih lanjut, data BPS juga mencatat peningkatan aktivitas perjalanan oleh wisatawan nasional (wisnas) yang melakukan perjalanan ke luar negeri sebanyak 756,02 ribu perjalanan pada April 2024, naik 33,13 persen (y-on-y). Angka-angka ini secara kolektif menggarisbawahi dinamika tinggi dan volume besar wisatawan yang terlibat dalam aktivitas pariwisata, baik yang masuk ke Indonesia maupun yang bepergian dari Indonesia, yang secara implisit juga menunjukkan potensi besar untuk perjalanan domestik.

Dengan volume wisatawan yang besar dan keragaman destinasi yang luar biasa di Indonesia, tantangan utama yang muncul adalah **information overload**. Wisatawan, baik domestik maupun mancanegara, seringkali kesulitan dalam menyaring dan menemukan destinasi yang paling sesuai dengan preferensi unik mereka di tengah melimpahnya pilihan (Ningrum, Rustamaji, & Fauziah, 2019).

Untuk mengatasi permasalahan tersebut, pemanfaatan teknologi **sistem rekomendasi** menjadi sangat relevan. Sistem rekomendasi dapat membantu pengguna dengan menyajikan saran destinasi yang dipersonalisasi berdasarkan preferensi historis, kemiripan antar destinasi, atau perilaku pengguna lain. Penelitian sebelumnya telah banyak mengeksplorasi berbagai metode untuk sistem rekomendasi pariwisata:

- Faurina dan Sitanggang (2023) mengimplementasikan metode **Content-Based Filtering (CBF)** dan **Collaborative Filtering (CF)** untuk rekomendasi wisata di Bali, di mana CBF fokus pada preferensi kategori destinasi dan CF menggunakan histori rating pengguna.
- Ridwansyah, Subartini, dan Sylviani (2024) menggarisbawahi bahwa Content-Based Filtering merupakan metode yang efektif untuk memberikan rekomendasi berdasarkan kesamaan atribut atau item yang disukai pengguna, serta terbukti dapat menghasilkan rekomendasi yang sederhana dan efisien.
- Ningrum et al. (2019) mengembangkan sistem serupa untuk destinasi di Yogyakarta menggunakan pendekatan **hybrid filtering** yang menggabungkan CBF dan CF, yang hasilnya menunjukkan penerimaan yang baik dari pengguna.

## 2. Mengapa dan Bagaimana Masalah Ini Harus Diselesaikan

Keterbatasan wisatawan dalam mengakses informasi yang relevan dan personal mengenai destinasi wisata dapat:
- Mengurangi kualitas pengalaman berwisata
- Menyebabkan konsentrasi wisatawan hanya pada destinasi populer
- Menghambat pertumbuhan pariwisata yang merata dan berkelanjutan

**Alasan pentingnya penyelesaian masalah:**
1. Meningkatkan Pengalaman Pengguna
2. Mendorong Eksplorasi Destinasi Baru
3. Optimalisasi Sumber Daya dan Waktu
4. Potensi Peningkatan Ekonomi Lokal

## 3. Referensi

1. Badan Pusat Statistik. (2024, 3 Juni). *Perkembangan Pariwisata dan Transportasi Nasional April 2024*.
2. Faurina, R., & Sitanggang, E. (2023). *Implementasi Metode Content-Based Filtering dan Collaborative Filtering pada Sistem Rekomendasi Wisata di Bali*. Techno. com, 22(4), 870-881.
3. Ningrum, A. S., Rustamaji, H. C., & Fauziah, Y. (2019). *Content Based Dan Collaborative Filtering Pada Rekomendasi Tujuan Pariwisata Di Daerah Yogyakarta*. Telematika: Jurnal Informatika dan Teknologi Informasi, 16(1), 44-51.
4. Ridwansyah, T., Subartini, B., & Sylviani, S. (2024). *Penerapan Metode Content-Based Filtering pada Sistem Rekomendasi*. Mathematical Sciences and Applications Journal, 4(2), 70-77.

# 📈 Business Understanding

Bagian ini menguraikan pemahaman bisnis terkait proyek pengembangan sistem rekomendasi tempat wisata di Indonesia. Ini mencakup identifikasi masalah yang ada, tujuan yang ingin dicapai, serta pendekatan solusi yang akan diimplementasikan.

## 1. Problem Statements (Pernyataan Masalah)

Sektor pariwisata Indonesia memiliki potensi ekonomi dan pengembangan yang sangat besar, namun belum termanfaatkan sepenuhnya. Tantangan utama terletak pada belum optimalnya proses penemuan dan pemilihan destinasi oleh wisatawan. Wisatawan kerap menghadapi _information overload_ dari berbagai sumber informasi, sementara platform yang ada seringkali bersifat generik dan **kurangnya personalisasi**. Akibatnya, proses perencanaan perjalanan menjadi **memakan waktu dan tidak efisien**. Hal ini juga menyebabkan wisatawan cenderung **kesulitan menemukan destinasi baru** atau yang kurang populer, dan lebih memilih destinasi yang sudah umum dikenal.

Kondisi ini berdampak langsung pada berbagai aspek bisnis dan pengembangan pariwisata:
1. **Pengalaman wisatawan menjadi kurang optimal**, yang dapat mempengaruhi tingkat kepuasan dan minat untuk berkunjung kembali.
2. **Banyak destinasi berkualitas**, termasuk yang memiliki rating tinggi namun belum populer, menjadi kurang termanfaatkan sehingga potensi pendapatan dari aset wisata tersebut tidak tergali maksimal.
3. **Distribusi manfaat ekonomi pariwisata menjadi tidak merata.** UMKM dan komunitas lokal pengelola destinasi wisata yang kurang populer kesulitan mendapatkan visibilitas dan akses pasar yang memadai.
4. **Pertumbuhan dan daya saing** sektor pariwisata nasional secara keseluruhan menjadi **terbatas** karena belum optimalnya pemanfaatan seluruh potensi destinasi yang ada.

**Pernyataan Masalah Utama:**
1. **Bagaimana** mengatasi information overload dan kurangnya personalisasi agar wisatawan dapat secara efisien menemukan destinasi wisata di Indonesia yang paling relevan dengan preferensi unik mereka, sehingga meningkatkan potensi kunjungan dan pendapatan destinasi?
2. **Bagaimana** mengembangkan sistem rekomendasi destinasi yang dipersonalisasi, yang tidak hanya meningkatkan kepuasan wisatawan, tetapi juga mampu mendorong penemuan destinasi baru (termasuk yang belum populer namun memiliki rating baik, atau dikelola UMKM/komunitas lokal), guna mendukung pemerataan manfaat ekonomi pariwisata dan pertumbuhan sektor secara lebih inklusif dan berkelanjutan?

## 2. Goals (Tujuan)

**Tujuan Utama:**  
Mengembangkan sistem rekomendasi tempat wisata di Indonesia yang cerdas dan adaptif.

**Tujuan Spesifik:**
- **Mengembangkan Model Content-Based Filtering dengan TF-IDF dan Cosine Similarity:** Tujuan ini adalah untuk membangun sistem rekomendasi yang menyarankan destinasi wisata berdasarkan kemiripan konten atau atributnya. Secara teknis, ini melibatkan penggunaan metode TF-IDF (_Term Frequency-Inverse Document Frequency_) untuk mengubah atribut teks setiap destinasi menjadi representasi numerik (vektor) yang menyoroti kata-kata kunci penting. Selanjutnya, Cosine Similarity akan digunakan untuk menghitung seberapa mirip satu destinasi dengan destinasi lainnya berdasarkan vektor fitur tersebut. Hasilnya, sistem dapat merekomendasikan tempat-tempat yang karakteristiknya serupa dengan yang pernah dikunjungi pengguna.
- **Mengembangkan model Collaborative Filtering dengan deep learning:** Poin ini berfokus pada pembuatan model rekomendasi yang belajar dari pola perilaku kolektif semua pengguna. Artinya, sistem akan menganalisis interaksi pengguna dengan destinasi (seperti rating yang diberikan) untuk menemukan pengguna lain dengan selera serupa. Dengan menggunakan teknik deep learning, model dapat menangkap pola preferensi yang kompleks dan tersembunyi. Dengan demikian, sistem dapat merekomendasikan destinasi yang disukai oleh pengguna-pengguna serupa, bahkan jika pengguna tersebut belum pernah melihat destinasi itu sebelumnya.
- **Menyediakan rekomendasi akurat dan dipersonalisasi:** Tujuan ini menekankan pada kualitas output sistem. "Akurat" berarti rekomendasi yang diberikan harus sesuai dan relevan dengan apa yang kemungkinan besar akan disukai pengguna. "Dipersonalisasi" berarti saran yang ditampilkan harus unik untuk setiap individu, berdasarkan preferensi pribadi mereka (baik dari konten yang mereka nilai maupun dari perilaku mereka dibandingkan pengguna lain), bukan rekomendasi generik yang sama untuk semua orang.
- **Meningkatkan pengalaman personalisasi pencarian destinasi:** Proyek ini bertujuan untuk membuat proses pencarian destinasi wisata menjadi lebih personal dan intuitif. Daripada hanya mengandalkan filter umum (seperti kota atau kategori), sistem rekomendasi akan secara proaktif menyajikan pilihan-pilihan yang telah disesuaikan dengan profil dan riwayat preferensi pengguna, seolah-olah sistem "mengenal" selera mereka.
- **Membantu menemukan destinasi baru dan beragam:** Salah satu tujuan penting adalah membantu pengguna keluar dari "gelembung" destinasi populer dan menemukan "**hidden gem**". Sistem rekomendasi, terutama melalui pendekatan Collaborative Filtering, dapat menyarankan destinasi yang mungkin tidak pernah terpikirkan oleh pengguna sebelumnya namun berpotensi besar untuk disukai. Ini juga membantu memperkenalkan keragaman destinasi wisata yang ada di Indonesia.

## 3. Solution Approach (Pendekatan Solusi)
Proyek ini bertujuan untuk mengembangkan sistem rekomendasi tempat wisata yang komprehensif untuk seluruh Indonesia, dengan mengimplementasikan dua pendekatan utama:
1. **Content-Based Filtering** menggunakan TF-IDF dan Cosine Similarity
2. **Collaborative Filtering** dengan model deep learning berdasarkan interaksi destinasi yang disukai pengguna

**Solusi yang diusulkan:**
| Pendekatan | Metode | Keunggulan | Referensi |
|------------|--------|------------|-----------|
| **Content-Based Filtering** | TF-IDF + Cosine Similarity | Rekomendasi berdasarkan kemiripan atribut | Ridwansyah et al. (2024) |
| **Collaborative Filtering** | Model Deep Learning | Rekomendasi berdasarkan pola preferensi pengguna | Faurina & Sitanggang (2023) |

**Perbandingan Pendekatan:**
| Aspek | Content-Based | Collaborative |
|-------|--------------|--------------|
| **Kekuatan** | Transparan, baik untuk preferensi spesifik | Personal, menemukan item tak terduga |
| **Kelemahan** | Terbatas pada kemiripan konten | Cold start problem |
| **Data Required** | Deskripsi destinasi | Histori interaksi pengguna |
| **Kompleksitas** | Relatif sederhana | Lebih kompleks |

# 🧠 Data Understanding

Bagian ini memberikan pemahaman mendalam mengenai dataset yang digunakan dalam proyek sistem rekomendasi tempat wisata di Indonesia.

## Dataset Overview
**Nama Dataset:** Indonesia Tourism Destination  
**Sumber:** Kaggle ([Link Dataset](https://www.kaggle.com/datasets/aprabowo/indonesia-tourism-destination))  

**Cakupan Data:**
- Destinasi wisata di 5 kota besar (Jakarta, Yogyakarta, Semarang, Bandung, Surabaya)
- Data pengguna dan rating

**File Utama:**
| File | Jumlah Data | Deskripsi |
|------|------------|-----------|
| `user.csv` | 300 | Data profil pengguna |
| `tourism_with_id.csv` | 437 | Data destinasi wisata |
| `tourism_rating.csv` | 10,000 | Data rating pengguna |

## Feature Description

### 1. `user.csv`
| Kolom | Tipe Data | Deskripsi |
|-------|----------|-----------|
| User_Id | Integer | ID unik pengguna |
| Location | String | Kota & provinsi domisili |
| Age | Integer | Usia pengguna (tahun) |

### 2. `tourism_with_id.csv`
| Kolom | Tipe Data | Deskripsi | Catatan |
|-------|----------|-----------|---------|
| Place_Id | Integer | ID unik destinasi | Primary Key |
| Place_Name | String | Nama destinasi | |
| Description | String | Deskripsi lengkap | |
| Category | String | Jenis wisata | 6 kategori |
| City | String | Lokasi kota | 5 kota |
| Price | Integer | Harga tiket (IDR) | |
| Rating | Float | Rating rata-rata (1-5) | |
| Time_Minutes | Float | Durasi kunjungan (menit) | 53% missing |
| Coordinate | Object | Koordinat geografis | |
| Lat | Float | Latitude | |
| Long | Float | Longitude | |
| Unnamed: 11 | Float | Kolom kosong | Diabaikan |
| Unnamed: 12 | Integer | Artefak | Diabaikan |

### 3. `tourism_rating.csv`
| Kolom | Tipe Data | Deskripsi | 
|-------|----------|-----------|
| User_Id | Integer | ID pengguna | Foreign Key |
| Place_Id | Integer | ID destinasi | Foreign Key | 
| Place_Ratings | Integer | Rating (1-5) | Target variable |

## Data Exploration Findings

### User Data Analysis
**Temuan Utama**
- 300 data unik user
- Data tidak memiliki missing value
- Mengandung data demografi

**Sebaran Geografis Pengguna**

Untuk mengetahui sebaran geografis pengguna, dilakukan perhitungan frekuensi setiap lokasi unik dan persentasenya terhadap total pengguna. Berikut adalah empat lokasi dengan jumlah pengguna terbanyak:
| Location | Count | Percentage |
|----------|-------|------------|
| Bekasi, Jawa Barat | 39 | 13.0% |
| Semarang, Jawa Tengah | 22 | 7.3% |
| Lampung, Sumatera Selatan | 20 | 6.7% |
| Yogyakarta, DIY | 20 | 6.7% |

![image](https://github.com/user-attachments/assets/1481669c-47a1-499a-b9fc-4d588d112592)

**Insight:** Data menunjukkan bahwa pengguna berasal dari berbagai lokasi di Indonesia. Bekasi, Jawa Barat, menjadi lokasi dengan kontribusi pengguna terbanyak (13.0%), diikuti oleh Semarang, Lampung, dan Yogyakarta. Adanya konsentrasi pengguna di beberapa kota besar ini bisa jadi mencerminkan basis pengguna awal aplikasi atau area dengan penetrasi internet yang lebih tinggi. Pemahaman ini dapat berguna jika personalisasi berdasarkan lokasi dipertimbangkan di masa depan.

**Distribusi Usia**

Statistik deskriptif untuk variabel usia pengguna dihitung untuk memahami profil usia pengguna

![image](https://github.com/user-attachments/assets/3b05b88f-f341-4fa0-917a-fda53aaefd75)

**Insight:** Rata-rata usia pengguna adalah sekitar 28.7 tahun, dengan median 29 tahun, menunjukkan distribusi yang relatif simetris. Rentang usia pengguna adalah dari 18 hingga 50 tahun, dengan standar deviasi 5.8 tahun, mengindikasikan variasi usia yang tidak terlalu lebar. Seperti yang dapat divisualisasikan pada histogram, mayoritas pengguna kemungkinan besar berada dalam rentang usia dewasa muda (20-an hingga awal 30-an). Informasi ini penting untuk memahami target audiens utama dari sistem rekomendasi.

### Tourism Data Analysis
**Kategori Destinasi**

Untuk mengetahui jenis destinasi wisata apa saja yang paling banyak terdapat dalam dataset, dilakukan perhitungan proporsi setiap kategori. Berikut merupakan tiga kategori teratas dengan persentase paling tinggi.

| Category | Percentage |
|----------|------------|
| Taman Hiburan | 30.9% |
| Budaya | 26.8% |
| Cagar Alam | 24.3% |

![Screen Shot 2025-06-01 at 08 32 38](https://github.com/user-attachments/assets/7f3fdcc3-e888-4379-8573-a1e288687934)

**Insight:** Tiga kategori destinasi wisata yang paling dominan dalam dataset adalah 'Taman Hiburan' (30.9%), 'Budaya' (26.8%), dan 'Cagar Alam' (24.3%). Hal ini menunjukkan bahwa sebagian besar destinasi yang tercakup dalam dataset berfokus pada ketiga jenis wisata tersebut. Keseimbangan atau ketidakseimbangan antar kategori ini dapat mempengaruhi variasi rekomendasi yang dihasilkan.

**Kota Destinasi**
Eksplorasi ini ntuk mengetahui lokasi kota destinasi wisata dari mana saja yang paling banyak terdapat dalam dataset, dilakukan perhitungan proporsi setiap kota. Berikut merupakan tiga kategori teratas dengan persentase paling tinggi.

| City | Percentage |
|------|------------|
| Yogyakarta | 28.8% |
| Bandung | 28.4% |
| Jakarta | 19.2% |

![Screen Shot 2025-06-01 at 08 21 55](https://github.com/user-attachments/assets/86fb8206-ebd3-4872-b242-ea4aeddc6ee3)

**Insight:** Grafik "Distribusi City" menunjukkan bahwa dataset destinasi wisata didominasi oleh Yogyakarta (28.8%) dan Bandung (28.4%), yang secara bersama-sama mencakup lebih dari separuh total destinasi. Jakarta menyusul dengan 19.2%, sementara Semarang (13.0%) dan Surabaya (10.5%) memiliki jumlah destinasi yang lebih sedikit. Distribusi yang tidak merata ini mengindikasikan bahwa sistem rekomendasi mungkin memiliki lebih banyak variasi pilihan untuk Yogyakarta dan Bandung, dan perlu perhatian agar destinasi di kota lain tetap mendapatkan representasi yang cukup dalam rekomendasi.

**Distribusi Harga**

Eksplorasi ini adalah untuk mengetahui sebaran harga tarif destinasi wisata dalam dataset. Berikut adalah statistik deskriptif untuk harga tarif seluruh destinasi.
| Statistic | Value (IDR) |
|-----------|-------------|
| Mean | 24,652 |
| Median | 5,000 |
| Max | 650,000 |

![Screen Shot 2025-06-01 at 08 36 29](https://github.com/user-attachments/assets/b95d66fc-d58b-4d98-a4af-9c8922a5baf4)

**Insight:** Distribusi harga tiket masuk menunjukkan adanya skewness positif yang signifikan. Nilai median (Rp5.000) jauh lebih rendah daripada nilai rata-rata (Rp24.652), yang mengindikasikan bahwa sebagian besar destinasi wisata memiliki harga tiket masuk yang relatif terjangkau, namun terdapat beberapa destinasi dengan harga tiket yang sangat tinggi (hingga Rp650.000) yang menaikkan nilai rata-rata. Visualisasi histogram price_dist.png akan memperjelas hal ini, dimana sebagian besar data akan terkonsentrasi di sisi kiri (harga rendah). Informasi ini penting jika harga akan digunakan sebagai fitur dalam model, karena outlier atau distribusi yang miring mungkin memerlukan perlakuan khusus seperti transformasi logaritmik.

**Rating Distribution:**

Eksplorasi ini adalah untuk mengetahui sebaran rata-rata rating yang diperoleh tiap destinasi wisata dalam dataset. Berikut adalah statistik deskriptif untuk rating seluruh destinasi.
| Statistic | Value |
|-----------|-------|
| Mean | 4.4 |
| Median | 4.5 |

![Screen Shot 2025-06-01 at 08 36 29](https://github.com/user-attachments/assets/bbb43f1f-8338-4b81-b830-cbdc1079de58)

**Insight:** Distribusi rating destinasi wisata ini menunjukkan kecenderungan negatif (skewed ke kiri), yang berarti sebagian besar rating berada di rentang nilai tinggi, sekitar 4.2 hingga 4.8. Hal ini mengindikasikan bahwa banyak pengguna memberikan penilaian positif terhadap destinasi tersebut. Namun, rata-rata rating (mean) yang sebesar 4.4 sedikit lebih rendah dibanding median sebesar 4.5, menandakan ada sejumlah rating rendah yang menarik nilai rata-rata ke bawah. Dengan kata lain, meskipun umumnya destinasi mendapatkan nilai bagus, ada beberapa penilaian kurang memuaskan yang memengaruhi distribusi keseluruhan.

### Rating Data Analysis
**Rating Statistics**
Analisis pada data rating bertujuan untuk memahami bagaimana pengguna memberikan penilaian terhadap destinasi wisata.
Frekuensi setiap nilai rating (1 hingga 5) dihitung untuk melihat bagaimana rating tersebar.

| Rating | Count |
|--------|-------|
| 3	| 2,842 |
| 4	| 2,672 |
| 2	| 2,538 |
| 5	| 1,228 |
| 1	| 720 |

| Statistic | Value |
|-----------|-------|
| Mean | 3.07 |
| Std Dev | 1.38 |
| Min | 1 |
| 25% | 2 |
| 50% | 3 |
| 75% | 4 |
| Max | 5 |

**Insight:** Distribusi rating menunjukkan bahwa pengguna paling sering memberikan rating 3 (2.842 kali), diikuti oleh rating 4 (2.672 kali) dan rating 2 (2.538 kali). Rating tertinggi (5) dan terendah (1) lebih jarang diberikan. Rata-rata rating sebesar 3.07 dengan median 3.0 mengindikasikan bahwa secara umum, kecenderungan penilaian pengguna sedikit di atas netral. Standar deviasi sebesar 1.38 menunjukkan adanya variasi yang cukup dalam penilaian yang diberikan oleh pengguna. Pemahaman distribusi rating ini krusial karena merupakan sinyal utama preferensi pengguna yang akan dipelajari oleh model collaborative filtering.

### Matrix Density

Dengan **total 10.000 rating,** kita dapat menghitung kepadatan matriks rating sebagai 10.000/(300×437) ≈ **7.6%**, yang termasuk sparse namun cukup untuk sistem rekomendasi dasar.

## 🔍 Ringkasan EDA

1.  **Kualitas Data**:
    * Data pengguna dan data rating lengkap.
    * Terdapat hanya 205 dari total 437 baris yang terisi atau sebanyak 53% nilai yang hilang (missing values) pada kolom `Time_Minutes`.
    * Adanya kolom-kolom `Unnamed` yang redundan dan tidak diperlukan.

2.  **Demografi Pengguna**:
    * Pengguna terkonsentrasi di Pulau Jawa, terutama di kota Bekasi, Semarang, dan Yogyakarta.
    * Rentang usia pengguna umumnya antara 18-40 tahun, dengan rata-rata usia 28.7 tahun.

3.  **Karakteristik Destinasi**:
    * Kategori destinasi yang mendominasi adalah taman hiburan dan situs budaya.
    * Yogyakarta dan Bandung merupakan kota dengan jumlah destinasi terbanyak dalam dataset.
    * Distribusi harga tiket masuk destinasi sangat miring (*highly skewed*).

4.  **Pola Pemberian Rating oleh Pengguna**:
    * Rata-rata rating yang diberikan pengguna adalah 3.07, yang menunjukkan kecenderungan netral.
    * Distribusi rating pengguna bersifat multimodal (memiliki beberapa puncak).
    * Matriks interaksi pengguna-item bersifat *sparse* (jarang), dengan kepadatan hanya 7.6%.

## 🚩 Permasalahan dan Insight Data

1.  **Missing Values**:
    * Kolom `Time_Minutes` pada data destinasi memiliki 53% data kosong, yang perlu ditangani jika fitur ini akan digunakan.
    * Kolom-kolom `Unnamed` dapat dihapus karena tidak memberikan informasi relevan.

2.  **Kemiringan Data (Data Skewness)**:
    * Distribusi harga tiket masuk destinasi sangat miring ke kanan (*right-skewed*), yang menandakan adanya beberapa destinasi dengan harga sangat tinggi dibandingkan mayoritas.
    * Distribusi rating yang diberikan pengguna bersifat multimodal, menunjukkan variasi dalam preferensi penilaian.

3.  **Kekosongan Data (Sparsity)**:
    * Matriks rating pengguna-destinasi memiliki kepadatan hanya 7.6%, mengindikasikan bahwa sebagian besar destinasi belum diberi rating oleh sebagian besar pengguna.
    * Masalah *cold start* yang timbul akibat kekarangan data ini perlu strategi penanganan di pengembangan sistem rekomendasi kedepannya.

4.  **Insights Penting**:
    * Mayoritas destinasi wisata dalam dataset adalah 'Taman Hiburan' dan 'Budaya'.
    * Kota Yogyakarta dan Bandung mendominasi dalam hal jumlah destinasi yang tersedia di dataset.
    * Rating yang diberikan pengguna cenderung netral hingga cukup baik, dengan banyak rating berada di angka 3 dan 4.

# ⚙️ Data Preparation

Tahap Data Preparation merupakan langkah berikutnya setelah pemahaman data Data Understanding. Pada tahap ini, dataset mentah yang telah dieksplorasi akan diolah dan ditransformasi menjadi format yang sesuai dan optimal untuk tahap pemodelan. Proses ini melibatkan serangkaian teknik untuk membersihkan, mengintegrasikan, dan menstrukturkan data guna meningkatkan kualitas dan relevansinya untuk analisis lebih lanjut. Berikut adalah tahapan persiapan data yang dilakukan secara berurutan:

## 1. Menggabungkan Kolom Nama dan Kategori Destinasi Wisata
Langkah awal dalam persiapan data adalah menggabungkan informasi esensial dari beberapa sumber data menjadi satu dataset yang komprehensif. Dalam konteks ini, data rating pengguna akan diperkaya dengan detail mengenai destinasi wisata.

* **Proses yang Dilakukan:**
    Dataset `rating` yang berisi `User_Id`, `Place_Id`, dan `Place_Ratings` digabungkan (merged) dengan subset dari dataset `tourism` yang memuat `Place_Id`, `Place_Name` (nama tempat wisata), dan `Category` (kategori destinasi). Penggabungan ini dilakukan menggunakan kolom `Place_Id` sebagai kunci (key) penggabungan. Metode penggabungan yang digunakan adalah `left join` (pd.merge(..., how='left')), yang memastikan semua data rating dari dataset `rating` tetap dipertahankan, dan informasi destinasi yang cocok akan ditambahkan.
    ```python
    # tourism_rating = pd.merge(rating, tourism[['Place_Id','Place_Name', 'Category']], on='Place_Id', how='left')
    ```
    Hasilnya adalah dataframe `tourism_rating` baru yang kini memiliki 10.000 baris dan 5 kolom: `User_Id`, `Place_Id`, `Place_Ratings`, `Place_Name`, dan `Category`.

* **Alasan Dilakukan:**
    * **Memperkaya Data Rating:** Tujuan utama penggabungan ini adalah untuk menambahkan konteks deskriptif (nama dan kategori destinasi) ke setiap entri rating. Informasi ini sangat penting, terutama untuk pengembangan sistem rekomendasi *Content-Based Filtering*.
    * **Analisis Lebih Mendalam:** Dengan informasi tambahan ini, analisis terhadap preferensi pengguna berdasarkan kategori atau nama tempat tertentu menjadi mungkin.
    * **Menjaga Integritas Data Rating:** Penggunaan `left join` memastikan tidak ada data rating yang hilang selama proses penggabungan, bahkan jika ada `Place_Id` di tabel rating yang (secara teoritis) tidak ditemukan di tabel tourism.

## 2. Standardisasi Format Kategori Destinasi
Setelah data digabungkan, langkah selanjutnya adalah melakukan standardisasi pada data kategorikal, khususnya pada kolom `Category`.

* **Proses yang Dilakukan:**
    1.  Pertama, dilakukan identifikasi terhadap semua nilai unik dalam kolom `Category` untuk memahami variasi jenis tempat wisata. Hasilnya menunjukkan kategori seperti 'Budaya', 'Bahari', 'Taman Hiburan', 'Cagar Alam', 'Pusat Perbelanjaan', dan 'Tempat Ibadah'.
        ```python
        # tourism_rating['Category'].unique()
        ```
    2.  Kemudian, dilakukan penggantian spasi dalam nama kategori dengan karakter underscore (`_`). Misalnya, "Taman Hiburan" diubah menjadi "Taman_Hiburan", "Cagar Alam" menjadi "Cagar_Alam", dan seterusnya untuk kategori lain yang mengandung spasi.
        ```python
        # tourism_rating['Category'] = tourism_rating['Category'].replace('Taman Hiburan', 'Taman_Hiburan')
        # # ... (penggantian serupa untuk kategori lain) ...
        # tourism_rating['Category'].unique()
        ```
    Hasilnya, semua kategori kini memiliki format yang konsisten tanpa spasi. Dipastikan juga menggunakan `tourism_rating.info()` bahwa tidak ada null value, yang menandakan bahwa seluruh proses transformasi berhasil.

* **Alasan Dilakukan:**
    * **Memudahkan Pemrosesan Teks:** Format tanpa spasi (menggunakan underscore) membuat setiap nama kategori menjadi satu token tunggal. Ini menyederhanakan proses analisis teks atau *feature engineering* di tahap selanjutnya (misalnya, saat menggunakan kategori dalam model TF-IDF).
    * **Konsistensi dan Keterbacaan:** Standardisasi ini meningkatkan konsistensi data dan mempermudah pembacaan serta penggunaan kategori sebagai fitur dalam model.

## 3. Mengatasi Missing Values dan Duplikasi Data
Kualitas data sangat mempengaruhi kinerja model. Oleh karena itu, pemeriksaan dan penanganan nilai hilang serta data duplikat adalah langkah penting.

* **Proses yang Dilakukan (Penanganan Missing Values):**
    Dilakukan pemeriksaan untuk mendeteksi keberadaan nilai `null` atau *missing values* pada setiap kolom dalam dataframe `tourism_rating` menggunakan metode `.isnull().sum()`.
    ```python
    # tourism_rating.isnull().sum()
    ```
    **Hasil:** Pemeriksaan menunjukkan bahwa tidak ada nilai hilang (semua kolom memiliki jumlah *missing values* 0) dalam dataframe `tourism_rating` yang telah digabungkan dan difokuskan pada kolom-kolom relevan.

* **Alasan Dilakukan (Penanganan Missing Values):**
    * **Memastikan Kelengkapan Data:** Langkah ini penting untuk memverifikasi bahwa data yang akan digunakan untuk pemodelan sudah lengkap.
    * **Mencegah Error pada Model:** Data yang tidak lengkap atau mengandung *missing values* dapat menyebabkan error selama proses pelatihan model atau menghasilkan prediksi yang tidak akurat.
    * Meskipun dalam kasus ini tidak ditemukan *missing values* pada kolom-kolom yang diperiksa, langkah verifikasi ini tetap merupakan praktik terbaik.

* **Proses yang Dilakukan (Penanganan Duplikasi Data):**
    1.  Dilakukan pengecekan jumlah baris data yang duplikat dalam dataframe `tourism_rating` menggunakan `.duplicated().sum()`.
        ```python
        # tourism_rating.duplicated().sum()
        # Output: np.int64(79)
        ```
        Hasilnya menunjukkan terdapat 79 baris data yang duplikat.
    2.  Baris-baris duplikat tersebut kemudian dihapus dari dataframe menggunakan `drop_duplicates(inplace=True)`.
    3.  Dilakukan verifikasi ulang untuk memastikan semua data duplikat telah terhapus.
        ```python
        # tourism_rating.drop_duplicates(inplace=True)
        # tourism_rating.duplicated().sum()
        # Output: np.int64(0)
        ```
    **Efek:** Setelah penghapusan duplikat, jumlah record dalam `tourism_rating` berkurang dari 10.000 menjadi 9.921 baris.

* **Alasan Dilakukan (Penanganan Duplikasi Data):**
    * **Menghindari Bias Model:** Data duplikat, terutama dalam konteks rating, dapat memberikan bobot yang tidak semestinya pada interaksi pengguna-item tertentu, sehingga berpotensi menyebabkan bias dalam model rekomendasi.
    * **Meningkatkan Kualitas Perhitungan Similarity:** Dalam *Collaborative Filtering*, data duplikat dapat mengganggu perhitungan kemiripan (similarity) antar pengguna atau antar item.
    * **Memastikan Keunikan Entri:** Setiap baris data rating seharusnya merepresentasikan satu interaksi unik. Penghapusan duplikat meningkatkan kualitas dan integritas data.

## 4. Penyiapan Data Final untuk Analisis
Untuk menghasilkan dataframe dari pemrosesan data secara keseluruhan, dibuat salinan kerja dari dataset yang telah bersih dan dilakukan pengurutan data. Nantinya, dataframe ini akan digunakan untuk diproses lebih lanjut dengan teknik dan metode terpisah sesuai dengan pendekatan solusi dan model yang akan dikembangkan.

* **Proses yang Dilakukan:**
    1.  Sebuah variabel baru bernama `preparation` dibuat sebagai salinan (working copy) dari dataframe `tourism_rating` yang telah melalui semua tahapan pembersihan sebelumnya.
    2.  Data dalam dataframe `preparation` kemudian diurutkan berdasarkan kolom `Place_Id`.
    ```python
    # preparation = tourism_rating
    # preparation.sort_values('Place_Id')
    ```
    **Struktur Data:** Dataframe `preparation` kini berisi 9.921 entri valid dengan 5 kolom utama: `User_Id`, `Place_Id`, `Place_Ratings`, `Place_Name`, dan `Category`.

* **Alasan Dilakukan:**
    * **Salinan Kerja (Working Copy):** Membuat salinan data adalah praktik yang baik untuk menjaga dataset asli yang telah dibersihkan tetap utuh, sementara modifikasi atau eksperimen lebih lanjut dapat dilakukan pada salinan tersebut.
    * **Mempermudah Analisis dan Visualisasi:** Mengurutkan data berdasarkan `Place_Id` dapat mempermudah inspeksi manual data, analisis eksploratif lebih lanjut (misalnya, melihat semua rating untuk destinasi tertentu secara berurutan), dan membantu dalam visualisasi pola rating antar tempat wisata.
    * **Kesiapan untuk Tahap Selanjutnya:** Dataset yang telah dibersihkan dan diorganisir ini dianggap siap untuk tahap *feature engineering* dan proses pembuatan model rekomendasi.

## 5. Persiapan Data untuk Model Content Based Filtering
### 1. Persiapan data
Sebelum membangun model CBF, data perlu disiapkan secara khusus. Karena CBF berfokus pada karakteristik intrinsik item (destinasi wisata), kita memerlukan daftar unik destinasi beserta fitur-fiturnya.

* **Proses yang Dilakukan:**
    1.  Salinan (`copy()`) dari dataset `preparation` (yang telah dibersihkan pada tahap Data Preparation) dibuat dengan nama `preparation_CBF`. Ini dilakukan untuk memastikan bahwa modifikasi data tidak memengaruhi dataset asli yang mungkin digunakan untuk pendekatan lain.
    2.  Duplikasi berdasarkan kolom `Place_Id` dihilangkan dari `preparation_CBF`. Langkah ini penting karena dalam CBF, kita hanya memerlukan satu representasi unik untuk setiap destinasi beserta fiturnya (nama, kategori), bukan multipel entri rating dari pengguna yang berbeda untuk destinasi yang sama.
        ```python
        # preparation_CBF = preparation.copy()
        # preparation_CBF = preparation_CBF.drop_duplicates('Place_Id')
        ```
    Hasil dari langkah ini adalah sebuah dataframe yang berisi **437 destinasi unik**, masing-masing dengan informasi `User_Id` (pengguna pertama yang meratingnya di data yang tidak terduplikasi), `Place_Id`, `Place_Ratings` (rating dari pengguna tersebut), `Place_Name`, dan `Category`.

### 2. Ekstraksi Informasi Destinasi Wisata
Untuk memfokuskan analisis pada fitur yang relevan untuk CBF, informasi spesifik destinasi diekstrak.

* **Proses yang Dilakukan:**
    1.  Kolom-kolom `Place_Id`, `Place_Name`, dan `Category` dari dataframe `preparation_CBF` diekstrak menjadi list terpisah.
        ```python
        # tourism_id = preparation_CBF['Place_Id'].tolist()
        # tourism_name = preparation_CBF['Place_Name'].tolist()
        # tourism_category = preparation_CBF['Category'].tolist()
        ```
        Verifikasi panjang list menunjukkan 437 entri untuk masing-masing, mengonfirmasi konsistensi data unik destinasi.
    2.  Sebuah dataframe baru bernama `tourism_data` dibuat dengan tiga kolom: `id` (dari `tourism_id`), `destination` (dari `tourism_name`), dan `category` (dari `tourism_category`).
        ```python
        # tourism_data = pd.DataFrame({
        #     'id': tourism_id,
        #     'destination': tourism_name,
        #     'category': tourism_category
        # })
        ```
    Dataframe `tourism_data` ini berisi 437 baris dan 3 kolom, yang secara khusus menyajikan metadata destinasi yang akan digunakan untuk perhitungan kesamaan.

### 3. Vektorisasi Fitur Kategori dengan TF-IDF
Inti dari CBF adalah representasi fitur item dalam format numerik yang dapat diolah. Dalam kasus ini, fitur `category` akan diubah menjadi vektor numerik menggunakan TF-IDF.

* **Proses yang Dilakukan:**
    1.  Identifikasi kategori unik pada `tourism_data['category']` menunjukkan enam kategori: 'Budaya', 'Bahari', 'Taman_Hiburan', 'Cagar_Alam', 'Pusat_Perbelanjaan', dan 'Tempat_Ibadah'.
    2.  Sebuah objek `TfidfVectorizer` diinisialisasi.
    3.  Kolom `category` dari `tourism_data` ditransformasikan menjadi matriks TF-IDF menggunakan metode `fit_transform()`. Matriks ini (`tfidf_matrix`) akan memberikan bobot numerik pada setiap kategori untuk setiap destinasi.
        ```python
        # tfidf = TfidfVectorizer()
        # tfidf_matrix = tfidf.fit_transform(tourism_data['category'])
        ```
    4.  Fitur (nama kategori) yang dihasilkan oleh TF-IDFVectorizer telah dinormalisasi menjadi *lowercase*, contohnya: `['bahari', 'budaya', 'cagar_alam', ..., 'tempat_ibadah']`.
    5.  Dimensi dari `tfidf_matrix` adalah (437, 6), yang berarti terdapat 437 destinasi dan 6 fitur kategori unik.
    6.  Representasi padat (`.todense()`) dari matriks ini menunjukkan bahwa setiap destinasi hanya memiliki bobot pada satu kategori (nilai 1 untuk kategori yang bersangkutan dan 0 untuk lainnya), karena setiap destinasi dalam dataset ini diklasifikasikan secara eksklusif ke dalam satu kategori.

* **Alasan Dilakukan:**
    TF-IDF mengubah data teks kategori menjadi representasi vektor numerik. Meskipun dalam kasus ini setiap destinasi hanya memiliki satu kategori (sehingga TF-IDF berperilaku mirip *one-hot encoding*), penggunaan TF-IDF adalah pendekatan standar yang fleksibel jika di masa depan fitur teks yang lebih kompleks (seperti deskripsi) ingin disertakan. Matriks numerik ini memungkinkan perhitungan matematis untuk kesamaan antar destinasi.

### 3. Ringkasan Hyperparameter TF-IDF Vectorizer (`TfidfVectorizer`)

Walaupun **tidak menyetel secara eksplisit**, dalam penggunaan **TF-IDF**, memang ada beberapa **hyperparameter**, meskipun banyak yang secara implisit menggunakan nilai default yang tetap memengaruhi performa sistem rekomendasi berbasis konten. Berikut hyperparameter defaultnya:

| Hyperparameter | Nilai (default jika tidak disebut) | Penjelasan                                                  |
| -------------- | ---------------------------------- | ----------------------------------------------------------- |
| `analyzer`     | `'word'` (default)                 | Unit analisis (kata)                                        |
| `lowercase`    | `True` (default)                   | Mengubah semua teks menjadi huruf kecil                     |
| `stop_words`   | `None` (default)                   | Tidak menghapus stopwords (bisa diatur ke `'english'`)      |
| `ngram_range`  | `(1,1)` (default)                  | Menggunakan unigram (1 kata)                                |
| `max_df`       | `1.0` (default)                    | Mengabaikan kata yang muncul di lebih dari 100% dokumen     |
| `min_df`       | `1` (default)                      | Mengabaikan kata yang muncul di kurang dari 1 dokumen       |
| `max_features` | `None` (default)                   | Tidak ada batas jumlah fitur                                |
| `norm`         | `'l2'` (default)                   | Normalisasi L2 pada setiap vektor TF-IDF                    |
| `use_idf`      | `True` (default)                   | Mengaktifkan pembobotan inverse document frequency          |
| `smooth_idf`   | `True` (default)                   | Menambahkan 1 ke dokument frequency untuk menghindari div/0 |
| `sublinear_tf` | `False` (default)                  | Tidak menggunakan sublinear scaling pada tf                 |

## 6. Persiapan Data untuk Model Collaborative Filtering
### 1. Persiapan data
Tahap awal dalam pengembangan model CF adalah mempersiapkan data interaksi pengguna-destinasi dan melakukan encoding pada ID pengguna serta ID destinasi.

* **Proses yang Dilakukan:**
    1.  Salinan dari dataset `preparation` (yang merupakan hasil dari tahap Data Preparation sebelumnya dan berisi 9.921 entri rating unik) dibuat dan disimpan dalam variabel `df`.
        ```python
        # df = preparation.copy()
        ```
    2.  ID pengguna (`User_Id`) dan ID tempat wisata (`Place_Id`) yang asli di-encode menjadi indeks numerik yang berurutan mulai dari 0. Proses ini melibatkan pembuatan *mapping dictionary*:
        * `user_to_user_encoded` (ID asli ke ID ter-encode) dan `user_encoded_to_user` (ID ter-encode ke ID asli).
        * `place_to_place_encoded` (ID asli ke ID ter-encode) dan `place_encoded_to_place` (ID ter-encode ke ID asli).
    3.  Hasil encoding ini ditambahkan sebagai kolom baru (`user_encoded` dan `place_encoded`) ke dalam dataframe `df`.
        ```python
        # user_ids = df['User_Id'].unique().tolist()
        # user_to_user_encoded = {x: i for i, x in enumerate(user_ids)}
        # # ... (dan seterusnya untuk user_encoded_to_user, place_ids, place_to_place_encoded, place_encoded_to_place) ...
        # df['user_encoded'] = df['User_Id'].map(user_to_user_encoded)
        # df['place_encoded'] = df['Place_Id'].map(place_to_place_encoded)
        ```
    4.  Dilakukan perhitungan jumlah pengguna unik (300) dan destinasi unik (437), serta identifikasi nilai rating minimum (1) dan maksimum (5) dari dataset.

* **Alasan Dilakukan:**
    * Model *neural network*, khususnya *embedding layers* di TensorFlow/Keras, memerlukan input berupa indeks integer yang dimulai dari 0. Encoding memastikan ID pengguna dan destinasi sesuai dengan format ini.
    * *Mapping dictionary* diperlukan untuk mengkonversi ID asli ke format yang dibutuhkan model dan sebaliknya, untuk menginterpretasikan hasil prediksi.
    * Mengetahui jumlah unik pengguna dan destinasi penting untuk menentukan ukuran *embedding layers*.
    * Informasi skala rating (min/max) digunakan untuk normalisasi nilai target (rating).

### 2. Pembagian Data Latih dan Validasi (Train-Validation Split)
Dataset kemudian diacak dan dibagi menjadi data latih (*training set*) dan data validasi (*validation set*).

* **Proses yang Dilakukan:**
    1.  Seluruh dataset `df` diacak secara acak (menggunakan `df.sample(frac=1, random_state=42)`) untuk memastikan tidak ada bias urutan.
    2.  Variabel input `x` dibentuk dari pasangan kolom `user_encoded` dan `place_encoded`.
    3.  Variabel target `y` (rating) dinormalisasi ke rentang [0, 1] menggunakan Min-Max Scaling: $y = (Place Ratings - min rating) / (max rating - min rating)$.
        ```python
        # x = df[['user_encoded', 'place_encoded']].values
        # y = df['Place_Ratings'].apply(lambda x: (x - min_rating) / (max_rating - min_rating)).values
        ```
    4.  Data dibagi menjadi 80% untuk data latih dan 20% untuk data validasi. Ini menghasilkan 7.936 sampel data latih dan 1.985 sampel data validasi.
        ```python
        # train_indices = int(0.8 * df.shape[0])
        # x_train, x_val, y_train, y_val = (
        #     x[:train_indices], x[train_indices:],
        #     y[:train_indices], y[train_indices:]
        # )
        ```

* **Alasan Dilakukan:**
    * Pengacakan data penting untuk memastikan bahwa data latih dan validasi merepresentasikan distribusi data keseluruhan secara merata.
    * Normalisasi nilai target (rating) ke rentang [0, 1] membantu stabilisasi proses pelatihan model *neural network* dan cocok dengan penggunaan fungsi aktivasi sigmoid pada layer output model.
    * Pembagian data menjadi set latih dan validasi adalah praktik standar untuk mengevaluasi seberapa baik model dapat melakukan generalisasi terhadap data baru yang belum pernah dilihat sebelumnya, serta untuk mendeteksi dan mencegah *overfitting*.

# 🧮 Modeling

Tahap pemodelan adalah inti dari proses CRISP-DM di mana teknik-teknik *machine learning* diterapkan untuk mencapai tujuan proyek. Dalam proyek sistem rekomendasi destinasi wisata Indonesia ini, akan dikembangkan dan disajikan dua solusi rekomendasi utama yang menggunakan algoritma berbeda untuk memberikan saran destinasi kepada pengguna. Tujuannya adalah untuk dapat memberikan rekomendasi *Top-N* (sejumlah N destinasi teratas) yang relevan.

Dua pendekatan utama yang akan diimplementasikan adalah:
1.  **Content-Based Filtering (Penyaringan Berbasis Konten):** Memanfaatkan atribut atau fitur dari destinasi wisata (dalam kasus ini, kategori destinasi) untuk merekomendasikan item yang serupa.
2.  **Collaborative Filtering (Penyaringan Kolaboratif):** Menggunakan interaksi historis pengguna dengan destinasi (seperti rating) dan menerapkan model *deep learning* berbasis *embedding* untuk menemukan pola kesukaan dan merekomendasikan destinasi berdasarkan preferensi pengguna lain yang serupa.

Berikut ini adalah penjelasan detail untuk masing-masing pendekatan:

## Solusi 1: Content-Based Filtering (CBF)
Pendekatan *Content-Based Filtering* (CBF) merekomendasikan item berdasarkan kemiripan antara fitur item yang telah disukai pengguna di masa lalu dengan fitur item lain yang tersedia. Dalam konteks proyek ini, CBF akan diimplementasikan dengan memanfaatkan **kategori destinasi wisata** sebagai fitur utama. Prosesnya melibatkan  perhitungan *Cosine Similarity* untuk mengidentifikasi kemiripan antar destinasi.

### 1. Perhitungan Kemiripan Antar Destinasi dengan Cosine Similarity
Setelah destinasi direpresentasikan sebagai vektor TF-IDF pada tahap data preparation, langkah pemodelan pertama adalah menghitung kemiripan antar semua pasangan destinasi.

* **Proses yang Dilakukan:**
    1.  Fungsi `cosine_similarity` dari `sklearn.metrics.pairwise` diterapkan pada `tfidf_matrix` yang berasal dari tahap data preparation.
        ```python
        # from sklearn.metrics.pairwise import cosine_similarity
        # cosine_sim = cosine_similarity(tfidf_matrix)
        ```
    2.  Hasilnya adalah matriks kemiripan (`cosine_sim`) berukuran 437x437. Setiap elemen (i, j) dalam matriks ini merepresentasikan skor kemiripan antara destinasi ke-i dan destinasi ke-j. Nilai diagonal adalah 1 (kemiripan destinasi dengan dirinya sendiri). Dalam kasus ini, karena setiap destinasi hanya memiliki satu kategori, skor kemiripan antar dua destinasi berbeda akan menjadi 1 jika mereka memiliki kategori yang sama, dan 0 jika berbeda.
    3.  Matriks kemiripan ini kemudian diubah menjadi DataFrame (`cosine_sim_df`) dengan nama destinasi sebagai indeks dan kolom untuk memudahkan interpretasi dan penggunaan.
        ```python
        # cosine_sim_df = pd.DataFrame(cosine_sim, index=tourism_data['destination'], columns=tourism_data['destination'])
        ```

* **Alasan Dilakukan:**
    *Cosine Similarity* adalah metrik yang umum digunakan untuk mengukur kesamaan antara dua vektor dalam ruang multidimensi. Metrik ini efektif untuk data tekstual yang telah divektorisasi. Matriks `cosine_sim_df` menjadi dasar bagi model CBF untuk menemukan destinasi yang paling mirip dengan destinasi input.

### 2. Implementasi Fungsi Rekomendasi Destinasi Wisata
Untuk menghasilkan rekomendasi, sebuah fungsi khusus dibuat.

* **Proses yang Dilakukan:**
    Sebuah fungsi bernama `destination_recommendations` didefinisikan. Fungsi ini menerima nama destinasi sebagai input, matriks kemiripan (`cosine_sim_df`), data item (`tourism_data`), dan jumlah rekomendasi yang diinginkan (`k`, default 5).
    Fungsi ini:
    1.  Mengambil baris/kolom yang sesuai dengan destinasi input dari matriks kemiripan.
    2.  Mengidentifikasi `k` destinasi lain dengan skor kemiripan tertinggi.
    3.  Menghilangkan destinasi input dari daftar rekomendasi (jika muncul).
    4.  Menggabungkan hasil dengan informasi kategori destinasi dan mengembalikan `k` destinasi teratas.
    ```python
    # def destination_recommendations(destination, similarity_data=cosine_sim_df, items=tourism_data[['destination', 'category']], k=5):
    #     # Ambil indeks destinasi yang paling mirip
    #     index = similarity_data.loc[:,destination].to_numpy().argpartition(range(-1, -k, -1))
    #     closest = similarity_data.columns[index[-1:-(k+2):-1]] # Ambil top-k
    #     closest = closest.drop(destination, errors='ignore') # Hapus destinasi input jika ada
    #     return pd.DataFrame(closest).merge(items).head(k) 
    ```

* **Contoh Output Rekomendasi (Top-5):**
    Ketika fungsi diuji dengan input nama destinasi dengan ID 400 (Hutan Bambu Keputih, kategori: Cagar_Alam), sistem memberikan output sebagai berikut:
    ```
   ✨ Rekomendasi Destinasi Serupa untuk: Hutan Bambu Keputih (Kategori: Cagar_Alam)
   ============================================================
   No.  Destination                              | Category            
   ------------------------------------------------------------
   1    Gunung Papandayan                        | Cagar_Alam          
   2    Gua Maria Kerep Ambarawa                 | Cagar_Alam          
   3    Bukit Paralayang, Watugupit              | Cagar_Alam          
   4    Ekowisata Mangrove Wonorejo              | Cagar_Alam          
   5    Cibubur Garden Diary (Cibugary)          | Cagar_Alam          
   ------------------------------------------------------------
    ```
    Ketika diuji dengan memasukkan ID Destinasi 400, sistem berhasil mengidentifikasi bahwa destinasi tersebut adalah Hutan Bambu Keputih yang termasuk dalam kategori Cagar_Alam. Berdasarkan informasi ini, sistem kemudian memberikan rekomendasi lima destinasi lain yang memiliki kategori serupa, yaitu Cagar_Alam. Rekomendasi yang dihasilkan mencerminkan kemampuan model untuk menghubungkan destinasi baru dengan destinasi lain yang serupa dari segi kategori, sehingga membantu pengguna menemukan tempat wisata dengan karakteristik dan tema yang konsisten sesuai preferensi awal mereka. Hal ini menunjukkan efektivitas model content-based filtering dalam menyediakan rekomendasi yang relevan dan sesuai konteks kategori destinasi yang diminati.

### 6. Ringkasan Hyperparameter Model Content Based Filtering Perhitungan Cosine Similarity (`cosine_similarity`)

Walaupun **tidak menyetel secara eksplisit**, dalam tahap **Content-Based Filtering** menggunakan **Cosine Similarity**, ada **hyperparameter** yang menggunakan nilai default yang tetap memengaruhi performa sistem rekomendasi berbasis konten. Berikut hyperparameter defaultnya:

| Hyperparameter | Nilai (default)  | Penjelasan                                            |
| -------------- | ---------------- | ----------------------------------------------------- |
| `dense_output` | `True` (default) | Output sebagai array numpy biasa, bukan sparse matrix |

### 7. Kelebihan dan Kekurangan Content-Based Filtering
Pendekatan CBF memiliki karakteristiknya sendiri:

* **Kelebihan:**
    * **Tidak Memerlukan Data Pengguna Lain:** Rekomendasi dapat dibuat berdasarkan profil item dan preferensi satu pengguna, tanpa bergantung pada perilaku pengguna lain.
    * **Transparansi:** Rekomendasi yang dihasilkan bersifat *explainable* atau dapat dijelaskan (misalnya, "direkomendasikan karena memiliki kategori yang sama").
    * **Penanganan Item Baru (*Item Cold Start*):** Selama fitur item baru tersedia (dalam hal ini, kategorinya diketahui), sistem dapat langsung merekomendasikannya atau merekomendasikan item lain yang mirip dengannya.
    * **Menangkap Minat Spesifik:** Mampu merekomendasikan item yang sangat spesifik atau *niche* jika pengguna menunjukkan preferensi terhadap fitur-fitur tersebut.

* **Kekurangan:**
    * **Ketergantungan pada Kualitas Fitur:** Kualitas rekomendasi sangat bergantung pada kelengkapan dan kualitas fitur item yang diekstrak. Jika fitur (kategori) terlalu umum atau tidak cukup deskriptif, rekomendasi mungkin kurang relevan. Dalam kasus ini, penggunaan hanya satu kategori per destinasi membatasi kedalaman pemahaman konten.
    * **Terbatasnya Serendipitas (*Limited Serendipity*):** Cenderung merekomendasikan item yang sangat mirip dengan apa yang sudah diketahui atau disukai pengguna. Ini mengurangi peluang pengguna untuk menemukan item yang menarik dari kategori atau jenis yang benar-benar baru bagi mereka.
    * ***Filter Bubble* atau *Overspecialization*:** Pengguna mungkin terjebak dalam rekomendasi yang monoton dan hanya berasal dari satu jenis kategori yang sama berulang kali.
    * **Masalah *User Cold Start*:** Meskipun dapat menangani item baru, CBF tetap memerlukan informasi awal mengenai preferensi pengguna (misalnya, satu destinasi yang disukai) untuk dapat mulai memberikan rekomendasi.

## Solusi 2: Collaborative Filtering (CF) dengan Embedding Deep Learning
Pendekatan *Collaborative Filtering* (CF) bekerja berdasarkan ide bahwa pengguna yang memiliki preferensi serupa di masa lalu cenderung akan menyukai item yang sama di masa depan. Berbeda dengan CBF yang fokus pada fitur item, CF fokus pada pola interaksi pengguna-item (misalnya, rating yang diberikan). Dalam proyek ini, CF diimplementasikan menggunakan model *deep learning* yang memanfaatkan teknik *embedding* untuk mempelajari representasi laten (tersembunyi) dari pengguna dan destinasi.



### 3. Membangun Model Deep Learning untuk Collaborative Filtering
Sebuah model *neural network* kustom dirancang menggunakan Keras API untuk melakukan *collaborative filtering* berbasis *embedding*.

* **Arsitektur Model (`RecommenderNet`):**
    Sebuah kelas `RecommenderNet` yang merupakan turunan dari `tf.keras.Model` didefinisikan dengan komponen utama sebagai berikut:
    1.  **Embedding Layers:**
        * `user_embedding`: Memetakan setiap ID pengguna ter-encode ke sebuah vektor *embedding* berdimensi rendah (dipilih 8 dimensi).
        * `destination_embedding`: Memetakan setiap ID destinasi ter-encode ke sebuah vektor *embedding* berdimensi rendah (8 dimensi).
        Kedua *embedding layers* ini menggunakan inisialisasi bobot 'he_normal' dan regularisasi L2 (dengan faktor 1e-4) untuk mencegah *overfitting*.
    2.  **Bias Layers:**
        * `user_bias`: Sebuah *embedding layer* yang mempelajari bias spesifik untuk setiap pengguna.
        * `destination_bias`: Sebuah *embedding layer* yang mempelajari bias spesifik untuk setiap destinasi.
    3.  **Metode `call` (Forward Pass):**
        * Menerima input berupa ID pengguna dan ID destinasi yang sudah di-encode.
        * Mengambil vektor *embedding* dan bias untuk pengguna dan destinasi.
        * Melakukan operasi *dot product* antara vektor *embedding* pengguna dan destinasi untuk menangkap interaksi atau kesesuaian preferensi.
        * Menambahkan bias pengguna dan bias destinasi ke hasil *dot product*.
        * Hasil akhir dilewatkan melalui fungsi aktivasi sigmoid untuk menghasilkan prediksi rating dalam rentang [0, 1].

* **Alasan Arsitektur Ini:**
    Arsitektur ini pada dasarnya mengimplementasikan teknik faktorisasi matriks (*Matrix Factorization*) dalam kerangka *neural network*. *Embedding layers* bertugas mempelajari fitur-fitur laten (tersembunyi) dari pengguna dan destinasi yang dapat menjelaskan pola rating yang diamati. Penambahan bias membantu model menangkap popularitas item atau kecenderungan pengguna dalam memberi rating yang tidak dapat dijelaskan oleh interaksi fitur laten saja. Sigmoid pada output memastikan prediksi sesuai dengan skala rating yang telah dinormalisasi.

### 4. Kompilasi dan Pelatihan Model
Model yang telah dirancang kemudian dikompilasi dan dilatih.

* **Proses Kompilasi dan Pelatihan:**
    1.  Model `RecommenderNet` diinisialisasi dengan jumlah pengguna unik, jumlah destinasi unik, dan ukuran *embedding* (8).
    2.  *Callbacks* disiapkan:
        * `EarlyStopping`: Menghentikan pelatihan jika `val_loss` tidak membaik selama 10 epoch, dan mengembalikan bobot terbaik.
        * `ReduceLROnPlateau`: Mengurangi *learning rate* jika `val_loss` stagnan selama 5 epoch.
    3.  Model dikompilasi menggunakan:
        * *Loss Function*: `MeanSquaredError()` (digunakan untuk mengukur error antara rating prediksi dan rating aktual yang telah dinormalisasi).
        * *Optimizer*: `Adam` dengan *learning rate* awal 0.001.
        * *Metrics*: `RootMeanSquaredError()` (RMSE) untuk memantau performa.
        ```python
        # model = RecommenderNet(num_users, num_destination, 8)
        # model.compile(
        #     loss = tf.keras.losses.MeanSquaredError(),
        #     optimizer = tf.keras.optimizers.Adam(learning_rate=0.001),
        #     metrics = [tf.keras.metrics.RootMeanSquaredError()]
        # )
        ```
    4.  Model dilatih (`model.fit`) menggunakan data latih (`x_train`, `y_train`), dengan data validasi (`x_val`, `y_val`) digunakan untuk evaluasi setiap epoch. Parameter pelatihan: `batch_size = 125`, `epochs = 100` (maksimum).
        ```python
        # history = model.fit(
        #     x = x_train, y = y_train,
        #     batch_size = 125, epochs = 100,
        #     validation_data = (x_val, y_val),
        #     callbacks=[early_stopping, reduce_lr]
        # )
        ```
    * **Observasi Pelatihan:**
        Pelatihan menunjukkan penurunan *loss* yang baik pada epoch-epoch awal. *Callback* `ReduceLROnPlateau` terpicu beberapa kali, mengurangi *learning rate* untuk membantu model menemukan konvergensi yang lebih baik. Akhirnya, `EarlyStopping` menghentikan pelatihan pada epoch ke-25 (berdasarkan deskripsi naratif, epoch terbaik adalah ke-15 dimana bobot dikembalikan), mencegah *overfitting* lebih lanjut. Pada epoch terbaik (epoch 15), model mencapai `training loss` sekitar 0.1144 dan `validation loss` sekitar 0.1247, dengan RMSE sekitar 0.35 pada skala rating yang dinormalisasi.

* **Alasan Dilakukan:**
    Proses kompilasi mendefinisikan bagaimana model akan belajar (optimizer, loss) dan bagaimana performanya akan diukur (metrics). Pelatihan iteratif memungkinkan model untuk menyesuaikan bobot *embedding* dan biasnya agar dapat memprediksi rating seakurat mungkin berdasarkan data historis. Penggunaan *callbacks* membantu mengoptimalkan proses pelatihan dan meningkatkan kemampuan generalisasi model.

### 5. Inferensi dan Contoh Penggunaan untuk Top-N Rekomendasi
Setelah model dilatih, model tersebut dapat digunakan untuk memberikan rekomendasi destinasi yang dipersonalisasi.

* **Proses Inferensi:**
    1.  Satu ID pengguna (`user_id`) dipilih sebagai contoh (misalnya, User ID 1).
    2.  Daftar destinasi yang sudah pernah dikunjungi/dirating oleh pengguna tersebut diidentifikasi.
    3.  Daftar destinasi yang *belum* pernah dikunjungi oleh pengguna tersebut dibuat.
    4.  ID pengguna (yang sudah di-encode) dipasangkan dengan setiap ID destinasi yang belum dikunjungi (yang juga sudah di-encode) untuk membentuk input bagi model.
    5.  Model (`model.predict`) digunakan untuk memprediksi skor rating untuk semua pasangan user-destinasi yang belum dikunjungi tersebut.
    6.  Prediksi rating diurutkan dari yang tertinggi, dan 10 destinasi teratas diambil sebagai rekomendasi.
    7.  ID destinasi yang direkomendasikan di-decode kembali ke nama destinasi asli dan kategorinya.
    8.  Sebagai konteks, 5 destinasi favorit pengguna (berdasarkan rating tertinggi yang pernah diberikan) juga ditampilkan, diikuti oleh 10 rekomendasi destinasi baru.

* **Contoh Output Rekomendasi (Top-10 untuk User ID: 1):**
    ```
      🎯 Showing Recommendations for User ID: 1
      ============================================================
      
      📌 Top 5 Destinations Visited by User (Based on Rating):
      ------------------------------------------------------------
      No.  Destination                         | Category            
      ------------------------------------------------------------
      1    Atlantis Water Adventure            | Taman_Hiburan       
      2    Museum Gedung Sate                  | Budaya              
      3    Taman Harmoni Keputih               | Cagar_Alam          
      4    Taman Sungai Mudal                  | Cagar_Alam          
      5    Surabaya North Quay                 | Taman_Hiburan       
      
      ✨ Top 10 Destination Recommendations for User:
      ------------------------------------------------------------
      No.  Destination                         | Category            
      ------------------------------------------------------------
      1    Bukit Jamur                         | Cagar_Alam          
      2    Glamping Lakeside Rancabali         | Taman_Hiburan       
      3    Monumen Yogya Kembali               | Budaya              
      4    Jogja Bay Pirates Adventure Waterpark | Taman_Hiburan       
      5    Selasar Sunaryo Art Space           | Taman_Hiburan       
      6    Keraton Surabaya                    | Budaya              
      7    Stone Garden Citatah                | Taman_Hiburan       
      8    Kota Mini                           | Taman_Hiburan       
      9    Taman Hiburan Rakyat                | Taman_Hibur
    ```
    Output rekomendasi ini menunjukkan bagaimana model collaborative filtering dapat memahami preferensi pengguna berdasarkan histori interaksi dan memberikan rekomendasi destinasi wisata yang relevan dan beragam. Dari daftar 5 destinasi yang sudah dikunjungi dan dinilai tinggi oleh pengguna dengan ID 1, terlihat bahwa pengguna menyukai berbagai kategori seperti Taman Hiburan, Budaya, dan Cagar Alam. Model kemudian merekomendasikan 10 destinasi baru yang belum dikunjungi, namun sesuai dengan pola preferensi tersebut, mencakup destinasi dari kategori yang sama seperti Cagar Alam, Taman Hiburan, dan Budaya, serta menambahkan kategori Bahari yang mungkin juga relevan. Rekomendasi ini menunjukkan kemampuan model dalam menangkap kesukaan pengguna terhadap beragam tipe destinasi dan memberikan opsi yang berpotensi menarik bagi pengguna, sehingga meningkatkan peluang kepuasan dan keterlibatan lebih lanjut. Secara keseluruhan, output ini memperlihatkan efektivitas model deep learning dalam mempersonalisasi rekomendasi berbasis data interaksi historis, menghasilkan daftar destinasi yang variatif namun tetap relevan dengan preferensi unik setiap pengguna.

### 6. Ringkasan Hyperparameter Model Collaborative Filtering

#### 1. **Embedding-related Hyperparameters**

| Hyperparameter           | Nilai                         | Penjelasan                                       |
| ------------------------ | ----------------------------- | ------------------------------------------------ |
| `embedding_size`         | `8` (saat inisialisasi)       | Ukuran vektor embedding untuk user dan destinasi |
| `embeddings_initializer` | `'he_normal'`                 | Metode inisialisasi bobot embedding              |
| `embeddings_regularizer` | `keras.regularizers.l2(1e-4)` | Regularisasi L2 untuk mencegah overfitting       |

#### 2. **Model Training Hyperparameters**

| Hyperparameter  | Nilai                       | Penjelasan                              |
| --------------- | --------------------------- | --------------------------------------- |
| `loss`          | `MeanSquaredError()`        | Fungsi loss untuk regresi rating        |
| `optimizer`     | `Adam(learning_rate=0.001)` | Optimizer yang digunakan                |
| `learning_rate` | `0.001`                     | Learning rate awal untuk Adam optimizer |
| `metrics`       | `RootMeanSquaredError()`    | Metrik evaluasi performa model          |

**Callback Hyperparameters**

#### 3. **EarlyStopping**

| Hyperparameter         | Nilai        | Penjelasan                                  |
| ---------------------- | ------------ | ------------------------------------------- |
| `monitor`              | `'val_loss'` | Metrik yang dipantau                        |
| `patience`             | `10`         | Berhenti jika tidak membaik selama 10 epoch |
| `verbose`              | `1`          | Menampilkan info saat early stop terjadi    |
| `restore_best_weights` | `True`       | Mengembalikan bobot terbaik saat pelatihan  |

#### 4. **ReduceLROnPlateau**

| Hyperparameter | Nilai        | Penjelasan                             |
| -------------- | ------------ | -------------------------------------- |
| `monitor`      | `'val_loss'` | Metrik yang dipantau                   |
| `factor`       | `0.1`        | Pengurangan learning rate saat stagnan |
| `patience`     | `5`          | Tunggu 5 epoch sebelum menurunkan LR   |
| `verbose`      | `1`          | Menampilkan info saat LR diturunkan    |
| `min_lr`       | `0.00001`    | Batas bawah learning rate              |

### 7. Kelebihan dan Kekurangan Collaborative Filtering (dengan Deep Learning)

* **Kelebihan:**
    * **Tidak Memerlukan Fitur Item Manual:** Model belajar langsung dari interaksi pengguna-item (rating), sehingga tidak memerlukan *feature engineering* yang ekstensif pada konten item.
    * **Kemampuan Menemukan Hubungan Kompleks dan Serendipitas:** Model *deep learning* dapat menangkap pola dan hubungan non-linear yang kompleks dalam data. Hal ini memungkinkan penemuan rekomendasi yang bersifat *serendipitous* (mengejutkan namun relevan) yang mungkin tidak ditemukan oleh CBF.
    * **Personalisasi yang Lebih Mendalam:** Dengan mempelajari *embedding* pengguna dan item, model dapat menghasilkan rekomendasi yang lebih personal dan akurat terhadap selera unik pengguna.
    * **Scalability (dengan arsitektur yang tepat):** Model *neural network* dapat diskalakan untuk menangani dataset yang besar.

* **Kekurangan:**
    * **Masalah *Cold Start*:** Sangat bergantung pada data interaksi historis. Sulit memberikan rekomendasi untuk pengguna baru (*user cold start*) atau item baru (*item cold start*) yang belum memiliki interaksi. Model tidak dapat membuat *embedding* untuk entitas baru tanpa interaksi.
    * **Ketergantungan pada Kuantitas dan Kualitas Data Interaksi:** Membutuhkan volume data interaksi yang cukup besar dan berkualitas baik untuk melatih model secara efektif. Performa dapat menurun drastis pada dataset yang sangat *sparse*.
    * ***Popularity Bias*:** Model mungkin cenderung merekomendasikan item-item populer yang memiliki banyak interaksi, sehingga item yang kurang populer (namun mungkin relevan) menjadi kurang terwakili.
    * **Kurang Transparan (*Less Explainable*):** Dibandingkan CBF, rekomendasi dari model *deep learning* berbasis *embedding* seringkali lebih sulit untuk dijelaskan ("black box"), karena didasarkan pada fitur-fitur laten yang dipelajari secara otomatis.

# 💯 Evaluation
Tahap evaluasi model bertujuan untuk menilai sejauh mana model-model sistem rekomendasi yang telah dikembangkan mampu mencapai tujuan yang ditetapkan dan menyelesaikan permasalahan yang ada. Pada tahap ini, kita akan mengukur kinerja kedua pendekatan model—*Content-Based Filtering* dan *Collaborative Filtering*—menggunakan serangkaian metrik evaluasi yang relevan dengan tugas prediksi rating dan kualitas daftar rekomendasi Top-N.

## Metrik Evaluasi yang Digunakan

Berikut adalah metrik-metrik yang digunakan untuk mengevaluasi performa model dalam proyek ini:

| Metric            | Type                             | Penggunaan                                                                                                |
|-------------------|----------------------------------|-----------------------------------------------------------------------------------------------------------|
| MSE               | Loss Function / Regression       | Mengukur rata-rata kuadrat perbedaan antara nilai aktual dan prediksi; digunakan sebagai fungsi kerugian untuk memantau dan mengoptimalkan proses pelatihan model *neural network*. Formula: $$\frac{1}{N} \sum_{i=1}^{N} (y_i - \hat{y}_i)^2$$ |
| RMSE              | Regression                       | Mengukur akar dari MSE, sehingga memiliki skala yang sama dengan variabel target (rating). Memberikan gambaran rata-rata magnitudo error prediksi, dengan bobot lebih besar pada error yang lebih besar. Formula: $$\sqrt{\frac{1}{N} \sum_{i=1}^{N} (y_i - \hat{y}_i)^2}$$ |
| MAE               | Regression                       | Mengukur rata-rata selisih absolut antara nilai aktual dan prediksi. Memberikan gambaran langsung tentang besaran rata-rata error tanpa mempedulikan arahnya dan kurang sensitif terhadap *outlier* dibandingkan RMSE. Formula:  $$\frac{1}{N} \sum_{i=1}^{N} |y_i - \hat{y}_i|$$ |
| Confusion Matrix  | Classification                   | Digunakan untuk mengevaluasi model klasifikasi (dalam kasus CBF yang dievaluasi sebagai tugas klasifikasi kategori). Menyajikan tabel True Positives (TP), True Negatives (TN), False Positives (FP), dan False Negatives (FN) untuk setiap kelas. |
| Precision@K       | Ranking Metric                   | Dari K item teratas yang direkomendasikan, berapa proporsi yang benar-benar relevan bagi pengguna. Formula: $$\frac{\text{Jumlah item relevan dalam K rekomendasi}}{\text{K}}$$ |
| Recall@K          | Ranking Metric                   | Dari semua item yang relevan bagi pengguna, berapa proporsi yang berhasil ditemukan dan direkomendasikan dalam K item teratas. Formula: $$\frac{\text{Jumlah item relevan dalam K rekomendasi}}{\text{Total item relevan untuk pengguna}}$$ |
| F1-Score@K        | Ranking Metric                   | Rata-rata harmonik dari Precision@K dan Recall@K, memberikan ukuran tunggal yang menyeimbangkan kedua metrik tersebut. Formula: $$2 \cdot \frac{Precision@K \cdot Recall@K}{Precision@K + Recall@K}$$ |

Di mana $N$ adalah jumlah sampel, $y_i$ adalah nilai aktual, dan $\hat{y}_i$ adalah nilai prediksi. Untuk semua metrik error (MSE, RMSE, MAE), nilai yang lebih rendah menunjukkan performa yang lebih baik. Untuk metrik ranking (Precision@K, Recall@K, F1-Score@K), nilai yang lebih tinggi menunjukkan performa yang lebih baik.

## Evaluasi Model Content-Based Filtering (CBF)

Evaluasi untuk model *Content-Based Filtering* (CBF) dalam proyek ini difokuskan pada kemampuannya untuk mengenali dan mengklasifikasikan destinasi wisata berdasarkan kategorinya, dengan studi kasus pada kategori 'Budaya'.

* **Konteks dan Proses Evaluasi:**
    Label *ground truth* dibuat dengan memberikan nilai 1 untuk destinasi yang termasuk dalam kategori 'Budaya' dan 0 untuk kategori lainnya. Sistem CBF kemudian memprediksi kategori sebuah destinasi dengan cara mencari destinasi lain yang memiliki *cosine similarity* tertinggi dengannya (berdasarkan fitur kategori yang telah di-vektorisasi menggunakan TF-IDF). Kategori dari destinasi paling mirip tersebut kemudian diambil sebagai kategori prediksi untuk destinasi input. Proses ini pada dasarnya menguji apakah sebuah destinasi 'Budaya' akan paling mirip dengan destinasi 'Budaya' lainnya.

* **Metrik yang Digunakan:**
    Hasil prediksi dibandingkan dengan *ground truth* menggunakan metrik `precision`, `recall`, `f1-score`, dan `accuracy` yang dihitung melalui fungsi `classification_report` dari pustaka `scikit-learn`.
    * **Precision** (TP / (TP + FP)): Mengukur proporsi prediksi positif ('Budaya') yang benar-benar 'Budaya'.
    * **Recall** (TP / (TP + FN)): Mengukur proporsi kasus 'Budaya' aktual yang berhasil diidentifikasi oleh model.
    * **F1-Score**: Rata-rata harmonik dari precision dan recall.
    * **Accuracy** ((TP + TN) / Total): Mengukur proporsi total prediksi yang benar (baik 'Budaya' maupun 'Non-Budaya').

* **Hasil dan Interpretasi:**
    ```
    # Diasumsikan output dari classification_report adalah:
    #               precision    recall  f1-score   support
    #            0       1.00      1.00      1.00       320  (Non-Budaya)
    #            1       1.00      1.00      1.00       117  (Budaya)
    #     accuracy                           1.00       437
    #    macro avg       1.00      1.00      1.00       437
    # weighted avg       1.00      1.00      1.00       437
    ```
    Hasil evaluasi menunjukkan performa yang **sempurna** dengan nilai `precision`, `recall`, dan `f1-score` semua mencapai **1.00 (100%)** untuk kedua kelas (0 untuk 'Non-Budaya' dan 1 untuk 'Budaya'). `Accuracy` keseluruhan juga mencapai **1.00**.
    Ini berarti model CBF, dengan logika prediksi yang digunakan, mampu dengan sempurna mengidentifikasi destinasi kategori 'Budaya' maupun 'Non-Budaya' tanpa kesalahan dalam konteks dataset dan tugas evaluasi ini. `Support` menunjukkan jumlah sampel untuk masing-masing kelas (320 untuk 'Non-Budaya' dan 117 untuk 'Budaya') dari total 437 destinasi yang diuji.

    Perlu dicatat bahwa skor sempurna ini sangat dipengaruhi oleh sifat deterministik dari evaluasi: karena kemiripan antar destinasi dalam CBF ini hanya didasarkan pada satu kategori per destinasi (skor similarity 1 jika kategori sama, 0 jika berbeda), maka destinasi dengan kategori 'Budaya' akan selalu memiliki kemiripan tertinggi dengan destinasi 'Budaya' lainnya. Evaluasi ini lebih mengonfirmasi konsistensi logika pencocokan kategori daripada kemampuan prediktif pada konten yang lebih kompleks atau ambigu.

## Evaluasi Model Collaborative Filtering (CF)

Evaluasi model *Collaborative Filtering* (CF) berbasis *deep learning* dilakukan dalam beberapa aspek: pemantauan performa selama pelatihan, akurasi prediksi rating pada data validasi, dan kualitas daftar rekomendasi Top-N.

### 1. Evaluasi Performa Selama Pelatihan (RMSE Plot)
Metrik *Root Mean Squared Error* (RMSE) dipantau pada setiap epoch untuk data latih (`train`) dan data validasi (`test`/`validation`) guna memahami dinamika proses pembelajaran model.
$$RMSE = \sqrt{\frac{1}{N} \sum_{i=1}^{N} (y_i - \hat{y}_i)^2}$$

![Screen Shot 2025-06-01 at 17 30 38](https://github.com/user-attachments/assets/33652065-e818-468d-9748-a42b74c6092a)

* **Visualisasi dan Interpretasi Kurva RMSE:**
    (Mengacu pada grafik `plt.plot(history.history['root_mean_squared_error'])` dkk.)
    * **Kurva RMSE Pelatihan (misalnya, garis biru):** Menunjukkan penurunan nilai RMSE seiring bertambahnya epoch. Hal ini mengindikasikan bahwa model berhasil mempelajari pola dari data pelatihan, dan kesalahannya dalam memprediksi rating pada data yang sudah dilihatnya semakin mengecil.
    * **Kurva RMSE Validasi (misalnya, garis oranye):** Menggambarkan kemampuan generalisasi model pada data baru. Pada grafik yang dihasilkan (sebagaimana dideskripsikan dalam narasi pelatihan), RMSE validasi awalnya menurun, kemudian cenderung stagnan bahkan sedikit meningkat setelah beberapa epoch (misalnya, sekitar epoch 12), sementara RMSE pelatihan terus menurun. Kesenjangan (*gap*) yang melebar antara kurva pelatihan dan validasi, atau peningkatan pada RMSE validasi, adalah indikasi *overfitting*. Stagnasi RMSE validasi menunjukkan bahwa model telah mencapai batas kemampuannya untuk belajar lebih lanjut dari data dengan konfigurasi saat itu. Implementasi *callbacks* seperti `EarlyStopping` dan `ReduceLROnPlateau` (yang menghentikan pelatihan pada epoch ke-25 dan mengembalikan bobot dari epoch ke-15) sangat penting untuk mendapatkan model dengan generalisasi terbaik.

### 2. Perhitungan RMSE dan MAE pada Data Validasi
Setelah pelatihan selesai dan model dengan bobot terbaik (berdasarkan `val_loss` terendah) diperoleh, performa akhirnya dievaluasi pada data validasi menggunakan RMSE dan MAE pada rating yang telah dinormalisasi (skala 0-1).
1.  **Mean Absolute Error (MAE)**: Mengukur rata-rata selisih absolut antara rating aktual dan prediksi.
    $$MAE = \frac{1}{N} \sum_{i=1}^{N} |y_i - \hat{y}_i|$$
2.  **Root Mean Squared Error (RMSE)**: Telah dijelaskan sebelumnya.

* **Hasil dan Interpretasi:**
    Berdasarkan output yang diperoleh:
    * **RMSE: 0.3498**
    * **MAE: 0.3012**

    Nilai-nilai ini, yang diukur pada skala rating ternormalisasi [0, 1], memberikan ukuran kuantitatif dari error prediksi model. RMSE sebesar 0.3498 menunjukkan bahwa, secara rata-rata dengan penalti lebih pada error besar, prediksi rating model memiliki simpangan sekitar nilai tersebut dari rating aktual ternormalisasi. MAE sebesar 0.3012 mengindikasikan bahwa rata-rata selisih absolut prediksi dari nilai sebenarnya adalah sekitar 0.3012. Untuk mendapatkan interpretasi yang lebih intuitif pada skala rating asli (1-5), nilai-nilai ini perlu dikonversi kembali. Namun, untuk perbandingan dan evaluasi relatif, metrik pada skala ternormalisasi ini sudah cukup informatif. Semakin rendah kedua nilai ini, semakin akurat model dalam memprediksi rating.

### 3. Evaluasi Kualitas Rekomendasi Top-N (Precision@K, Recall@K, F1-Score@K)
Selain akurasi prediksi rating, evaluasi performa rekomendasi Top-N sangat penting untuk model *collaborative filtering*. Untuk evaluasi ini, digunakan K=10 (Top-10 rekomendasi). Item dianggap "relevan" jika rating aktualnya pada data validasi mencapai ambang batas tertentu (dalam proyek ini, rating asli $\geq 3$, yang setara dengan 0.5 pada skala ternormalisasi 0-1).

* **Precision@10**: Dari 10 destinasi yang direkomendasikan, berapa proporsi yang benar-benar relevan.
* **Recall@10**: Dari semua destinasi yang relevan untuk seorang pengguna, berapa proporsi yang berhasil muncul dalam 10 rekomendasi teratas.
* **F1-Score@10**: Rata-rata harmonik dari Precision@10 dan Recall@10.

* **Hasil dan Interpretasi:**
    Berdasarkan hasil perhitungan metrik evaluasi Top-10:
    * **Recall@10: 0.9673**
    * **Precision@10: 0.4044**
    * **F1-Score@10: 0.5703**

    Interpretasi hasil ini adalah sebagai berikut:
    * **Recall@10 yang sangat tinggi (0.9673)** menunjukkan bahwa model sangat efektif dalam menemukan dan menyajikan sebagian besar (sekitar 96.73%) destinasi yang kemungkinan besar akan disukai oleh pengguna (berdasarkan ambang batas relevansi). Ini berarti pengguna memiliki peluang kecil untuk melewatkan destinasi favorit potensial mereka dari daftar rekomendasi.
    * **Precision@10 sebesar 0.4044** mengindikasikan bahwa dari 10 destinasi teratas yang direkomendasikan, rata-rata sekitar 40.44% (atau sekitar 4 dari 10 destinasi) adalah destinasi yang benar-benar relevan. Meskipun nilai ini menunjukkan kemampuan model yang cukup baik dalam memprioritaskan item relevan, masih terdapat ruang untuk meningkatkan ketepatan sasaran rekomendasi.
    * **F1-Score@10 sebesar 0.5703** memberikan keseimbangan antara presisi dan recall. Dalam kasus ini, F1-Score cukup dipengaruhi oleh nilai Recall yang tinggi, menandakan bahwa model cenderung lebih inklusif (memastikan banyak item relevan masuk rekomendasi) dengan risiko beberapa item yang direkomendasikan mungkin kurang relevan.

Secara keseluruhan, model *collaborative filtering* menunjukkan performa yang menjanjikan, terutama dalam hal cakupan (Recall). Upaya di masa depan dapat difokuskan pada peningkatan presisi untuk lebih mempertajam relevansi item-item di posisi teratas rekomendasi.

# 📋 Kesimpulan

Proyek pengembangan sistem rekomendasi destinasi wisata Indonesia ini telah berhasil mengimplementasikan dan mengevaluasi dua pendekatan utama: *Content-Based Filtering* (CBF) dan *Collaborative Filtering* (CF) berbasis *deep learning*. Evaluasi menunjukkan bahwa kedua model memiliki karakteristik dan potensi yang berbeda dalam menyelesaikan permasalahan dan mencapai tujuan bisnis yang telah ditetapkan.

* **Model Content-Based Filtering (CBF):**
    * Model CBF menunjukkan **akurasi sempurna (1.00)** dalam tugas evaluasi spesifiknya, yaitu mengklasifikasikan destinasi berdasarkan kategori 'Budaya'. Hasil ini mengonfirmasi konsistensi logika internal model dalam mencocokkan item berdasarkan kesamaan fitur kategori tunggal.
    * **Kelebihan utama CBF** terletak pada transparansinya, kemampuannya menangani destinasi baru (*item cold start*) selama fitur kategorinya tersedia, dan kemampuannya melayani pengguna dengan preferensi kategori yang sangat spesifik.
    * Namun, **keterbatasannya** adalah ketergantungan pada kualitas fitur yang digunakan (dalam hal ini, kategori tunggal membatasi kedalaman), serta kurangnya kemampuan untuk menghasilkan rekomendasi yang mengejutkan (*serendipity*) dan potensi terjadinya *filter bubble*.

* **Model Collaborative Filtering (CF) dengan Deep Learning:**
    * Model CF menunjukkan **performa yang menjanjikan** dalam memprediksi preferensi pengguna, dengan **RMSE sebesar 0.3498** dan **MAE sebesar 0.3012** pada data validasi (skala rating ternormalisasi 0-1).
    * Dalam evaluasi kualitas rekomendasi Top-10, model CF mencapai **Recall@10 yang sangat tinggi (0.9673)**, yang berarti model sangat efektif dalam menemukan sebagian besar destinasi yang relevan bagi pengguna. **Precision@10 (0.4044)** menunjukkan bahwa sekitar 4 dari 10 rekomendasi teratas relevan, dengan **F1-Score@10 sebesar 0.5703** memberikan keseimbangan yang baik antara kedua metrik tersebut.
    * **Kelebihan utama CF** adalah kemampuannya untuk personalisasi yang mendalam berdasarkan perilaku kolektif pengguna, potensi untuk *serendipity*, dan tidak bergantung pada fitur item eksplisit.
    * **Kelemahan utamanya** adalah masalah *cold start* untuk pengguna dan item baru, serta sensitivitas terhadap kekarangan data (*data sparsity*).

**Perbandingan dan Kesesuaian Penggunaan:**

Tidak ada satu model yang superior secara absolut untuk semua skenario.
* **Model Collaborative Filtering (CF)** menunjukkan potensi yang lebih besar sebagai sistem rekomendasi utama. Tingginya nilai Recall@10 sangat relevan dengan tujuan bisnis untuk membantu wisatawan mengatasi *information overload* dan **menemukan beragam destinasi yang mungkin mereka sukai**, termasuk destinasi baru atau kurang populer. Kemampuan personalisasinya yang mendalam juga sejalan dengan tujuan untuk meningkatkan pengalaman pengguna.
* **Model Content-Based Filtering (CBF)** tetap berharga untuk kasus penggunaan spesifik, seperti **memberikan rekomendasi yang dapat dijelaskan**, menangani destinasi baru, atau melayani pengguna yang menginginkan eksplorasi mendalam dalam kategori tertentu. CBF juga dapat berfungsi sebagai sistem *fallback* yang baik.

Secara keseluruhan, kedua model berhasil dikembangkan dan dievaluasi, memberikan pemahaman yang berharga tentang kekuatan dan keterbatasan masing-masing. Model CF berbasis *deep learning* menunjukkan kinerja yang sangat baik dalam hal cakupan rekomendasi yang relevan, menjadikannya kandidat kuat untuk implementasi inti. Untuk pengembangan sistem yang lebih komprehensif dan robust di masa depan, pendekatan *hybrid* yang mengkombinasikan keunggulan dari kedua model ini sangat direkomendasikan guna memaksimalkan kepuasan pengguna dan mencapai tujuan bisnis secara lebih efektif.
