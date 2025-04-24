# Tahapan Pembuatan Model Klasifikasi dengan Decision Tree
Berikut adalah penjabaran setiap tahapan menggunakan kalimat naratif dari proses pembuatan model klasifikasi menggunakan algoritma **Decision Tree**.

## 1. Mengimpor Library
Langkah pertama adalah mengimpor berbagai library Python yang dibutuhkan. Library `pandas` digunakan untuk manipulasi data, `sklearn` digunakan untuk preprocessing, pembuatan model, pembagian data, dan evaluasi performa model, sedangkan `matplotlib.pyplot` digunakan untuk membuat visualisasi pohon keputusan.

## 2. Memuat Dataset
Dataset dimuat dari file `dataset.csv` menggunakan fungsi `pd.read_csv()` dan disimpan dalam sebuah DataFrame bernama `df`. Data ini berisi informasi mengenai atribut-atribut seseorang seperti usia, penghasilan, status mahasiswa, dan riwayat kredit, serta apakah orang tersebut membeli komputer atau tidak.

## 3. Melihat Informasi Awal Dataset
Data yang telah dimuat kemudian diperiksa dengan `df.head()` untuk menampilkan beberapa baris awal, serta `df.info()` untuk melihat jumlah data, tipe data setiap kolom, dan mendeteksi apakah ada nilai yang hilang.

## 4. Pra-pemrosesan Data (Label Encoding)
Karena algoritma Decision Tree memerlukan input dalam bentuk numerik, maka semua fitur kategori seperti usia, pendapatan, status mahasiswa, dan riwayat kredit diubah menjadi angka menggunakan `LabelEncoder` dari library `sklearn.preprocessing`.

## 5. Memisahkan Fitur dan Label
Setelah proses encoding selesai, fitur (variabel input) dipisahkan dari label (target). Fitur disimpan dalam variabel `X`, yaitu seluruh kolom kecuali `Buys_Computer`, sedangkan label disimpan dalam `y`, yaitu kolom `Buys_Computer`.

## 6. Membagi Dataset Menjadi Data Latih dan Uji
Dataset kemudian dibagi menjadi dua bagian, yaitu 80% untuk pelatihan dan 20% untuk pengujian. Pembagian dilakukan menggunakan fungsi `train_test_split()` dengan `random_state=42` agar hasil pembagian konsisten setiap kali dijalankan.

## 7. Membangun dan Melatih Model Decision Tree
Sebuah model klasifikasi dibuat menggunakan `DecisionTreeClassifier` dengan parameter `criterion='entropy'`, yang berarti model akan menggunakan informasi entropy untuk menentukan pemisahan. Model ini kemudian dilatih menggunakan data latih dengan fungsi `fit()`.

## 8. Melakukan Prediksi dan Evaluasi Model
Setelah model dilatih, data uji digunakan untuk menguji performa model dengan fungsi `predict()`. Hasil prediksi kemudian dievaluasi menggunakan metrik akurasi, confusion matrix, dan classification report. Ini bertujuan untuk mengukur sejauh mana model dapat memprediksi dengan benar.

## 9. Visualisasi Pohon Keputusan
Pohon keputusan yang telah dibangun divisualisasikan menggunakan fungsi `plot_tree()` dari `sklearn.tree`. Visualisasi ini membantu untuk memahami bagaimana model mengambil keputusan berdasarkan nilai fitur.

## 10. Menampilkan Struktur Pohon dalam Bentuk Teks
Sebagai tambahan dari visualisasi grafis, struktur pohon juga ditampilkan dalam bentuk teks menggunakan fungsi `export_text()`. Ini menunjukkan secara hierarkis bagaimana cabang dan simpul pohon dibentuk, serta kondisi yang digunakan untuk membagi data.
