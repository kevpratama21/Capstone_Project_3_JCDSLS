Capstone Project Module 3 JCDSLS - Kevin Pratama

# Customer Lifetime Value
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

## **3. Data Preprocessing**
---
- Distribution
- Descriptive Statistics
- Correlation
