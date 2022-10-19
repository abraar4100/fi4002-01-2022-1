# 10219015
Muhammad Abraar Abhirama


## materi sebelumnya
+ Pada perkuliahan-perkuliahan sebelumnya, materi perkuliahan yang telah diajarkan ialah sebagai berikut:
- Metode Runge-Kutta Orde 1,2,3, dan 4
- Metode Euler
- Metode Monte-Carlo
- Metode Transformasi Fourier


## materi paling menarik
+ Materi paling menarik yang diajarkan menurut saya ialah transformasi Fourier. Hal ini dikarenakan transformasi Fourier dapat menggambarkan suatu keadaan fisis dalam bentuk deret matematis yang dapat terlihat polanya. Menurut saya, penggambaran pola deret ini sangat berguna untuk mengetahui pola periodisitas dari suatu sistem fisis. Materi Metode Monte-Carlo juga sangat menarik karena ada kesan "tricky" yang saya rasakan, namun saya belum 100% memahami materinya.


## materi paling membosankan
+  Materi yang paling membosankan menurut saya adalah Metode Euler dan Runge-Kutta. Hal ini sebenarnya tidak membosankan, hanya saja kedua metode ini menurut saya hanya memodelkan persamaan diferensial ke dalam model numerik. Berbeda jika dibandingkan dengan Fourier yang memiliki gagasan bahwasannya suatu fungsi fisis dapat dimodelkan ke dalam bentuk deret.


## materi yang sudah dipahami
+ Sejauh ini materi yang paling saya mengerti adalah materi mengenai Metode Euler dan Runge-Kutta. Saya memahami bagaimana algoritma kedua metode tersebut berjalan. Selain itu permasalahan fisis yang diberikan juga masih sederhana (Predator-Prey), sehingga saya masih dapat mengerti materi ini.


## materi yang belum dipahami
+ Sejauh ini materi yang belum saya pahami adalah materi metode Monte-Carlo dikarenakan masih terdapat kesan "tricky" yang belum saya pahami. Kesan "tricky" yang saya rasakan adalah antara lain - melakukan looping di dalam looping (nested), melakukan looping/iterasi terhadap list, dan juga beberapa ide lainnya yang sekiranya menuntut sense of programming yang cukup tinggi


## contoh program
#### Step 1: Mengimport library yang diperlukan
import matplotlib.pyplot as plt
import numpy as np

#### Step 2: Mendefinisikan metode Runge-Kutta orde 04 (rk4) sebagai fungsi
def rk04(r, t, h):                    
        k0 = h*f(r, t)
        k1 = h*f(r+0.5*k0, t+0.5*h)
        k2 = h*f(r+0.5*k1, t+0.5*h)
        k3 = h*f(r+k2, t+h)
        return (k0 + 2*k1 + 2*k2 + k3)/6
        
##### Step 3: Mendefinisikan fungsi Predator-Prey    
#variabel a,b,c, dan d adalah variabel tebakan yang nantinya 
def f(r, t):
        a = 1
        b = 0.2
        c = 0.5
        d = 0.2
        x, y = r[0], r[1] #x dan y perlu didefinisikan sebagai elemen array ke-0 (r[0]) dan ke-1 (r[1]) agar nantinya dapat selalu di-update dari setiap iterasi yang ada
        fxd = x*(a - b*y)
        fyd = -y*(c - d*x)
        return np.array([fxd, fyd], float) #fungsi ini akan memiliki output berupa array  yang dimensinya tersusun dari fxd dan fyd yang merupakan model dari predator-prey
 
##### Step 4: Mendefinisikan step/partisi untuk setiap iterasi
dt=0.001 #partisi waktu
tpoints = np.arange(0, 75, dt) #seberapa banyak iterasi yang diinginkan     
xpoints, ypoints  = [], [] #list kosong untuk setiap variabel x dan y untuk nantinya diupdate lalu di-append (storing) ke list xpoints dan ypoints
r = np.array([2, 2], float) #mendefinisikan array 2x2 bertipe bilangan float yang nantinya 
for t in tpoints:
        xpoints.append(r[0])#mengupdate elemen array ke-0 menjadi variabel xpoints terbaru untuk setiap iterasi        
        ypoints.append(r[1])#mengupdate elemen array ke-1 menjadi variabel ypoints terbaru untuk setiap iterasi            
        r += rk04(r, t, dt) #mengupdate nilai dari metode Runge-Kutta untuk setiap iterasi

##### Step 5: Menampilkan hasil plotting grafik
plt.title("Predator-Prey")
plt.plot(tpoints,xpoints,"k", label = "Domba (Prey)")
plt.plot(tpoints,ypoints,"r", label = "Serigala (Predator)")
plt.legend()
plt.xlabel("Waktu")
plt.ylabel("Populasi")
plt.savefig("SPSF.png") #menyimpan gambar dalam format .png
plt.show()

Hasilnya adalah sebagai berikut




## cara perkuliahan
+ Saya cenderung menyukai perkuliahan SPSF yang lebih banyak melakukan hands-on dengan topik-topik komputasi fisis masa kini seperti halnya clustering, neural network, dan mungkin juga kecerdasan buatan (AI). Harapan saya melalui perkuliahan ini saya mendapat banyak pandangan baru mengenai komputasi fisis.


## topik sistem fisis
+ Topik mengenai forecasting. Menurut saya topik ini sangat menarik untuk dipelajari apapun jenis forecastingnya. Karena menurut saya seluruh sistem fisis dapat diprediksi melalui. forecasting, terutama untuk sistem yang depended terhadap waktu. Berdasarkan pemahaman saya, forecasting/prediksi dapat dilakukan dengan beberapa metode seperti halnya Neural Network, SVR, SVM, dll. Namun pada intinya yang dipelajari adalah bagaimana memahami looping berjalan (looping bobot, dan beberapa konsep komputasi lainnya.


## simulasi dan visualisasi
+ Topik yang berkaitan dengan prediksi (apapun metodenya) menurut saya sangat menarik untuk dipelajari. Mungkin dapat dimulai dari sejenis Support Vector Machine (SVM) dan juga Support Vector Regression (SVR). Hal ini sangat menarik dikarenakan selalu ada kemungkinan/kesempatan untuk meninjau proses stokastik dari suatu sistem fisis. Sekiranya pustaka Python yang akan digunakan adalah Pandas (Python for Data Analysis) untuk memanipulasi dataframe, NumPy (Numerical Python) untuk melakukan komputasi numerik, dan SciPy (Scientific Python) untuk komputasi matematis yang lebih lanjut serta untuk memvisualisasi data.
