# Tugas-Akhir-Pemodelan-Oseanografi-Kelompok-13
Repositori ini dibuat untuk memenuhi Tugas Akhir Praktikum Pemodelan Oseanografi 2022. Pengerjaan untuk repositori kali ini menggunakan bahasa pemrograman python yang dapat dilakukan pada beberapa platform seperti Jupyter Notebook dan Google Colaboratory. Sedangkan untuk library yang digunakan kali ini adalah Matplotlib dan Numpy. Seluruh script yang dibuat adalah hasil Kelompok 13 Oseanografi 2020. Semoga bermanfaat!
# Authors (Kelompok 13)
1. Diva Arivannisa
2. Faiz Firman Barmawi
3. Fina Naafiatur Rofiqoh (26050120120017)
4. Mujieb Hariz Herlambang (26050120130114)
5. Putri Salwa Adilah
6. Rheyhan Adwimadiputra
7. Zhikrillah Qalbhin Naim
# Installasi Library
1. Matplotlib: merupakan library yang digunakan untuk visualisasi data seperti pembuatan plot grafik.\
Dapat di install menggunakan:
```
pip install matplotlib
```
```
conda install matplotlib
```
```
conda install -c conda-forge matplotlib
```
3. Numpy: merupakan library yang berfungsi untuk memproses komputasi numerik seperti vektor dan matriks.\
Dapat di install menggunakan:
```
pip install numpy
```
```
conda install numpy
```
# Modul 1 - Adveksi Difusi 1 Dimensi
## Adveksi
Adveksi merupakan mekanisme perpindahan massa suatu materi dari suatu titik ke titik lainnya. Adveksi berkaitan dengan aliran fluida. Adveksi dapat digambarkan menggunakan **Persamaan Gelombang Linier Orde 1** dan termasuk dalam persamaan diferensial hiperbolik yang menggambarkan mekanisme transportasi suatu gas atau zat cair dengan arah tertentu. Terdapat 2 tipe persamaan yaitu eksplisit dan implisit.
* Eksplisit
1. Terdapat stabilitas hitungan.
2. Hitungannya lebih mudah.
3. Pengkodingan lama dan sulit.
* Implisit
1. Tidak terdapat stabilitas hitungan.
2. Hitungannya lebih sulit.
3. Pengkodingan mudah dan cepat.

Persamaan Utama\
![image](https://user-images.githubusercontent.com/106014055/169699063-e2c71dbc-e757-40e0-80d9-7b419cb727bd.png)\
Keterangan:\
F = Konsentrasi suatu zat\
t = waktu\
U = kecepatan\
x = arah sumbu horizontal\

Persamaan Turunan
* FTCS _(Forward Time Central Space)_\
  FTCS merupakan gabungan dari selisih maju terhadap waktu dan selisih pusat terhadap ruang. Solusi FTCS juga termasuk ke dalam solusi stabil bersyarat.\
  ![image](https://user-images.githubusercontent.com/106014055/169700950-1df4f8d5-fcac-4b25-9c0e-60a3d1ab0d27.png)

  Syarat Kestabilan:\
  ![image](https://user-images.githubusercontent.com/106014055/169700736-3e7b36f3-d4a6-4c14-a3c7-cacc25e14985.png)
  
  Diskritisasi FTCS\
  ![image](https://user-images.githubusercontent.com/106014055/169703085-3ac5df99-8c84-4b5d-97b9-234f70285584.png)

* Leapfrog\
  Metode Leapfrog atau metode beda hingga ini merupakan perluasan dari metode beda tengah _(Central Difference)_ terhadap ruang dan waktu. Skema Leapfrog didapatkan dari turunan deret taylor, yang merupakan skema yang konsisten. Metode Leapfrog ini akan konsisten apabila nilai dari C kurang dari atau sama dengan 1.\
 ![image](https://user-images.githubusercontent.com/106014055/169701321-e18b53b2-dde3-451c-9ef4-e32533818dbe.png)\
 dimana nilai C adalah:\
 ![image](https://user-images.githubusercontent.com/106014055/169701393-349dc247-3f2d-4368-a458-d20d75125082.png)
 
* Upstream\
  Merupakan skema yang digunakan untuk melengkapi ketidaksempurnaan dari metode Leapfrog. Karena, nilai konsentrasi dalam komputer dan lapangan seringkali tidak selaras. Untuk menguji metode Upstream ini dibuat untuk model positif dari konsentrasi di alam yang merujuk ke laut.\
  Metode ini menggunakan pendekatan beda maju untuk turunan waktu. Sedangkan untuk turunan terhadap ruang dilakukan dengan melihat arah kecepatan u dan o.\
  -u > 0 : menggunakan pendekatan beda mundur
  -u < 0 : menggunakan pendekatan beda maju.
  
  Stabilitas metode Upstream:\
  ![image](https://user-images.githubusercontent.com/106014055/169701969-1648c443-e085-4e64-971a-f81d2d491673.png)

## Difusi
Merupakan suatu proses dimana suatu zat bergerak dari konsentrasi tinggi ke rendah. Pada difusi ini, diskritisasi dilakukan secara eksplisit (FTCS) dengan eksplisit continue maupun discontinue. Syarat batas terpebuhi sama dengan *overflow*.
Contoh aplikasi difusi di bidang Oseanografi adalah Oil Spill.

Persamaan dasar\
![image](https://user-images.githubusercontent.com/106014055/169703386-c7c24ec5-63b4-4cf7-a0d7-5fc69466d685.png)

# Modul 2 - Adveksi Difusi 2 Dimensi
# Modul 3 - Model Hidrodinamika 1 Dimensi
# Modul 4 - Model Hidrodinamika 2 Dimensi
# Penutup
