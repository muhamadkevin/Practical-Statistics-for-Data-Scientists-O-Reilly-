# Practical Statistics for Data Scientists — Bab 1–4

| | |
|---|---|
| **Nama** | Muhamad Kevin |
| **NIM** | 101032300243 |
| **Kelas** | BS1TK-47-REG-G13 |

Repositori ini berisi rangkuman dan implementasi kode Python untuk **Bab 1 sampai Bab 4** dari buku *Practical Statistics for Data Scientists* (Peter Bruce, Andrew Bruce & Peter Gedeck, 2nd ed.). Setiap bab disajikan dalam satu Jupyter Notebook yang menggabungkan penjelasan konsep (Bahasa Indonesia) dengan contoh kode dan visualisasi.

---

## Daftar Isi

1. [Struktur Proyek](#struktur-proyek)
2. [Instalasi & Cara Menjalankan](#instalasi--cara-menjalankan)
3. [Bab 1 — Exploratory Data Analysis](#bab-1--exploratory-data-analysis-eda)
4. [Bab 2 — Data and Sampling Distributions](#bab-2--data-and-sampling-distributions)
5. [Bab 3 — Statistical Experiments and Significance Testing](#bab-3--statistical-experiments-and-significance-testing)
6. [Bab 4 — Regression and Prediction](#bab-4--regression-and-prediction)
7. [Dataset](#dataset)
8. [Referensi](#referensi)

---

## Struktur Proyek

```
DeepLearning/
├── README.md
└── notebooks/
    ├── 01_Exploratory_Data_Analysis.ipynb
    ├── 02_Data_and_Sampling_Distributions.ipynb
    ├── 03_Statistical_Experiments_and_Significance_Testing.ipynb
    ├── 04_Regression_and_Prediction.ipynb
    └── data/                 # dataset CSV yang dipakai di notebook
```

## Instalasi & Cara Menjalankan

```bash
pip install numpy pandas matplotlib seaborn scipy statsmodels scikit-learn jupyter
cd notebooks
jupyter notebook
```

Setiap notebook memakai fungsi `load()` yang membaca dataset dari folder `notebooks/data/`. Jika file tidak ditemukan secara lokal, data otomatis diunduh dari [repositori GitHub resmi buku](https://github.com/gedeck/practical-statistics-for-data-scientists).

---

## Bab 1 — Exploratory Data Analysis (EDA)

📓 [`01_Exploratory_Data_Analysis.ipynb`](notebooks/01_Exploratory_Data_Analysis.ipynb)

**EDA** adalah langkah pertama dalam setiap proyek data science: kita *melihat*, *meringkas*, dan *memvisualisasikan* data sebelum membuat model. Istilah ini dipopulerkan oleh John Tukey (1977).

**Materi:**
1. Elemen data terstruktur (numerik, kategorikal, biner, ordinal)
2. Data rektangular dengan pandas DataFrame
3. Estimasi lokasi — mean, median, trimmed mean, weighted mean & weighted median
4. Estimasi variabilitas — variance, standard deviation, IQR, MAD
5. Mengeksplorasi distribusi data — boxplot, frequency table, histogram, density plot
6. Mengeksplorasi data biner & kategorikal — mode, expected value, bar chart
7. Korelasi — koefisien korelasi, correlation matrix, scatterplot
8. Mengeksplorasi dua variabel atau lebih — hexagonal binning, contour, contingency table, boxplot/violin plot, faceting

**Rangkuman:**
- EDA adalah fondasi setiap proyek data: selalu **lihat datanya** sebelum membuat model.
- Kenali **tipe data** karena menentukan analisis yang cocok.
- **Lokasi**: mean mudah dihitung tapi sensitif outlier; median & trimmed mean lebih **robust**.
- **Variabilitas**: std & variance paling umum; IQR & MAD lebih robust.
- **Korelasi** hanya mengukur hubungan **linear**; selalu cek dengan scatterplot.

---

## Bab 2 — Data and Sampling Distributions

📓 [`02_Data_and_Sampling_Distributions.ipynb`](notebooks/02_Data_and_Sampling_Distributions.ipynb)

Di era big data, **sampling** tetap penting. Data yang kita punya hampir selalu hanyalah **sampel** dari **populasi** yang lebih besar.

**Materi:**
1. Random sampling & sample bias
2. Selection bias & regression to the mean
3. Sampling distribution, Central Limit Theorem & standard error
4. Bootstrap
5. Confidence interval
6. Distribusi normal & QQ-plot
7. Distribusi long-tailed
8. Distribusi Student's t
9. Distribusi binomial
10. Distribusi chi-square & F
11. Distribusi Poisson, eksponensial & Weibull

**Rangkuman:**
- **Random sampling** mengurangi bias; kualitas data > kuantitas data.
- Waspadai **selection bias**, data snooping, dan **regression to the mean**.
- Menurut **Central Limit Theorem**, distribusi mean sampel cenderung normal.
- **Standard error** = $s/\sqrt{n}$; turun seiring akar n.
- **Bootstrap** adalah cara serbaguna tanpa asumsi distribusi untuk mengestimasi SE dan **confidence interval**.
- Distribusi normal penting untuk *statistik*, tetapi data mentah sering **long-tailed**.
- **t** untuk sampel kecil, **binomial** untuk jumlah sukses, **chi-square/F** untuk uji hipotesis, **Poisson/eksponensial/Weibull** untuk event dalam waktu.

---

## Bab 3 — Statistical Experiments and Significance Testing

📓 [`03_Statistical_Experiments_and_Significance_Testing.ipynb`](notebooks/03_Statistical_Experiments_and_Significance_Testing.ipynb)

**Desain eksperimen** adalah pilar praktik statistik untuk mengonfirmasi atau menolak sebuah hipotesis:

> Rumuskan hipotesis → Desain eksperimen → Kumpulkan data → Inferensi / kesimpulan

**Materi:**
1. A/B testing
2. Hypothesis test (null & alternative hypothesis, one-way vs two-way)
3. Resampling & permutation test
4. Statistical significance & p-value
5. t-test
6. Multiple testing (Bonferroni, FDR)
7. Degrees of freedom
8. ANOVA
9. Chi-square test & Fisher's exact test
10. Multi-arm bandit algorithm
11. Power & sample size

**Rangkuman:**
- **A/B test** dengan **randomization** adalah cara paling kuat untuk mengukur efek sebuah treatment.
- **Hypothesis test** melindungi kita dari tertipu keacakan; $H_0$ = tidak ada efek.
- **Permutation test** adalah cara intuitif & bebas asumsi untuk menguji signifikansi.
- **p-value** = probabilitas hasil seekstrem ini jika $H_0$ benar — **bukan** probabilitas $H_0$ benar.
- Banyak uji → **alpha inflation**; gunakan koreksi (Bonferroni, FDR) atau holdout data.
- **ANOVA** untuk >2 grup numerik; **chi-square** untuk data count; **Fisher's exact** untuk count kecil.
- **Multi-arm bandit** mengoptimalkan hasil *selama* eksperimen berlangsung.
- Hitung **power & sample size** sebelum memulai eksperimen.

---

## Bab 4 — Regression and Prediction

📓 [`04_Regression_and_Prediction.ipynb`](notebooks/04_Regression_and_Prediction.ipynb)

Pertanyaan utama: *Apakah variabel X berhubungan dengan Y, dan bisakah X dipakai untuk memprediksi Y?*

**Materi:**
1. Simple linear regression
2. Multiple linear regression
3. Menilai model (RMSE, R², t-statistic) & cross-validation
4. Model selection, stepwise regression & regularization (Ridge/Lasso)
5. Weighted regression
6. Prediksi: confidence interval vs prediction interval
7. Factor variables (dummy / reference coding)
8. Menginterpretasikan regresi — correlated predictors, multicollinearity, confounding, interaksi
9. Regression diagnostics — outlier, leverage, Cook's distance, heteroskedasticity, partial residual plot
10. Polynomial regression, spline & GAM

**Rangkuman:**
- **Regresi linear** memodelkan Y sebagai kombinasi linear prediktor, di-fit dengan **least squares**.
- Nilai model dengan **RMSE**, **R²**, dan terutama **cross-validation**.
- Pilih model dengan **AIC**/stepwise atau gunakan **regularization** (Ridge/Lasso).
- **Prediction interval** (individu) selalu lebih lebar dari **confidence interval** (rata-rata).
- Variabel kategorikal di-encode dengan **dummy/reference coding** (k−1 kolom).
- Hubungan non-linear dapat ditangkap dengan **polynomial**, **spline**, dan **GAM**.

---

## Dataset

| Bab | Dataset |
|---|---|
| 1 | `state.csv`, `dfw_airline.csv`, `airline_stats.csv`, `kc_tax.csv.gz`, `lc_loans.csv`, `sp500_data.csv.gz`, `sp500_sectors.csv` |
| 2 | `loans_income.csv`, `sp500_data.csv.gz` |
| 3 | `web_page_data.csv`, `four_sessions.csv`, `click_rates.csv` |
| 4 | `LungDisease.csv`, `house_sales.csv` |

## Library yang Digunakan

`numpy` · `pandas` · `matplotlib` · `seaborn` · `scipy` · `statsmodels` · `scikit-learn`

## Referensi

- Bruce, P., Bruce, A., & Gedeck, P. (2020). *Practical Statistics for Data Scientists: 50+ Essential Concepts Using R and Python* (2nd ed.). O'Reilly Media.
- Repositori kode & data resmi: <https://github.com/gedeck/practical-statistics-for-data-scientists>
