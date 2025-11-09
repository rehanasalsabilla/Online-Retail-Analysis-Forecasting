# 🛍️ Online Retail Analysis & Forecasting

## 📘 Pengertian Proyek
Proyek ini bertujuan untuk **menganalisis perilaku pelanggan dan memprediksi pendapatan masa depan** menggunakan dataset *Online Retail* dari UCI Machine Learning Repository.  
Analisis mencakup **pola penjualan**, **perilaku pelanggan**, **kontribusi produk dan negara**, **identifikasi pelanggan bernilai tinggi**, serta **forecasting pendapatan masa depan** menggunakan model *ARIMA* dan *Prophet*.

---

## 📖 Deskripsi Proyek
Proyek ini merupakan studi komprehensif terhadap data transaksi e-commerce yang dilakukan oleh perusahaan retail Inggris pada periode **Desember 2010 – Desember 2011**.  
Tujuannya adalah untuk menemukan wawasan strategis terkait performa bisnis dan membantu perusahaan dalam **pengambilan keputusan berbasis data (data-driven decision making)**.  

Analisis mencakup:
1. Eksplorasi data transaksi untuk memahami perilaku pembelian pelanggan.  
2. Segmentasi pelanggan dengan **RFM (Recency, Frequency, Monetary)** dan **K-Means Clustering**.  
3. Prediksi pendapatan masa depan menggunakan **ARIMA dan Prophet** untuk memahami arah tren penjualan.

---

