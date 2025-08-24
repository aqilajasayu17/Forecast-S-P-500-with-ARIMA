# Forecast-S-P-500-with-ARIMA
### **Time Series Prediction for S&P 500**
Dataset:https://finance.yahoo.com/quote/%5EGSPC/history/

Dataset pada penelitian ini merupakan data dari saha, S&P 500, dimana rentang waktu yang akan diteliti adalah dari 23 Agustus 2024 hingga 23 Agustus 2025. Terdapat enam variabel dan variabel yang akan digunakan adalah variabel "Close", tujuan penggunaan dari variabel tersebut ialah untuk menjadi acuan dalam pengambilan keputusan investasi seperti kapan harus buy, hold, atau sell.

### **Plot Data Aktual**

<img width="1032" height="575" alt="Image" src="https://github.com/user-attachments/assets/957ee466-b33c-4d9b-8bde-f097a52b5128" />
Pada plot terlihat bahwa data sering mengalami fluktuasi, dimana harga sempat naik mulai dari akhir 2024 hingga awal 2025 sekitar 6200-6300 kemudian mengalami penurunan yang sangat signifikan dari Maret hingga April 2025 dan mulai kembali normal yang ditunjukan dengan tren naik mencapai lebih dari 6400 pada Agustus 2025. Kesimpulan dari hasil plot data aktual bahwa harga sempat turun drastis pada awal 2025 yang kemudian kembali normal dengan cepat dan kembali memiliki nilai yang tinggi pada akhir 2025, oleh karena itu pada periode ini memberikan gambaran pasar yang sempat naik turun namun memiliki pemulihan y ang kuat.

### **Check Stationary dengan ADF dan Plot ACF PACF**
Dikarenakan pada data aktual  memiliki pola tren dari awal hingga akhir yang tidak konsisten maka model akan menangkap pola tren tersebut sehingga menyebabkan prediksi yang bias. Oleh karena itu sebelum melakukan penelitian akan dilakukan test ADF dan plot ACF PACF untuk melihat stationer data.
<img width="748" height="572" alt="image" src="https://github.com/user-attachments/assets/c86ac4fb-31b1-408c-a9ff-812fe3fa7f55" />
<img width="754" height="571" alt="image" src="https://github.com/user-attachments/assets/9cde0d2e-559b-41cc-9b5a-3d8652a4c477" />
Pada plot ACF memiliki lag yang menurun secara perlahan dan pada PACF memiliki nilai yang signifikan di lag 1 dan lag 2. Selain itu pada uji adf memiliki nilai p-value sebesar 0.6417290206734335 dengan artian data belum sattioner karna lebih dari nilai alfa (0,05).
### **Transform to stationary: Differencing**
Differencing merupakan salah satu metode untuk merubah data menjadi stationer, sehingga di dapatkan plot seperti berikut.
<img width="1000" height="513" alt="image" src="https://github.com/user-attachments/assets/60e53161-e1a2-4316-a13c-06d9002428b6" />
Dari plot hasil differencing sudah terlihat bahwa nilai sudah mendekati sekitar 0 dan tidak memiliki nilai tren yang terlalu signifikan, dengan artian data sudah lebih stationer dibandingkan sebelum differencing. Dari hasil adf juga didapatkan nilai p-value sebesar 8.479058744395605e-16 dengan artian nilai tersebut sudah lebih kecil dibandingkan dengan nilai alfa (0,05).
<img width="662" height="509" alt="image" src="https://github.com/user-attachments/assets/bbe1d480-c989-4e4e-8241-d73b9a11daf2" />
<img width="668" height="525" alt="image" src="https://github.com/user-attachments/assets/f80d8efc-07be-488e-9c12-5be5ada7411c" />
Dari plot ACF PACF akan didapatkan model ARMA(p,q), terdapat pada lag ke-1 yang melewati garis signifikan, sehingga didapatkan model ARMA (1,1). 
### **ARIMA Model Manual (1,1,1)**
<img width="272" height="407" alt="image" src="https://github.com/user-attachments/assets/bdf3c552-a69a-44fd-afd3-3dba0bb00d91" />
<img width="1178" height="568" alt="image" src="https://github.com/user-attachments/assets/5f0acbf6-9df7-4450-ace8-b5c015c404ad" />
Dari hasil predict arima menunjukkan bahwa terdapat kenaikan harga setelah Agustus 2025, dimana prediksi ini memiliki kenaikan secara perlahan dan terus mengalami kenaikan dalam waktu dekat.
### **ARIMA Model Auto (0,1,4)**
Dengan menggunakan auto arima didapatkan model ARIMA(0,1,4), sehingga menghasilkan nilai prediksi sebagai berikut.
<img width="281" height="422" alt="image" src="https://github.com/user-attachments/assets/532b67cf-a1c2-4bd4-a019-1a36f9d59b28" />
<img width="1330" height="646" alt="image" src="https://github.com/user-attachments/assets/c9300fdd-c5fd-4d45-9a55-305a8c67f026" />
Dari hasil plot perbandingan antara arima manual dengan arima auto didapatkan hasil bahwa arima manual (1,2,1) memiliki model yang lebih bagus untuk prediksi beberapa periode kedepan dibandingkan dengan arima auto.
### **Perbandingan Nilai MAPE Manual (1,2,1) dengan MAPE Auto (0,1,4)**
<img width="418" height="46" alt="image" src="https://github.com/user-attachments/assets/7cac2bc2-f51e-4e0a-97ef-89844c76eef3" />
<img width="395" height="47" alt="image" src="https://github.com/user-attachments/assets/b7f5f7bc-7487-45fc-be89-1a475b2a9c18" />
Perbandingan antara model arima manual dengan arima auto dapat dilihat dari nilai MAPE dan RMSE, semakin kecil nilai MAPE dan RMSE maka semakin baik akurasi prediksi. Prediksi arima secara manual lebih bagus dibanding arima secara auto baik dari sisi MAPE maupun RMSE. Sehingga Prediksi dengan menggunakan model ARIMA (1,2,1) lebih sesuai untuk melakukan prediksi pada data Saham S&P 500 untuk beberapa periode kedepan.










