# 🌱 Klasifikasi Tingkat Stres Tanaman untuk Sistem Irigasi Pintar Berbasis Alat Komparasi Algoritma dengan Penyeimbangan SMOTE dan Seleksi Fitur Chi-Square

Repositori ini berisi implementasi kode dan dokumentasi penelitian mengenai **klasifikasi tingkat stres hidrasi tanaman** menggunakan pendekatan _Supervised Machine Learning_. Penelitian ini bertujuan mendukung sistem **Smart Irrigation** melalui klasifikasi kondisi tanaman berdasarkan data sensor lingkungan.

---

## 👥 Kontributor

- **Thariq Fadhlurrahman**  
  _Informatics Student, Universitas Muhammadiyah Malang_
- **Muhammad Daffa Maulana Billah**
- **Rajwaa Rindu Izzany**

---

# 📌 Ringkasan Penelitian

Salah satu tantangan utama dalam pertanian modern adalah inefisiensi penggunaan air akibat sistem irigasi yang masih bergantung pada jadwal tetap maupun pengamatan manual.

Penelitian ini mengembangkan model klasifikasi tingkat stres hidrasi tanaman menggunakan pendekatan **data mining** berbasis **Supervised Learning** untuk mengelompokkan kondisi tanaman ke dalam tiga kelas, yaitu:

- 🟢 **Kelas 0** : Normal
- 🟡 **Kelas 1** : Stres Ringan
- 🔴 **Kelas 2** : Stres Berat

Dataset yang digunakan terdiri dari **543.210 observasi** hasil pencatatan sensor lingkungan pertanian (_Agro-Environmental Dataset_). Sebelum proses pelatihan model dilakukan beberapa tahapan prapemrosesan, meliputi:

- Penghapusan atribut penyebab **data leakage**
- Standarisasi data teks
- Label Encoding
- Normalisasi menggunakan **MinMaxScaler**
- Penyeimbangan kelas menggunakan **SMOTE**
- Seleksi fitur menggunakan **Chi-Square**

Penelitian membandingkan dua algoritma klasifikasi, yaitu:

- Decision Tree (CART)
- Gaussian Naive Bayes

Pengujian dilakukan pada **8 skenario eksperimen** untuk mengetahui pengaruh SMOTE dan seleksi fitur terhadap performa model.

---

# 📂 Struktur Repository

```text
├── data/
│   └── agro_environmental_dataset.csv
│
├── notebooks/
│   └── *.ipynb
│
├── reports/
│   └── figures/
│
└── README.md
```

---

# 📊 Dataset

Dataset berasal dari **Kaggle** dengan nama:

> **Agro-Environmental Dataset**

Dataset berisi data telemetri sensor IoT pada lingkungan pertanian.

Jumlah data:

- **543.210 observasi**

---

# 📑 Fitur yang Digunakan

## Fitur Fisik dan Kimia Tanah

- soil_type
- bulk_density
- organic_matter_pct
- cation_exchange_capacity
- salinity_ec
- buffering_capacity
- moisture_regime
- soil_temp_c
- soil_ph

## Fitur Nutrisi Tanah

- nitrogen_ppm
- phosphorus_ppm
- potassium_ppm
- nutrient_balance

## Fitur Iklim Mikro

- air_temp_c
- thermal_regime
- light_intensity_par
- plant_category

---

# ⚙️ Data Preprocessing

Tahapan preprocessing yang dilakukan meliputi:

1. Menghapus atribut penyebab **Data Leakage**
   - `location_id`
   - `failure_flag`
   - `suitability_score`

2. Standarisasi teks
   - Uppercase
   - Trim whitespace

3. Label Encoding

4. Normalisasi menggunakan **MinMaxScaler**

5. Penyeimbangan kelas menggunakan **SMOTE**

6. Seleksi fitur menggunakan **Chi-Square**

---

# 🤖 Algoritma yang Digunakan

