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
- **Mengembangkan Model Content-Based Filtering dengan TF-IDF dan Cosine Similarity:** Tujuan ini adalah untuk membangun sistem rekomendasi yang menyarankan destinasi wisata berdasarkan kemiripan konten atau atributnya. Secara teknis, ini melibatkan penggunaan metode TF-IDF (_Term Frequency-Inverse Document Frequency_) untuk mengubah deskripsi teks setiap destinasi menjadi representasi numerik (vektor) yang menyoroti kata-kata kunci penting. Selanjutnya, Cosine Similarity akan digunakan untuk menghitung seberapa mirip satu destinasi dengan destinasi lainnya berdasarkan vektor fitur tersebut. Hasilnya, sistem dapat merekomendasikan tempat-tempat yang karakteristiknya serupa dengan yang pernah disukai atau dicari pengguna.
- **Mengembangkan model Collaborative Filtering dengan deep learning:** Poin ini berfokus pada pembuatan model rekomendasi yang belajar dari pola perilaku kolektif semua pengguna. Artinya, sistem akan menganalisis interaksi pengguna dengan destinasi (seperti rating yang diberikan atau destinasi yang disukai) untuk menemukan pengguna lain dengan selera serupa. Dengan menggunakan teknik deep learning (jaringan syaraf tiruan yang canggih), model dapat menangkap pola preferensi yang kompleks dan tersembunyi. Dengan demikian, sistem dapat merekomendasikan destinasi yang disukai oleh pengguna-pengguna "kembarannya", bahkan jika pengguna tersebut belum pernah melihat destinasi itu sebelumnya.
- **Menyediakan rekomendasi akurat dan dipersonalisasi:** Tujuan ini menekankan pada kualitas output sistem. "Akurat" berarti rekomendasi yang diberikan harus sesuai dan relevan dengan apa yang kemungkinan besar akan disukai pengguna. "Dipersonalisasi" berarti saran yang ditampilkan harus unik untuk setiap individu, berdasarkan preferensi pribadi mereka (baik dari konten yang mereka sukai maupun dari perilaku mereka dibandingkan pengguna lain), bukan rekomendasi generik yang sama untuk semua orang.
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

**Metrik Evaluasi:**
| Metric | Type | Penggunaan |
|--------|------|------------|
| RMSE | Regression | Mengukur error prediksi rating |
| NDCG@k | Ranking | Kualitas peringkat rekomendasi |
| Binary Crossentropy | Loss Function | Memantau training model |

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
**Asal Data:** Proyek Capstone Bangkit Academy 2021 (Aplikasi GetLoc)  

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
| Time_Minutes | Float | Durasi kunjungan (menit) | 47% missing |
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
**Key Findings:**
- 300 unique users
- Complete data (no null values)
- Contains demographic information

**Sebaran Geografis Pengguna**

Untuk mengetahui sebaran geografis pengguna, dilakukan perhitungan frekuensi setiap lokasi unik dan persentasenya terhadap total pengguna. Berikut adalah lima lokasi dengan jumlah pengguna terbanyak:
| Location | Count | Percentage |
|----------|-------|------------|
| Bekasi, Jawa Barat | 39 | 13.0% |
| Semarang, Jawa Tengah | 22 | 7.3% |
| Lampung, Sumatera Selatan | 20 | 6.7% |
| Yogyakarta, DIY | 20 | 6.7% |

