# Gold-Price-Forecasting-using-LSTM-GRU

## 1. Project Overview

Harga emas merupakan salah satu komoditas global yang penting dan sering digunakan sebagai instrumen lindung nilai (hedging) maupun investasi. Namun pergerakan harga emas sangat volatil karena dipengaruhi oleh berbagai faktor, seperti kondisi ekonomi makro, suku bunga, geopolitik, dan sentimen pasar.

Model tradisional seperti ARIMA sulit menangkap non-linearitas pada data harga emas. Oleh karena itu, proyek ini menggunakan pendekatan Deep Learning dengan model LSTM dan GRU untuk memprediksi harga emas secara lebih akurat.

---

## 2. Tujuan Proyek

1. Mengimplementasikan model LSTM dan GRU untuk forecasting harga emas.
2. Membandingkan performa kedua model berdasarkan:
   - MSE  
   - RMSE  
   - MAE  
   - MAPE  
   - R² Score  
3. Menentukan model terbaik berdasarkan evaluasi kuantitatif dan visualisasi hasil.
4. Melakukan forecasting harga emas untuk 30 hari ke depan.

---

## 3. Repository Structure

```

gold-price-forecasting/
│
├── README.md                → Dokumentasi project
├── presentation.pdf         → Slide presentasi Mini Project
├── gold_lstm_gru.ipynb      → Implementasi model LSTM & GRU
└── images/                  → Visualisasi hasil (opsional)
```

---

## 4. Dataset

- Sumber: Yahoo Finance  
- Ticker: GC=F (Gold Futures — COMEX)  
- Periode: 2005–2024  
- Jumlah data: ±5025 entri  
- Fitur yang digunakan: Close (harga penutupan)  
- Sequence length: 60 hari  
- Train/Test split: 80% train — 20% test  
- Normalisasi: MinMaxScaler  

---

## 5. Metodologi

### a. Preprocessing
- Mengisi missing values menggunakan forward fill.  
- Normalisasi data menggunakan MinMaxScaler.  
- Membentuk sequence sepanjang 60 hari sebagai input model.  

### b. Arsitektur Model

#### LSTM Model
- Tiga layer LSTM (50 units)
- Dropout 0.2 pada setiap layer
- Dense layer (25 units → 1 output)
- Loss function: Mean Squared Error (MSE)
- Optimizer: Adam (learning rate 0.001)

#### GRU Model
- Tiga layer GRU (50 units)
- Dropout 0.2
- Dense layer (25 units → 1 output)
- Loss function: MSE
- Optimizer: Adam

---

## 6. Hasil Eksperimen

### Evaluasi Kuantitatif (Test Set)

| Model | RMSE | MAE | R² | MAPE |
|-------|------|------|------|--------|
| LSTM | 159.99 | 135.49 | 0.6605 | 6.70% |
| GRU  | 121.90 | 111.42 | 0.8029 | 5.67% |

### Analisis Residual
- GRU memiliki residual yang lebih kecil dan lebih terpusat.
- LSTM menunjukkan fluktuasi residual lebih besar.
- GRU lebih stabil dalam generalisasi pada dataset.

### Forecasting 30 Hari ke Depan
- GRU menghasilkan prediksi yang lebih halus dan realistis.
- LSTM cenderung menghasilkan prediksi yang lebih fluktuatif.


---

## 8. Cara Menjalankan Notebook

1. Clone repository ini:
```

git clone [https://github.com/username/gold-price-forecasting.git](https://github.com/username/gold-price-forecasting.git)

```

2. Install dependencies:
```

pip install -r requirements.txt

```

3. Jalankan notebook:
```

jupyter notebook gold_lstm_gru.ipynb

```

Notebook akan:
- Mengunduh dataset dari Yahoo Finance  
- Melakukan preprocessing  
- Melatih model  
- Menampilkan visualisasi dan hasil  

---


Berisi:
- Latar belakang  
- Metodologi  
- Arsitektur model  
- Hasil eksperimen  
- Evaluasi dan kesimpulan  

---

## 10. Kesimpulan

- Model GRU memberikan performa terbaik dibanding LSTM.  
- GRU memiliki RMSE lebih rendah, MAE lebih rendah, MAPE lebih kecil, dan R² lebih tinggi.  
- GRU juga lebih efisien secara parameter dan lebih stabil pada data harga emas.  
- Untuk forecasting harga emas pada dataset ini, GRU merupakan pilihan model yang lebih baik.

---

## 11. Anggota Kelompok

- Kosmas Rio Legowo  
- Bagus Cipta Pratama  
- Muhammad Hanif Zuhair  
- Muhammad Akmal Fauzan  
- Muhammad Irsyad Hannan  

---
