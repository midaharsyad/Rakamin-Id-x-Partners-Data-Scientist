# 📊 Machine Learning-Based Credit Scoring for Loan Default Prediction – ID/X Partners

## 📌 Project Overview
ID/X Partners sebagai perusahaan konsultan membantu institusi keuangan dalam mengelola dan menganalisis data kredit dalam jumlah besar. Tanpa analisis yang tepat, data tersebut belum dimanfaatkan secara optimal untuk membedakan nasabah berisiko rendah dan tinggi.

Proyek ini bertujuan membangun sistem Credit Scoring berbasis Machine Learning untuk memprediksi risiko gagal bayar nasabah. Model ini diharapkan dapat membantu perusahaan dalam mengambil keputusan pemberian kredit yang lebih akurat, seperti menentukan limit pinjaman, tenor, serta mengurangi potensi kredit macet.

---

## 🎯 Objectives
- Memprediksi risiko gagal bayar nasabah  
- Mengidentifikasi faktor utama yang memengaruhi risiko kredit  
- Membantu proses persetujuan kredit berbasis data  
- Mengurangi potensi kerugian akibat kredit bermasalah  
- Mengoptimalkan strategi penyaluran kredit  

---

## 📂 Dataset
- **466.285 data pinjaman**
- **75 fitur awal**

### Struktur Data
- Fitur numerik: loan amount, interest rate, installment, annual income  
- Fitur kategorikal: grade, home ownership, purpose  
- Riwayat kredit: total account, inquiry, credit history  

### Target
- 0 = Lancar  
- 1 = Gagal Bayar  

---

## 🧹 Data Cleaning
- Menghapus kolom dengan missing value 100%  
- Menghapus kolom dengan missing >50%  
- Imputasi median untuk fitur numerik  
- Menghapus kolom tidak relevan (ID, URL, dll)  
- Konversi tipe data tanggal ke datetime  

---

## 📊 Exploratory Data Analysis

### Target Distribution
- Lancar: ~88%  
- Gagal bayar: ~12%  

### Financial Insights
- Pinjaman dominan: $5.000 – $15.000  
- Suku bunga dominan: 12% – 15%  
- Grade rendah → risiko lebih tinggi  

### Correlation Insights
- Multikolinearitas:
  - loan_amnt  
  - funded_amnt  
  - funded_amnt_inv  
  - installment  

- Fitur lain relatif independen  

### Risk Correlation
- Meningkatkan risiko:
  - int_rate  
  - inq_last_6mths  
  - term  

- Menurunkan risiko:
  - annual_inc  
  - total_rev_hi_lim  
  - credit_age  

### Outlier Analysis
- annual_inc → outlier ekstrem → capping (p99)  
- loan_amnt → stabil  

---

## ⚙️ Feature Engineering

### Feature Creation
- inst_to_inc_ratio  
- utilization_ratio  
- loan_to_inc_ratio  
- credit_age_years  
- grade_int_interaction  

### Data Handling
- Missing value → imputasi median  
- Outlier → capping  
- Drop fitur redundant  

### Encoding
- Ordinal encoding (grade)  
- One-hot encoding (kategori lain)  

---

## 🤖 Modeling
Model yang digunakan:
- Logistic Regression  
- Random Forest  
- XGBoost  
- LightGBM  
- CatBoost  

### Evaluation Metrics
- Accuracy  
- Precision  
- Recall  
- F1 Score  
- ROC-AUC  

---

## 🏆 Best Model
**CatBoost**
- ROC-AUC ~0.70  
- Recall tinggi untuk deteksi risiko  
- Stabil pada data imbalance  

---

## 📊 Model Evaluation

### Confusion Matrix
- True Positive  : 6.982  
- True Negative  : 51.702  
- False Positive : 31.044  
- False Negative : 3.439  

### Insight
Model cukup baik dalam mendeteksi risiko, namun masih terdapat kesalahan pada klasifikasi nasabah lancar.

---

## 🔍 Feature Importance (CatBoost)
- grade_int_interaction  
- int_rate  
- utilization_ratio  
- annual_inc  
- inst_to_inc_ratio  
- dti  
- revol_bal  

---

## 💡 Business Recommendations
- Menyaring kredit untuk nasabah berisiko tinggi  
- Mengatur limit sesuai kemampuan finansial  
- Membatasi cicilan agar tidak melebihi gaji  
- Menggunakan model sebagai credit scoring otomatis  
- Memberikan benefit untuk nasabah loyal  
- Monitoring dan retraining model secara berkala  

---

## 🛠️ Tools & Libraries
- Python  
- Pandas  
- NumPy  
- Scikit-learn  
- CatBoost  
- XGBoost  
- LightGBM  
- Matplotlib  
- Seaborn  

---

## 👩‍💻 Author
**Khamidah Arsyad Daud**  
Machine Learning & Data Analysis Enthusiast 🚀