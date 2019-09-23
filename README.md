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
<br>
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

![contoh](https://raw.githubusercontent.com/febiandika/Analytic-Model-Deployment/master/Capture1.PNG)

4. Lalu, pilih 'POST' pada kotak berwarna merah dan pada kotak berwarna biru isikan alamat API saya : http://febiandika12.pythonanywhere.com/api

![contoh1](https://raw.githubusercontent.com/febiandika/Analytic-Model-Deployment/master/Capture3.png)

5. Selanjutnya, pilih tab Body -> raw -> JSON(application/json) seperti berikut:

![contoh2](https://raw.githubusercontent.com/febiandika/Analytic-Model-Deployment/master/Capture4.png)

6. Masukan data yang akan diuji. Data dibentuk menjadi bentuk JSON dengan menuliskan data dengan cara sebagai berikut :
* **Untuk 1 input data**
<br>
{		
    "PAY_AMT1":1000,
    "PAY_AMT2":1500,
    "PAY_AMT3":1000
}
<br>
<br>

* **Untuk lebih dari 1 input data (dalam contoh ini 10 data dan untuk lebih jelasnya bisa dilihat di file dataset.txt)**
<br>
[{
		"PAY_AMT1":1000,
		"PAY_AMT2":1500,
		"PAY_AMT3":1000
{
		"PAY_AMT1":2000,
		"PAY_AMT2":1500,
		"PAY_AMT3":2400
	
},
{		"PAY_AMT1":2600,
		"PAY_AMT2":1200,
		"PAY_AMT3":2100
	
},
{		"PAY_AMT1":2300,
		"PAY_AMT2":1800,
		"PAY_AMT3":1300
	
},
{		"PAY_AMT1":1350,
		"PAY_AMT2":2300,
		"PAY_AMT3":1200
	
},
{		"PAY_AMT1":4300,
		"PAY_AMT2":2100,
		"PAY_AMT3":1200
	
},
{		"PAY_AMT1":2100,
		"PAY_AMT2":1300,
		"PAY_AMT3":1500
	
},
{		"PAY_AMT1":2500,
		"PAY_AMT2":2300,
		"PAY_AMT3":2200
	
},
{		"PAY_AMT1":1200,
		"PAY_AMT2":1300,
		"PAY_AMT3":1400
	
},
{		"PAY_AMT1":1320,
		"PAY_AMT2":1460,
		"PAY_AMT3":2340
}]
<br>
Catatan : Nilai diatas hanya contoh, bisa diganti sesuai dengan data yang dimiliki pengguna.
<br>
Masukkan data pada bagian sebagai berikut:
<br>
![contoh3](https://raw.githubusercontent.com/febiandika/Analytic-Model-Deployment/master/Capture5.PNG)
<br>
7. Melihat output pada bagian sebagai berikut:
![contoh4](https://raw.githubusercontent.com/febiandika/Analytic-Model-Deployment/master/Capture6.PNG)
