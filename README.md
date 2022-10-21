# Customer Lifetime Value Prediction
<br>

## **1. Business Problem Understanding**
---

**1.1. Context**

Sebuah perusahaan yang bergerak di bidang auto insurance ingin meningkatkan profitnya.
Dari seluruh populasi customernya perusahaan ingin melakukan evalusi mengenai aspek apa saja yang dianggap dapat memberikan pengaruh dalam peningkatan profit perusahaan.

Parameter yang akan digunakan untuk evalusai customer adalah dengan menggunakan nilai customer lifetime value (CLV).
CLV adalah sebuah metrik untuk memperkirakan total nilai customer terhadap sebuah perusahaan dalam jangka waktu tertentu (mengikuti durasi hubungan bisnis keduanya). 
Secara sederhana, CLV adalah prediksi atas nilai total pendapatan yang bisa perusahaan dapatkan dari customernya. Semakin besar CLV maka semakin besar juga profit perusahaan

**1.2. Problem Statement**

Salah satu permasalahan perusahaan auto insurance ini adalah menentukan aspek apa saja yang dapat memberikan pengaruh dalam peningkatan profit perusahaan sehingga dapat memfokuskan strategi bisnisnya ke aspek-aspek yang dianggap berpengaruh nantinya. 
Perusahaan juga perlu mengetahui berapa biaya maksimal yang bisa dikeluarkan untuk mengakuisisi customer. Jangan sampai biaya akuisisi yang dikeluarkan melebihi batas sehingga mengurangi profit perusahaan secara signifikan.

**1.3. Goals**

Berdasarkan permasalahan tersebut, perusahaan auto insurance ini perlu memiliki tool yang dapat memprediksi CLV, sehingga dapat membantu untuk menentukan aspek apa saja yang berpengaruh dalam memberikan profit kepada perusahaan dan menentukan biaya maksimal untuk melakukan akuisisi customer.

**1.4. Analytic Approach**

Jadi, yang perlu kita lakukan adalah menganalisis data untuk dapat menemukan pola dari fitur-fitur yang ada, yang dapat membedakan satu customer dengan yang lainnya.

Selanjutnya, kita akan membangun suatu model regresi yang akan membantu perusahaan untuk menyediakan tool yang dapat memprediksi CLV dari setiap customer, sehingga akan berguna untuk melihat profit yang akan didapatkan perusahaan dari setiap customer.

**1.5. Metric Evaluation**

Evaluasi metrik yang akan digunakan yaitu:
- RMSE adalah nilai rataan akar kuadrat dari error 
- MAE adalah rataan nilai absolut dari error
- MAPE adalah rataan nilai persentase error yang dihasilkan oleh model regresi
- R-squared adalah nilai seberapa baik model dapat merepresentasikan varians keseluruhan data
<br>

## **2. Data Understanding**
---
**2.1. Data Info**
- Dataset yang digunakan berisi informasi customer dan informasi polis asuransi kendaraan mereka dari sejak awal menggunakan produk asuransi perusahaan auto insurance ini.
- Setiap baris data merepresentasikan informasi terkait keterangan seorang customer dengan polis asuransi kendaraan miliknya.

**Attributes Information**

| **Attribute** | **Data Type** | **Description** |
| --- | --- | --- |
| Vehicle Class             | Object    | Tipe kendaraan |
| Coverage                  | Object    | Jenis pertanggungan polis asuransi customer |
| Renew Offer Type          | Object    | Penawaran untuk pembaruan polis |
| EmploymentStatus          | Object    | Status pekerjaan cutomer |
| Marital Status            | Object    | Status pernikahan cutomer |
| Education                 | Object    | Tingkat pendidikan customer |
| Number of Policies        | Float     | Jumlah polis yang dimiliki customer |
| Monthly Premium Auto      | Float     | Premi customer perbulan (USD) |
| Total Claim Amount        | Float     | Jumlah claim customer (USD) |
| Income                    | Float     | Pendapatan cutomer (USD) |
| Customer Lifetime Value   | Float     | Customer Lifetime Value (Target) |

