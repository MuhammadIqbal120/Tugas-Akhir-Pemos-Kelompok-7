# Tugas-Akhir-Pemos-Kelompok-7
Repositori ini dibuat untuk memenuhi Tugas Akhir Praktikum Pemodelan Oseanografi 2022. Repositori ini memuat teori, metode, dan file aplikasi yang dapat memproses beberapa persamaan adveksi difusi dan model hidrodinamika untuk penyelesaian dalam pemodelan dari suatu fenomena atau dinamika oseanografi.

# 1. AUTHORS of TEAM 7
1. Muhammad Iqbal_26050120120022 A
2. Faiz Zaidan Amin_26050120140209 B
3. MHD Rayhan Azra_26050120140106 A
4. Harizal Fikra_26050120130091 A
5. Bisma Dwiki Akbar_26050120140075 B
6. Nabila Ismi Oktaviani_26050120140051 B
7. Rivani Aida Putri_26050120140113 B

# 2. Teori Dasar
📌 **2.1. Adveksi Difusi**

**Persamaan Adveksi**

Adveksi merupakan proses transportasi berupa aliran rata-rata atau arus, seperti sungai atau gerakan pasang surut yang digerakkan oleh gaya gravitasi atau tekanan dan berupa gerak horizontal.
Persamaan adveksi adalah salah satu persamaan diferensial parsial yang memodelkan pergerakan suatu konsentrat dalam cairan yang mengalir, dengan asusmsi konsentrat tersebut tidak mengalami proses difusi didalam cairan

Persamaan yang digunakan adalah

<img width="102" alt="image" src="https://user-images.githubusercontent.com/106181201/170124739-4602f60e-77e0-4d3f-bdc8-b489cad8ec25.png">

**FTCS (Forward in Time Central in Space)**

Persamaan beda hingga dengan metode FTCS ini adalah pendekatan beda maju untuk turunan waktu dan beda pusat untuk turunan ruang ( Forward in Time and Central in Space – FTCS). 
Bila :
- Indeks n untuk waktu
- Indeks m untuk ruang
- u adalah kecepatan aliran yang dianggap konstan terhadap ruang dan waktu

maka persamaannya dideskritisasikan menjadi:

<img width="173" alt="image" src="https://user-images.githubusercontent.com/106181201/170126225-ea835dd4-a5be-4914-aa58-78d9e9a24603.png">

Pada dasarnya metode beda hingga ini tidak stabil secara numerik

**Leapfrog/CTCS (Center Time Center Space)**

Persamaan beda hingga dengan metoda ini adalah pendekatan beda pusat untuk turunan waktu dan beda pusat untuk turunan ruang (Central in Time and Central in Space – CTCS), persamaannya dapat dideskritisasi menjadi:

<img width="165" alt="image" src="https://user-images.githubusercontent.com/106181201/170127147-40b587c3-3542-472d-b8dd-c8bc1659e533.png">

Khusus pada awal langkah (t = 0) deskritisasi persamaan diatas menggunakan beda maju untuk waktu dan beda pusat untuk ruang (metode FTCS) maka pada t = ∆t atau n =1 deskritisasi yang digunakan adalah :

<img width="148" alt="image" src="https://user-images.githubusercontent.com/106181201/170127226-595fddea-9913-418a-b0af-b0312537019a.png">

Dimana F0 diambil dari nilai awal yang diberikan di semua ruang

Kriteria stabilitas untuk menyelesaikan persamaan adveksi dengan menggunakan metode beda hingga eksplisit adalah
<img width="81" alt="image" src="https://user-images.githubusercontent.com/106181201/170127305-3652309d-9084-4fb3-b09f-c9facd23081a.png">


**Upstream (Forward Time, Forward/Back Space)**

Pada metode ini digunakan pendekatan metode beda maju untuk turunan terhadap waktu, sedangkan untuk turunan terhadap ruang dilakukan dengan melihat arah kecepatan u.
- Jika u > 0, turunan terhadap ruang menggunakan pendekatan beda mundur
<img width="165" alt="image" src="https://user-images.githubusercontent.com/106181201/170127384-17daa62c-48df-4976-be2e-6cdfac58656e.png">

