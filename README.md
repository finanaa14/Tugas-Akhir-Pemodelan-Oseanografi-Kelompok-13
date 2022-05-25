# Tugas-Akhir-Pemodelan-Oseanografi-Kelompok-13🌊
Repositori ini dibuat untuk memenuhi Tugas Akhir Praktikum Pemodelan Oseanografi 2022. Pengerjaan untuk repositori kali ini menggunakan bahasa pemrograman python yang dapat dilakukan pada beberapa platform seperti Jupyter Notebook dan Google Colaboratory. Sedangkan untuk *library* yang digunakan kali ini adalah Matplotlib, Numpy, dan Siphon. Seluruh *script* yang dibuat adalah hasil Kelompok 13 Oseanografi 2020. Semoga bermanfaat!
# Authors 👥
1. Diva Arivannisa (26050120140123)
2. Faiz Firman Barmawi
3. Fina Naafiatur Rofiqoh (26050120120017)
4. Mujieb Hariz Herlambang (26050120130114)
5. Putri Salwa Adilah (26050120140152)
6. Rheyhan Adwimadiputra
7. Zhikrillah Qalbhin Naim (26050120140155)
# Installasi 🖥️
**Matplotlib**\
Merupakan *library* yang digunakan untuk visualisasi data seperti pembuatan plot grafik.\
Dapat di *install* menggunakan:
```
pip install matplotlib
```
```
conda install matplotlib
```
```
conda install -c conda-forge matplotlib
```
***Numpy***\
Merupakan *library* yang berfungsi untuk memproses komputasi numerik seperti vektor dan matriks.\
Dapat di *install* menggunakan:
```
pip install numpy
```
```
conda install numpy
```
**Siphon**
Merupakan *library* yang digunakan untuk mengunduh data dari web lain.\
Dapat di *install* menggunakan
```
pip install siphon
```
# Modul 1 - Adveksi Difusi 1 Dimensi📝
## Adveksi
Adveksi merupakan mekanisme perpindahan massa suatu materi dari suatu titik ke titik lainnya. Adveksi ini biasanya berkaitan dengan aliran fluida. Adveksi dapat digambarkan menggunakan **Persamaan Gelombang Linier Orde 1** dan termasuk dalam persamaan diferensial hiperbolik yang menggambarkan mekanisme transportasi suatu gas atau zat cair dengan arah tertentu. Terdapat 2 tipe persamaan yaitu eksplisit dan implisit.
* Eksplisit
1. Terdapat stabilitas hitungan.
2. Hitungannya lebih mudah.
3. Pengkodingan lama dan sulit.
* Implisit
1. Tidak terdapat stabilitas hitungan.
2. Hitungannya lebih sulit.
3. Pengkodingan mudah dan cepat.

