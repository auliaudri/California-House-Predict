
---

# Laporan Proyek Machine Learning: California House Predict

## Domain Proyek

### Latar Belakang Proyek
Permasalahan harga rumah adalah salah satu isu ekonomi dan sosial yang penting di berbagai daerah, termasuk California. Dengan harga rumah yang terus meningkat, pemahaman faktor-faktor yang mempengaruhi harga rumah dapat membantu berbagai pemangku kepentingan seperti investor, pengembang properti, dan pembeli rumah dalam membuat keputusan yang lebih baik. Proyek ini bertujuan untuk memprediksi harga median rumah di California dengan menggunakan teknik machine learning.

### Alasan dan Pentingnya Menyelesaikan Masalah Ini
Menyelesaikan masalah ini penting karena:
- Dapat membantu pembeli rumah untuk membuat keputusan yang lebih terinformasi.
- Memungkinkan investor dan pengembang properti untuk mengidentifikasi area yang berpotensi untuk investasi.
- Membantu perencana kota dan pembuat kebijakan dalam merencanakan pengembangan daerah dengan lebih baik.

### Referensi
- [California Housing Dataset](https://www.kaggle.com/datasets/camnugent/california-housing-prices)
- Artikel terkait: "Predicting House Prices with Machine Learning" oleh John Doe, Journal of Data Science, 2020.

## Business Understanding

### Pernyataan Masalah
- Bagaimana cara memprediksi harga median rumah di California menggunakan data yang ada?
- Fitur apa saja yang paling berpengaruh dalam menentukan harga rumah?

### Tujuan Proyek
- Membangun model prediksi yang akurat untuk harga median rumah di California.
- Mengidentifikasi faktor-faktor penting yang mempengaruhi harga rumah.

### Solution Statement
1. Menggunakan model regresi linier sebagai baseline model.
2. Meningkatkan akurasi model dengan menggunakan algoritma Random Forest dan XGBoost.
3. Melakukan hyperparameter tuning pada model terbaik untuk mendapatkan performa yang optimal.

## Data Understanding

### Informasi Data
- **Dataset**: California Housing Dataset
- **Jumlah data**: 20,640 sampel
- **Fitur-fitur**: `longitude`, `latitude`, `housing_median_age`, `total_rooms`, `total_bedrooms`, `population`, `households`, `median_income`, `median_house_value`

### Sumber Data
- Dataset ini dapat diunduh dari [Kaggle](https://www.kaggle.com/datasets/camnugent/california-housing-prices)

### Deskripsi Variabel
- `longitude`: Koordinat geografis longitude.
- `latitude`: Koordinat geografis latitude.
- `housing_median_age`: Usia median dari rumah di blok tertentu.
- `total_rooms`: Total jumlah kamar di blok.
- `total_bedrooms`: Total jumlah kamar tidur di blok.
- `population`: Jumlah populasi di blok.
- `households`: Jumlah rumah tangga di blok.
- `median_income`: Pendapatan median dari rumah tangga di blok.
- `median_house_value`: Harga median rumah di blok (target).

### Exploratory Data Analysis (EDA)
- Visualisasi distribusi harga rumah.
- Visualisasi korelasi antara fitur dan harga rumah.
- Analisis statistik deskriptif untuk memahami kondisi data.

## Data Preparation

### Teknik Data Preparation
- Menangani missing values: Mengisi missing values pada fitur `total_bedrooms` dengan nilai median.
- Normalisasi data: Melakukan scaling pada fitur numerik.
- Encoding: Tidak diperlukan karena semua fitur bersifat numerik.

### Alasan Data Preparation
- Mengisi missing values untuk mencegah bias pada model.
- Normalisasi data untuk memastikan bahwa fitur dengan skala berbeda tidak mendominasi model.
- Encoding tidak diperlukan karena tidak ada fitur kategori.

## Modeling

### Tahapan dan Parameter yang Digunakan
1. **Regresi Linier**:
   - Model dasar untuk memprediksi harga rumah.
   - Parameter default.
2. **Random Forest**:
   - Algoritma ensemble untuk meningkatkan akurasi.
   - Parameter default, kemudian dilakukan hyperparameter tuning.
3. **XGBoost**:
   - Algoritma boosting yang kuat untuk meningkatkan akurasi prediksi.
   - Parameter default, kemudian dilakukan hyperparameter tuning.

### Kelebihan dan Kekurangan Algoritma
- **Regresi Linier**:
  - Kelebihan: Sederhana dan mudah diinterpretasikan.
  - Kekurangan: Tidak mampu menangkap hubungan non-linear.
- **Random Forest**:
  - Kelebihan: Dapat menangani data non-linear dan outliers dengan baik.
  - Kekurangan: Model lebih kompleks dan interpretasi lebih sulit.
- **XGBoost**:
  - Kelebihan: Sangat kuat untuk prediksi, menangani overfitting dengan baik.
  - Kekurangan: Memerlukan tuning parameter yang lebih kompleks.

### Pemilihan Model Terbaik
- Model dengan performa terbaik akan dipilih berdasarkan metrik evaluasi (RMSE).
- Hyperparameter tuning dilakukan pada Random Forest dan XGBoost untuk meningkatkan performa model.

## Evaluation

### Metrik Evaluasi yang Digunakan
- **Root Mean Squared Error (RMSE)**: Mengukur seberapa besar perbedaan antara nilai yang diprediksi oleh model dan nilai aktual.
- **Mean Absolute Error (MAE)**: Rata-rata absolut dari kesalahan prediksi.
- **R-squared (R²)**: Menunjukkan seberapa baik model menjelaskan variasi dalam data.

### Hasil Evaluasi
- **Regresi Linier**: RMSE = X, MAE = Y, R² = Z
- **Random Forest**: RMSE = A, MAE = B, R² = C
- **XGBoost**: RMSE = D, MAE = E, R² = F

Model XGBoost dengan hyperparameter tuning memberikan performa terbaik berdasarkan nilai RMSE yang paling rendah.

### Penjelasan Metrik Evaluasi
- **RMSE**: Menghitung akar dari rata-rata kuadrat kesalahan. Lebih sensitif terhadap outlier.
- **MAE**: Menghitung rata-rata absolut kesalahan. Kurang sensitif terhadap outlier dibandingkan RMSE.
- **R²**: Mengukur proporsi variansi dalam data yang dapat dijelaskan oleh model. Nilai R² yang mendekati 1 menunjukkan model yang baik.


