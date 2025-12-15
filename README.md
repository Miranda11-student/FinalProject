# Predictive Leads Scoring for Bank Term Deposit Campaigns

Tim Data Scientist:

•	Dian Maya Safitri

•	Ghofar Ismail

•	Miranda Puspitasari
________________________________________

## Background
Kampanye pemasaran deposito berjangka di Portugal menggunakan telemarketing sebagai kanal utama. Tingkat konversi nasabah rendah (~11%) sehingga banyak panggilan tidak produktif, menimbulkan biaya operasional tinggi. Dengan data historis yang tersedia, tujuan proyek ini adalah memahami pola perilaku nasabah dan mengembangkan model prediktif untuk prioritisasi leads.

Stakeholder Terdampak:

•	Divisi Marketing Campaign / Telemarketing

•	Sales Agents

•	Divisi Finance / CFO
________________________________________
## Problem Statement
Kampanye telemarketing memiliki tingkat konversi rendah. Pertanyaan kunci yang ingin dijawab:

1.	Bagaimana faktor demografi, riwayat kontak, dan kondisi makro memengaruhi respons nasabah?
2.	Segmentasi usia mana yang cenderung konversi tinggi?
3.	Efektivitas saluran komunikasi, frekuensi, dan durasi panggilan?
4.	Bagaimana membangun model prediksi untuk memprioritaskan leads?
________________________________________
## Goals
•	Identifikasi variabel kunci yang memengaruhi keputusan nasabah.
•	Insight untuk strategi kampanye lebih efektif dan efisien.
•	Segmentasi nasabah dengan potensi konversi tinggi.
•	Model prediksi probabilitas konversi untuk kampanye berikutnya.
________________________________________
## Analytics Approach
1.	Exploratory Data Analysis (EDA):
o	Memahami distribusi variabel, segmentasi nasabah, dan efektivitas panggilan.
2.	Data Preprocessing & Feature Engineering:
o	Penanganan missing values, data duplikat, outlier.
o	Mapping fitur ordinal & kategorikal.
o	Split train/test.
o	Pipeline preprocessing dengan ColumnTransformer.
3.	Machine Learning:
o	Model klasifikasi untuk prediksi konversi.
o	Model: Random Forest, XGBoost, LightGBM, Bagging, Voting Classifier.
o	Penanganan imbalance menggunakan SMOTE.
4.1 Dataset
•	Sumber: UCI Bank Marketing Dataset
•	Jumlah Baris: 41.188
•	Kolom: 20
•	Tipe: Binary Classification (y: yes/no)
Catatan: Variabel duration tidak digunakan untuk prediksi karena berpotensi menyebabkan data leakage.
________________________________________
## Evaluation Metrics
•	Focus: Meminimalkan False Negatives (FN) → meningkatkan peluang konversi.
•	Metrik utama: Recall
Recall=TPTP+FNRecall = \frac{TP}{TP + FN}Recall=TP+FNTP 
•	Metode lain: Precision, F2 Score, Accuracy
Definisi Confusion Matrix:
Actual\Predicted	Positive	Negative
Positive	TP	FN
Negative	FP	TN
________________________________________
## Feature Engineering
•	Numerik: age, campaign, pdays, previous, indikator ekonomi
•	Kategorikal: job, marital, default, housing, loan, contact, month, day_of_week, poutcome, generation
•	Ordinal: education (custom order)
•	Target: y (0/1)
Generational Mapping: Baby Boomer, Gen X, Millennials, Gen Z
________________________________________
## Modelling Approach
•	Pipeline preprocessing: ColumnTransformer + SMOTE
•	Models: Random Forest, Bagging, XGBoost, LightGBM, Voting Classifier
•	Cross-Validation: StratifiedKFold (5-fold), scoring: F2, Recall, Precision, Accuracy
•	Hyperparameter tuning: Random Forest fokus optimasi Recall
________________________________________
## Cost-Benefit Analysis
•	Fungsi cost_benefit_analysis(y_true, y_pred, benefit_TP, cost_FN, cost_FP, benefit_TN) digunakan untuk menghitung biaya dan manfaat prediksi.
•	Fokus utama: mengurangi FN untuk menangkap nasabah potensial.
________________________________________
## Results (Example)
•	Conversion rate tertinggi pada kontak pertama (~13%).
•	Nasabah dengan pdays=-1 (belum pernah dihubungi) memiliki risiko FN lebih tinggi.
•	Segmentasi generasi: Millennials dan Gen X cenderung konversi lebih tinggi.
•	Random Forest terpilih sebagai model terbaik berdasarkan Recall.
________________________________________

________________________________________
## References
•	UCI Machine Learning Repository — Bank Marketing Dataset
•	BAI.org — Banking attitudes, generation-by-generation
•	Press Release Banco de Portugal (2014)
•	Moro, S., Cortez, P., & Rita, P. (2014). Bank Marketing Campaigns

## link Tablue : https://public.tableau.com/app/profile/ghofar.ismail8792/viz/BankMarketingCampaign_17638186946940/ConversionRate?publish=yes
<img width="1758" height="792" alt="image" src="https://github.com/user-attachments/assets/b003b539-fc2d-4b1c-bab1-9f256ac06eb1" />

## link Streamlit : 
https://telemarketing-app-mypfurxobnty7kdxfgfalg.streamlit.app/

