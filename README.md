# Laporan Proyek Machine Learning - Cahya Navila

## Domain Proyek: Kesehatan
Diabetes melitus merupakan salah satu penyakit tidak menular yang prevalensinya terus meningkat secara global dan nasional. Menurut Survei Kesehatan Indonesia (SKI) 2023 yang dirilis Kementrian Kesehatan, prevalensi diabetes pada penduduk Indonesia usia 15 tahun mencapai 11,7%, naik dari 10,9% pada 2018. Peningkatan ini menunjukkan bahwa hampir 1 dari 9 orang dewasa di Indonesia mengidap diabetes, menjadikan penyakit ini sebagai masalah kesehatan masyarakat yang serius.

Secara global, menurut Internasional Diabetes Federation (IDF), pada tahun 2021 terdapat sekitar 537 juta orang dewasa yang mengidap diabetes di seluruh dunia. Angka ini diperkirakan akan terus meningkat setiap tahunnya. Indonesia sendiri menempati posisi kelima sebagai negara dengan jumlah penderita diabetes terbanyak di dunia, dengan estimasi 19,5 juta orang pada tahun 2021. Jika tidak ditangani secara serius, jumlah ini diperkirakan dapat mencapai 28,6 juta pada tahun 2045.

Salah satu kelompok yang memiliki risiko lebih tinggi untuk terkena diabetes adalah wanita. Penelitian oleh Wahyuni (2010) menemukan bahwa wanita memiliki kecenderungan 1,39 kali lebih besar untuk mengidap diabetes dibanidngkan pria (p=0.000), berdasarkan studi di Poltekkes Kemenkes Semarang. Selain itu, faktor-faktor biologis seperti kehamilan, perubahan hormon, dan risiko diabetes gestasional menjadikan wanita sebagai kelompok yang sangat rentan terhadap komplikasi diabetes bila tidak terdeteksi secara dini.

Melihat tingginya angka kasus dan risiko komplikasi yang mungkin timbul, upaya deteksi dini menjadi sangat penting dalam pencegahan dan penganganan diabetes. Dalam hal ini, kemajuan teknologi Machine Learning dapat dimanfaatkan untuk membantu proses klasifikasi pasien berdasarkan data medis yang tersedia. Melalui model prediktif, Mechine Learning dapat mendeteksi pola-pola risiko dan menghasilkan klasifikasi apakah seseorang berpotensi mengidap diabetes atau tidak, sehingga tindakan bisa diambil tindakan lebih cepat.

Oleh karena itu, proyek ini bertujuan untuk membangun sistem klasifikasi diabetes berbasis Machine Learning khusus untuk pasien wanita, dengan harapan dapat berkontribusi dalam proses deteksi dini, mempercepat diagnosis, serta mengurangi risiko komplikasi serius yang mungkin terjadi di masa depan.

                                                                          Referensi

Chou, C. Y., Hsu, D. Y., & Chou, C. H. (2023). Predicting the onset of diabetes with machine learning methods. Journal of Personalized Medicine, 13(3), 406.

Databoks Katadata. (2023). Prevalensi diabetes Indonesia naik jadi 11,7% pada 2023. Diakses pada 24 Mei 2025, dari https://databoks.katadata.co.id/layanan-konsumen-kesehatan/statistik/8a95a31a9cb29b4/prevalensi-diabetes-indonesia-naik-jadi-117-pada-2023

Hartono, H., & Ediyono, S. (2024). Hubungan Tingkat Pendidikan, Lama Menderita Sakit dengan Tingkat Pengetahuan 5 Pilar Penatalaksanaan Diabetes Mellitus di Wilayah Kerja Puskesmas Sungai Durian Kabupaten KBU Raya Kalimantan Barat. The Shine Cahaya Dunia S-1 Keperawatan, 9(01).

Wahyuni, S. (2010). Faktor-faktor yang berhubungan dengan penyakit diabetes melitus (DM) dat sekunder riskesdas 2007.


## Business Understanding

