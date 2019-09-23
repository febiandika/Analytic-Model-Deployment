# Analytic-Model-Deployment

## 1. Deploy Model Credit Scoring 
Model ini digunakan untuk melakukan credit scoring dengan menggunakan algoritma Random Forest untuk memprediksi apakah suatu konsumen akan terlambat membayar kredit pada bulan ke-empat.
<br>
Variabel yang digunakan untuk melakukan penghitungan credit scoring adalah:
<br>
* PAY_AMT1 : Jumlah pembayaran kredit yang dilakukan pelanggan pada bulan pertama.
* PAY_AMT2 : Jumlah pembayaran kredit yang dilakukan pelanggan pada bulan kedua.
* PAY_AMT3 : Jumlah pembayaran kredit yang dilakukan pelanggan pada bulan ketiga.
<br>
Output yang dihasilkan ada 2, yaitu:
<br>
0: Pelanggan diprediksi tidak akan telat melakukan pembayaran kredit
1: Pelanggan diprediksi akan telat melakukan pembayaran kredit

## 2. Make server on pythonanywhere
Untuk membuat suatu model deployment, digunakan pythonanywhere untuk membuat server untuk model yang telah dibuat. Pada pythonanywhere terdapat dua file yang diupload dalam pythonanywhere dan yang digunakan yaitu :
<br>
* modelcs.pkl : file yang berisi model Random Forest yang digunakan untuk melakukan credit scoring.
* flask_app.py : file yang digunakan sebagai file "server" yang tersimpan didalam pythonanywhere. Untuk isi dari flask_app.py yang saya buat dapat dilihat di : https://www.pythonanywhere.com/user/febiandika12/shares/09f5710b7fcc48f29820edde2d7f2bb8/ 

## 3. Menguji model dengan menggunakan postman
### 3.1 Cara menggunakan postman
1. Pertama kali, gunakan google chrome untuk menggunakan postman. Hal ini dikarenakan postman yang akan digunakan merupakan ekstensi dari google chrome.
2. Install ekstensi postman pada google chrome dengan menggunakan keyword 'postman chrome'.
3. Setelah terinstall jalankan aplikasi postman sehingga muncul tampilan sebagai berikut.

4. Lalu, pilih 'POST' pada kotak berwarna merah dan pada kotak berwarna biru isikan alamat API saya : http://febiandika12.pythonanywhere.com/api
5. Selanjutnya, pilih tab Body -> raw -> JSON(application/json)
6. Masukan data yang akan diuji dengan cara sebagai berikut :
* **Untuk 1 input data**
* **Untuk lebih dari 1 input data**
