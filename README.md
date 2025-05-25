# Laporan Proyek Machine Learning - Tb Ulfah Nur Sya'baniah

## Project Overview (Ulasan Proyek)
**Judul:**
# **Meningkatkan Aksesibilitas Ruang Terbuka di Kota Urban: Pendekatan Content-Based Filtering dan Cluster Analysis**

### Latar Belakang Proyek  
Urbanisasi yang semakin pesat telah mengubah lanskap kota-kota di seluruh dunia. Pertumbuhan penduduk dan peningkatan kepadatan di wilayah perkotaan menuntut perencanaan ruang yang lebih cermat guna menjaga kualitas hidup masyarakat. Ruang terbuka publik tidak hanya berfungsi sebagai area rekreasi dan interaksi sosial, tetapi juga berperan penting dalam menjaga kesehatan fisik dan mental penduduk. Di tengah tantangan urbanisasi ini, banyak kota menghadapi ketidakseimbangan antara penyediaan ruang terbuka dan tingkat aksesibilitas yang dirasakan oleh warganya. Kondisi ini menimbulkan kebutuhan mendesak untuk dianalisis secara mendalam agar solusi yang tepat dapat diimplementasikan.

### Mengapa Proyek Ini Penting  
Proyek ini penting untuk diselesaikan karena beberapa alasan berikut:

1. **Peningkatan Kualitas Hidup Masyarakat:**  
   Ruang terbuka publik yang terintegrasi secara proporsional dapat membantu mengurangi stres, meningkatkan kesehatan mental, dan mendorong aktivitas fisik. Dengan demikian, perbaikan dalam distribusi dan aksesibilitas ruang terbuka dapat memberikan dampak positif dalam meningkatkan kesejahteraan penduduk.

2. **Dasar Kebijakan Urban Berbasis Data:**  
   Dengan mengintegrasikan data perencanaan ruang dan indikator aksesibilitas, proyek ini menyediakan bukti nyata yang dapat digunakan oleh perencana kota dan pembuat kebijakan. Hasil riset dan analitik berbasis data sangat penting untuk merumuskan intervensi dan strategi pembangunan kota yang efisien dan berkelanjutan.

3. **Benchmarking dan Pengembangan Sistem Rekomendasi:**  
   Proyek ini tidak hanya menawarkan analisis terperinci terhadap kondisi ruang terbuka dan aksesnya, tetapi juga mengembangkan sistem rekomendasi menggunakan pendekatan content-based filtering dan collaborative filtering. Hal ini memungkinkan kota-kota dengan karakteristik serupa dapat dibandingkan secara kuantitatif, sehingga membantu dalam adopsi praktik terbaik serta memperkuat dasar penetapan intervensi kebijakan.

### Hasil Riset dan Referensi Terkait  
Beberapa riset dan publikasi internasional menekankan pentingnya keberadaan ruang terbuka sebagai bagian dari perencanaan kota yang efektif, di antaranya:

- **UN-Habitat:**  
  Data dan laporan dari UN-Habitat menyoroti bahwa persentase ruang terbuka yang cukup dan aksesibilitas yang baik mempunyai korelasi positif dengan peningkatan kualitas hidup di kota-kota urban. Dataset yang tersedia di [UN-Habitat: Open Spaces and Green Areas](https://data.unhabitat.org/pages/open-spaces-and-green-areas) menjadi salah satu referensi utama untuk menganalisis dan benchmarking kondisi ruang terbuka publik.

- **World Health Organization (WHO):**  
  WHO juga telah mengemukakan bahwa ruang terbuka publik yang memadai merupakan salah satu faktor pendukung kesehatan masyarakat, yang membantu mengurangi risiko penyakit dan meningkatkan aktivitas fisik serta kesejahteraan mental. Informasi dan fakta terkait dampak aktivitas fisik terhadap kesehatan dapat ditemukan dalam [WHO Fact Sheet on Physical Activity](https://www.who.int/news-room/fact-sheets/detail/physical-activity).

- **Publikasi tentang Sistem Rekomendasi:**  
  Penelitian terbaru dalam sistem rekomendasi menunjukkan bahwa penggunaan metode content-based filtering dan collaborative filtering dapat secara efektif mengelompokkan data dan menghasilkan rekomendasi yang relevan. Pendekatan ini terbukti efektif dalam berbagai domain, termasuk perencanaan kawasan kota, di mana perbandingan antar kota dapat membantu menentukan strategi intervensi yang tepat. Sebagai contoh, dokumen _"Comparison Between Collaborative Filtering and Content-Based Filtering"_ dapat diakses melalui [link berikut](https://pdfs.semanticscholar.org/3b99/05ffb0aed764cd5fbeb3ed5dff0843cf9103.pdf).

### Kesimpulan  
Dengan menggabungkan pendekatan machine learning untuk analisis data perencanaan ruang, proyek ini memberikan kontribusi signifikan dalam menyediakan solusi berbasis data untuk mengoptimalkan distribusi ruang terbuka dan aksesibilitas kota. Hasil analisis dan rekomendasi yang dihasilkan tidak hanya mendukung perbaikan kualitas hidup, tetapi juga memberikan dasar ilmiah bagi perumusan kebijakan pembangunan kota yang responsif dan berkelanjutan.

---

## Business Understanding

### 1. Proses Klarifikasi Masalah

**a. Diskusi dan Pengumpulan Informasi**  
- **Analisa Konteks Urban:**  
  Proyek ini berangkat dari pengamatan bahwa di banyak kota terdapat ketidakseimbangan antara penyediaan ruang terbuka publik dan tingkat aksesibilitas yang dirasakan oleh penduduk.  
- **Studi Literatur dan Data Terpercaya:**  
  Data UN-Habitat menunjukkan bahwa ruang terbuka yang cukup dapat meningkatkan kualitas hidup. Sedangkan literatur dari World Health Organization (WHO) menekankan dampak positif ruang terbuka bagi kesehatan mental dan fisik.  

**b. Identifikasi Variabel Kunci**  
- **Indikator Utama:**  
  1. *Average share of the built-up area of cities that is open space for public use for all (%) [a]*  
  2. *Average share of urban population with convenient access to open public spaces (%) [b]*  
- **Fitur Turunan:**  
  Perhitungan selisih antara [b] dan [a] (Difference (b - a)) yang memberikan gambaran tentang ketidaksesuaian antara penyediaan fisik dan aksesibilitas.

---

### 2. Problem Statements (Pernyataan Masalah)

- **Ketidakseimbangan Indikator:**  
  Banyak kota menampilkan perbedaan yang signifikan antara ketersediaan ruang terbuka dan aksesibilitas penduduk. Meskipun area ruang terbuka publik mungkin memadai, distribusinya tidak selalu mendukung akses yang optimal bagi seluruh masyarakat.
  
- **Keterbatasan Benchmarking:**  
  Saat ini, belum ada sistem rekomendasi yang secara kuantitatif mengelompokkan dan membandingkan kota berdasarkan kedua indikator tersebut, sehingga perbandingan praktik terbaik ("best-practice") untuk perencanaan ruang terbuka sulit dilakukan.
  
- **Keterbatasan Data Interaksi:**  
  Data yang ada bersifat kuantitatif pada dua indikator utama. Data interaksi atau umpan balik pengguna (misalnya, rating terhadap kota) belum tersedia sehingga menantang penerapan metode collaborative filtering langsung.

---

### 3. Goals (Tujuan)

Proyek ini memiliki beberapa tujuan strategis, antara lain:

- **Analisis dan Segmentasi:**  
  Menggunakan data kuantitatif untuk mengidentifikasi pola dan segmentasi kota berdasarkan rasio alokasi ruang terbuka ([a]) dan aksesibilitas ([b]). Tujuannya adalah mengelompokkan kota dengan karakteristik serupa sehingga perencanaan intervensi bisa disesuaikan.

- **Pengembangan Sistem Rekomendasi:**  
  Membangun model rekomendasi berbasis content‑based filtering yang memungkinkan perbandingan antar kota sehingga memperkuat basis data dalam merumuskan strategi perbaikan tata ruang.

- **Dukungan Kebijakan Urban:**  
  Menyajikan insight berbasis data untuk mendukung pembuat kebijakan dalam menentukan intervensi yang tepat, misalnya, apakah perlu menambah fasilitas ruang terbuka, memperbaiki konektivitas, atau melakukan redistribusi pemanfaatan ruang.

---

### 4. Solution Approach

Untuk mencapai tujuan di atas, saya mengusulkan dua pendekatan solusi, yaitu:

#### **A. Content‑Based Filtering**

**Metode:**
- **Fitur Numerik:**  
  Model ini menggunakan dua indikator utama (ruang terbuka [a] dan akses [b]) beserta fitur turunan (Difference (b - a)) sebagai representasi konten dari masing-masing kota.
- **Penentuan Kemiripan:**  
  Menggunakan algoritma Nearest Neighbors untuk mengukur jarak (Euclidean distance) antar kota yang telah dinormalisasi, sehingga kota-kota dengan pola serupa akan saling direkomendasikan.
- **Implementasi:**  
  Pendekatan ini sudah diimplementasikan dalam proyek, menghasilkan rekomendasi dan segmentasi berbasis similarity dari fitur-fitur utama.

**Keunggulan:**
- Transparan dan mudah dijelaskan.
- Tidak tergantung pada data interaksi, sehingga cocok digunakan dalam kondisi data yang terbatas.
  
**Kekurangan:**
- Cenderung menghasilkan rekomendasi yang sangat mirip (over-specialization) tanpa variasi tambahan, karena hanya mengandalkan data fitur yang tersedia.

---

#### **B. Collaborative Filtering (Opsional/Hybrid Model)**

**Metode:**
- **Integrasi Umpan Balik Pengguna:**  
  Jika di masa depan data tambahan berupa umpan balik, rating, atau interaksi pengguna terhadap kota tersedia, pendekatan collaborative filtering dapat diterapkan.  
- **Perhitungan Similarity:**  
  Menggunakan cosine similarity untuk menghitung kemiripan antar pengguna (atau antar kota berdasarkan feedback) dan menggabungkannya dengan similarity berbasis konten.
  
**Kerangka Dasar Hybrid Model:**  
Sebagai kerangka dasar pengembangan, berikut pseudocode yang dapat dikembangkan ketika data interaksi sudah tersedia:

```python
from sklearn.metrics.pairwise import cosine_similarity

# Misalkan ratings adalah DataFrame dengan index sebagai user ID dan kolom sebagai City Code.
# ratings = pd.read_csv("user_ratings.csv", index_col=0)

# Collaborative Filtering: Hitung similarity antar pengguna (atau antar kota)
# collaborative_similarity = cosine_similarity(ratings)

# Content-Based Filtering: Gunakan fitur utama
content_similarity = cosine_similarity(df_scaled[required_columns])

# Kombinasikan kedua similarity dengan bobot 0.5 untuk masing-masing (misalnya)
alpha = 0.5
# hybrid_similarity = alpha * content_similarity + (1 - alpha) * collaborative_similarity
```

**Keunggulan:**
- **Personalisasi dan Diversifikasi:**  
  Dapat merekomendasikan kota yang tidak hanya mirip secara fitur, tetapi juga berdasarkan pola interaksi pengguna.
- **Pendekatan Hybrid:**  
  Dengan menggabungkan kedua metode, sistem dapat menyeimbangkan antar informasi objektif (data fitur) dan subjektif (feedback pengguna).

**Kekurangan:**
- **Ketergantungan pada Data:**  
  Saat ini, data interaksi belum tersedia sehingga model collaborative filtering belum dapat diimplementasikan secara langsung.
- **Cold-Start Problem:**  
  Untuk kota atau pengguna baru, data rating yang minim dapat menyulitkan pembangkitan rekomendasi yang akurat.

---

### Kesimpulan Business Understanding

Proses klarifikasi masalah telah mengidentifikasi tantangan utama di perencanaan ruang terbuka, yaitu ketidakseimbangan antara penyediaan ruang dan akses, keterbatasan benchmarking antar kota, dan ketiadaan data interaksi. Dengan menetapkan tujuan untuk menganalisis dan mengelompokkan kota berdasarkan indikator utama serta mengembangkan sistem rekomendasi berbasis data, proyek ini menyediakan dasar ilmiah untuk mendukung kebijakan urban yang lebih tepat sasaran.

---

## Data Understanding

### 1. Informasi Umum dan Sumber Data

- **Sumber Data:**  
  Dataset yang digunakan dalam proyek ini diperoleh dari situs UN-Habitat, yang menyediakan informasi mengenai ruang terbuka dan green areas di berbagai kota.  
  **Link Download:**  
  [UN-Habitat – Open Spaces and Green Areas](https://data.unhabitat.org/pages/open-spaces-and-green-areas)

  Indicator Title: SDG 11.7.1: Average share of the built-up area of cities that is open space for public use for all, by sex, age and persons with disabilities.

- **Jumlah Baris dan Kolom:**  
  Dataset memiliki 1711 entri (baris) dengan 15 kolom. Ukuran ini menunjukan bahwa dataset cukup besar untuk analisis komparatif antar kota maupun negara, namun juga perlu diperhatikan dalam hal komputasi untuk model rekomendasi nanti.

- **Tipe Data:**  
  - Terdapat kolom bertipe numerik seperti integer (misalnya, *SDG Goal*, *Country or Territory Code*, *Data Reference Year*) dan float (misalnya, *SDG Target* serta dua kolom indikator [a] dan [b]).  
  - Sebagian besar kolom bersifat *object* (teks), terutama yang berisi informasi geografis dan metadata (seperti *Country or Territory Name*, *SDG Region*, *City Code*, *City Name*, *Data Source*, dan *FootNote*).

---

### 2. Kualitas Data dan Missing Values  
- **Kolom dengan Data Lengkap:**  
  Kolom-kolom seperti *SDG Goal*, *SDG Target*, *SDG Indicator*, *Country or Territory Code*, *Country or Territory Name*, *Data Units*, *Data Reference Year*, *Data Source*, dan *FootNote* memiliki 1711 entri yang lengkap. Ini memastikan bahwa aspek dasar metadata dan pengidentifikasi selalu ada di setiap baris.

- **Kolom Geografis yang Hampir Lengkap:**  
  - *SDG Region*, *SDG Sub-Region*, *City Code*, dan *City Name* masing-masing memiliki 14 missing values.  
  - Missing values ini relatif kecil dibandingkan total 1711 baris (sekitar 0,8% dari dataset), namun perlu diperhatikan untuk analisis yang memanfaatkan informasi geografis.

- **Kolom Indikator Kunci:**  
  - *Average share of the built-up area of cities that is open space for public use for all (%) [a]* memiliki 199 missing values (sekitar 11,6% dari total data).  
  - *Average share of urban population with convenient access to open public spaces (%) [b]* memiliki 149 missing values (sekitar 8,7%).  
  Karena keduanya merupakan indikator utama untuk perancangan ruang publik, tingkat missing value yang cukup signifikan di kolom ini perlu ditangani, baik melalui imputasi, penghapusan baris, atau metode lain, agar analisis dan model dapat memperoleh hasil yang andal.

---

### 3. Statistik Deskriptif untuk Kolom Numerik  
- **Rentang Nilai dan Distribusi:**  
  Dengan fungsi `df.describe()`, kita dapat memperoleh informasi seperti nilai minimum, maksimum, rata-rata, dan standar deviasi untuk kolom-kolom numerik. Meskipun output lengkap dari `describe()` tidak ditampilkan di sini, kita dapat menyimpulkan:
  - Nilai-nilai indikator harus berada di rentang 0-100 (dengan asumsi satuan adalah persen).
  - Perbedaan nilai antar baris dapat memberikan informasi mengenai sebaran dan variasi dalam penyediaan ruang terbuka publik dan aksesibilitasnya di berbagai kota.

- **Implikasi Statistik Deskriptif:**  
  Informasi seperti rata-rata dan distribusi nilai akan membantu mengidentifikasi apakah ada outlier atau pola khusus. Jika terdapat nilai maksimum yang jauh lebih tinggi/lunak dibandingkan rata-rata, mungkin hal itu menunjukkan adanya kota dengan kinerja luar biasa (baik positif atau negatif) dalam menyediakan ruang terbuka.
  
- **Kondisi Data:**  
  Data belum mengalami normalisasi atau standarisasi awal saat diunduh, sehingga nilai-nilai pada beberapa fitur seperti persentase ruang terbuka dan aksesibilitas perlu dipersiapkan melalui teknik scaling. Beberapa entri mengandung missing values yang diatasi dengan penghapusan atau imputasi, proses ini dijelaskan lebih lanjut di bagian Data Preparation.

### 4. Variabel (Fitur) pada Data

Dataset yang digunakan mengandung beberapa variabel, yakni:

1. **SDG Goal**  
   Fitur ini merupakan angka yang menunjukkan tujuan utama dari Sustainable Development Goals (SDG). Setiap nomor mewakili salah satu tujuan global, seperti pengentasan kemiskinan, peningkatan kualitas pendidikan, dan perlindungan lingkungan. Penggunaan angka di sini membantu dalam pengkategorian dan pengelompokan entri berdasarkan tujuan SDG yang relevan.

2. **SDG Target**  
   Fitur ini mengindikasikan target spesifik yang hendak dicapai dalam kerangka SDG. Bentuk datanya berupa numerik (float64) sehingga dapat digunakan untuk representasi level pencapaian atau sasaran kuantitatif yang lebih terukur dalam setiap tujuan. Nilai target ini mendukung evaluasi kemajuan suatu negara atau wilayah dalam memenuhi kriteria SDG.

3. **SDG Indicator**  
   Berupa data teks, fitur ini mendeskripsikan indikator yang mengukur pencapaian terhadap target SDG. Indikator tersebut biasanya berupa parameter yang konkrit, misalnya persentase akses terhadap fasilitas umum atau data statistik lain yang mendukung analisis pencapaian tujuan SDG.

4. **Country or Territory Code**  
   Fitur ini adalah kode numerik unik yang mengidentifikasi setiap negara atau wilayah teritori dalam dataset. Dengan adanya kode ini, data dapat dengan mudah diurutkan atau diklasifikasikan berdasarkan masing-masing entitas geografis, yang mana akan mendukung analisis komparatif antar negara atau wilayah.

5. **Country or Territory Name**  
   Berupa data teks, fitur ini menyajikan nama lengkap negara atau wilayah teritori. Informasi ini memberikan konteks geografis yang jelas dan membantu dalam memahami distribusi data serta relevansi antara setiap entitas yang dianalisis.

6. **SDG Region**  
   Fitur ini mengklasifikasikan data berdasarkan region SDG, yaitu pengelompokan geografis sesuai dengan standar internasional. Meskipun terdapat beberapa missing values (sekitar 14 entri), kategori ini tetap penting untuk segmentasi dan analisis regional guna mengidentifikasi tren atau pola tertentu dalam konteks lokasi.

7. **SDG Sub-Region**  
   Mirip dengan fitur SDG Region, fitur ini memberikan tingkat klasifikasi yang lebih spesifik dengan mengidentifikasikan sub-region dari tiap entitas. Penggunaan sub-region memungkinkan analisis yang lebih mendalam dalam pengelompokan geografis, sehingga potensi perbedaan daerah dapat dikenali dengan lebih jelas.

8. **City Code**  
   Fitur ini adalah kode unik untuk setiap kota, yang biasanya berupa kombinasi karakter atau angka. Meskipun bertipe data objek, City Code memudahkan identifikasi dan penelusuran masing-masing entitas kota secara spesifik dalam dataset.

9. **City Name**  
   Merupakan nama dari kota atau wilayah urban, fitur ini sangat krusial dalam konteks perencanaan ruang terbuka publik. Nama kota sebagai informasi geografis membantu dalam melakukan analisis berbasis lokasi dan memahami konteks urban dari data yang disajikan.

10. **Average share of the built-up area of cities that is open space for public use for all (%) [a]**  
    Fitur numerik ini mengukur persentase rata-rata dari area terbangun di kota yang disediakan sebagai ruang terbuka untuk penggunaan publik. Angka ini memberikan insight tentang seberapa banyak ruang yang dialokasikan untuk kebutuhan publik, yang esensial dalam perencanaan kota yang berkelanjutan.

11. **Average share of urban population with convenient access to open public spaces (%) [b]**  
    Fitur ini memberikan gambaran tentang persentase populasi urban yang memiliki akses mudah ke ruang terbuka publik. Dengan data numerik tersebut, analisis dapat melihat sejauh mana fasilitas publik menjangkau masyarakat, sehingga berperan sebagai indikator penting dalam evaluasi kesejahteraan perkotaan.

12. **Data Units**  
    Fitur ini menjelaskan satuan pengukuran yang digunakan dalam data—misalnya satuan persen untuk indikator ruang terbuka atau satuan lain yang relevan. Informasi satuan sangat penting untuk memastikan bahwa nilai-nilai data diinterpretasikan secara tepat dan konsisten dalam analisis.

13. **Data Reference Year**  
    Fitur ini menunjukkan tahun referensi atau tahun pengambilan data. Mengetahui konteks waktu data sangat penting untuk analisis tren, pembandingan antar periode, dan validitas konteks temporal dari data yang dikumpulkan.

14. **Data Source**  
    Fitur ini menginformasikan asal-usul data atau sumber penyedia data, seperti lembaga pemerintahan, organisasi internasional, atau metode pengumpulan data tertentu. Mengetahui sumber data mendukung verifikasi dan kredibilitas analisis, sehingga memberikan dasar kepercayaan pada hasil yang diperoleh.

15. **FootNote**  
    Fitur ini berisi catatan tambahan atau penjelasan yang melengkapi interpretasi data. FootNote dapat menyajikan detail kontekstual, keterangan pengukuran, atau informasi penting lainnya yang membantu dalam memahami kondisi serta nuansa data yang tidak tercakup oleh fitur utama.

### 5. Penanganan Duplikasi

1. **Integritas Data Terjaga**  
   Fakta bahwa tidak ada baris duplikat berarti setiap entri di dataset merupakan catatan unik. Ini mengindikasikan bahwa data sudah dikumpulkan dan disusun dengan baik, tanpa terjadi pengulangan yang tidak terinformasi. Hal ini sangat penting untuk memastikan bahwa analisis statistik dan pemodelan selanjutnya tidak akan mengalami bias akibat adanya data yang berulang.

2. **Keandalan Analisis yang Lebih Tinggi**  
   Dengan tidak adanya duplikasi, hasil perhitungan statistik seperti rata-rata, median, atau distribusi nilai akan mencerminkan variasi yang nyata pada dataset. Setiap baris menyumbang informasi unik sehingga analisis lebih akurat dan representatif terhadap kondisi sebenarnya.

3. **Penghematan Waktu dalam Pembersihan Data**  
   Salah satu langkah awal dalam prapemrosesan data adalah identifikasi duplikasi. Output ini menunjukkan bahwa tidak perlu melakukan proses penghapusan duplikasi, sehingga Anda dapat lebih cepat berfokus pada aspek lain seperti penanganan missing values, outlier, atau feature engineering.

4. **Dasar yang Kuat untuk Pengembangan Model**  
   Model machine learning atau sistem rekomendasi sangat mengandalkan kualitas data input. Data yang bebas dari duplikasi membantu dalam mencegah overestimation atau bias selama pelatihan model karena tidak ada informasi yang terulang secara tidak perlu. Dengan demikian, model yang dibangun nantinya akan lebih andal dan valid.

Secara keseluruhan, hasil "Jumlah baris duplikat: 0" merupakan indikator positif bahwa dataset memiliki integritas data yang tinggi. Hal ini merupakan fondasi yang kuat untuk melanjutkan ke tahapan analisis eksplorasi lebih lanjut dan pengembangan model tanpa harus khawatir adanya bias yang ditimbulkan oleh entri data yang berulang.

---

### 6. Tahapan Eksploratory Data Analysis (EDA)

Beberapa langkah eksplorasi yang telah dilakukan dalam analisis data meliputi:

- **Statistik Deskriptif:**  
  Dilakukan perhitungan ringkasan statistik (mean, median, standard deviation) untuk masing-masing fitur. Hal ini membantu memahami sebaran dan kecenderungan umum nilai fitur.
  
- **Visualisasi Distribusi:**  
  - **Histogram dan Boxplot:** Menganalisis distribusi dari [a] dan [b] untuk mengidentifikasi adanya outlier dan memahami sebaran data.  
  - **Contoh Insight:** Ditemukan bahwa nilai [a] berada di rentang yang relatif sempit (misalnya, 9%–20%), sedangkan nilai [b] memiliki variasi yang lebih luas, mengindikasikan adanya perbedaan signifikan dalam tingkat akses di beberapa kota.
  
- **Visualisasi Hubungan Antar Variabel:**  
  - **Scatter Plot:** Contohnya, scatter plot yang memetakan “Difference (b - a)” terhadap “Average share of urban population with convenient access to open public spaces (%) [b]” serta visualisasi cluster berdasarkan kedua fitur utama.  
  - **Insight Visual:** Dari plot tersebut dapat diidentifikasi pola-pola keberelahan yang menunjukkan bahwa beberapa kota memiliki akses yang jauh lebih baik dibandingkan dengan ruang terbuka yang disediakan, sedangkan untuk kelompok lainnya, keseimbangan berada pada titik mendekati nol.
  
- **Segmentasi Awal Menggunakan Clustering:**  
  Visualisasi clustering pada data yang telah di‑scale memberikan gambaran mengenai kelompok-kelompok kota yang memiliki karakteristik serupa. Hal ini tidak hanya membantu dalam penyusunan sistem rekomendasi, tetapi juga menyediakan insight bagi perencana kota untuk melakukan benchmark dan merancang kebijakan yang lebih terarah.

### 4. Visualisasi Contoh

Berikut adalah contoh kode untuk visualisasi distribusi dan hubungan antar variabel:

```python
import matplotlib.pyplot as plt
import seaborn as sns

# Contoh Histogram untuk fitur [a]
plt.figure(figsize=(8, 5))
sns.histplot(df_scaled["Average share of the built-up area of cities that is open space for public use for all (%) [a]"], bins=30, kde=True)
plt.title("Distribusi Persentase Ruang Terbuka Publik ([a])")
plt.xlabel("Persentase Ruang Terbuka")
plt.ylabel("Frekuensi")
plt.show()

# Contoh Scatter Plot untuk melihat hubungan antara Difference (b - a) dan [b]
plt.figure(figsize=(10, 6))
sns.scatterplot(
    x='Difference (b - a)',
    y='Average share of urban population with convenient access to open public spaces (%) [b]',
    hue='Cluster',  # jika sudah dilakukan clustering
    palette='viridis',
    data=df_scaled,
    alpha=0.7
)
plt.title("Hubungan antara Difference (b - a) dan Akses ([b])")
plt.xlabel("Difference (b - a)")
plt.ylabel("Akses ke Ruang Terbuka Publik (%) [b] (scaled)")
plt.legend(title="Cluster")
plt.show()
```

**Insight dari EDA:**  
- **Distribusi yang Relatif Konsisten:** Data ruang terbuka ([a]) menunjukkan rentang yang stabil, namun terdapat outlier di beberapa kota yang mungkin perlu analisis lebih lanjut.  
- **Perbedaan dalam Akses:** Variasi yang lebih besar pada nilai [b] membuka peluang untuk mengevaluasi mengapa beberapa kota memiliki akses yang jauh lebih tinggi, yang mungkin terkait dengan faktor infrastruktur atau penataan kota.  
- **Pemisahan Cluster yang Menjanjikan:** Hasil clustering awal menunjukkan adanya kelompok kota dengan karakteristik yang serupa, misalnya, kota dengan nilai Difference (b - a) tinggi versus rendah, yang dapat dijadikan dasar untuk rekomendasi kebijakan perbaikan.

---

## Data Preparation

Bagian ini menjelaskan secara rinci tahapan data preparation yang dilakukan pada notebook proyek, mulai dari pembersihan data awal hingga transformasi fitur. Proses ini penting untuk memastikan kualitas dan konsistensi data, sehingga hasil pemodelan nantinya dapat lebih akurat dan andal.

### 1. Pembersihan Data (Data Cleaning)

- **Identifikasi Missing Values:**  
  Saya memeriksa dataset untuk menemukan adanya entri yang hilang atau tidak lengkap. Dengan menggunakan fungsi seperti `df.isnull().sum()`, saya mengidentifikasi variabel yang memiliki missing values. Dataset awal memiliki 1711 baris. Setelah menghapus baris yang memiliki missing values di salah satu atau kedua kolom indikator utama, dataset berkurang menjadi 1363 baris. Artinya, sebanyak 1711 – 1363 = 348 baris (sekitar 20,3% dari total data) telah dihapus karena tidak memiliki data lengkap untuk kedua indikator kunci. Ini menunjukkan bahwa cukup banyak data yang tidak lengkap di bagian indikator ruang terbuka dan aksesibilitas, sehingga perlu perhatian khusus pada langkah pra-pemrosesan data.
  **Alasan:** Missing values dapat menyebabkan bias atau error pada model. Oleh karena itu, saya melakukan penanganan melalui penghapusan entri (jika jumlahnya relatif kecil) atau imputasi (jika diperlukan) agar data menjadi lebih representatif.

- **Penghapusan Duplikasi:**  
  Saya memeriksa tidak adanya baris duplikat pada dataset. 
  **Alasan:** Duplikasi data dapat mengacaukan statistik deskriptif dan membuat model terlatih pada data yang tidak unik, sehingga dapat menurunkan kinerja prediksi.

### 2. Transformasi Data

- **Konversi Tipe Data:**  
  Pastikan bahwa setiap variabel memiliki tipe data yang sesuai, mengonversi variabel numerik yang berformat string menjadi tipe data numerik dengan `pd.to_numeric()`.  
  **Alasan:** Tipe data yang tepat diperlukan agar operasi matematika dan statistik dapat dilakukan secara akurat.

- **Ekstraksi Fitur Turunan:**  
  Dibuat fitur tambahan yaitu **Difference (b - a)**, yang dihitung sebagai selisih antara:
  - `Average share of urban population with convenient access to open public spaces (%) [b]`  
    dan  
  - `Average share of built-up area of cities that is open space for public use for all (%) [a]`  
  **Alasan:** Fitur ini membantu mengungkap perbedaan antara aksesibilitas dan penyediaan ruang terbuka, sehingga model dapat lebih mudah mengklasifikasikan ketidaksesuaian antar kota.

### 3. Normalisasi dan Scaling (Data Transformation)

- **Normalisasi Data:**  
  Sebelum melakukan pemodelan (misalnya clustering atau perhitungan similarity), data harus berada dalam skala yang seragam. Kami menerapkan teknik scaling, seperti Min-Max Scaling atau Standardization, sehingga nilai-nilai dari kedua fitur utama ([a] dan [b]) berada dalam rentang yang sebanding.  
  **Alasan:** Skala yang berbeda-beda pada fitur dapat membuat algoritma berbasis jarak (seperti KMeans atau Nearest Neighbors) menjadi bias pada fitur dengan rentang nilai yang lebih besar. Dengan melakukan scaling, model dapat mengukur jarak antar titik data secara adil.

- **Implementasi pada Notebook:**  
  Transformasi data dilakukan secara berurutan:
  1. Data dibaca dan divalidasi (cek format dan missing values).  
  2. Penghapusan duplikasi dan imputasi untuk missing values (jika diperlukan).  
  3. Konversi tipe data agar konsisten.  
  4. Ekstraksi fitur turunan (Difference (b - a)).  
  5. Scaling data menggunakan teknik normalisasi yang dipilih.
  
  Contoh kode untuk scaling:
  ```python
  from sklearn.preprocessing import StandardScaler
  scaler = StandardScaler()
  df_scaled = df_clean.copy()
  df_scaled[required_columns] = scaler.fit_transform(df_scaled[required_columns])

  # Lihat sampel data setelah scaling
  df_scaled[required_columns].head()
  ```
  
### 4. Alasan dan Manfaat Tahapan Data Preparation

- **Memastikan Kualitas Data:**  
  Setiap tahapan pembersihan dan transformasi bertujuan untuk mengurangi noise dan ketidakkonsistenan data, sehingga hasil analisis dan pemodelan dapat dipercaya.
  
- **Meningkatkan Efektivitas Model:**  
  Proses scaling dan normalisasi sangat krusial untuk algoritma berbasis jarak, sehingga model dapat mengukur kesamaan/pemisahan antar data secara lebih objektif.
  
- **Mempermudah Interpretasi Hasil:**  
  Dengan menyiapkan data yang bersih dan terstruktur, tahap eksplorasi data (EDA) dapat dilakukan dengan lebih mendalam, sehingga insight yang diperoleh lebih akurat dan bermanfaat untuk pengembangan sistem rekomendasi.

---

## Modeling and Result

Bagian ini mendokumentasikan proses pembuatan sistem rekomendasi yang dirancang untuk mengatasi masalah ketidakseimbangan antara penyediaan ruang terbuka dan tingkat akses di berbagai kota. Saya menyajikan dua pendekatan solusi rekomendasi menggunakan algoritma yang berbeda, serta menampilkan output top‑N recommendation sebagai hasil pemodelan.

---

### 1. Sistem Rekomendasi dengan Content‑Based Filtering

**a. Pendekatan dan Implementasi**  
Pendekatan content‑based filtering memanfaatkan fitur numerik yang telah disiapkan, yaitu:
- Persentase ruang terbuka ([a])  
- Tingkat akses ruang terbuka ([b])  
- Fitur turunan: **Difference (b - a)**  

Pada tahap ini, saya juga telah melakukan segmentasi data, dengan menggunakan KMeans atau teknik clustering lain, untuk mengelompokkan kota berdasarkan pola kemiripan fitur. Setelah itu, untuk setiap kota yang dimasukkan sebagai input, saya menghitung kemiripan (menggunakan metode Nearest Neighbors dengan Euclidean distance) antara kota tersebut dengan kota lainnya dalam cluster yang sama. Proses ini memastikan bahwa rekomendasi yang diberikan adalah kota-kota dengan karakteristik serupa.

Berikut contoh kode yang telah digunakan untuk menghasilkan top‑N recommendations:

```python
from sklearn.neighbors import NearestNeighbors
import numpy as np

def get_recommendations(input_city_code, n_recommendations=5):
    # Misalnya, City Code disimpan di df_clean
    target = df_clean[df_clean['City Code'] == input_city_code]
    if target.empty:
        print(f"Kota dengan kode {input_city_code} tidak ditemukan.")
        return
    # Pastikan indeks antara df_clean dan df_scaled sama
    target_index = target.index[0]
    target_features = features_for_clustering[target_index].reshape(1, -1)
    
    # Menggunakan cluster yang sudah didapat dari KMeans (misalnya, k = 2)
    target_cluster = kmeans.labels_[target_index]
    cluster_indices = np.where(kmeans.labels_ == target_cluster)[0]
    subset_features = features_for_clustering[cluster_indices]
    
    # Inisialisasi NearestNeighbors dan cari rekomendasi
    nn = NearestNeighbors(n_neighbors=n_recommendations+1, metric='euclidean')
    nn.fit(subset_features)
    distances, indices = nn.kneighbors(target_features)
    
    # Skip indeks pertama karena merupakan kota itu sendiri
    recommended_indices = cluster_indices[indices.flatten()][1:]
    recommendations = df_clean.iloc[recommended_indices]
    return recommendations[['City Name', 'Country or Territory Name', 
                            'Average share of the built-up area of cities that is open space for public use for all (%) [a]',
                            'Average share of urban population with convenient access to open public spaces (%) [b]']]

# Contoh penggunaan fungsi untuk mendapatkan top-5 rekomendasi
print("Rekomendasi untuk kota AF_KABUL:")
print(get_recommendations('AF_KABUL', n_recommendations=5))
```

**b. Kelebihan dan Kekurangan Content‑Based Filtering**  
*Keunggulan:*
- **Transparansi dan Interpretabilitas:** Rekomendasi dihasilkan berdasarkan kesamaan langsung fitur numerik yang mudah diinterpretasikan, sehingga mudah dijelaskan kepada pemangku kepentingan.
- **Tidak Memerlukan Data Interaksi:** Cocok untuk kondisi saat data umpan balik atau rating pengguna belum tersedia.

*Kekurangan:*
- **Over-specialization:** Rekomendasi cenderung menampilkan kota yang sangat mirip dengan input, sehingga kurang bervariasi.
- **Terbatas pada Fitur yang Tersedia:** Tidak menangkap aspek laten atau preferensi pengguna yang mungkin muncul dari data interaksi.

---

### 2. Sistem Rekomendasi dengan Collaborative Filtering (Opsional/Hybrid Model)

Meskipun data interaksi pengguna atau rating terhadap kota belum tersedia saat ini, saya menyertakan kerangka dasar pengembangan model hybrid sebagai solusi jangka panjang. Pendekatan ini menggabungkan dua informasi, yaitu konten kota (content-based) dan umpan balik pengguna (collaborative).

**a. Kerangka Dasar Hybrid Model**  
Kerangka dasar pengembangan hybrid model dapat dirancang sebagai berikut:

1. **Content-Based Filtering:**  
   Menggunakan fitur utama ([a] dan [b]) untuk menghitung similarity antar kota. Contoh, menggunakan cosine similarity:
   ```python
   from sklearn.metrics.pairwise import cosine_similarity
   content_similarity = cosine_similarity(df_scaled[required_columns])
   ```

2. **Collaborative Filtering:**  
   Ketika data ratings/feedback sudah tersedia, misalnya melalui sebuah matriks rating (baris = pengguna, kolom = kode kota), kita dapat menghitung similarity antar kota berdasarkan umpan balik pengguna menggunakan cosine similarity:
   ```python
   # Misalnya, ratings disimpan di DataFrame 'ratings'
   # collaborative_similarity = cosine_similarity(ratings.T)  # jika kolom menyangkut kota
   ```

3. **Penggabungan (Hybrid):**  
   Menggabungkan dua similarity dengan bobot tertentu, misalnya:
   ```python
   alpha = 0.5
   # hybrid_similarity = alpha * content_similarity + (1 - alpha) * collaborative_similarity
   ```
   Hasil hybrid similarity ini kemudian dapat digunakan untuk menghasilkan rekomendasi yang lebih bervariasi dan personal.

**b. Kelebihan dan Kekurangan Collaborative Filtering (Hybrid)**  
*Keunggulan:*
- **Personalisasi yang Lebih Tinggi:** Apabila didukung data interaksi, pendekatan ini bisa menangkap preferensi pengguna yang tidak terekspresikan secara eksplisit lewat fitur numerik.
- **Diversifikasi Rekomendasi:** Dapat merekomendasikan kota yang tidak hanya serupa secara konten tetapi juga relevan berdasarkan pola interaksi pengguna.

*Kekurangan:*
- **Ketergantungan Data:** Pendekatan ini membutuhkan data rating yang lengkap dan berkualitas. Pada kondisi awal, saat data tersebut belum tersedia, model collaborative filtering tidak dapat diimplementasikan secara optimal.
- **Cold-Start Problem:** Untuk entitas atau pengguna baru, tidak ada data interaksi yang cukup, sehingga rekomendasi berdasarkan collaborative filtering mungkin kurang akurat.

---

### 3. Top-N Recommendation sebagai Output

Berikut adalah ringkasan hasil output rekomendasi menggunakan metode content‑based filtering (solusi yang telah diimplementasikan):

- **Contoh Output untuk Kota "AF_KABUL":**
  - **Rekomendasi:**
    - Kabul, Afghanistan  
    - Tabuk, Saudi Arabia  
    - Butwal, Nepal  
    - Eldoret, Kenya  
    - Irbid, Jordan  

Output ini menunjukkan bahwa sistem berhasil mengelompokkan kota dengan pola yang serupa dalam hal penyediaan ruang terbuka dan akses, sehingga memberikan rekomendasi kota yang dapat dijadikan benchmark untuk intervensi kebijakan.

---

### 4. Ringkasan Evaluasi Model

- **Kualitas Clustering:**  
  Evaluasi awal menggunakan metrik Silhouette Score untuk clustering menunjukkan nilai sekitar 0.38, yang mengindikasikan pengelompokan moderat. Walaupun belum optimal, langkah-langkah tuning parameter dan penambahan fitur tambahan diharapkan dapat meningkatkan performa.

- **Efektivitas Rekomendasi:**  
  Hasil top‑N rekomendasi memberikan gambaran bahwa kota-kota yang direkomendasikan memiliki kemiripan signifikan berdasarkan fitur [a] dan [b]. Pendekatan hybrid (jika data tersedia) nantinya akan meningkatkan personalisasi rekomendasi.

---

### Kesimpulan Modeling and Result

Dalam proyek ini, saya telah mengembangkan dua solusi rekomendasi untuk menyelesaikan permasalahan ketidakseimbangan antara ruang terbuka dan aksesibilitas di kota-kota urban:
- **Content-Based Filtering:**  
  Sudah diimplementasikan dan menghasilkan rekomendasi berbasis kemiripan numerik, dengan keunggulan dalam transparansi dan interpretabilitas.
- **Collaborative Filtering (Hybrid Model – Opsional):**  
  Merupakan kerangka dasar yang siap dikembangkan ketika data rating/feedback tersedia, berpotensi meningkatkan personalisasi rekomendasi.

Dengan kedua pendekatan tersebut, sistem rekomendasi dapat digunakan sebagai alat pendukung pengambilan kebijakan dalam perencanaan ruang terbuka secara lebih berbasis data. Langkah selanjutnya adalah melakukan validasi lebih mendalam, tuning parameter model, dan mengumpulkan data interaksi untuk mengembangkan solusi hybrid yang utuh.

---

## Evaluation

### 1. Metrik Evaluasi yang Digunakan

Dalam proyek ini, saya menggunakan beberapa metrik evaluasi yang sesuai dengan konteks data, permasalahan (problem statement), dan solusi yang diinginkan. Metrik utama yang saya gunakan adalah:

- **Silhouette Score:**  
  Metrik ini digunakan untuk mengevaluasi kualitas pengelompokan (clustering) yang dilakukan pada data.  
  - **Rumus:**  
    Untuk setiap titik data \( i \), Silhouette Score dihitung dengan rumus:
     
    $$
    \[
    s(i) = \frac{b(i) - a(i)}{\max\{a(i), b(i)\}}
    \]
    $$
    
    di mana:  
    - \( a(i) \) adalah jarak rata-rata dari titik \( i \) ke semua titik lain dalam cluster yang sama (intra-cluster distance).  
    - \( b(i) \) adalah jarak rata-rata dari titik \( i \) ke semua titik di cluster terdekat yang berbeda (inter-cluster distance).  
  - **Interpretasi:**  
    Nilai Silhouette Score berkisar antara -1 hingga 1. Nilai yang mendekati 1 menunjukkan bahwa titik data tersebut berada jauh dari cluster lain, sehingga clustering berkualitas tinggi. Nilai mendekati 0 menunjukkan adanya tumpang tindih antar cluster, sedangkan nilai negatif mengindikasikan bahwa titik data mungkin salah diklaster.
  
- **Top-N Recommendation Evaluation (secara konseptual):**  
  Meskipun proyek ini berfokus utama pada pengembangan sistem rekomendasi dengan content‑based filtering, evaluasi output rekomendasi juga diperlukan untuk mengukur relevansi rekomendasi.  
  - **Metrik yang Umum Digunakan (untuk konteks rekomendasi):**  
    **Precision@N** dan **Recall@N**.  
    - **Precision@N:** Ukuran berapa proporsi item yang direkomendasikan yang benar-benar relevan.  
    - **Recall@N:** Proporsi item relevan yang berhasil direkomendasikan dari keseluruhan item relevan.
  - **Catatan:**  
    Karena data umpan balik atau rating pengguna belum tersedia, evaluasi rekomendasi saat ini dilakukan secara kualitatif melalui analisis kesamaan fitur antar kota. Namun, metrik evaluasi ini dapat diintegrasikan ketika data interaksi telah tersedia.

### 2. Hasil Evaluasi Berdasarkan Metrik

- **Evaluasi Clustering dengan Silhouette Score:**  
  Setelah melakukan clustering (dengan KMeans), saya menghitung Silhouette Score untuk menilai keterpisahan antar cluster.  
  - **Contoh Hasil:**  
    Pada salah satu eksperimen model KMeans, didapatkan nilai Silhouette Score sebesar 0.38.  
  - **Interpretasi Hasil:**  
    - Nilai 0.38 mengindikasikan bahwa struktur clustering yang terbentuk bersifat moderat. Meskipun terdapat pemisahan antar cluster, masih ada beberapa titik data yang berada di perbatasan, menunjukkan bahwa peningkatan pada pemilahan cluster (misalnya melalui penambahan fitur atau tuning parameter) dapat memberikan hasil yang lebih kompak.
  - **Implikasi terhadap Problem Statement:**  
    Hasil ini sejalan dengan pernyataan masalah, yang menunjukkan adanya ketidakseimbangan antara penyediaan ruang terbuka dan akses. Pengelompokan yang moderat juga mendukung tujuan untuk mengidentifikasi kota-kota yang memiliki karakteristik serupa sehingga intervensi atau benchmark bisa disusun lebih tepat.

- **Evaluasi Rekomendasi (Top-N):**  
  Dengan menggunakan pendekatan content‑based filtering, sistem rekomendasi menghasilkan output top‑N (misalnya, top-5 rekomendasi) untuk tiap kota.  
  - **Analisa Hasil:**  
    Rekomendasi yang diberikan (untuk kota "AF_KABUL" atau "AL_TIRANE") menunjukkan kecenderungan untuk mengelompokkan kota dengan nilai fitur [a] dan [b] yang hampir serupa.  
  - **Validasi Kualitatif:**  
    Analisis mendalam terhadap output rekomendasi mendukung bahwa kota-kota yang direkomendasikan memiliki kesamaan dalam distribusi ruang terbuka dan akses, yang secara konseptual memenuhi tujuan sistem rekomendasi.  
  - **Rencana Evaluasi Lanjutan:**  
    Ketika data interaksi atau umpan balik dari pengguna tersedia, evaluasi menggunakan metrik Precision@N dan Recall@N akan dilakukan untuk mengukur relevansi dan efektivitas rekomendasi secara kuantitatif.

### 3. Kelebihan dan Keterbatasan Metrik Evaluasi

- **Kelebihan:**
  - **Silhouette Score:**  
    Memberikan ukuran yang jelas dan kuantitatif mengenai kualitas clustering tanpa memerlukan label ground truth. Hal ini sangat sesuai untuk evaluasi unsupervised learning.
  - **Top-N Recommendation Metrics (Secara Konseptual):**  
    Metrik-metrik seperti Precision@N dan Recall@N membantu mengevaluasi relevansi output sistem rekomendasi secara praktis dan dapat mengarahkan perbaikan sistem ketika data interaksi sudah tersedia.

- **Keterbatasan:**
  - **Silhouette Score:**  
    Meskipun memberikan gambaran umum, skor ini tidak sepenuhnya menangkap konteks domain dan dapat terpengaruh oleh keputusan parameter dalam clustering.
  - **Evaluasi Rekomendasi:**  
    Tanpa data umpan balik pengguna, evaluasi rekomendasi hanya bersifat kualitatif. Model collaborative filtering dan metrik rekomendasi kuantitatif (Precision@N, Recall@N) akan lebih informatif ketika data rating tersedia.

---

### 4. Kesimpulan Evaluasi

Secara keseluruhan, evaluasi menggunakan Silhouette Score menunjukkan bahwa model clustering memiliki kualitas sedang (misalnya, skor 0.38) yang mendukung segmentasi awal kota berdasarkan fitur ruang terbuka dan aksesibilitas. Evaluasi top‑N rekomendasi secara kualitatif juga mendukung bahwa sistem sudah mampu mengidentifikasi kota-kota yang serupa, sekaligus membuka peluang untuk pengembangan sistem rekomendasi hybrid ketika data interaksi telah terakumulasi. Dengan demikian, metrik evaluasi yang digunakan tidak hanya relevan dengan konteks data dan masalah yang dihadapi, tetapi juga memberikan arahan jelas untuk perbaikan dan pengembangan lebih lanjut.

---