![image](https://github.com/user-attachments/assets/1481669c-47a1-499a-b9fc-4d588d112592)

**Insight:** Data menunjukkan bahwa pengguna berasal dari berbagai lokasi di Indonesia. Bekasi, Jawa Barat, menjadi lokasi dengan kontribusi pengguna terbanyak (13.0%), diikuti oleh Semarang, Lampung, dan Yogyakarta. Adanya konsentrasi pengguna di beberapa kota besar ini bisa jadi mencerminkan basis pengguna awal aplikasi atau area dengan penetrasi internet yang lebih tinggi. Pemahaman ini dapat berguna jika personalisasi berdasarkan lokasi dipertimbangkan di masa depan.

**Distribusi Usia**

Statistik deskriptif untuk variabel usia pengguna dihitung untuk memahami profil usia pengg

![image](https://github.com/user-attachments/assets/3b05b88f-f341-4fa0-917a-fda53aaefd75)

**Insight:** Rata-rata usia pengguna adalah sekitar 28.7 tahun, dengan median 29 tahun, menunjukkan distribusi yang relatif simetris. Rentang usia pengguna adalah dari 18 hingga 50 tahun, dengan standar deviasi 5.8 tahun, mengindikasikan variasi usia yang tidak terlalu lebar. Seperti yang dapat divisualisasikan pada histogram, mayoritas pengguna kemungkinan besar berada dalam rentang usia dewasa muda (20-an hingga awal 30-an). Informasi ini penting untuk memahami target audiens utama dari sistem rekomendasi.

### Tourism Data Analysis
**Kategori Destinasi**

Untuk mengetahui jenis destinasi wisata apa saja yang paling banyak terdapat dalam dataset, dilakukan perhitungan proporsi setiap kategori.

| Category | Percentage |
|----------|------------|
| Taman Hiburan | 30.9% |
| Budaya | 26.8% |
| Cagar Alam | 24.3% |

![Screen Shot 2025-06-01 at 08 32 38](https://github.com/user-attachments/assets/7f3fdcc3-e888-4379-8573-a1e288687934)

**Insight:** Tiga kategori destinasi wisata yang paling dominan dalam dataset adalah 'Taman Hiburan' (30.9%), 'Budaya' (26.8%), dan 'Cagar Alam' (24.3%). Hal ini menunjukkan bahwa sebagian besar destinasi yang tercakup dalam dataset berfokus pada ketiga jenis wisata tersebut. Keseimbangan atau ketidakseimbangan antar kategori ini dapat mempengaruhi variasi rekomendasi yang dihasilkan.

**Kota Destinasi**
| City | Percentage |
|------|------------|
| Yogyakarta | 28.8% |
| Bandung | 28.4% |
| Jakarta | 19.2% |

![Screen Shot 2025-06-01 at 08 21 55](https://github.com/user-attachments/assets/86fb8206-ebd3-4872-b242-ea4aeddc6ee3)

**Insight:** Grafik "Distribusi City" menunjukkan bahwa dataset destinasi wisata didominasi oleh Yogyakarta (28.8%) dan Bandung (28.4%), yang secara bersama-sama mencakup lebih dari separuh total destinasi. Jakarta menyusul dengan 19.2%, sementara Semarang (13.0%) dan Surabaya (10.5%) memiliki jumlah destinasi yang lebih sedikit. Distribusi yang tidak merata ini mengindikasikan bahwa sistem rekomendasi mungkin memiliki lebih banyak variasi pilihan untuk Yogyakarta dan Bandung, dan perlu perhatian agar destinasi di kota lain tetap mendapatkan representasi yang cukup dalam rekomendasi.

**Distribusi Harga**

| Statistic | Value (IDR) |
|-----------|-------------|
| Mean | 24,652 |
| Median | 5,000 |
| Max | 650,000 |

![Screen Shot 2025-06-01 at 08 36 29](https://github.com/user-attachments/assets/b95d66fc-d58b-4d98-a4af-9c8922a5baf4)

**Insight:** Distribusi harga tiket masuk menunjukkan adanya skewness positif yang signifikan. Nilai median (Rp5.000) jauh lebih rendah daripada nilai rata-rata (Rp24.652), yang mengindikasikan bahwa sebagian besar destinasi wisata memiliki harga tiket masuk yang relatif terjangkau, namun terdapat beberapa destinasi dengan harga tiket yang sangat tinggi (hingga Rp650.000) yang menaikkan nilai rata-rata. Visualisasi histogram price_dist.png akan memperjelas hal ini, dimana sebagian besar data akan terkonsentrasi di sisi kiri (harga rendah). Informasi ini penting jika harga akan digunakan sebagai fitur dalam model, karena outlier atau distribusi yang miring mungkin memerlukan perlakuan khusus seperti transformasi logaritmik.

**Rating Distribution:**
| Statistic | Value |
|-----------|-------|
| Mean | 4.4 |
| Median | 4.5 |

![Screen Shot 2025-06-01 at 08 36 29](https://github.com/user-attachments/assets/bbb43f1f-8338-4b81-b830-cbdc1079de58)

**Insight:** Distribusi harga tiket masuk menunjukkan adanya skewness positif yang signifikan. Nilai median (Rp5.000) jauh lebih rendah daripada nilai rata-rata (Rp24.652), yang mengindikasikan bahwa sebagian besar destinasi wisata memiliki harga tiket masuk yang relatif terjangkau, namun terdapat beberapa destinasi dengan harga tiket yang sangat tinggi (hingga Rp650.000) yang menaikkan nilai rata-rata. Visualisasi histogram price_dist.png akan memperjelas hal ini, dimana sebagian besar data akan terkonsentrasi di sisi kiri (harga rendah). Informasi ini penting jika harga akan digunakan sebagai fitur dalam model, karena outlier atau distribusi yang miring mungkin memerlukan perlakuan khusus seperti transformasi logaritmik.

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

**Matrix Density**
Dengan **total 10.000 rating,** kita dapat menghitung kepadatan matriks rating sebagai 10.000/(300×437) ≈ **7.6%**, yang termasuk sparse namun cukup untuk sistem rekomendasi dasar.

Tentu, berikut adalah terjemahan dari bagian tersebut ke dalam Bahasa Indonesia:

## 🔍 Key Insights

1.  **Kualitas Data**:
    * Data pengguna dan data rating lengkap.
    * Terdapat 47% nilai yang hilang (missing values) pada kolom `Time_Minutes`.
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
    * Kolom `Time_Minutes` pada data destinasi memiliki 47% data kosong, yang perlu ditangani jika fitur ini akan digunakan.
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

# ⚙️ Persiapan Data (Data Preparation)

Tahap persiapan data (Data Preparation) merupakan langkah berikutnya setelah pemahaman data (Data Understanding). Pada tahap ini, dataset mentah yang telah dieksplorasi akan diolah dan ditransformasi menjadi format yang sesuai dan optimal untuk tahap pemodelan. Proses ini melibatkan serangkaian teknik untuk membersihkan, mengintegrasikan, dan menstrukturkan data guna meningkatkan kualitas dan relevansinya untuk analisis lebih lanjut. Berikut adalah tahapan persiapan data yang dilakukan secara berurutan:

## 1. Penggabungan Data Rating dengan Informasi Destinasi
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
    Hasilnya, semua kategori kini memiliki format yang konsisten tanpa spasi.

* **Alasan Dilakukan:**
    * **Memudahkan Pemrosesan Teks:** Format tanpa spasi (menggunakan underscore) membuat setiap nama kategori menjadi satu token tunggal. Ini menyederhanakan proses analisis teks atau *feature engineering* di tahap selanjutnya (misalnya, saat menggunakan kategori dalam model TF-IDF).
    * **Konsistensi dan Keterbacaan:** Standardisasi ini meningkatkan konsistensi data dan mempermudah pembacaan serta penggunaan kategori sebagai fitur dalam model.

## 3. Mengatasi Nilai Hilang (Missing Values) dan Duplikasi Data
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
Sebagai langkah akhir dalam persiapan data, dibuat salinan kerja dari dataset yang telah bersih dan dilakukan pengurutan data.

* **Proses yang Dilakukan:**
    1.  Sebuah variabel baru bernama `preparation` dibuat sebagai salinan (working copy) dari dataframe `tourism_rating` yang telah melalui semua tahapan pembersihan sebelumnya.
    2.  Data dalam dataframe `preparation` kemudian diurutkan berdasarkan kolom `Place_Id`.
    ```python
    # preparation = tourism_rating
    # preparation.sort_values('Place_Id')
    ```
    **Struktur Data Final:** Dataframe `preparation` kini berisi 9.921 entri valid dengan 5 kolom utama: `User_Id`, `Place_Id`, `Place_Ratings`, `Place_Name`, dan `Category`.

* **Alasan Dilakukan:**
    * **Salinan Kerja (Working Copy):** Membuat salinan data adalah praktik yang baik untuk menjaga dataset asli yang telah dibersihkan tetap utuh, sementara modifikasi atau eksperimen lebih lanjut dapat dilakukan pada salinan tersebut.
    * **Mempermudah Analisis dan Visualisasi:** Mengurutkan data berdasarkan `Place_Id` dapat mempermudah inspeksi manual data, analisis eksploratif lebih lanjut (misalnya, melihat semua rating untuk destinasi tertentu secara berurutan), dan membantu dalam visualisasi pola rating antar tempat wisata.
    * **Kesiapan untuk Tahap Selanjutnya:** Dataset yang telah dibersihkan dan diorganisir ini dianggap siap untuk tahap *feature engineering* dan proses pembuatan model rekomendasi.

# 🧮 Modeling

Tahap ini berfokus pada pembangunan model machine learning untuk mengklasifikasikan tingkat risiko kesehatan mental berdasarkan fitur-fitur yang telah diproses. Untuk memperoleh gambaran performa awal dan membandingkan efektivitas berbagai algoritma, digunakan **lima model klasifikasi populer** sebagai baseline dengan **hyperparameter default**. Tujuan utamanya adalah mengidentifikasi model terbaik untuk dioptimalkan lebih lanjut pada tahap selanjutnya.

## Model yang Digunakan

Berikut lima model klasifikasi yang digunakan:

### 1. **K-Nearest Neighbors (KNN)**  
KNN mengklasifikasikan sampel baru berdasarkan mayoritas label dari k tetangga terdekat dalam ruang fitur. Model ini cocok digunakan karena data telah melalui proses standarisasi, yang sangat penting dalam algoritma berbasis jarak seperti KNN.

**Hyperparameter Default:**
```python
KNeighborsClassifier(
    n_neighbors=5,       # Jumlah tetangga yang digunakan
    weights='uniform',   # Bobot: 'uniform' (sama) atau 'distance' (berdasarkan jarak)
    algorithm='auto',    # Algoritma: 'auto', 'ball_tree', 'kd_tree', atau 'brute'
    leaf_size=30,        # Ukuran leaf untuk struktur tree
    p=2,                 # Parameter jarak (1=manhattan, 2=euclidean)
    metric='minkowski'   # Metrik jarak
)
```
### 2. **Decision Tree (DT)**  
DT membangun struktur pohon berdasarkan pembagian informasi (information gain) untuk memisahkan kelas target. Algoritma ini mampu menangkap interaksi antar fitur dan memberikan interpretasi yang jelas terhadap proses klasifikasi.
**Hyperparameter Default:**
```python
DecisionTreeClassifier(
    criterion='gini',     # Kriteria split: 'gini' atau 'entropy'
    splitter='best',      # Strategi split: 'best' atau 'random'
    max_depth=None,       # Kedalaman maksimal pohon (None=tanpa batas)
    min_samples_split=2,  # Minimum sampel untuk split node
    min_samples_leaf=1,   # Minimum sampel di leaf node
    min_weight_fraction_leaf=0.0,
    max_features=None,    # Jumlah fitur yang dipertimbangkan untuk split
    random_state=None,
    max_leaf_nodes=None   # Jumlah maksimal leaf nodes
)
```

### 3. **Random Forest (RF)**  
RF adalah algoritma ensemble yang membangun banyak pohon keputusan dan menggabungkan prediksinya untuk meningkatkan akurasi dan mengurangi overfitting. Cocok untuk dataset dengan fitur heterogen dan kompleks, serta tahan terhadap outlier.
**Hyperparameter Default:**
```python
RandomForestClassifier(
    n_estimators=100,     # Jumlah pohon dalam ensemble
    criterion='gini',     # Kriteria split: 'gini' atau 'entropy'
    max_depth=None,       # Kedalaman maksimal per pohon
    min_samples_split=2,
    min_samples_leaf=1,
    min_weight_fraction_leaf=0.0,
    max_features='auto',  # Jumlah fitur: 'auto'=sqrt(n_features)
    max_leaf_nodes=None,
    bootstrap=True,       # Penggunaan bootstrap sampling
    random_state=None
)
```

### 4. **Support Vector Machine (SVM)**  
SVM bekerja dengan mencari hyperplane terbaik yang memisahkan kelas dalam ruang fitur berdimensi tinggi. Penggunaan SVM didukung oleh standarisasi fitur, karena SVM sangat sensitif terhadap skala data.
**Hyperparameter Default:**
```python
SVC(
    C=1.0,               # Parameter regularisasi
    kernel='rbf',        # Jenis kernel: 'linear', 'poly', 'rbf', 'sigmoid'
    degree=3,            # Derajat untuk kernel poly
    gamma='scale',       # Koefisien kernel:'scale'=1/(n_features*X.var())
    coef0=0.0,          # Term independen dalam kernel
    shrinking=True,      # Menggunakan shrinking heuristic
    probability=False,   # Mengestimasi probabilitas
    tol=1e-3,            # Toleransi kriteria stopping
    max_iter=-1          # Maksimum iterasi (-1=no limit)
)
```

### 5. **Naive Bayes (NB)**  
NB adalah model probabilistik yang mengasumsikan independensi antar fitur. Meskipun sederhana, model ini sering memberikan hasil yang kompetitif, terutama jika data sudah bersih dan variabel relevan.
**Hyperparameter Default:**
```python
GaussianNB(
    priors=None,         # Probabilitas prior kelas
    var_smoothing=1e-9   # Penambahan varians untuk stabilitas numerik
)
```

## Alasan Penggunaan Banyak Model

Penggunaan lima model ini bertujuan untuk:
- **Membandingkan performa awal (baseline)** dari berbagai pendekatan klasifikasi.
- **Mengidentifikasi model yang paling sesuai** dengan karakteristik data.
- Menjadi dasar dalam proses **seleksi dan tuning model terbaik** pada tahap selanjutnya.

Seluruh model dilatih menggunakan data training dan diuji dengan data testing yang telah dipisahkan sebelumnya. Evaluasi dilakukan dengan metrik akurasi, precision, recall, dan f1-score untuk memperoleh gambaran menyeluruh terhadap performa model.

# 💯 Evaluation

Tahap evaluasi bertujuan untuk menilai performa model dalam mengklasifikasikan tingkat risiko kesehatan mental berdasarkan fitur-fitur yang tersedia. Evaluasi dilakukan menggunakan metrik standar untuk kasus klasifikasi, yaitu **akurasi**, **precision**, **recall**, dan **F1-score**. Selain itu, **confusion matrix** digunakan untuk melihat distribusi prediksi model terhadap kelas-kelas yang ada.

## Metrik Evaluasi yang Digunakan

- **Akurasi** mengukur proporsi prediksi yang benar dari keseluruhan prediksi.
```
Accuracy = (True Positive + True Negative) / (True Positive + True Negative + False Positive + False Negative)
```

- **Precision** menghitung seberapa banyak prediksi positif yang benar.
```
Precision = True Positive / (True Positive + False Positive)
```

- **Recall** mengukur kemampuan model dalam menangkap seluruh data positif yang benar.
```
Recall = True Positive / (True Positive + False Negative)
```

- **F1-Score** adalah rata-rata harmonik dari precision dan recall, memberikan keseimbangan di antara keduanya.
```
F1-Score = 2 * (Precision * Recall) / (Precision + Recall)
```

## Hasil Evaluasi pada Data Latih

| Model             | Akurasi | Precision (avg)  | Recall (avg)  | F1-score (avg) |
|-------------------|---------|------------------|---------------|----------------|
| KNN               | 0.96    | 0.96             | 0.96          | 0.96           |
| Decision Tree     | 1.00    | 1.00             | 1.00          | 1.00           |
| Random Forest     | 1.00    | 1.00             | 1.00          | 1.00           |
| SVM               | 0.99    | 0.99             | 0.99          | 0.99           |
| Naive Bayes       | 0.88    | 0.87             | 0.87          | 0.87           |

**Interpretasi:**
Model seperti **Decision Tree** dan **Random Forest** mencapai akurasi 100% pada data latih, mengindikasikan kemungkinan **overfitting**, yakni ketika model terlalu menghafal data tanpa kemampuan generalisasi yang baik. Model **SVM** dan **KNN** juga menunjukkan performa tinggi (masing-masing 99% dan 96%), sementara **Naive Bayes** sedikit lebih rendah (88%).

## Evaluasi pada Data Uji

| Model              | Akurasi | Precision (avg) | Recall (avg) | F1-score (avg) |
|-------------------|---------|------------------|---------------|----------------|
| KNN               | 0.94    | 0.94             | 0.92          | 0.93           |
| Decision Tree     | 1.00    | 1.00             | 1.00          | 1.00           |
| Random Forest     | 0.98    | 0.98             | 0.98          | 0.98           |
| SVM               | 0.98    | 0.98             | 0.98          | 0.98           |
| Naive Bayes       | 0.87    | 0.86             | 0.85          | 0.85           |

**Interpretasi:**

- **Decision Tree** menunjukkan akurasi sempurna bahkan di data uji, namun ini jarang terjadi dan mengindikasikan kemungkinan **overfitting**, meskipun hasilnya sangat baik.

- **Random Forest** dan **SVM** menampilkan hasil sangat tinggi dan konsisten (98%), menjadikannya kandidat kuat karena mampu menangkap pola kompleks sekaligus menjaga generalisasi yang baik.

- **KNN** menurun sedikit pada recall, terutama di kelas minoritas, namun tetap menunjukkan generalisasi yang solid dengan akurasi 94%.

- **Naive Bayes** mencatat akurasi terendah, kemungkinan karena asumsi independensi antar fitur tidak sepenuhnya berlaku pada data ini.

# 📋 Kesimpulan

Berdasarkan evaluasi:
- **Decision Tree** memiliki akurasi sempurna, baik saat dites menggunakan data latih maupun data uji. Perlu ditinjau lebih lanjut karena berpotensi overfitting.
- **Random Forest** dan **SVM** menjadi dua alternatif model terbaik karena menghasilkan metrik yang tinggi, seimbang, dan konsisten.

## Rekomendasi:
- Model **Decision Tree** cocok digunakan jika data memiliki dimensionalitas (jumlah fitur) dan varians antar fitur yang rendah. Model ini mudah dipahami dan diinterpretasikan, tetapi performanya dapat menurun secara signifikan ketika dihadapkan dengan data yang memiliki variansi tinggi atau mengandung banyak noise.
- Model **Random Forest** adalah pilihan yang lebih seimbang dan umumnya lebih andal. Model ini menghasilkan akurasi yang tinggi dan konsisten, serta cukup robust terhadap data berdimensionalitas tinggi maupun varians fitur yang besar. Selain itu, Random Forest lebih toleran terhadap outlier dan noise kecil, sehingga cocok digunakan untuk data dunia nyata yang sering kali tidak bersih atau memiliki ketidakteraturan.
- Sama seperti **Random Forest**, **SVM** juga menawarkan performa yang baik dan dapat menangani data dengan margin yang kompleks. Namun, model ini relatif lebih kompleks untuk dilatih, terutama pada dataset besar dan berdimensionalitas tinggi. Selain itu, SVM cenderung kurang toleran terhadap outlier dan perbedaan distribusi antara data latih dan data aktual di lapangan, yang dapat menyebabkan penurunan performa jika data tidak distandarkan atau dibersihkan dengan baik.