- Decision Tree (CART)
- Gaussian Naive Bayes

---

# 📈 Hasil Eksperimen Terbaik

Performa terbaik diperoleh pada:

### Decision Tree + SMOTE (Baseline)

| Metric    | Nilai      |
| --------- | ---------- |
| Accuracy  | **82.30%** |
| Precision | **82.68%** |
| Recall    | **85.08%** |
| F1-Score  | **82.78%** |

---

# 📊 Perbandingan Seluruh Skenario

| No  | Kondisi Data          | Model             | Accuracy   | Precision  | Recall     | F1-Score   |
| --- | --------------------- | ----------------- | ---------- | ---------- | ---------- | ---------- |
| 1   | Baseline (No SMOTE)   | Decision Tree     | 82.22%     | 83.56%     | 81.99%     | 82.68%     |
| 2   | Baseline (No SMOTE)   | Naive Bayes       | 62.81%     | 62.94%     | 65.99%     | 63.03%     |
| 3   | Baseline (SMOTE)      | **Decision Tree** | **82.30%** | **82.68%** | **85.08%** | **82.78%** |
| 4   | Baseline (SMOTE)      | Naive Bayes       | 60.71%     | 62.22%     | 65.67%     | 60.55%     |
| 5   | Chi-Square (No SMOTE) | Decision Tree     | 81.08%     | 83.10%     | 80.54%     | 81.48%     |
| 6   | Chi-Square (No SMOTE) | Naive Bayes       | 59.78%     | 59.57%     | 63.13%     | 59.92%     |
| 7   | Chi-Square (SMOTE)    | Decision Tree     | 81.04%     | 81.38%     | 83.28%     | 81.55%     |
| 8   | Chi-Square (SMOTE)    | Naive Bayes       | 59.47%     | 60.24%     | 63.91%     | 59.36%     |

---

# 🛠️ Instalasi

Clone repository:

```bash
git clone https://github.com/Wickleyy/Klasifikasi-Tingkat-Stres-Tanaman-untuk-Sistem-Irigasi-Pintar
cd Klasifikasi-Tingkat-Stres-Tanaman-untuk-Sistem-Irigasi-Pintar
```

Install seluruh dependency:

```bash
pip install -r requirements.txt
```

Atau install secara manual:

```bash
pip install pandas numpy scikit-learn imbalanced-learn matplotlib seaborn
```

---

# ▶️ Cara Menjalankan

1. Buka folder **notebooks/**
2. Jalankan menggunakan:
   - Google Colab
   - Jupyter Notebook
3. Sesuaikan path dataset.
4. Jalankan seluruh sel (_Run All_).

---

# 📌 Metodologi Penelitian

```text
Dataset
      │
      ▼
Data Cleaning
      │
      ▼
Text Standardization
      │
      ▼
Label Encoding
      │
      ▼
Normalization
      │
      ▼
Train-Test Split
      │
      ▼
SMOTE
      │
      ▼
Chi-Square Feature Selection
      │
      ▼
Decision Tree & Naive Bayes
      │
      ▼
Evaluation
```

---

# 🏆 Kesimpulan

- Decision Tree memberikan performa terbaik dibandingkan Gaussian Naive Bayes pada seluruh skenario pengujian.
- Penerapan **SMOTE** meningkatkan kemampuan model dalam mengenali seluruh kelas secara lebih seimbang.
- Seleksi fitur menggunakan **Chi-Square** berhasil mengurangi jumlah fitur tanpa penurunan performa yang signifikan.
- Model terbaik memperoleh **Accuracy sebesar 82,30%** dengan **Recall 85,08%**, sehingga layak digunakan sebagai dasar pengambilan keputusan pada sistem irigasi presisi.

---

## 📄 Lisensi

Repositori ini dibuat untuk keperluan penelitian akademik dan pengembangan ilmu pengetahuan.

---

⭐ Jika repository ini bermanfaat, jangan lupa berikan **Star** di GitHub.