-Jika u < 0, turunan terhadap ruang menggunakan pendekatan beda maju

<img width="156" alt="image" src="https://user-images.githubusercontent.com/106181201/170127481-fbad8d06-d300-40e2-a48e-0c71e4495c06.png">

Jika kedua persamaan tersebut digabungkan, maka deskritisasi persamaan adveksi dengan metode upstream menjadi :
<img width="291" alt="image" src="https://user-images.githubusercontent.com/106181201/170127545-703ec4f6-4f35-4b70-8c62-7848b6508e5b.png">

Kriteria stabilitas yang harus dipenuhi :
<img width="85" alt="image" src="https://user-images.githubusercontent.com/106181201/170127581-3bca39dc-f180-4fb8-9f1b-d88570a4a8fb.png">

**Persamaan Difusi**

Difusi merupakan mekanisme penyebaran konsentrasi akibat adanya kecepatan aliran dan perbedaan konsentrasi.

Persamaan difusi adalah persamaan diferensial parsial yang menggambarkan perpindahan suatu zat dalam pelarut dari bagian berkonsentrasi tinggi ke bagian yang berkonsentrasi rendah

Persamaan yang digunakan adalah

<img width="111" alt="image" src="https://user-images.githubusercontent.com/106181201/170124838-b7b1c224-96db-4625-b75e-129c83df89dc.png">


**Persamaan Adveksi-Difusi**

Diskritisasi Persamaan Adveksi-Difusi 2D

<img width="354" alt="image" src="https://user-images.githubusercontent.com/106181201/170129048-c87f3f7a-6caf-476c-b035-128fea5eb8e4.png">


**📌 2.2. Model Hidrodinamika**

**2.2.1 Apa itu Model Hidrodinamika?**
        
Model matematika dapat digunakan dalam persoalan-persoalan polusi lingkungan seperti yang terjadi pada perairan, dengan disimulasikan atau diturunkan fenomena kejadiannya. Hidrodinamika merupakan cabang ilmu dari mekanika fluida, khususnya zat cair incompresibble yang dipengaruhi oleh gaya internal dan eksternal. Dalam hidrodinamika laut, gaya-gaya yang penting adalah gaya gravitasi, gaya gesekan, dan gaya coriolis. Dalam oseanografi, mekanika fluida digunakan berdasarkan mekanika Newton yang dimodifikasi dengan memperhitungkan turbulensi. Oleh karena itu, model hidrodinamika merupakan model yang dibangun dari adanya proses-proses yang mempengaruhi pergerakan massa air. Model hidrodinamika ini bertujuan untuk mensimulasikan elevasi muka air laut dan arus yang dipengaruhi oleh beberapa parameter. Model hidrodinamika dibangun berdasarkan persamaan konservasi massa atau kontinuitas dan persamaan momentum.

**2.2.2 Persamaan-persamaan Model Hidrodinamika 1 Dimensi**

Persamaan pengatur fluida dapat disajikan sebagai berikut:

Persamaan pengatur berdasarkan hukum momentum

<img width="109" alt="momentum" src="https://user-images.githubusercontent.com/106155232/170067525-f940348b-2f73-4d6e-b3b3-67e098f8ce69.png">

Persamaan pengatur berdasarkan hukum kontinuitas

<img width="111" alt="kontinuitas" src="https://user-images.githubusercontent.com/106155232/170068001-ee372456-5a72-415a-85c5-75c43faac470.png">

dimana u adalah kecepatan sesaat (m/dt), elevasi (m), H adalah kedalaman terukur (m) konstan terhadap ruang, dan g adalah koefisien gravitasi bumi (m/dt2)

Sistem persamaan diatas dapat diubah menjadi persamaan transpor Ut (m2/dt), dimana:

<img width="84" alt="u" src="https://user-images.githubusercontent.com/106155232/170068935-cab8f784-6d67-482c-8f0a-b8c8512b6371.png">

Persamaan pengatur berdasarkan hukum momentum menjadi

<img width="118" alt="transpor momentum" src="https://user-images.githubusercontent.com/106155232/170069166-613d9982-e505-4d1d-a688-20cdfa06859f.png">

Persamaan pengatur berdasarkan hukum kontinuitas menjadi

