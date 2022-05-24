# Tugas-Akhir-Pemos-Kelompok-7
Repositori ini dibuat untuk memenuhi Tugas Akhir Praktikum Pemodelan Oseanografi 2022. Repositori ini memuat teori, metode, dan file aplikasi yang dapat memproses beberapa persamaan adveksi difusi dan model hidrodinamika untuk penyelesaian dalam pemodelan dari suatu fenomena atau dinamika oseanografi.

# 1. AUTHORS of TEAM 3
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

**FTCS (Forward in Time Central in Space)**

**Leapfrog/CTCS (Center Time Center Space)**

**Upstream (Forward Time, Forward/Back Space)**

**Persamaan Difusi**

**Persamaan Adveksi-Difusi**

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

Persamaan pengatur berdasarkan hukum momentum menjadi

Persamaan pengatur berdasarkan hukum kontinuitas menjadi

**2.2.3 Contoh Hasil Pemodelan Oseanografi**

**Hasil Output Pemodelan 🖥️**

**a).Grafik 1**

**b).Grafik 2**

**c).Grafik 3**

**d).Grafik 4**

**e.) Grafik 5**

**2.2.4 Perbedaan Model Hidrodinamika 1 Dimensi dan 2 Dimensi**

# 3. Installasi Miniconda 3


# 4. Metode Pengerjaan
1. Modul 2 : Adveksi Difusi 2D
    
    Seperti yang telah dijelaskan di pendahuluan, pada modul 2 ini kita perlu menggunakan library berupa matplotlib dan numpy. Matplotlib berfungsi untuk membuat plot grafik dari hasil running script yang telah dilakukan. sedangkan numpy berfungsi untuk melakukan perhitungan data yang akan dianalisis, sehingga langkah awal dalam pemodelan ini perlu dilakukan import kedua library tersebut. script tersebut seperti yang ada dibawah ini.
```
import matplotlib.pyplot as plt
import numpy as np
import sys
```

2. Modul 3 : Model Hidrodinamika 1D
3. Modul 4 : Model Hidrodinamika 2D

**📌 4.1. Adveksi Difusi 2D**

**📌 4.2. Model Hidrodinamika 1D**

**📌 4.3. Model Hidrodinamika 2D**

# 5. Kegunaan dan Penerapan Script dalam Oseanografi

**📌 5.1. Adveksi Difusi 1 Dimensi**

**📌 5.2. Adveksi Difusi 2 Dimensi**

**📌 5.3. Model Hidrodinamika 1 Dimensi**

**📌 5.4. Model Hidrodinamika 2 Dimensi**

# 6. Penutup
**📌 6.1. Kesimpulan**

**📌 6.2. Saran**

**📌 6.3. Ucapan Terima Kasih**