<br>

**2.2. EDA**
---
- Distribution
- Descriptive Statistics
- Correlation
<br>

## **3. Data Preprocessing**
---
- Cek Feature, Unique Value, dan Missing Value
- Handling Outlier
<br>

## **4. Modeling**
---
- Encoding
- Splitting Data
- Choose Bechmark Model
- Hyperparameter Tuning
- Predict Test dataset 
<br>

## **5. Conclusion**
---
Model terbaik yang dipilih untuk memprediksi CLV adalah XGBoost. Metrik evaluasi yang digunakan pada model adalah nilai RMSE, MAE, MAPE, dan R-squared. Jika ditinjau dari nilai MAPE yang dihasilkan oleh model setelah dilakukan hyperparameter tuning, yaitu sekitar 4%, kita dapat menyimpulkan bahwa bila nanti model yang kita buat ini digunakan untuk memprediksi Customer Lifetime Value pada rentang nilai seperti yang dilatih terhadap model, maka hasil prediksi CLVnya rata-rata dapat meleset kurang lebih sekitar 4% dari CLV yang seharusnya.

Tetapi, tidak menutup kemungkinan juga prediksinya meleset lebih jauh karena bias yang dihasilkan model masih cukup tinggi. Bila dilihat dari visualisasi antara CLV aktual dan prediksi serta residual performa prediksi model mulai menurun ketika CLV sekitar 8.000 keatas. Bias yang dihasilkan oleh model ini dikarenakan oleh terbatasnya fitur pada dataset yang bisa merepresentasikan aspek customer dan juga polis asuransi mereka.

Beberapa limitasi model yang tercipta karena adanya rentang nilai yang dipakai untuk train model ini yaitu:
- Nilai Customer Lifetime Value maksimal 16646.5203465
- Nilai Total Claim Amount maksimal 974.566507
- Nilai Monthly Premium Auto maksimal 163

Berdasarkan pemodelan yang sudah dilakukan, fitur 'Number of Policies', 'Monthly Premium Auto', dan 'Vehicle Class' menjadi fitur yang paling berpengaruh terhadap target 'Customer Lifetime Value'.
Hal tersebut dapat menjawab bussiness problem mengenai apa saja aspek yang mempengaruhi CLV customer.
Dengan mengetahui fitur apa saja yang mempengaruhi CLV customer maka perusahaan dapat memfokuskan usaha marketingnya terhadap ketiga aspek tersebut untuk dapat meningkatkan profit perusahaan. 

Berdasarkan pemodelan yang sudah dilakukan, perusahaan memiliki tool untuk memprediksi nilai Customer Lifetime Value.
Dengan dapat diprediksinya CLV maka dapat membantu bussiness problem mengenai perhitungan biaya maksimal untuk akuisisi customer. Perusahaan dapat mengatur agar biaya akuisisi tidak sampai melebihi CLV atau sebisa mungkin jauh lebih rendah dibanding CLV agar perusahaan mendapat profit maksimal.
<br>

## **6. Recommendation**
---
Beberapa hal yang dapat dilakukan untuk mengembangkan model agar lebih baik lagi yaitu:

- Eksperimen menggunakan model machine learning lainnya yang belum digunakan pada project ini
- Eksperimen dalam hyperparameter tuning lebih lanjut
- Penambahan fitur lain yang behubungan dengan informasi polis customer, seperti informasi berapa bulan lamanya customer sudah menggunakan asuransi dari perusahaan ini.
- Mengecek prediksi data mana saja yang menghasilkan nilai error tinggi. lalu melakukan analisa hubungan antara error tersebut dengan setiap variable independen dengan tujuan untuk mengetahui sebenarnya variable mana saja yang menyebabkan prediksi model menghasilkan error yang tinggi.