<img width="120" alt="transpor kontinuitas" src="https://user-images.githubusercontent.com/106155232/170069378-7a6d4963-92d2-4fb3-b248-aa8341ae5939.png">

**2.2.3 Contoh Hasil Pemodelan Oseanografi**

**Hasil Output Pemodelan 🖥️**

**a).Grafik 1**

**b).Grafik 2**

**c).Grafik 3**

**d).Grafik 4**

**2.2.4 Perbedaan Model Hidrodinamika 1 Dimensi dan 2 Dimensi**

# 3. Installasi Miniconda 3


# 4. Metode Pengerjaan
**4.1. Adveksi Difusi 2D**
    
Seperti yang telah dijelaskan di pendahuluan, pada modul 2 ini kita perlu menggunakan library berupa matplotlib dan numpy. Matplotlib berfungsi untuk membuat plot grafik dari hasil running script yang telah dilakukan. sedangkan numpy berfungsi untuk melakukan perhitungan data yang akan dianalisis, sehingga langkah awal dalam pemodelan ini perlu dilakukan import kedua library tersebut. script tersebut seperti yang ada dibawah ini.
```
import matplotlib.pyplot as plt
import numpy as np
import sys
```
Selanjutnya masukan parameter persebaran polutan yang digunakan
```
#parameter awal
C = 0   #nilai kecepatan aliran
ad = 1  #koefisiendifusi

#arah arus
theta = 334

#paramter lanjutan
q = 0.95
x = 500
y = 500
dx = 5
dy = 5

#lama simulasi
Tend = 101
#tend 1
dt = 0.5
#polutan
px = 250
py = 231
Ic = 1019
```
Kemudian kerjakan script untuk perhitungan U, V dan Persebaran polutan
```
#perhitungan u dan v ()
u = C = np.sin(theta*np.pi/180)
v = C = np.cos(theta*np.pi/180)
dt_count = 1/((abs(u)/(q*dx))+(abs(v)/(q*dy))+(2*ad/(q*dx**2))+(2*ad/(q*dy**2)))

Nx = int(x/dx)  #number of mesh in x direction
Ny = int(y/dy)  #number of mesh in y direction
Nt = int(Tend/dt)

#perhitungan titik polutan di buang
px1 = int(px/dx)
py1 = int(py/dy)

#fungsi disederhanakan
lx = u*dt/dx
ly = v*dt/dy
ax = ad*dt/dx**2
ay = ad*dt/dy**2
cfl = (2*ax + 2*ay + abs(lx) + abs(ly))  #syarat kestabilan CFL

#perhitungan cfl
if cfl >= q:
    print('CFL Violated, please use dt :'+str(round(dt_count,4)))
    sys.exit
#%%
```
Selanjutanya proses untuk membuat Grid
```
#pembuatan grid 
x_grid = np.linspace(0-dx, x+dx, Nx+2) #ghostnode boundary
y_grid = np.linspace(0-dx, y+dy, Ny+2) #ghostnode boundary
t = np.linspace(0, Tend, Nt+1)
x_mesh, y_mesh = np.meshgrid(x_grid,y_grid)
F = np.zeros((Nt+1, Ny+2, Nx+2))
```
Lalu dilakukan pembuatan Iterasi
```
#kondisi awal
F[0,py1,px1] = Ic
#%%

#Iterasi
for n in range (0,Nt):
    for i in range (1,Ny+1):
        for j in range (1,Nx+1):
          F[n+1,i,j]=((F[n,i,j]*(1-abs(lx)-abs(ly))) + \
                (0.5*(F[n,i-1,j]*(ly+abs(ly)))) + \
                (0.5*(F[n,i+1,j]*(abs(ly)-ly))) + \
                (0.5*(F[n,i,j-1]*(lx+abs(lx)))) + \
                (0.5*(F[n,i,j+1]*(abs(lx)-lx))) + \
                (ay*(F[n,i+1,j]-2*(F[n,i,j])+F[n,i-1,j])) +\
                (ax*(F[n,i,j+1]-2*(F[n,i,j])+F[n,i,j-1])))
    #syarat batas
    F[n+1,0,:] = 0 #bc bawah
    F[n+1,:,0] = 0 #bc kiri
    F[n+1,Ny+1,:] = 0 #bc atas
    F[n+1,:,Nx+1] = 0 #bc kanan
#%%
```
lalu terakhir membuat script untuk Output gambar, lalu lakukan running dari script tersebut
```
#output gambar
    plt.clf()
    plt.pcolor(x_mesh, y_mesh, F[n+1,:,:],cmap = 'jet',shading = 'auto', edgecolors = 'k')
    cbar = plt.colorbar(orientation = 'vertical',shrink = 0.95, extend ='both')
    cbar.set_label(label='concentration', size = 8)
    #plt clim (0,100)
    plt.title('Harizal Fikra_26050120130091 \n t='+str(round(dt*(n+1),3))+', initial condition='+str(Ic),fontsize=10)
    plt.xlabel('x_grid',fontsize=9)
    plt.ylabel('y_grid',fontsize=9)
    plt.axis([0, x, 0, y])
    #pltpause(0.01)
    plt.savefig(str(n+1)+'.jpg', dpi = 300)
    plt.pause(0.01)
    plt.close()
    print('running timestep ke:' +str(n+1) + 'dari:' +str(Nt) + '('+ percentage(n+1, Nt)+')')
    print('nilai CFL:' +str(cfl) + 'dengan arah: ' +str(theta))
```


