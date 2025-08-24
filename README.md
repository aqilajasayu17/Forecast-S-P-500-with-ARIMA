# Forecast-S-P-500-with-ARIMA
### **Time Series Prediction for S&P 500**
Dataset:https://finance.yahoo.com/quote/%5EGSPC/history/

Dataset pada penelitian ini merupakan data dari saha, S&P 500, dimana rentang waktu yang akan diteliti adalah dari 23 Agustus 2024 hingga 23 Agustus 2025. Terdapat enam variabel dan variabel yang akan digunakan adalah variabel "Close", tujuan penggunaan dari variabel tersebut ialah untuk menjadi acuan dalam pengambilan keputusan investasi seperti kapan harus buy, hold, atau sell.

### **Plot Data Aktual**

<img width="1032" height="575" alt="Image" src="https://github.com/user-attachments/assets/957ee466-b33c-4d9b-8bde-f097a52b5128" />
Pada plot terlihat bahwa data sering mengalami fluktuasi, dimana harga sempat naik mulai dari akhir 2024 hingga awal 2025 sekitar 6200-6300 kemudian mengalami penurunan yang sangat signifikan dari Maret hingga April 2025 dan mulai kembali normal yang ditunjukan dengan tren naik mencapai lebih dari 6400 pada Agustus 2025. Kesimpulan dari hasil plot data aktual bahwa harga sempat turun drastis pada awal 2025 yang kemudian kembali normal dengan cepat dan kembali memiliki nilai yang tinggi pada akhir 2025, oleh karena itu pada periode ini memberikan gambaran pasar yang sempat naik turun namun memiliki pemulihan y ang kuat.

### **Check Stationary dengan ADF dan Plot ACF PACF**
Dikarenakan pada data aktual  memiliki pola tren dari awal hingga akhir yang tidak konsisten maka model akan menangkap pola tren tersebut sehingga menyebabkan prediksi yang bias.  Oleh karena itu sebelum melakukan penelitian 