## 🗂️ Dataset
- **Sumber:** [UCI Machine Learning Repository – Online Retail Dataset](https://archive.ics.uci.edu/ml/datasets/online+retail)  
- **Periode Data:** 1 Desember 2010 – 9 Desember 2011  
- **Jumlah Data:** 541.909 transaksi  
- **Fitur Utama:**
  - `InvoiceNo` — Nomor transaksi  
  - `StockCode` — Kode produk  
  - `Description` — Deskripsi produk  
  - `Quantity` — Jumlah produk  
  - `InvoiceDate` — Tanggal transaksi  
  - `UnitPrice` — Harga per unit  
  - `CustomerID` — ID pelanggan  
  - `Country` — Negara asal pelanggan  

---

## ⚙️ Tools dan Teknologi
| Kategori | Teknologi |
|-----------|------------|
| Bahasa Pemrograman | Python 3 |
| Analisis Data | Pandas, NumPy |
| Visualisasi | Matplotlib, Seaborn |
| Segmentasi & Clustering | Scikit-learn (K-Means) |
| Time Series Forecasting | Statsmodels (ARIMA), Prophet |
| Evaluasi Model | MAPE, MAE, RMSE |
| Lingkungan Eksekusi | Jupyter Notebook / Kaggle |

---

## 🔍 Tahapan Analisis

### 1️⃣ Data Preparation
- Menghapus data duplikat dan nilai kosong pada kolom `CustomerID`.  
- Menghapus transaksi tidak valid (`Quantity ≤ 0`, `UnitPrice ≤ 0`).  
- Menambahkan kolom baru:
  - `Revenue = Quantity × UnitPrice`
  - Ekstraksi bulan dan tahun dari `InvoiceDate` untuk analisis temporal.

---

### 2️⃣ Exploratory Data Analysis (EDA)
Analisis deskriptif dan visual dilakukan untuk memahami karakteristik data.

- **Distribusi Transaksi per Bulan:**  
  Aktivitas penjualan meningkat signifikan menjelang **akhir tahun (November–Desember)** yang mengindikasikan adanya efek *seasonality* seperti liburan dan promosi akhir tahun.

- **Negara Dominan:**  
  Sebagian besar transaksi berasal dari **United Kingdom** dengan lebih dari **85% kontribusi total penjualan**, menunjukkan fokus bisnis pada pasar domestik.

- **Top Produk Terlaris:**  
  Produk **“Paper Craft, Little Birdie”** memiliki kontribusi revenue tertinggi, disusul produk dekorasi rumah kecil dan mainan anak.

- **Pola Penjualan:**  
  Pola penjualan menunjukkan tren **fluktuatif namun meningkat menjelang akhir tahun**, dengan lonjakan besar pada Q4.

---

### 3️⃣ RFM Analysis dan Clustering
Analisis RFM digunakan untuk memahami perilaku pelanggan:
- **Recency** → waktu sejak pembelian terakhir.  
- **Frequency** → jumlah transaksi yang dilakukan.  
- **Monetary** → total uang yang dibelanjakan.

Hasil segmentasi dengan **K-Means (k=4)** menghasilkan empat kelompok pelanggan:
| Cluster | Karakteristik | Deskripsi |
|----------|----------------|------------|
| 0 | Inactive Customers | Pelanggan jarang berbelanja dan nilai belanja rendah |
| 1 | Loyal High Spenders | Pelanggan sering membeli dengan nilai transaksi tinggi |
| 2 | VIP Customers | Kontributor utama terhadap revenue perusahaan |
| 3 | Regular Buyers | Pembeli aktif dengan nilai moderat |

📈 **Cluster 2 (VIP Customers)** diidentifikasi sebagai pelanggan paling bernilai karena memiliki nilai *monetary* tertinggi dan tingkat pembelian berulang.

---

### 4️⃣ Forecasting Analysis (Analisis Peramalan)

#### 🔹 Pertanyaan 1:
**Bagaimana pola penjualan dan perilaku pelanggan dalam dataset Online Retail selama periode observasi?**  
Pola penjualan menunjukkan peningkatan yang signifikan menjelang akhir tahun, terutama pada bulan November dan Desember.  
Perilaku pelanggan bersifat *seasonal*, dengan peningkatan frekuensi pembelian di periode liburan.  
Pelanggan VIP memberikan kontribusi utama terhadap total pendapatan tahunan.

#### 🔹 Pertanyaan 2:
**Produk apa yang memiliki kontribusi penjualan tertinggi, dan negara mana yang paling dominan dalam transaksi?**  
Produk **“Paper Craft, Little Birdie”** memberikan kontribusi tertinggi terhadap total penjualan, diikuti oleh produk dekoratif kecil dan aksesoris rumah.  
Negara dengan transaksi terbanyak dan revenue tertinggi adalah **United Kingdom**, diikuti oleh **Netherlands** dan **EIRE** (Irlandia).

#### 🔹 Pertanyaan 3:
**Siapa pelanggan yang paling bernilai (loyal dan berkontribusi besar terhadap revenue)?**  
Berdasarkan hasil RFM dan K-Means, **Cluster 2 (VIP Customers)** merupakan pelanggan paling bernilai dengan rata-rata pembelian tinggi, frekuensi transaksi sering, dan *recency* rendah.  
Mereka memberikan kontribusi lebih dari **40% total revenue**.

#### 🔹 Pertanyaan 4:
**Bagaimana tren pendapatan per bulan, dan bagaimana perkiraan pendapatan untuk periode mendatang (forecasting)?**

- **Tren Pendapatan:**  
  Revenue bulanan meningkat tajam di akhir tahun, terutama pada Q4 2011, menunjukkan adanya **seasonal demand**.  
  Pola ini penting untuk strategi stok dan promosi.

- **Model Peramalan:**  
  Dua model digunakan:  
  - **ARIMA (AutoRegressive Integrated Moving Average)**  
  - **Prophet (Facebook Prophet)**  

  Hasil evaluasi:
  | Model | MAE | RMSE | MAPE | Akurasi |
  |--------|------|-------|-------|----------|
  | ARIMA | 219,530 | 285,753 | 23.30% | ✅ Stabil dan akurat |
  | Prophet | 1,118,559 | 1,322,004 | 167.45% | ❌ Tidak stabil |

  **ARIMA** menunjukkan performa terbaik dengan error terkecil dan hasil prediksi paling realistis.  
  Prediksi menunjukkan **penurunan ringan di awal tahun** setelah puncak penjualan Desember, kemudian **kembali stabil di pertengahan tahun**.  
  Hal ini mencerminkan **pola musiman alami** pada industri ritel.

---

## 📊 Hasil Akhir Analisis
- Total **pendapatan perusahaan**: £8.88 juta dari **18532 transaksi unik**.  
- **Negara dominan:** United Kingdom (kontribusi >85%).  
- **Produk terlaris:** Paper Craft, Little Birdie.  
- **Pelanggan paling bernilai:** Cluster 2 (VIP Customers).  
- **Model forecasting terbaik:** ARIMA, dengan error terendah dan prediksi stabil.

---

## 💡 Insight dan Manfaat
- Perusahaan memiliki basis pelanggan yang kuat di Inggris, dengan potensi ekspansi internasional.  
- Adanya **musim penjualan (seasonal pattern)** di Q4 membuka peluang untuk strategi promosi tahunan.  
- Segmentasi RFM membantu **menargetkan pelanggan bernilai tinggi** dengan strategi loyalitas khusus.  
- Model forecasting ARIMA memberikan dasar kuat untuk **perencanaan stok dan strategi pemasaran jangka pendek.**

---

## 🧾 Kesimpulan Akhir
Proyek **Online Retail Analysis & Forecasting** berhasil memberikan pemahaman mendalam mengenai:
1. **Pola penjualan dan perilaku pelanggan** secara temporal.  
2. **Identifikasi pelanggan utama dan produk unggulan.**  
3. **Prediksi pendapatan masa depan** dengan model ARIMA yang terbukti efektif.  

Hasil analisis ini dapat digunakan oleh perusahaan untuk:
- **Optimasi strategi pemasaran berbasis data.**
- **Manajemen persediaan berdasarkan pola musiman.**
- **Peningkatan retensi pelanggan bernilai tinggi.**

---

### ✨ Author
**Rehana Putri**  
📍 Institut Teknologi Sepuluh Nopember (ITS)  
📅 Tahun: 2025  
💼 Bidang: Data Analytics & Forecasting