**📌 4.2. Model Hidrodinamika 1D**
        
Sama seperti modul sebelumnya, pada modul 3 ini kita menggunakan dua library utama juga, matplotlib dan numpy. Matplotlib berfungsi untuk membuat plot grafik dari hasil running script yang telah dilakukan. sedangkan numpy berfungsi untuk melakukan perhitungan data yang akan dianalisis, sehingga langkah awal dalam pemodelan ini perlu dilakukan import kedua library tersebut. script tersebut seperti yang ada dibawah ini.
```
import matplotlib.pyplot as plt
import numpy as np
```
Selanjutnya kita perlu mengisi paramater apa saja yang memengaruhi model yang akan kita buat
```
p = 7500 #Panjang Grid
T = 2000 #Waktu Simulasi 
A = 0.1 #Amplitudo
D = 5 #Depth/kedalaman
dt = 2
dx = 100
To = 500 #Periode

g = 9.8
pi = np.pi
C = np.sqrt(g*D) #Kecepatan Arus
s = 2*pi/To #Kecepatan Sudut Gelombang
L = C*To #Panjang Gelombang
k = 2*pi/L #Koefisien Panjang Gelombang
Mmax = int(p//dx)
Nmax = int(T//dt) 

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
 ```
Langkah dalam penulisan script ini kita perlu melakukan ploting untuk kemudian dapat ditampilkan dalam bentuk grafik. dalam hal ini kita juga dapat menentukan size yang akan digunakan dan jumlah grafik yang akan kita buat. Disini kita menggunakan 4 grafik dimana ax0 merupakan Perubahan Kecepatan Arus Dalam Grid Tertentu di Sepanjang waktu, ax1 merupakan Perubahan elevasi muka air dalamm grid tertentu di sepanjang waktu, ax2 merupakan Perubahankecepatan arus dalam grid tertentu di sepanjang grid, dan ax 3 merupakan perubahan elevasi permukaan air dalam grid waktu tertetu di sepanjang grid
```
def rand_col_hex_string():
    return f'#{format(np.random.randint(0,16777215), "#08x")[2:]}'

hasilu_np = np.array(hasilu)
hasilz_np = np.array(hasilz)

fig0, ax0 = plt.subplots(figsize=(12,8))
for i in range(1, 16):
    col0 = rand_col_hex_string()
    line, = ax0.plot(hasilu_np[:,i-1], c=col0, label=f'n={i}')
    ax0.legend()

    ax0.set(xlabel='Waktu', ylabel='Kecepatan Arus',
            title=''' Kelompok 8 Pemodelan Oseanografi 2022
            Perubahan Kecepatan Arus Dalam Grid Tertentu di Sepanjang Waktu''')
    ax0.grid()

fig1, ax1 = plt.subplots(figsize=(12,8))
for i in range(1, 16):
    col1 = rand_col_hex_string()
    line, = ax1.plot(hasilz_np[:,i-1], c=col1, label=f'n={i}')
    ax1.legend()

    ax1.set(xlabel='Waktu', ylabel='Elevasi Muka Air',
            title=''' Kelompok 8 Pemodelan Oseanografi 2022
            Perubahan Elevasi Permukaan Air Dalam Grid Tertentu di Sepanjang Waktu''')
    ax1.grid()

fig2, ax2 = plt.subplots(figsize=(12,8))
for i in range(1, 16):
    col2 = rand_col_hex_string()
    line, = ax2.plot(hasilu_np[i-1], c=col2, label=f't={i}')
    ax2.legend()

    ax2.set(xlabel='Grid', ylabel='Kecepatan Arus',
            title=''' Kelompok 8 Pemodelan Oseanografi 2022
            Perubahan Kecepatan Arus Dalam Waktu Tertentu di Sepanjang Grid''')
    ax2.grid()

fig3, ax3 = plt.subplots(figsize=(12,8))
for i in range(1, 16):
    col3 = rand_col_hex_string()
    line, = ax3.plot(hasilz_np[i-1], c=col3, label=f't={i}')
    ax3.legend()
    ax3.set(xlabel='Grid', ylabel='Elevasi Muka Air',
            title=''' Kelompok 8 Pemodelan Oseanografi 2022
            Perubahan Elevasi Permukaan Air Dalam Waktu Tertentu di Sepanjang Grid''')
    ax3.grid()
```
Terakhir kita perlu memberikan perintah untuk menampilkan hasil plotting grafik tersebut
```
plt.show()
```
Selanjutnya kita hanya perlu melakukan running dari script tersebut, kemudian simpan hasil grafik yang berhasil didapatkan.


