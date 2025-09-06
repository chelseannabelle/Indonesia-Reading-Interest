## Dataset
- File asli: `TGM 2020-2023_eng.csv`
- Format: CSV → juga bisa dikonversi ke XLS untuk pengecekan manual di Excel
- Dataset mengandung beberapa **missing values** dan **outlier (nilai ekstrim)**

---

## Metode Outlier Removal

### 1. IQR (Interquartile Range)
- Hitung **Q1 (25%)** dan **Q3 (75%)**
- Hitung **IQR = Q3 – Q1**
- Tentukan batas bawah: `Q1 – 1.5*IQR`
- Tentukan batas atas: `Q3 + 1.5*IQR`
- Data di luar range → dianggap **outlier**

### 2. Z-score
- Hitung skor-z untuk setiap data
- Data dengan `|z| > 3` → dianggap **outlier**

---

## Hasil
- Histogram **sebelum cleaning** → banyak data ekstrim.
- Setelah **IQR** → distribusi data lebih normal.
- Setelah **Z-score** → distribusi juga lebih stabil.
- File hasil preprocessing disimpan sebagai:
  - `TGM_clean.csv` (IQR)
  - `TGM_clean_zscore.csv` (Z-score)

---

## Struktur Repo
- data/ → dataset asli & hasil preprocessing
- notebook/ → kode preprocessing dan eksperimen
- img/ → visualisasi histogram (before & after)
- README.md → laporan singkat


---

## Catatan
- Dataset asli mengandung nilai kosong & outlier.
- Data hasil cleaning lebih siap dipakai untuk analisis lanjutan (misalnya clustering, regresi, atau visualisasi lebih lanjut).
