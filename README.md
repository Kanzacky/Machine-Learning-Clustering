# Machine Learning: Clustering (Dry Bean Dataset)

Repository ini berisi implementasi dari Modul 4 Machine Learning yang berfokus pada teknik **Clustering** (Unsupervised Learning). Studi kasus yang digunakan dalam proyek ini adalah segmentasi morfologi biji kacang kering menggunakan dataset **Dry Bean Dataset**.

## 📖 Deskripsi Studi Kasus

Dataset ini berisi **13.611 data biji kacang kering** dari 7 varietas berbeda (SEKER, BARBUNYA, BOMBAY, CALI, DERMASON, HOROZ, SIRA). Data diambil menggunakan kamera beresolusi tinggi, di mana dari citra tersebut diekstraksi **16 fitur morfologi** fisik seperti area, perimeter, panjang sumbu (axis length), kelingkaran (circularity), dan sebagainya.

**Tujuan Proyek:**  
Mengelompokkan biji kacang berdasarkan karakteristik morfologi fisiknya secara **unsupervised** menggunakan algoritma **K-Means Clustering** tanpa menggunakan label kelas (varietas aslinya). Proyek ini juga bertujuan menganalisis apakah cluster yang terbentuk secara otomatis oleh K-Means berkorelasi dengan varietas biji kacang yang sebenarnya.

---

## 📂 Struktur Repositori

- `machine_learning_clustering_drybean.ipynb`: Notebook utama berisi seluruh alur kerja mulai dari pemuatan data, eksplorasi, pembersihan, scaling, clustering, evaluasi, hingga penyimpanan model.
- `Dry_Bean_Dataset.xlsx`: Dataset mentah yang digunakan untuk proses clustering.
- `.venv/`: Virtual environment Python untuk menjaga dependensi project agar terisolasi.

---

## 🛠️ Teknologi dan Library yang Digunakan

Proyek ini dibangun menggunakan bahasa pemrograman Python. Berikut adalah pustaka (library) utama yang diperlukan:
- **Data Manipulation:** `numpy`, `pandas`
- **Data Visualization:** `matplotlib`, `seaborn`
- **Machine Learning:** `scikit-learn`
  - `StandardScaler` (untuk Feature Scaling)
  - `KMeans` (Algoritma Clustering)
  - `silhouette_score`, `davies_bouldin_score`, `calinski_harabasz_score` (Metrik Evaluasi Model)
- **Model Deployment/Saving:** `joblib`

---

## ⚙️ Tahapan Analisis (Workflow)

Di dalam Jupyter Notebook, analisis dilakukan secara terstruktur melalui tahapan berikut:

1. **Import Library:** Memuat semua library yang dibutuhkan untuk komputasi.
2. **Persiapan Dataset:** Memuat file Excel `Dry_Bean_Dataset.xlsx` dan melakukan eksplorasi data awal (EDA).
3. **Data Cleaning:** Menangani missing values dan data duplikat agar model lebih robust.
4. **Pemilihan Fitur untuk Clustering:** Memilih fitur morfologi yang relevan tanpa memasukkan label kelas/varietas.
5. **Scaling Fitur:** Menggunakan `StandardScaler` untuk menyamakan skala distribusi fitur morfologi yang bervariasi (misalnya: 'Area' dengan satuan puluhan ribu vs 'ShapeFactor' dengan skala nol koma).
6. **Clustering dengan K-Means:**
   - Eksplorasi centroid dan inersia K-Means.
   - Penggunaan **Elbow Method** untuk mencari nilai parameter $K$ yang optimal.
   - Implementasi final K-Means dengan nilai optimum.
   - Visualisasi scatter plot cluster.
7. **Evaluasi Model Clustering:** Mengevaluasi kinerja clustering menggunakan _Silhouette Score_, _Davies-Bouldin Index_, dan _Calinski-Harabasz Score_.
8. **Analisis Cluster:** Melakukan _profiling_ karakteristik morfologi untuk masing-masing klaster dan membandingkannya dengan varietas asli.
9. **Simpan Model:** Menyimpan model K-Means yang sudah dilatih dengan `joblib` (`.pkl`) untuk kebutuhan deployment atau inferensi di masa depan.
10. **Interpretasi dan Kesimpulan:** Menyimpulkan insight yang diperoleh dari hasil pemodelan.

---

## 🚀 Cara Menjalankan Proyek

1. **Clone repositori atau unduh folder ini.**
2. **Aktifkan Virtual Environment:**
   - Linux/macOS: `source .venv/bin/activate`
   - Windows: `.venv\Scripts\activate`
3. **Install Dependensi** (Jika belum tersedia, silakan install library yang diperlukan):
   ```bash
   pip install numpy pandas matplotlib seaborn scikit-learn openpyxl joblib jupyter
   ```
4. **Jalankan Jupyter Notebook:**
   ```bash
   jupyter notebook
   ```
5. Buka file `machine_learning_clustering_drybean.ipynb` dan jalankan cell (Shift + Enter) secara berurutan.

---

## 📌 Sumber Data
Dataset diambil dari **UCI Machine Learning Repository** (ID: 602).  
[Link Dataset Dry Bean](https://archive.ics.uci.edu/dataset/602/dry+bean+dataset)
