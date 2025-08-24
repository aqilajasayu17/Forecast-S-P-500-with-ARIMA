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
<img width="1108" height="567" alt="image" src="https://github.com/user-attachments/assets/1662f227-ef2c-4804-9942-072d12cc45c6" />
Dari plot hasil differencing sudah terlihat bahwa nilai sudah mendekati sekitar 0 dan tidak memiliki nilai tren yang terlalu signifikan, dengan artian data sudah lebih stationer dibandingkan sebelum differencing.
<img width="749" height="576" alt="image" src="https://github.com/user-attachments/assets/72ff332e-2ddc-435c-a4a6-2e315f9a42bd" />
<img width="752" height="581" alt="image" src="https://github.com/user-attachments/assets/6d19b139-fa35-4931-8b80-ae7fefac4e9a" />
Dari plot ACF PACF akan didapatkan model ARMA(p,q), terdapat pada lag ke-3 yang melewati garis signifikan, sehingga didapatkan model ARMA (3,3). 










