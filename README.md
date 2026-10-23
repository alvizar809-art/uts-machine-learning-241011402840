# uts-machine-learning-241011402840
Tugas UTS Machine Learning - Linear Regression dan Logistic Regression

IDENTITAS MAHASISWA
--
- Nama  : M.alvizar
- NIM   : 241011402840
- Kelas : 05TPLE005

RINGKASAN HASIL
--

## 1. Linear Regression

Linear Regression digunakan untuk memprediksi nilai penjualan berdasarkan biaya iklan menggunakan dataset `Ads_Data.csv`.

**Hasil model:**
- Persamaan regresi: ŷ = 28.6313 + 9.1684X
- Intercept: 28.6313
- Koefisien: 9.1684

**Evaluasi model:**

| Metrik | Training | Testing |
|---|---:|---:|
| MAE | 3.4789 | 8.2791 |
| MSE | 19.1359 | 106.1912 |
| RMSE | 4.3745 | 10.3049 |
| R² | 0.9710 | 0.7008 |

**Analisis:**

Model menghasilkan nilai R² sebesar 0.9710 pada data training dan 0.7008 pada data testing. Hal ini menunjukkan bahwa model menjelaskan variasi penjualan dengan sangat baik pada data training, tetapi kinerjanya lebih rendah pada data testing. Perbedaan tersebut menunjukkan bahwa kemampuan prediksi pada data yang belum pernah dilihat masih perlu diperhatikan.

Pada pengujian Gradient Descent, learning rate 0.02 menghasilkan loss akhir sekitar 19.135948 dan menunjukkan konvergensi. Learning rate 0.1 menyebabkan divergensi, sedangkan learning rate 0.001 menghasilkan loss akhir sekitar 21.489054.

## 2. Logistic Regression

Logistic Regression digunakan untuk mengklasifikasikan email menjadi spam dan non-spam berdasarkan jumlah link dan kata promosi menggunakan dataset `Email_Data.csv`.

**Dataset:**
- Total data: 60 email
- Email non-spam: 35
- Email spam: 25
- Data training: 45 email
- Data testing: 15 email

**Persamaan model:**

P(Spam) = sigmoid(-11.2618 + 1.0437 × JumlahLink + 0.8897 × KataPromo)

**Hasil evaluasi pada threshold 0.5:**

| Metrik | Hasil |
|---|---:|
| Accuracy | 0.8667 (86.67%) |
| Precision | 0.9000 (90%) |
| Recall | 0.9000 (90%) |
| F1-score | 0.9000 (90%) |

**Confusion Matrix:**

```text
[[4, 1],
 [1, 9]]
```

Keterangan:
- True Negative (TN): 4
- False Positive (FP): 1
- False Negative (FN): 1
- True Positive (TP): 9

**Analisis:**

Model memperoleh accuracy sebesar 86.67%, yang berarti 13 dari 15 data pengujian diklasifikasikan dengan benar. Precision, recall, dan F1-score masing-masing sebesar 90%. Hasil ini menunjukkan bahwa model dapat mengklasifikasikan email spam dan non-spam dengan cukup baik pada data pengujian yang digunakan.

## 3. Perbandingan dengan scikit-learn

Pada percobaan Bonus, Linear Regression manual dan scikit-learn menghasilkan nilai intercept 28.6313, koefisien 9.1684, dan MSE testing 106.1912.

Pada Logistic Regression, kedua model memperoleh accuracy sebesar 0.8667 atau 86.67%, dengan confusion matrix yang sama, yaitu:

```text
[[4, 1],
 [1, 9]]
```

Nilai log loss model manual adalah 0.5006, sedangkan scikit-learn adalah 0.4922. Nilai log loss scikit-learn yang lebih rendah menunjukkan bahwa probabilitas prediksinya sedikit lebih baik pada data pengujian ini.

## Kesimpulan

Linear Regression dapat digunakan untuk memprediksi penjualan berdasarkan biaya iklan, sedangkan Logistic Regression dapat digunakan untuk mengklasifikasikan email spam dan non-spam. Evaluasi menunjukkan bahwa model Logistic Regression memperoleh accuracy sebesar 86.67%. Perbandingan dengan scikit-learn juga menunjukkan hasil yang sebanding pada data pengujian, meskipun nilai log loss Logistic Regression sedikit berbeda.

