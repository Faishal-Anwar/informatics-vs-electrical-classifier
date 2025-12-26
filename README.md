# Klasifikasi Judul Skripsi: Teknik Informatika vs Teknik Elektro

## 👥 Tim Pengembang (Kelompok 1)
Proyek ini dikembangkan oleh:
- **Faishal Anwar Hasyim**
- **Alif Naufal Adani**
- **Akhmad Syaifudin**
- **Faizal Imam Syafangat**
- **Bintang Bimantara Putra**

---

## 📖 Deskripsi Proyek
Proyek ini bertujuan untuk membangun sistem **klasifikasi teks otomatis** untuk membedakan judul skripsi atau jurnal akademik ke dalam dua kategori jurusan: **Teknik Informatika** dan **Teknik Elektro**.

Seringkali terjadi ambiguitas antara topik berbasis perangkat lunak (*software/data*) dan perangkat keras (*hardware/kelistrikan*). Sistem ini menggunakan pendekatan **Machine Learning** dengan algoritma **K-Nearest Neighbors (KNN)** yang dioptimalkan dengan **TF-IDF N-Gram** dan metode pelabelan otomatis berbasis kamus (*Lexicon-based Auto Labeling*) untuk mengatasi masalah tersebut.

---

## 🎯 Tujuan (Objective)
Proyek ini dirancang untuk:
1.  **Otomatisasi Kategori:** Menggantikan proses pemilahan manual judul penelitian di repositori kampus.
2.  **Analisis Pola Semantik:** Memahami pola kata kunci yang membedakan topik Informatika (e.g., *Mining, Android, Algoritma*) dengan Elektro (e.g., *Tegangan, PLC, Mikrokontroler*).
3.  **Akurasi Tinggi:** Mencapai klasifikasi yang presisi menggunakan optimasi *hyperparameter* (pencarian nilai K terbaik).

---

## ⚙️ Teknologi & Metodologi

### 1. **Natural Language Processing (NLP)**
- **Preprocessing Ketat:** Pembersihan teks menggunakan Regex, penanganan singkatan akademik (*slangwords*), dan *stopword removal* (menggunakan pustaka **Sastrawi**).
- **Smart Labeling (Auto-Label):** Sistem pelabelan otomatis menggunakan **Kamus Data Berbobot** (*Weighted Dictionary*) untuk menentukan label awal (*Ground Truth*) yang akurat, lengkap dengan logika *tie-breaker* untuk judul yang ambigu.
- **Feature Extraction:** Menggunakan **TF-IDF Vectorizer** dengan **N-Gram (1,2)** untuk menangkap konteks frasa (contoh: membedakan "Sistem Informasi" vs "Sistem Kendali").

### 2. **Machine Learning Model**
- **Algoritma:** K-Nearest Neighbors (KNN) dengan metrik *Euclidean*.
- **Hyperparameter Tuning:** Melakukan pencarian otomatis nilai **K terbaik** (dari K=1 s.d K=30) untuk mendapatkan *Error Rate* terendah.
- **Evaluasi:** Menggunakan Confusion Matrix, Classification Report, dan ROC Curve.

### 3. **Visualisasi Data**
- **WordCloud:** Memvisualisasikan kata-kata paling dominan di jurusan Informatika vs Elektro.
- **Matplotlib & Seaborn:** Visualisasi grafik *Error Rate vs K Value* dan *ROC Curve*.

---

## 📊 Hasil Analisis

Proyek ini menghasilkan model yang mampu membedakan nuansa topik dengan baik.
- **Best K:** Nilai K optimal ditemukan pada **K=20** (menandakan model stabil dan tidak *overfitting*).
- **Akurasi:** Model mampu mencapai akurasi tinggi pada data uji.
- **ROC Curve:** Menunjukkan kemampuan separasi kelas yang sangat baik (Area Under Curve mendekati 1.0).

*(Anda dapat menambahkan screenshot grafik Error Rate atau WordCloud dari notebook Anda di sini)*

---

## 🛠️ Cara Menjalankan Proyek Ini

### 1. Clone Repository
```bash
git clone https://github.com/Faishal-Anwar/informatics-vs-electrical-classifie.git
cd Discord-Sentiment-Analysis

#### 2. Buat Virtual Environment
Sangat disarankan untuk menggunakan virtual environment agar dependensi proyek tidak bercampur dengan instalasi Python global Anda.
```bash
virtualenv venv
```

#### 3. Aktifkan Virtual Environment
```bash
venv\Scripts\activate
```
macOS/Linux:
```bash
source venv/bin/activate
```
Setelah aktif, nama environment (venv) akan muncul di awal baris terminal Anda.

#### 4. Instal Dependensi
Instal semua pustaka Python yang dibutuhkan yang tercantum dalam file requirements.txt.
```bash
pip install -r requirements.txt
```

#### 5. Jalankan Jupyter Notebook
Setelah semua dependensi terinstal, jalankan server Jupyter Notebook.
```bash
jupyter notebook
```
Perintah ini akan membuka tab baru di browser web Anda. Dari sana, navigasikan dan buka file notebook.ipynb untuk menjalankan kode.