### Problem Statements
- Bagaimana memprediksi apakah seseorang, khususnya wanita, menderita diabetes berdasarkan data medis yang tersedia, mengingat prevalensi diabetes yang terus meningkat secara signifikan, sementara deteksi dini masih belum optimal dan terdapat berbagai tantangan dalam klasifikasi risiko berdasarkan data klinis, terutama di fasilitas kesehatan dengan sumber daya terbatas?
- Algoritma Machine Learning mana yang paling optimal dalam memprediksi diabetes pada dataset tersebut?

### Goals
- Mengembangkan model klasifikasi Machine Learning yang mampu mendeteksi potensi diabetes pada pasien wanita dengan akurasi dan efisiensi yang baik.
- Membandingkan performa empat algoritma: Random Forest, Decision Tree, Support Vector Machine (SVM), dan XGBoost.


    ### Solution statements
    - Menggunakan empat algoritma Machine Learning yaitu:
    1. Decision Three
    2. Random Forest
    3. Support Vectore Machine (SVM)
    4. XGBoost

       Semua algoritma ini digunakan untuk melakukan klasifikasi apakah seorang pasien wanita memiliki risiko diabetes (positif) atau tidak (negatif), berdasarkan fitur-fitur medis yang tersedia.

    - Evaluasi performa model dilakukan dengan beberapa metrik yaitu:
    1. Accuracy
    2. Precision
    3. Recall
    4. F1-score
    5. Confusion Matrix

    - Pemilihan model terbaik dilakukan berdasarkan hasil evaluasi performa dari masing-masing model.

## Data Understanding
Dataset yang digunakan dalam proyek ini diambil dari publikasi ilmiah berjudul "Predicting the Onset of Diabetes with Machine Learning Methods" oleh Chun-Yang Chou, Ding-Yang Hsu, dan Chun-Hang Chou, yang diterbitkan dalam Journal of Personalized Medicine (MDPI) pada tahun 2023. Dataset tersebut dapat diakses melalui link berikut: https://drive.google.com/file/d/1eAplOYO-k7ZYHj4uHAY1tEr8VTeaxS6u/view?usp=sharing
Dataset ini terdiri dari 15000 pasien wanita yang berusia anatara 20 hingga 80 tahun. Para wanita ini adalah pasien yang telah pergi ke rumah sakit di pusat Kota Taipe anatara tahun 2018 hingga 2022 yang telah atau belum didiagnosa diabetes.

