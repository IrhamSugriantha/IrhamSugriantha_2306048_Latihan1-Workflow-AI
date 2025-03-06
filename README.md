# Praktikum_AI_Workflow

## Deskripsi Singkat
Proyek ini bertujuan untuk menerapkan kecerdasan buatan (AI) dalam menganalisis data penjualan toko alat tulis. Dengan memanfaatkan teknik machine learning, sistem akan membantu dalam mengevaluasi tren penjualan, mengidentifikasi produk yang perlu di-restock, dan memberikan wawasan berbasis data untuk pengambilan keputusan yang lebih baik.

## Instruksi Cara Menjalankan Kode
1. **Persiapan Data**
   - Pastikan Anda memiliki dataset penjualan alat tulis dalam format CSV.
   - Contoh data terdiri dari 50 transaksi dengan 10 jenis produk alat tulis.
   - Upload file CSV ke Google Colab atau jalankan di lingkungan Python lokal.

2. **Menginstal dan Mengimpor Library yang Dibutuhkan**
   ```python
   import pandas as pd
   import numpy as np
   import matplotlib.pyplot as plt
   from sklearn.model_selection import train_test_split
   from sklearn.tree import DecisionTreeClassifier
   from sklearn.metrics import accuracy_score
   ```

3. **Membaca dan Memproses Data**
   ```python
   df = pd.read_csv("data_penjualan_alat_tulis.csv")
   df["Tanggal"] = pd.to_datetime(df["Tanggal"])
   df["Total Penjualan"] = df["Jumlah Terjual"] * df["Harga Satuan"]
   df["Keuntungan"] = df["Total Penjualan"] - (df["Jumlah Terjual"] * 10000)
   ```

4. **Pelatihan Model AI**
   ```python
   X = df[["Jumlah Terjual", "Stok"]]
   y = (df["Stok"] < 5).astype(int)
   X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)
   model = DecisionTreeClassifier()
   model.fit(X_train, y_train)
   y_pred = model.predict(X_test)
   print("Akurasi Model:", accuracy_score(y_test, y_pred))
   ```

5. **Visualisasi Data**
   ```python
   plt.scatter(df["Jumlah Terjual"], df["Stok"], c=df["Keuntungan"], cmap="coolwarm")
   plt.xlabel("Jumlah Terjual")
   plt.ylabel("Stok")
   plt.title("Analisis Penjualan dan Stok Alat Tulis")
   plt.colorbar(label="Keuntungan")
   plt.show()
