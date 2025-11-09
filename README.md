# 🛍️ Online Retail Analysis & Forecasting

## 📘 Pengertian Proyek
Proyek ini bertujuan untuk **menganalisis perilaku pelanggan dan memprediksi pendapatan masa depan** berdasarkan data transaksi e-commerce. Analisis mencakup **RFM segmentation**, **K-Means clustering**, serta **perbandingan model forecasting (ARIMA vs Prophet)** untuk mengidentifikasi pola penjualan dan tren bisnis.

---

## 📖 Deskripsi Proyek
Analisis dilakukan menggunakan dataset *Online Retail* dari UCI Machine Learning Repository. Proyek ini berfokus pada tiga aspek utama:
1. **Exploratory Data Analysis (EDA)** untuk memahami karakteristik data penjualan.
2. **Customer Segmentation (RFM + Clustering)** untuk mengelompokkan pelanggan berdasarkan perilaku pembelian.
3. **Revenue Forecasting** menggunakan dua pendekatan model time series — **ARIMA** dan **Prophet** — untuk memperkirakan pendapatan enam bulan ke depan.

---

## 🗂️ Dataset
- **Nama:** Online Retail Dataset  
- **Sumber:** [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/online+retail)
- **Deskripsi:** Berisi transaksi dari sebuah perusahaan retail Inggris pada tahun 2010–2011.
- **Jumlah Data:** 541.909 baris dan 8 kolom.
- **Fitur Utama:**
  - `InvoiceNo` – Nomor faktur transaksi  
  - `StockCode` – Kode produk  
  - `Description` – Deskripsi produk  
  - `Quantity` – Jumlah barang  
  - `InvoiceDate` – Tanggal transaksi  
  - `UnitPrice` – Harga per unit  
  - `CustomerID` – ID pelanggan  
  - `Country` – Negara asal pembeli

---

## ⚙️ Tools dan Teknologi
| Kategori | Teknologi |
|-----------|------------|
| Bahasa Pemrograman | Python 3 |
| Data Processing | Pandas, NumPy |
| Visualisasi | Matplotlib, Seaborn |
| Machine Learning | Scikit-learn |
| Time Series | Statsmodels, pmdarima, Prophet |
| Analisis & Modeling | ARIMA, K-Means Clustering |
| Lingkungan | Jupyter Notebook / Kaggle Notebook |

---

## 🔍 Tahapan Analisis

### 1️⃣ Data Preparation
- Menghapus data kosong & duplikat.  
- Menghapus transaksi tidak valid (`Quantity <= 0`, `UnitPrice <= 0`).  
- Menambahkan kolom baru:  
  - `Revenue = Quantity × UnitPrice`  
  - `Month`, `Year` untuk analisis temporal.

### 2️⃣ Exploratory Data Analysis (EDA)
- **Statistik Deskriptif** untuk memahami sebaran data.  
- **Top Produk & Negara Terlaris** berdasarkan total penjualan.  
- **Tren Bulanan** dan **jumlah transaksi per bulan**.  
- **Heatmap korelasi** antar variabel numerik.  
- **Analisis Outlier** pada variabel `Revenue` dan `Quantity`.

### 3️⃣ RFM Analysis & Clustering
- **RFM Metrics:**
  - *Recency* → waktu sejak pembelian terakhir.
  - *Frequency* → frekuensi transaksi.
  - *Monetary* → total pengeluaran pelanggan.
- **Clustering dengan K-Means** (k = 4) untuk segmentasi pelanggan.
- **Hasil Segmentasi:**
  - Cluster 2 → VIP Customers (nilai transaksi tertinggi).
  - Cluster 1 → Loyal High Spenders.
  - Cluster 3 → Regular Buyers.
  - Cluster 0 → Inactive Customers.

### 4️⃣ Revenue Forecasting
Perbandingan dua model untuk memprediksi pendapatan 6 bulan ke depan:
- **ARIMA (AutoRegressive Integrated Moving Average)**
- **Prophet (Meta/Facebook Prophet)**  

Langkah:
1. Mengonversi data transaksi menjadi agregasi bulanan.
2. Split data menjadi train (80%) dan test (20%).
3. Melatih model dan menghasilkan prediksi jangka pendek.
4. Visualisasi tren dan hasil perbandingan kedua model.

### 5️⃣ Evaluasi Model
Metrik yang digunakan:
- **MAE (Mean Absolute Error)**
- **MSE (Mean Squared Error)**
- **RMSE (Root Mean Squared Error)**
- **MAPE (Mean Absolute Percentage Error)**

📊 **Hasil Evaluasi:**
| Model | MAE | RMSE | MAPE | Keterangan |
|--------|------|-------|-------|-------------|
| ARIMA | 219,530 | 285,753 | 23.30% | ✅ Akurat dan stabil |
| Prophet | 1,118,559 | 1,322,004 | 167.45% | ❌ Fluktuatif dan kurang stabil |

**Kesimpulan Evaluasi:**  
Model **ARIMA** memiliki performa terbaik dengan error terkecil dan hasil prediksi paling realistis untuk dataset ini.

---

## 📈 Hasil Akhir Analisis
- Total **pendapatan perusahaan**: £8.88 juta dari **18532 transaksi unik**.
- **Negara dengan revenue tertinggi:** United Kingdom.
- **Top Produk Terlaris:** *Paper Craft, Little Birdie*.
- **Segmen pelanggan:** 4 cluster dengan profil berbeda.
- **Model Forecasting terbaik:** ARIMA (lebih stabil dan presisi).

---

## 💡 Insight dan Manfaat
- Pelanggan terbagi menjadi beberapa segmen yang bisa ditargetkan secara strategis.
- Pola penjualan menunjukkan peningkatan signifikan menjelang akhir tahun (musim liburan).
- Model ARIMA dapat digunakan untuk **perencanaan stok, budgeting, dan strategi pemasaran** jangka pendek.
- Prophet cocok digunakan bila dataset menunjukkan **pola musiman jangka panjang** setelah pembersihan data lebih lanjut.

---

## 🧾 Kesimpulan Akhir
Proyek ini berhasil:
1. Melakukan **data cleaning dan eksplorasi mendalam** terhadap transaksi e-commerce.
2. Mengidentifikasi **segmen pelanggan utama** dengan metode **RFM + K-Means**.
3. Melakukan **forecasting pendapatan bulanan** menggunakan dua pendekatan model.
4. Menunjukkan bahwa **ARIMA outperform Prophet** pada dataset ini.  

Secara keseluruhan, analisis ini dapat menjadi dasar dalam **pengambilan keputusan bisnis berbasis data (data-driven decision making)** di sektor e-commerce.

---

### ✨ Author
**Rehana Putri**  
*Online Retail Analysis & Forecasting Project*  
📅 2025  