### Variabel-variabel pada diabetes dataset adalah sebagai berikut:
- PatientID adalah ID unik dari masing-masing pasien wanita. Tidak digunakan dalam model karena tidak berpengaruh terhadapa proses klasifikasi.
- Pregnancie adalah jumlah kehamilan yang pernah dialami pasien.
- PlasmaGlucose adalah konsentrasi glukosa dalam plasma darah (dalam mg/dL).
- DiastolicBloodPressure adalah tekanan darah diastolik (dalam mm Hg).
- TricepsThickness adalah ketebalan lipatan kulit trisep (dalam mm).
- SerumInsulin adalah kadar insulin dalam serum darah (dalam mu U/ml).
- BMI (Indeks Massa Tubuh) adalah berat badan dalam kg dibagi kuadrat tinggi (dalam kg/m²).
- DiabetesPedigree adalah fungsi silsilah diabetes (faktor keturunan).
- Age adalah usia responden (dalam tahun).
- Diabetic adalah label target (0 = tidak diabetes, 1 = diabetes)

  ![info](https://github.com/user-attachments/assets/e3f78c88-367f-4f82-83b3-4e3043d9bc25)


### Exploratory Data Analysis
- Dataset terdiri 15000 baris dan 10 kolom (1 PatienID, 7 fitur, dan 1 target)
- Target klasifikasi (Positif = 1 dan Negatif = 0)
- Semua fitur bertipe data numerik
- Ststistika deskriptif dari fitur-fitur

  ![statistika deskriptif](https://github.com/user-attachments/assets/44327485-54ad-4cf9-ace1-763aa8edf488)

 1. Pregnancies
   - Rata-rata pasien telah mengalami kehamilan sebanyak 3 kali.
   - Kehamilan terbanyak tercatat sebanyak 14 kali, dan paling sedikit 0 kali.
   - Mayoritas mengalami kehamilan antara 0 hingga 6 kali.
 2. PlasmaGlucose
   - Rata-rata kadar glukosa pasien adalah 107.85 mg/dL, dengan nilai maksimum mencapai 192 mg/dL.
   - Kadar glukosa terendah adalah 44 mg/dL.
   - Mayoritas pasien memiliki kadar glukosa 84 hingga 129 mg/dL.
 3. DiastolicBloodPressure
   - Tekanan darah rata-rata pasien adalah 71.22 mm Hg.
   - Sebagian besar pasien memiliki tekanan darah antara 58 hingga 85 mm Hg.
   - Tekanan darah terendah adalah 24 mm Hg.
 4. TricepsThickness
   - Rata-rata ketebalan lipatan kulit trisep adalah 28.81 mm.
   - Mayoritas nilai berada antara 15 hingga 41 mm, dengan nilai maksimum 93 mm.
   - Nilai minimum 7 mm.
 5. SerumInsulin
  - Rata-rata kadar insulin pasien adalah 137.85 mu U/ml.
  - Kadar insulin tertinggi adalah 799 mu U/ml.
  - Kadar insulin terendah adalah 14 mu U/ml.
 6. BMI
  - Rata-rata BMI pasien adalah 31.5.
  - Mayoritas pasien memiliki BMI antara 21.25 hingga 39.25.
  - Nilai BMI minimum adalah 18.2.
 7. DiabetesPedigree
  - Rata-rata dari faktor keturunan adalah 0.39.
  - Mayoritas pasien memiliki faktor keturunan antara 0.13 hingga 0.61.
 8. Age
  - Rata-rata usia pasien adalah 30.13 tahun, dengan rentang usia dari 21 hingga 77 tahun.
  - Mayoritas pasien berada pada rentang usia 22 hingga 35 tahun.
- Melakukan pengecekan missing dan diperoleh bahwa di dataset tidak terdapat missing value.
- Melakukan pengecekan duplikat dan diperoleh bahwa di dataset tidak terdapat duplikat.
- Melakukan pengecekan outlier dan diperoleh oulier di beberapa kolom:

 1. TricepsThickness

 Dalam kolom tricepsthickness nilai dikatakan outlier kalau berada di bawah -24 dan di atas 80. Berdasarkan hasil statistika deskriptif menunjukkan bahwa dalam kolom tricepsthickness memiliki nilai minimal 7 dan maksimal 93. Jadi dapat disimpulkan bahwa outlier ini berasal dari data yang berada di atas 80. Nilai ini dalam dunia nyata memang sangat tidak umum sehingga bisa disebabkan oleh kesalahan input. Oleh karena itu, oulier dalam kolom tricepsthickness akan dihapus.

 2. SerumInsulin

 Dalam kolom seruminsulin nilai dikatakan outlier kalau berada di bawah -195 dan di atas 429. Berdasarkan hasil statistika deskriptif menunjukkan bahwa dalam kolom seruminsulin memiliki nilai minimal 14 dan maksimal 799. Jadi dapat disimpulkan bahwa outlier ini berasal dari data yang berada di atas 429. Nilai ini dalam dunia nyata memang sangat tidak umum sehingga bisa disebabkan oleh kesalahan input. Oleh karena itu, outlier dalam kolom seruminsulin akan dihapus.

 3. DiabetsPedigree

 Dalam kolom diabetespedigree nilai dikatakan outlier kalau berasa di bawah -0.58 dan di atas 1.33. Berdasarkan hasil statistika deskriptif menunjukkan bahwa dalam kolom diabetespedigree memiliki nilai minimal 0.07 dan maksimal 2.3. Jadi dapat disimpulkan bahwa outlier ini berasal dari data yang berada di atas 1.33. Namun karena data dengan nilai diabetespedigree 2.3 masih mungkin terjadi dalam dunia nyata, maka outlier ini tidak dihapus.

 4. Age
 
 Dalam kolom age ini nilai dikatakan outlier kalau berada di bawah 2.5 tahun dan di atas 54.5 tahun. Berdasarkan hasil statistika deskriptif menunjukkan bahwa dalam kolom age memilki minimal nilai 21 tahun dan maskimal 77 tahun. Jadi dapat disimpulkan bahwa oulier ini berasal dari data yang berada diatas 54.5 tahun. Namun karena memang data ini dikumpulkan untuk rentang usia 20 hingga 80 tahun maka outlier ini tidak dihapus.

- Dalam dataset lebih banyak mengandung data pasien tidak diabates dibanding diabetes. Pasien yang tidak diabetes jumlahnya 2 kali lebih banyak dibandingkan pasien diabetes.
- Fitur DiastolicPressure memiliki korelasi dengan diabetic sangat kecil (0,09).

## Data Preparation
1. Penghapusan kolom PatientID

Penghapusan kolom PatienID di awal karena kolom ini merupakan identifikasi unik pasien yang tidak mengandung informasi penting untuk prediksi.

2. Penghapusan outlier pada kolom TricepsThickness dan SerumInsulin

Penghapusan oulier pada kolom TricepThickness dan SerumInsulin dilakukan karena nilainya mencurigakan dan tidak masuk akal secara medis. Pada kolom TricepsThickness, data dikategorikan sebagai outlier jika nilainya berada di bawah -24 atau di atas 80. Berdasarkan hasil statistik deskriptif, nilai minimum dalam data ini adalah 7 dan nilai maksimum mencapai 93. Maka, data yang bernilai lebih dari 80 dianggap sebagai outlier. Dalam konteks medis, ketebalan triceps yang melebihi angka tersebut tidak lazim ditemukan, sehingga nilai-nilai tersebut dianggap tidak masuk akal secara medis. Sementara itu, pada kolom SerumInsulin, nilai dikategorikan sebagai outlier jika berada di bawah -195 atau di atas 429. Statistik deskriptif menunjukkan bahwa nilai minimum adalah 14 dan maksimum mencapai 799. Oleh karena itu, nilai-nilai di atas 429 dianggap sebagai outlier. Berdasarkan referensi medis, kadar insulin serum yang melebihi angka tersebut sangat jarang dijumpai dan dianggap tidak wajar secara klinis, sehingga dikelompokkan sebagai nilai yang mencurigakan atau tidak masuk akal secara medis.

3. Penghapusan kolom DiastolicBloodPressure

Penghapusan kolom DiastolicPressure karena korelasinya dengan diabetic sangat kecil (0,09).

4. Pemabgian data train-test

Dataset dibagi menjadi dua bagian yaitu:
- Data latih (train): 80% dari data digunakan untuk melatih model.
- Data uji (test): 20% dari data digunakan untuk menguji performa model.

Pembagian dilakukan dengan menggunakan train_test_split, dengan random_state=40 untuk memastikan replikasi konsisten.

5. Scaling fitur

Melakukan pengubahan nilai fitur agar berada dalam rentang 0 sampai 1 yaitu dengan MinMaxScale dari sklearn.preprocessing. Tujuan dari scaling ini agar model machine learning tidak bias terhadap fitur dengan skala besar. Selain itu digunakan fit(X_train) untuk menghindari kebocoran data dari data uji.

6. Oversamplig dengan SMOOTE

Distribusi target diabetic tidak seimbang (jumlah kelas 0 lebih banyak dibandingkan kelas 1). Oleh karena itu, dilakukan oversampling menggunakan SMOTE untuk menyamakan distribusi kelas, agar model tidak bias terhadap kelas mayoritas.

## Modeling
Pada proyek ini digunakan empat algoritma machine learning untuk melakukan klasifikasi diabetes pada wanita, yaitu: Decision Tree, Random Forest, Support Vector Machine (SVM), dan XGBoost. Pelatihan model dilakukan pada data yang telah di-resample menggunakan SMOTE (X_resampled dan y_resampled), dan pengujian dilakukan terhadap data uji yang telah diskalakan (X_test_scaled).

1. Decision Tree
- Cara kerja

Decision Tree bekerja dengan membagi data ke dalam cabang-cabang berdasarkan fitur yang memberikan informasi terbaik. Proses ini berlanjut hingga mencapai daun (leaf) yang merepresentasikan label kelas. Model ini membuat keputusan dengan menelusuri cabang dari akar ke daun.

- Parameter yang digunakan
  - random_state=40: Untuk memastikan hasil pelatihan konsisten setiap kali dijalankan.
  - Parameter lainnya menggunakan default:
    - criterion='gini': Mengukur kualitas split.
    - max_depth=None: Tidak ada batasan kedalaman pohon (berpotensi overfitting).
    - min_samples_split=2: Minimal jumlah sampel untuk split.
- Kelebihan
  - Mudah dipahami dan diinterpretasikan.
- Kekurangan
  - Rentan terhadap overfitting jika tidak dibatasi kedalamannya.
  - Sensitif terhadap data yang tidak diskalakan dan outlier

2. Random Forest
- Cara kerja

Random Forest merupakan kumpulan (ensemble) dari banyak pohon keputusan (Decision Tree) yang dilatih pada subset data yang berbeda secara acak (bagging). Hasil akhir ditentukan dengan voting mayoritas dari seluruh pohon.

- Parameter yang digunakan
  - random_state=40: Untuk reprodusibilitas hasil.
  - Parameter default lainnya:
    - n_estimators=100: Jumlah pohon dalam hutan.
    - max_depth=None: Kedalaman pohon tidak dibatasi.
    - bootstrap=True: Menggunakan sampling acak data.
- Kelebihan 
  - Lebih akurat dan tahan terhadap overfitting dibanding single tree.
- Kekurangan 
  - Kurang interpretatif dan membutuhkan lebih banyak waktu komputasi.

3. Support Vectore Machine (SVM)
- Cara kerja

SVM mencari hyperplane terbaik yang memisahkan kelas dengan margin maksimum. Untuk data non-linear, digunakan kernel (dalam kasus ini: RBF) yang memetakan data ke dimensi yang lebih tinggi agar dapat dipisahkan secara linear.

- Parameter yang digunakan
  - random_state=40: Untuk konsistensi hasil.
  - Parameter default lainnya:
    - kernel='rbf': Kernel radial basis function, default dan umum digunakan untuk data non-linear.
    - C=1.0: Parameter regularisasi.
    - gamma='scale': Skala otomatis terhadap fitur.

- Kelebihan
  - Cocok untuk data berdimensi tinggi dan non-linear.
- Kekurangan
  - Memerlukan tuning dan lambat pada dataset besar.

4. XGBoost
- Cara kerja

XGBoost (Extreme Gradient Boosting) adalah algoritma boosting yang membangun model secara bertahap. Setiap model baru dibuat untuk memperbaiki kesalahan dari model sebelumnya, menggunakan metode gradient descent dan penambahan regulasi untuk menghindari overfitting.

- Parameter yang digunakan
  - learning_rate=0.1: Mengontrol besarnya perubahan model pada setiap iterasi.
  - max_depth=3: Mencegah overfitting dengan membatasi kedalaman pohon.
  - n_estimators=300: Jumlah pohon dalam boosting.
  - eval_metric='logloss': Digunakan untuk evaluasi klasifikasi biner.
  - random_state=40: Agar hasil dapat direproduksi.

- Kelebihan
  - Performa tinggi dan cepat, dan mengurangi overfitting secara otomatis dengan regularisasi.
- Kekurangan
  - Banyak parameter, tuning bisa kompleks.


Model yang dipilih adalah XGBoost karena performanya tinggi dan hasil dari evalusinya paling bagus.




## Evaluation
Pada proyek klasifikasi diabetes pada wanita ini, digunakan beberapa metrik evaluasi untuk mengukur performa masing-masing model.
1. Accuracy

Mengukur proporsi prediksi yang benar dari seluruh prediksi.

Rumus:

![akurasi](https://github.com/user-attachments/assets/29dcf7d3-a663-4a42-a735-b3aefe75c32a)


Cocok digunakan saat distribusi kelas seimbang. Namun, pada data yang imbalanced, metrik ini bisa menyesatkan.

2. Precision

Mengukur proporsi prediksi positif yang benar-benar positif.

Rumus:  

![precision1](https://github.com/user-attachments/assets/9d829d75-a9e5-4b3c-a1e1-c17489827790)

Penting ketika konsekuensi dari false positive tinggi, misalnya diagnosis salah positif.

3. Recall

Mengukur proporsi kasus positif yang berhasil dideteksi model.

Rumus:

![recall1](https://github.com/user-attachments/assets/629c3829-475f-4f60-84e8-15f4bdaba1cd)

Sangat penting dalam konteks medis, karena tidak boleh melewatkan pasien yang benar-benar sakit.

4. F1 Score

Merupakan harmonisasi antara precision dan recall.

Rumus:

![f1](https://github.com/user-attachments/assets/2d35e09e-edf8-44a4-a5a0-223eb8acbc67)

Berguna saat perlu keseimbangan antara precision dan recall.

5. Confusion Matrix

Membantu memberikan gambaran detail tentang prediksi model, berapa banyak true positive, false positive, true negative, dan false negative yang dihasilkan.

![confusion](https://github.com/user-attachments/assets/c002aebc-b724-4772-8bf8-ae95e9aa545e)


- True Positive (TP): Kasus positif yang berhasil dideteksi sebagai positif.
- False Positive (FP): Kasus negatif yang salah diklasifikasikan sebagai positif.
- True Negative (TN): Kasus negatif yang berhasil diklasifikasikan dengan benar.
- False Negative (FN): Kasus positif yang gagal dideteksi (dianggap negatif).
 
**Evaluasi Model Decision Tree**
- Memiliki akurasi 0.89
- Memiliki precision 0.82
- Memiliki recall 0.82
- Memiliki F1 score 0.82
- Berdasarkan confusion matrix
  - 1838 pasien tidak diabetes diprediksi dengan benar (true negative).
  - 720 pasien diabetes diprediksi dengan benar (true positive).
  - 154 pasien tidak diabetes salah diprediski sebagai diabetes (false positive).
  - 150 pasien diabetes salah diprediksi sebagai tidak diabetes (false negative).

**Evaluasi Model Random Forest**
- Memiliki akurasi 0.93
- Memiliki precision 0.88
- Memiliki recall 0.89
- Memiliki F1 score 0.89
- Berdasarkan confusion matrix
  - 1895 pasien tidak diabetes diprediksi dengan benar (true negative).
  - 779 pasien diabetes diprediksi dengan benar (true positive).
  - 97 pasien tidak diabetes salah diprediski sebagai diabetes (false positive).
  - 91 pasien diabetes salah diprediksi sebagai tidak diabetes (false negative).

**Evaluasi Model Support Vectore Machine (SVM)**
- Memiliki akurasi 0.88
- Memiliki precision 0.76
- Memiliki recall 0.89
- Memiliki F1 score 0.82
- Berdasarkan confusion matrix
  - 1756 pasien tidak diabetes diprediksi dengan benar (true negative).
  - 781 pasien diabetes diprediksi dengan benar (true positive).
  - 236 pasien tidak diabetes salah diprediski sebagai diabetes (false positive).
  - 89 pasien diabetes salah diprediksi sebagai tidak diabetes (false negative).

**Evaluasi Model XGBoost**
- Memiliki akurasi 0.95
- Memiliki precision 0.91
- Memiliki recall 0.93
- Memiliki F1 score 0.92
- Berdasarkan confusion matrix
  - 1916 pasien tidak diabetes diprediksi dengan benar (true negative).
  - 814 pasien diabetes diprediksi dengan benar (true positive).
  - 76 pasien tidak diabetes salah diprediski sebagai diabetes (false positive).
  - 56 pasien diabetes salah diprediksi sebagai tidak diabetes (false negative).

  ![evaluasi](https://github.com/user-attachments/assets/02348754-5bbf-4997-8d38-a5135585a75e) 

Berdasarkan hasil di atas model yang memiliki performa paling bagus adalah XGBoost.



**---Ini adalah bagian akhir laporan---**



