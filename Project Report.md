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


Baik, mari kita susun bagian **Pemodelan (Modeling)** untuk laporan proyek Anda, dimulai dengan pendekatan *Content-Based Filtering* berdasarkan informasi yang telah Anda berikan.

# 🧮 Modeling

Tahap pemodelan adalah inti dari proses CRISP-DM di mana teknik-teknik *machine learning* diterapkan untuk mencapai tujuan proyek. Dalam proyek sistem rekomendasi destinasi wisata Indonesia ini, akan dikembangkan dan disajikan dua solusi rekomendasi utama yang menggunakan algoritma berbeda untuk memberikan saran destinasi kepada pengguna. Tujuannya adalah untuk dapat memberikan rekomendasi *Top-N* (sejumlah N destinasi teratas) yang relevan.

Dua pendekatan utama yang akan diimplementasikan adalah:
1.  **Content-Based Filtering (Penyaringan Berbasis Konten):** Memanfaatkan atribut atau fitur dari destinasi wisata (dalam kasus ini, kategori destinasi) untuk merekomendasikan item yang serupa.
2.  **Collaborative Filtering (Penyaringan Kolaboratif):** Menggunakan interaksi historis pengguna dengan destinasi (seperti rating) dan menerapkan model *deep learning* berbasis *embedding* untuk menemukan pola kesukaan dan merekomendasikan destinasi berdasarkan preferensi pengguna lain yang serupa.

Berikut ini adalah penjelasan detail untuk masing-masing pendekatan:

## Solusi 1: Content-Based Filtering (CBF)
Pendekatan *Content-Based Filtering* (CBF) merekomendasikan item berdasarkan kemiripan antara fitur item yang telah disukai pengguna di masa lalu dengan fitur item lain yang tersedia. Dalam konteks proyek ini, CBF akan diimplementasikan dengan memanfaatkan **kategori destinasi wisata** sebagai fitur utama. Prosesnya melibatkan transformasi data kategori menggunakan TF-IDF (*Term Frequency-Inverse Document Frequency*) untuk mengukur bobot pentingnya setiap kategori, diikuti dengan perhitungan *Cosine Similarity* untuk mengidentifikasi kemiripan antar destinasi.

### 1. Persiapan Data untuk Content-Based Filtering
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

### 4. Perhitungan Kemiripan Destinasi dengan Cosine Similarity
Setelah destinasi direpresentasikan sebagai vektor TF-IDF, langkah selanjutnya adalah menghitung kemiripan antar semua pasangan destinasi.

* **Proses yang Dilakukan:**
    1.  Fungsi `cosine_similarity` dari `sklearn.metrics.pairwise` diterapkan pada `tfidf_matrix`.
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

### 5. Implementasi Fungsi Rekomendasi
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
    Hasil ini menunjukkan bahwa sistem berhasil merekomendasikan lima destinasi lain yang juga berkategori 'Bahari', sesuai dengan kategori 'Pantai Ancol'.

### 6. Kelebihan dan Kekurangan Content-Based Filtering
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

Pendekatan *Content-Based Filtering* ini menjadi salah satu pilar dalam sistem rekomendasi yang dikembangkan, memberikan dasar rekomendasi berdasarkan karakteristik eksplisit dari destinasi wisata.

## Solusi 2: Collaborative Filtering (CF) dengan Embedding Deep Learning
Pendekatan *Collaborative Filtering* (CF) bekerja berdasarkan ide bahwa pengguna yang memiliki preferensi serupa di masa lalu cenderung akan menyukai item yang sama di masa depan. Berbeda dengan CBF yang fokus pada fitur item, CF fokus pada pola interaksi pengguna-item (misalnya, rating yang diberikan). Dalam proyek ini, CF diimplementasikan menggunakan model *deep learning* yang memanfaatkan teknik *embedding* untuk mempelajari representasi laten (tersembunyi) dari pengguna dan destinasi.

### 1. Persiapan Data dan Encoding untuk Collaborative Filtering
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
    * Mengetahui jumlah unik pengguna dan destinasi penting untuk menentukan ukuran *embedding layers*. Informasi skala rating (min/max) digunakan untuk normalisasi nilai target (rating).

### 2. Pembagian Data Latih dan Validasi (Train-Validation Split)
Dataset kemudian diacak dan dibagi menjadi data latih (*training set*) dan data validasi (*validation set*).

* **Proses yang Dilakukan:**
    1.  Seluruh dataset `df` diacak secara acak (menggunakan `df.sample(frac=1, random_state=42)`) untuk memastikan tidak ada bias urutan.
    2.  Variabel input `x` dibentuk dari pasangan kolom `user_encoded` dan `place_encoded`.
    3.  Variabel target `y` (rating) dinormalisasi ke rentang [0, 1] menggunakan Min-Max Scaling: $y = (Place_Ratings - min_rating) / (max_rating - min_rating)$.
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
        * Mengaktifkan Dropout layers untuk mencegah overfitting.
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
        Pelatihan menunjukkan penurunan *loss* yang baik pada epoch-epoch awal. *Callback* `ReduceLROnPlateau` terpicu beberapa kali, mengurangi *learning rate* untuk membantu model menemukan konvergensi yang lebih baik. Akhirnya, `EarlyStopping` menghentikan pelatihan pada epoch ke-22 (berdasarkan deskripsi naratif, epoch terbaik adalah ke-12 dimana bobot dikembalikan), mencegah *overfitting* lebih lanjut. Pada epoch terbaik (epoch 12), model mencapai `training loss` sekitar 0.1161 dan `validation loss` sekitar 0.1245, dengan RMSE sekitar 0.35 pada skala rating yang dinormalisasi.

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
    No.  Destination                       | Category            
    ------------------------------------------------------------
    1    Atlantis Water Adventure          | Taman_Hiburan       
    2    Museum Gedung Sate                | Budaya              
    3    Taman Harmoni Keputih             | Cagar_Alam          
    4    Taman Sungai Mudal                | Cagar_Alam          
    5    Surabaya North Quay               | Taman_Hiburan       

    ✨ Top 10 Destination Recommendations for User:
    ------------------------------------------------------------
    No.  Destination                       | Category            
    ------------------------------------------------------------
    1    Bukit Jamur                       | Cagar_Alam          
    2    Glamping Lakeside Rancabali       | Taman_Hiburan       
    3    Monumen Yogya Kembali             | Budaya              
    4    Jogja Exotarium                   | Taman_Hiburan       
    5    Jogja Bay Pirates Adventure Waterpark | Taman_Hiburan       
    6    Keraton Surabaya                  | Budaya              
    7    Bukit Bintang Yogyakarta          | Taman_Hiburan       
    8    Taman Hiburan Rakyat              | Taman_Hiburan       
    9    Pantai Depok Jogja                | Bahari              
    10   Obyek Wisata Goa Kreo             | Cagar_Alam
    ```
    Output ini menunjukkan kemampuan model *deep learning* dalam memberikan rekomendasi yang beragam dan relevan berdasarkan pola preferensi yang dipelajari dari interaksi pengguna.

### 6. Kelebihan dan Kekurangan Collaborative Filtering (dengan Deep Learning)

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

Pendekatan *Collaborative Filtering* berbasis *deep learning* ini melengkapi CBF dengan menawarkan personalisasi yang didorong oleh perilaku kolektif pengguna, mampu menangkap nuansa preferensi yang lebih halus.



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
