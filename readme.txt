README Proyek Pemodelan Bank Marketing Campaign
Deskripsi Proyek
Proyek ini bertujuan untuk membangun model Machine Learning yang dapat memprediksi apakah seorang nasabah akan membuka term deposit (kelas yes atau no) berdasarkan data kampanye pemasaran bank. Model utama yang digunakan adalah XGBoost, karena memberikan performa terbaik dibanding model lain.

Tahapan Pemodelan
Eksplorasi Data

Analisis distribusi kelas, hubungan antar fitur, dan outliers.
Hasil Dataset memiliki distribusi kelas yang seimbang (~52% kelas 0 dan ~48% kelas 1).
Data Preprocessing

Penanganan Missing Value
Fitur numerik diisi dengan nilai rata-rata.
Fitur kategorikal diisi dengan modus.
One-Hot Encoding
Fitur kategorikal seperti housing, loan, contact, dan poutcome dikonversi menjadi representasi numerik.
Feature Engineering
Fitur tambahan seperti job_encoded dan month_encoded dibuat berdasarkan frekuensi kategori.
Scaling
Semua fitur numerik diskalakan menggunakan teknik standar untuk meningkatkan performa model.
Pemilihan Model

Model yang Dicoba
Logistic Regression
Random Forest
XGBoost
Alasan Memilih XGBoost
Performa terbaik pada validasi silang dan skor metrik.
Mampu menangani hubungan non-linear dengan baik.
Hyperparameter Tuning

Dilakukan dengan GridSearchCV untuk mengoptimalkan parameter seperti
learning_rate, max_depth, n_estimators, dan subsample.
Hasil tuning meningkatkan akurasi model secara signifikan.
Evaluasi Model

Metrik yang Digunakan
Accuracy, Precision, Recall, F1-Score, dan ROC-AUC.
Hasil Akhir
XGBoost menunjukkan performa terbaik dengan rata-rata akurasi ~85% pada validasi silang.
Prediksi Data Aktual

Model dideploy menggunakan pickle dan diuji pada data aktual.
Data diproses dengan preprocessing yang sama seperti pada data pelatihan.
Hasil prediksi disimpan ke file CSV untuk analisis lebih lanjut.
File dan Struktur
xgboost_model.pkl

File model XGBoost yang telah dilatih dan disimpan.
sample_with_predictions.csv

Data aktual dengan prediksi dari model XGBoost.
Kode Utama

preprocess_actual_data Fungsi untuk preprocessing data aktual.
xgboost_model.predict Digunakan untuk prediksi pada data aktual.
README.md

Penjelasan singkat tentang proyek ini.
Cara Menggunakan
Prediksi dengan Model

Pastikan file xgboost_model.pkl tersedia.
Jalankan kode preprocessing dan prediksi.
Hasil prediksi akan disimpan di file CSV.
Analisis Prediksi

Periksa kolom XGBoost_Prediction pada file hasil untuk melihat apakah nasabah akan membuka term deposit.
Rekomendasi untuk Bisnis
Nasabah Potensial
Fokuskan kampanye pada nasabah dengan hasil prediksi yes untuk meningkatkan peluang konversi.
Optimalisasi Waktu Kampanye
Berdasarkan fitur penting seperti month_encoded, sesuaikan kampanye pada bulan-bulan dengan tingkat keberhasilan tinggi.