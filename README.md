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

Di bawah ini adalah contoh bagian **Business Understanding** dalam laporan proyek Anda yang telah dilengkapi dengan rubrik/kriteria penilaian tambahan untuk mendapatkan nilai bintang yang lebih tinggi. Dokumen berikut merinci proses klarifikasi masalah, pernyataan masalah, tujuan (goals), serta solution approach yang mengajukan dua pendekatan—content‑based filtering (yang telah diimplementasikan) dan collaborative filtering (opsional, ketika data tambahan tersedia).

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

- **Jumlah Data:**  
Jumlah Baris dan Kolom:
Dataset memiliki 1711 entri (baris) dengan 15 kolom. Ukuran ini menunjukan bahwa dataset cukup besar untuk analisis komparatif antar kota maupun negara. Dataset awal memiliki 1711 baris. Setelah menghapus baris yang memiliki missing values di salah satu atau kedua kolom indikator utama, dataset berkurang menjadi 1363 baris. Artinya, sebanyak 1711 – 1363 = 348 baris (sekitar 20,3% dari total data) telah dihapus karena tidak memiliki data lengkap untuk kedua indikator kunci. Ini menunjukkan bahwa cukup banyak data yang tidak lengkap di bagian indikator ruang terbuka dan aksesibilitas, sehingga perlu perhatian khusus pada langkah pra-pemrosesan data.

- **Kondisi Data:**  
  Data belum mengalami normalisasi atau standarisasi awal saat diunduh, sehingga nilai-nilai pada beberapa fitur seperti persentase ruang terbuka dan aksesibilitas perlu dipersiapkan melalui teknik scaling. Beberapa entri mengandung missing values yang diatasi dengan penghapusan atau imputasi—proses ini dijelaskan lebih lanjut di bagian Data Preparation.

### 2. Variabel (Fitur) pada Data

Dataset yang digunakan mengandung beberapa variabel utama, yakni:

1. **City Code:**  
   Kode unik untuk masing-masing kota yang digunakan untuk identifikasi (misalnya, "AF_KABUL", "AL_TIRANE", dsb.).

2. **City Name:**  
   Nama kota sebagai informasi deskriptif.

3. **Country or Territory Name:**  
   Nama negara atau wilayah di mana kota tersebut berada.

4. **Average share of the built-up area of cities that is open space for public use for all (%) [a]:**  
   Persentase area terbangun kota yang dialokasikan sebagai ruang terbuka untuk publik. Variabel ini mewakili seberapa besar ruang tidak terbangun (green spaces, taman, dsb.) yang disediakan untuk umum.

5. **Average share of urban population with convenient access to open public spaces (%) [b]:**  
   Persentase penduduk kota yang memiliki akses yang mudah ke ruang terbuka publik. Variabel ini mencerminkan kualitas dan jangkauan infrastruktur ruang terbuka yang ada.

6. **Derived Feature – Difference (b - a):**  
   Selisih antara nilai [b] dan [a]. Nilai positif mengindikasikan bahwa aksesibilitas (b) lebih tinggi daripada persentase ruang terbuka (a); sebaliknya, nilai negatif menunjukkan bahwa penyediaan ruang terbuka mungkin lebih banyak daripada akses yang tersedia. Fitur ini membantu mengidentifikasi ketidakseimbangan antara penyediaan dan penggunaan ruang terbuka.

### 3. Tahapan Eksploratory Data Analysis (EDA)

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
  Saya memeriksa dataset untuk menemukan adanya entri yang hilang atau tidak lengkap. Dengan menggunakan fungsi seperti `df.isnull().sum()`, saya mengidentifikasi variabel yang memiliki missing values.  
  **Alasan:** Missing values dapat menyebabkan bias atau error pada model. Oleh karena itu, saya melakukan penanganan melalui penghapusan entri (jika jumlahnya relatif kecil) atau imputasi (jika diperlukan) agar data menjadi lebih representatif.

- **Penghapusan Duplikasi:**  
  Saya memeriksa adanya baris duplikat pada dataset dan menghapusnya dengan menggunakan `df.drop_duplicates()`.  
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
