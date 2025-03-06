## **Deskripsi**
Proyek ini bertujuan untuk menerapkan kecerdasan buatan (AI) dalam analisis penjualan alat tulis. Sistem akan membantu dalam pencatatan data, analisis pola penjualan, dan memberikan rekomendasi restock berdasarkan data yang dikumpulkan. Dengan menggunakan teknik *machine learning*, proyek ini akan meningkatkan efisiensi pengelolaan stok di toko alat tulis.

## **Instruksi Cara Menjalankan Kode**
1. **Persiapan Lingkungan**
   - Pastikan Anda memiliki Python terinstal.
   - Instal pustaka yang dibutuhkan dengan perintah berikut:
     ```bash
     pip install pandas numpy scikit-learn matplotlib
     ```

2. **Menyiapkan Data**
   - Kode akan membuat dataset penjualan alat tulis dalam format CSV secara otomatis.
   - File CSV akan disimpan dengan nama `data_penjualan_alattulis.csv`.

3. **Membaca dan Membersihkan Data**
   - Data dari file CSV akan dibaca menggunakan *pandas*.
   - Pengecekan dilakukan untuk memastikan tidak ada data kosong.
   - Konversi format tanggal dilakukan agar sesuai dengan analisis.

4. **Transformasi Data**
   - Kolom baru *Total Penjualan* dan *Keuntungan* akan ditambahkan berdasarkan perhitungan:
     - `Total Penjualan = Jumlah Terjual × Harga Satuan`
     - `Keuntungan = Total Penjualan - (Jumlah Terjual × 10.000)`

5. **Pelatihan Model AI**
   - Data dipisahkan menjadi *training set* (80%) dan *testing set* (20%).
   - *Decision Tree Classifier* digunakan untuk memprediksi apakah stok produk perlu di-restock.
   - Model dievaluasi menggunakan *accuracy_score*.

6. **Prediksi Restock Produk**
   - Model akan memprediksi apakah suatu produk perlu di-restock berdasarkan jumlah terjual dan stok yang tersisa.

7. **Visualisasi Data**
   - Data divisualisasikan menggunakan *Matplotlib* dengan *scatter plot* untuk melihat hubungan antara jumlah terjual, stok, dan keuntungan.

8. **Menjalankan Program**
   - Jalankan kode Python menggunakan perintah:
     ```bash
     python nama_file.py
     ```
   - Program akan menampilkan analisis data, hasil prediksi restock, serta grafik hubungan penjualan dan stok.