**Persamaan Utama**\
![image](https://user-images.githubusercontent.com/106014055/169699063-e2c71dbc-e757-40e0-80d9-7b419cb727bd.png)\
Keterangan:\
F = Konsentrasi suatu zat\
t = waktu\
U = kecepatan\
x = arah sumbu horizontal

**Persamaan Turunan**
* **FTCS _(Forward Time Central Space)_**\
  FTCS merupakan gabungan dari selisih maju terhadap waktu dan selisih pusat terhadap ruang. Solusi FTCS juga termasuk ke dalam solusi stabil bersyarat.\
  ![image](https://user-images.githubusercontent.com/106014055/169700950-1df4f8d5-fcac-4b25-9c0e-60a3d1ab0d27.png)

  Syarat Kestabilan:\
  ![image](https://user-images.githubusercontent.com/106014055/169700736-3e7b36f3-d4a6-4c14-a3c7-cacc25e14985.png)
  
  Diskritisasi FTCS\
  ![image](https://user-images.githubusercontent.com/106014055/169703085-3ac5df99-8c84-4b5d-97b9-234f70285584.png)

* **Leapfrog**\
  Metode Leapfrog atau metode beda hingga ini merupakan perluasan dari metode beda tengah _(Central Difference)_ terhadap ruang dan waktu. Skema Leapfrog didapatkan dari turunan deret taylor, yang merupakan skema yang konsisten. Metode Leapfrog ini akan konsisten apabila nilai dari C kurang dari atau sama dengan 1.\
 ![image](https://user-images.githubusercontent.com/106014055/169701321-e18b53b2-dde3-451c-9ef4-e32533818dbe.png)\
 dimana nilai C adalah:\
 ![image](https://user-images.githubusercontent.com/106014055/169701393-349dc247-3f2d-4368-a458-d20d75125082.png)
 
* **Upstream**\
  Merupakan skema yang digunakan untuk melengkapi ketidaksempurnaan dari metode Leapfrog. Karena, nilai konsentrasi dalam komputer dan lapangan seringkali tidak selaras. Untuk menguji metode Upstream ini dibuat untuk model positif dari konsentrasi di alam yang merujuk ke laut.\
  Metode ini menggunakan pendekatan beda maju untuk turunan waktu. Sedangkan untuk turunan terhadap ruang dilakukan dengan melihat arah kecepatan u dengan ketentuan sebagai berikut:\
  u > 0 : menggunakan pendekatan beda mundur\
  u < 0 : menggunakan pendekatan beda maju.
  
  Stabilitas metode Upstream:\
  ![image](https://user-images.githubusercontent.com/106014055/169701969-1648c443-e085-4e64-971a-f81d2d491673.png)

## Difusi
Merupakan suatu proses dimana suatu zat bergerak dari konsentrasi tinggi ke rendah. Pada difusi ini, diskritisasi dilakukan secara eksplisit (FTCS) dengan eksplisit continue maupun discontinue. Syarat batas terpebuhi sama dengan *overflow*.
Contoh aplikasi difusi di bidang Oseanografi adalah **Oil Spill**.

Persamaan dasar\
![image](https://user-images.githubusercontent.com/106014055/169703386-c7c24ec5-63b4-4cf7-a0d7-5fc69466d685.png)

# Modul 2 - Adveksi Difusi 2 Dimensi📍
Adveksi Difusi 2 Dimensi  menggunakan persamaan yang telah dimodifikasi untuk menggambarkan pemodelan dalam 2 dimensi seperti dalam x dan y, x dan z, maupun y dan z. Dalam Adveksi Difusi 2 Dimensi ini menggunakan persamaan sebagai berikut:
1. Persamaan Adveksi 2 Dimensi\
![image](https://user-images.githubusercontent.com/106014055/170067742-437d1654-53e3-445f-88e6-ecfbe942367d.png)

3. Persamaan Difusi 2 Dimensi\
![image](https://user-images.githubusercontent.com/106014055/170067970-b8692362-2401-4867-bee1-10c2df3dc02b.png)

5. Diskritisasi Suku Adveksi 2 Dimensi\
![image](https://user-images.githubusercontent.com/106014055/170070084-efe2242c-0144-44e1-b25c-15662d8e9cc7.png)

7. Diskritisasi Suku Difusi 2 Dimensi\
![image](https://user-images.githubusercontent.com/106014055/170071462-8bea2921-d525-48df-b204-917741f61628.png)

9. Diskritisasi Gabungan Adveksi Difusi 2 Dimensi\
![image](https://user-images.githubusercontent.com/106014055/170077808-3f17d7ca-7253-4c87-9948-f92468c4c532.png)

11. Syarat Batas\
Menggambarkan kondisi ruang maupun waktu dari model yang di bangun. Menggunakan syarat batas sebagai berikut:\
![image](https://user-images.githubusercontent.com/106014055/170155991-f419975e-2f78-4151-ae62-fabda0bd17ac.png)

13. Pemotongan Iterasi\
Pemotongan iterasi dapat dilakukan apabila telah mencapai batas sebagai berikut:\
![image](https://user-images.githubusercontent.com/106014055/170156382-4f6e18f9-6c53-4777-b97f-2e133f6055e3.png)

15. Kriteria Kestabilan\
Merupakan metode untuk menentukan seberapa besar nilai stabilitasdari model yang dibangun.\
![image](https://user-images.githubusercontent.com/106014055/170157206-8724b151-f1e3-4825-bfd9-512718c4e78c.png)

**Script** yang digunakan untuk memodelkan adveksi difusi 2 dimensi adalah sebagai berikut:
1. _Library_ yang digunakan
```
import matplotlib.pyplot as plt
import numpy as np
import sys
```
2. Pendefinisian 
```
def percentage(part, whole):
    percentage = 100 * float(part)/float(whole)
    return str(round(percentage,2)) + "x"
```
3. Penentuan Parameter Awal
```
# parameter awal 
C = 0.41
Ad = 1.41

# arah arus (berdasar *geographic convention*)
theta = 41
#theta = 101
#theta = 176
#theta = 356

# parameter lanjutan
q = 0.95    #kriteria kestabilan
x = 300     #Jumlah grid horizontal x
y = 300     #jumlah grid vertikal y
dx = 3
dy = 3

# lama simulasi
Tend = 104
#Tend = 1
dt = 0.5
#Polutan 
px = 150
py = 134
Ic = 514
```
3. Perhitungan U dan V
```
u = C * np.sin(theta*np.pi/180)
v = C * np.cos(theta*np.pi/180)
dt_count = 1/((abs(u)/q*dx))+(abs(v)/(q*dy))+(2*Ad/(q*dx**2))+(2*Ad/q*dy**2)

Nx = int(x/dx)      #number of mesh in x direction
Ny = int(y/dy)      #number of mesh in y direction
Nt = int(Tend/dt)   #number of timesteps
```
4. Perhitungan titik polutan dibuang
```
px1 = int(px/dx)
py1 = int(py/dy)
```
5. Penyederhanaan fungsi dan perhitungan CFL
```
lx = u*dt/dx
ly = v*dt/dy
ax = Ad*dt/dx**2
ay = Ad*dt/dy**2
cfl = (2*ax + 2*ay + abs(lx) + abs(ly))     #syarat kestabilan cfl
#perhitungan CFL
if cfl >= q:
    print('CFL Violated, please use dt :' + str(round(dt_count,4)))
    sys.exit()
```
6. Pembuatan grid
```
x_grid = np.linspace(0-dx, x+dx, Nx+2)      #ghostnode pada boundary
y_grid = np.linspace(0-dx, y+dy, Ny+2)
t = np.linspace(0, Tend, Nt+1)
x_mesh,y_mesh = np.meshgrid(x_grid,y_grid)
F = np.zeros((Nt+1, Ny+2, Nx+2))

#kondisi awal
F[0,py1,px1] = Ic
```
7. Iterasi 
```
for n in range (0,Nt):
    for i in range (1,Ny+1):
        for j in range(1,Nx+1):
            F[n+1,i,j]=((F[n,i,j]*(1-abs(lx)-abs(ly))) + \
                (0.5*(F[n,i-1,j]*(ly+abs(ly)))) + \
                (0.5*(F[n,i+1,j]*(abs(ly)-ly))) + \
                (0.5*(F[n,i,j-1]*(lx+abs(lx)))) + \
                (0.5*(F[n,i,j+1]*(abs(lx)-lx))) + \
                (ay*(F[n,i+1,j]-2*(F[n,i,j])+F[n,i-1,j])) +\
                (ax*(F[n,i,j+1]-2*(F[n,i,j])+F[n,i,j-1])))
```
8. Syarat batas
```
 F[n+1,0,:] = 0 #BC bawah
 F[n+1,:,0] = 0 #BC kiri
 F[n+1,Ny+1,:] = 0 #BC atas
 F[n+1,:,Nx+1] = 0 #BC kanan
```
9. Pembuatan output gambar
```
plt.clf()
plt.pcolor(x_mesh, y_mesh, F[n+1,:,:],cmap = 'jet',shading = 'auto',edgecolors = 'k')
cbar = plt.colorbar(orientation = 'vertical', shrink = 0.95, extend = 'both')
cbar.set_label(label='concentration', size = 8)

#plt.clim(0,100)
plt.title('Nama_NIM \n t= '+ str(round(dt*(n+1),3))+', Initial Condition='+str(Ic), fontsize = 10)
plt.xlabel('x_grid', fontsize = 9)
plt.ylabel('y_grid', fontsize = 9)
plt.axis([0, x, 0, y])
#plt.pause(0.01)
plt.savefig(str(n+1)+' .jpg', dpi = 300)
plt.pause(0.01)
plt.close()
print('running timestep ke: ' + str(n+1) + ' dari: ' + str(Nt) + '('+ percentage(n+1,Nt)+')')
print( ' Nilai CFL: ' +str(cfl) + 'dengan arah:' +str(theta))
```
Berikut merupakan contoh *output* yang dihasilkan dari *script* diatas:
![208 ](https://user-images.githubusercontent.com/106015581/170193151-6720953b-397e-49a8-a0b4-ce1f986a73e5.jpg)

# Modul 3 - Model Hidrodinamika 1 Dimensi📈
**Hidrodinamika** adalah ilmu yang mempelajari tentang pergerakansuati fluida.\
**Model hidrodinamika** merupakan model yang dibangun dari adanya proses-proses yang mempengaruhi massa air. Dalam pemodelan hidrodinamika berlaku **Hukum Konservasi Massa/Kontinuitas** dan **Hukum Momentum**. Pemodelan hidrodinamika ini mensimulasikan elevasi muka air laut dan arus yang dipengaruhi oleh beberapa parameter.
1. Persamaan Momentum
![pers momentum](https://user-images.githubusercontent.com/106015581/170194368-efa49f99-2f8d-431c-94cd-93ca71eb2c9a.JPG)
2. Persamaan Kontinuitas

3. Persamaan Pembangun

4. Persamaan Transport

5. Diskritisasi

Keterangan:

**Kelemahan Model Hidrodinamika:**
1. Memerlukan banyak data
2. Rawan terjadinya *error* ketika terdapat perhitungan aliran kritis
3. Simulasi atau *running* memerlukan waktu yang lama dengan timestep yang cenderung harus kecil

Berikut merupakan *script* yang dapat digunakan untuk model hidrodinamika 1 dimensi
1. *Import Library*
```
import matplotlib.pyplot as plt
import numpy as np
```
2. Proses Awal
```
p = 5000 #Panjang Grid
T = 1200 #Waktu Simulasi 
A = 0.5 #Amplitudo
D = 15 #Depth/kedalaman
dt = 2
dx = 100
To = 300 #Periode
```
3. Parameter Lanjutan
```
g = 9.8
pi = np.pi
C = np.sqrt(g*D) #Kecepatan Arus
s = 2*pi/To #Kecepatan Sudut Gelombang
L = C*To #Panjang Gelombang
k = 2*pi/L #Koefisien Panjang Gelombang
Mmax = int(p//dx)
Nmax = int(T//dt) 
```
4. Penyelesaian Persamaan Hidrodinamika 1D
```
zo = [None for _ in range(Mmax)]
uo = [None for _ in range(Mmax)]

hasilu = [None for _ in range(Nmax)]
hasilz = [None for _ in range(Nmax)]

for i in range(1, Mmax+1):
    zo[i-1] = A*np.cos(k*(i)*dx)
    uo[i-1] = A*C*np.cos(k*((i)*dx+(0.5)*dx))/(D+zo[i-1])
for i in range(1, Nmax+1):
    zb = [None for _ in range(Mmax)]
    ub = [None for _ in range(Mmax)]
    zb[0] = A*np.cos(s*(i)*dt)
    ub[-1] = A*C*np.cos(k*L-s*(i)*dt)/(D+zo[-1])
    for j in range(1, Mmax):
        ub[j-1] = uo[j-1]-g*(dt/dx)*(zo[j]-zo[j-1])
    for k in range(2, Mmax+1):
        zb[k-1] = zo[k-1]-(D+zo[k-1])*(dt/dx)*(ub[k-1]-ub[k-2])
        hasilu[i-1] = ub
        hasilz[i-1] = zb
    for p in range(0, Mmax):
        uo[p] = ub[p]
        zo[p] = zb[p]

def rand_col_hex_string():
    return f'#{format(np.random.randint(0,16777215), "#08x")[2:]}'

hasilu_np = np.array(hasilu)
hasilz_np = np.array(hasilz)
```
5. Pembuatan Grafik
```
def rand_col_hex_string():
  return f'#(format(np.random.randint(0.16777215), "#08x")[2:1]}'

hasilu_np = np.array(hasilu)
hasilz_np = np.array(hasilz)

fig0, ax0 = plt.subplots(figsize=(12,8))
for i in range(1, 16):
    col0 = rand_col_hex_string()
    line, = ax0.plot(hasilu_np[:,i-1], c=col0, label=f'n={i}')
    ax0.legend()

    ax0.set(xlabel='Waktu', ylabel='Kecepatan Arus',
            title=''' 
            Perubahan Kecepatan Arus Dalam Grid Tertentu di sepanjang Waktu''')
    ax0.grid()

fig1, ax1 = plt.subplots(figsize=(12,8))
for i in range(1, 16):
    col1 = rand_col_hex_string()
    line, = ax1.plot(hasilz_np[:,i-1], c=col1, label=f'n={i}')
    ax1.legend()

    ax1.set(xlabel='Waktu', ylabel='Elevasi Muka Air',
            title=''' 
            Perubahan Elevasi Permukaan Air Dalam Grid Tertentu di sepanjang Waktu''')
    ax1.grid()

fig2, ax2 = plt.subplots(figsize=(12,8))
for i in range(1, 16):
    col2 = rand_col_hex_string()
    line, = ax2.plot(hasilu_np[i-1], c=col2, label=f't={i}')
    ax2.legend()

    ax2.set(xlabel='Grid', ylabel='Kecepatan Arus',
            title=''' 
            Perubahan Kecepatan Arus Dalam Waktu Tertentu di sepanjang Grid''')
    ax2.grid()

fig3, ax3 = plt.subplots(figsize=(12,8))
for i in range(1, 16):
    col3 = rand_col_hex_string()
    line, = ax3.plot(hasilz_np[i-1], c=col3, label=f't={i}')
    ax3.legend()

    ax3.set(xlabel='Grid', ylabel='Elevasi Muka Air',
            title=''' 
            Perubahan Elevasi Permukaan Air Dalam Waktu Tertentu di sepanjang Grid''')
    ax3.grid()

plt.show()
```
Hasil *running* yang diperoleh dari script diatas adalah sebagai berikut:
1. Perubahan Elevasi Permukaan Air Dalam Grid Tertentu di Sepanjang Waktu\
![perubahan elevasi permukaan air dalam grid tertentu](https://user-images.githubusercontent.com/106014055/170155230-15254dee-5bb0-4fbd-b4a2-11e62e4828f2.png)

2. Perubahan Elevasi Permukaan Air Dalam Waktu Tertentu di Sepanjang Grid\
![perubahan elevasi permukaan air dalam waktu tertentu](https://user-images.githubusercontent.com/106014055/170155258-629579f3-edfd-441b-bcea-aaa071e1247a.png)

3. Perubahan Kecepatan Arus Dalam Grid Tertentu di Sepanjang Waktu\
![perubahan kecepatan arus dalam grid tertentu](https://user-images.githubusercontent.com/106014055/170155286-f73898ed-280c-4897-98b7-a716a3d348ea.png)

4. Perubahan Kecepatan Arus Dalam Waktu Tertentu di Sepanjang Grid\
![perubahan kecepatan arus dalam waktu tertentu](https://user-images.githubusercontent.com/106014055/170155319-40131652-0720-4e8c-9a7d-60a9295023d5.png)

# Modul 4 - Model Hidrodinamika 2 Dimensi📊
Pada modul 4 ini, data yang digunakan adalah data _real time_ dari buoy yang berada di lapangan. Data buoy yang digunakan berasal dari data _National Data Buoy Center_ yang dimiliki oleh NOAA. Output yang dihasilkan dari pemodelan akan menunjukkan tiga grafik, yaitu grafik kecepatan dan arah angin, tekanan udara, dan suhu perairan terhadap waktu. Dari output tersebut kemudian dianalisis untuk mengetahui korelasi antara parameter yang ada.
*Script* yang dapat digunakan untuk model hidrodinamika 2 dimensi adalah sebagai berikut:

1. _Library_ yang digunakan
```
import matplotlib.pyplot as plt
from siphon.simplewebservice.ndbc import NDBC
```
2. Memasukkan _station id_ buoy NDBC. _Station ID_ dapat dilihat pada laman _https://www.ndbc.noaa.gov/_
```
df = NDBC.realtime_observations('AAMC1') #station ID
df.head()
```
3. Pembuatan grafik
```
fig, (ax1, ax2, ax3) = plt.subplots(3, 1, figsize=(12,10))
ax2b = ax2.twinx()

#pressure
ax1.plot(df['time'], df['pressure'], color='black')
ax1.set_ylabel('Pressure [hPa]')
fig.suptitle('Mujieb Hariz Herlambang_26050120130114_A', fontsize=18)


#wind speed, gust, direction
ax2.plot(df['time'], df['wind_speed'], color='tab:orange')
ax2.plot(df['time'], df['wind_gust'], color='tab:olive', linestyle='--')
ax2b.plot(df['time'], df['wind_direction'], color='tab:blue', linestyle='-')
ax2.set_ylabel('Wind Speed [m/s]')
ax2b.set_ylabel('Wind Direction')


#water temperature
ax3.plot(df['time'], df['water_temperature'], color='tab:brown')
ax3.set_ylabel('Water Temperature [degC]')

plt.show()
```
Grafik yang dihasilkan dari running script ini adalah sebagai berikut:
![GRAFIK 1](https://user-images.githubusercontent.com/106166450/170160839-a08bcf91-e10a-4f46-b175-cb9d7f25f2d4.png)

![plot_wind_pres](https://user-images.githubusercontent.com/106166450/170161162-f38dd642-6bfb-471b-87c2-b320c51a94c7.png)

Stasiun 41008 - GREYS REEF - 40 NM Tenggara Savannah, GA Dimiliki dan dipelihara oleh National Data Buoy Center Pelampungcakram 3 meter ARES payload 31.400 N 
80.866 W (31°24'0" N 80°51'59" W) Kedalaman air: 16 m Jari- jari lingkaran arloji: 69 yard.

# Penutup
Demikianlah tugas akhir praktikum metode Pemodelan Oseanografi ini kami buat. Seluruh authors memohon maaf apabila terdapat kesalahan dalam tugas akhir ini. Kelompok 13 selaku author dari repositori kali ini juga mengucapkan terimakasih kepada:
1. Prof. Dr. Denny Nugroho Sugianto, S.T., M.Si. selaku dosen pengampu mata kuliah Pemodelan Oseanografi
2. Dr. Aris Ismanto, S.SI., M.Si. selaku dosen pengampu mata kuliah Pemodelan Oseanografi
3. Dr, Elis Sulistyawati. S.T., M.Si. selaku dosen pengampu mata kuliah Pemodelan Oseanografi
4. Rikha Widiaratih, S.Si., M.Si. selaku dosen pengampu mata kuliah Pemodelan Oseanografi
5. Tim Asisten Pemodelan Oseanografi 2022 yang mendampingi dari awal praktikum sampai tugas akhir ini.
6. Seluruh teman-teman Oseanografi 2020 yang turut mendukung tersusunnya repositori ini.