**📌 4.3. Model Hidrodinamika 2D**

   Langkah pertama yang perlu dilakukan apabila belum terdapat library matplotlib dan Siphon kita perlu menginstal library tersebut dengan menggunakan anaconda prompt. Code dibawah merupakan code untuk mengistall library siphon, kemudian jika dituliskan pada anaconda prompt lalu tekan enter dan tunggu hingga berhasil
```
(base) C:\Users\ACER>pip install siphon
```
Kemudian dalam pemodelan di modul 4 berdasarkan data yang telah disedikan oleh NDBC
```
# Copyright (c) 2018 Siphon Contributors
# Distributed under the terms of the BSD 3-Clause License
# SPDX-License-Identifier : BSD-3-Clause
"""
NDBC Buoy Meteorological Data Request
======================================
The NDBC keeps a 45-day recent rolling file for each buoy. This examples shows how to access
the basic meteorological data from a buoy and make a simple plot.
"""
```
Seperti yang telah disinggung di pendahuluan bahwassannya kita perlu menggunakan library berupa matplotlib dan siphon. Matplotlib berfungsi untuk membuat plot grafik dari hasil running script yang telah dilakukan. sedangkan siphon berfungsi untuk mengunduh data dari layanan data jarak jauh dalam hal ini yaitu data dari NDBC. jadi langkah awal dalam pemodelan ini perlu dilakukan import kedua library tersebut. script tersebut seperti yang ada dibawah ini.
```
import matplotlib.pyplot as plt

from siphon.simplewebservice.ndbc import NDBC
```
Selanjutnya kita perlu mengisikan atau mengkoneksikan data buoy yang kita gunakan berdasarkan pada id stasiun yang diinginkan, berikut script untuk mengkoneksikan data pada id stasiun NDBC yang ingin digunakan.
```
# Get a pandas data frrame of all of the observations, meteorological data os the default
# observation set query.
df = NDBC.realtime_observations('51003') #Stasiun ID
df.head()
```
Selanjutnya langkah dalam penulisan script ini kita perlu melakukan ploting untuk kemudian dapat ditampilkan dalam bentuk grafik. dalam hal ini kita juga dapat menentukan size yang akan digunakan dan jumlah grafik yang akan kita buat. Disini kita menggunakan 3 grafik diman ax1 merupakan #pressure, ax2 merupakan Wind Speed, gust, direction, dan ax3 merupakan #water temperature
```
# Let's make a simple time series plot to ceckout what the data look like.
fig, (ax1, ax2, ax3) = plt.subplots(3, 1, figsize=(12, 10))
ax2b = ax2.twinx()
```
selanjutnya kita dapat memberikan label keterangan pada plot grafik yaang akan menjadi output dari pemodelan ini, berikut script untuk ploting labelnya.
```
# Pressure
ax1.plot(df['time'], df['pressure'], color='black')
ax1.set_ylabel('pressure [hPa]')
fig.suptitle('Tugas Akhir Praktikum Pemos_Kelompok 8', fontsize = 18)


# Wind speed, gust, direction
ax2.plot(df['time'], df['wind_speed'], color='tab:orange')
ax2.plot(df['time'], df['wind_gust'], color='tab:olive', linestyle='--')
ax2b.plot(df['time'], df['wind_direction'], color='tab:blue', linestyle='-')
ax2.set_ylabel('Wind Speed [m/s]')
ax2b.set_ylabel('Wind Direction')


# Water temperature
ax3.plot(df['time'], df['water_temperature'], color='tab:red')
ax3.set_ylabel('water Temperature [degC]')
```
kemudian langkah terakhir yaitu kita perlu memberikan perintah untuk kemudian menampilkan hasil plotting grafik tersebut
```
plt.show()
```
Kemduian setelah itu kita tinggal melakukan running dari script pemodelan tersebut. Simpan hasil grafik yang telah berhasil didapatkan.
Buka Website NDBC-NOAA
website buka
![image](https://user-images.githubusercontent.com/106149671/170101109-99aaa6d9-cdc7-419b-b884-06d15690b4aa.png)

Kemudian bisa kita cari id stasiun yang kita gunakan pada script tadi melalui kolom pencarian
![image](https://user-images.githubusercontent.com/106149671/170101278-f6af5c41-fb56-4fc8-846b-f9009547fa1f.png)


kemudian kita dapat melakukan analisis terhadap keadaan buoy terkait dengan lokasi dan sebagainnya dari website tersebut.
# 5. Kegunaan dan Penerapan Script dalam Oseanografi

**📌 5.1. Adveksi Difusi 1 Dimensi**
Penerapan dalam Oseanografi : 
1. 
2.
3.

Kelebihan : 
1.
2. 
3. 

Kekurangan : 
1. 
2. 
3. 

**📌 5.2. Adveksi Difusi 2 Dimensi**
Penerapan dalam Oseanografi : 
1. 
2.
3.

Kelebihan : 
1.
2. 
3. 

Kekurangan : 
1. 
2. 
3. 

**📌 5.3. Model Hidrodinamika 1 Dimensi**
Penerapan dalam Oseanografi : 
1. 
2.
3.

Kelebihan : 
1.
2. 
3. 

Kekurangan : 
1. 
2. 
3. 

**📌 5.4. Model Hidrodinamika 2 Dimensi**
Penerapan dalam Oseanografi : 
1. 
2.
3.

Kelebihan : 
1.
2. 
3. 

Kekurangan : 
1. 
2. 
3. 

# 6. Penutup
**📌 6.1. Kesimpulan**

**📌 6.2. Saran**

**📌 6.3. Ucapan Terima Kasih**

Demikian tugas akhir praktikum pemodelan oseanografi yang kami buat. Seluruh authors mohon maaf apabila terdapat kesalahan dalam penyampaian materi dalam tugas akhir ini. Seluruh author dari kelompok 7 mengucapkan terimakasih kepada:
1. Dr. Aris Ismanto, S.Si., M.Si. selaku dosen pengampu mata kuliah pemodelan oseanografi 
2. Prof. Dr. Denny Nugroho Sugianto, S.T., M.Si. selaku dosen pengampu mata kuliah pemodelan oseanografi 
3. Dr. Elis Indrayanti, S.T., M.Si. selaku dosen pengampu mata kuliah pemodelan oseanografi 
4. Rikha Widiaratih, S.Si., M.Si. selaku dosen pengampu mata kuliah pemodelan oseanografi 
5. Tim asisten Praktikum Pemodelan Oseanografi 2022 yang mendampingi dalam pengerjaan tugas selama praktikum hingga tugas akhir 
6. seluruh teman teman Oseanografi 2020 yang telah mendukung dalam pengerjaan tugas akhir ini
