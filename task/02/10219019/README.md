# 10219019
Abdu Rafie


## materi sebelumnya
+ Runge-kutta, monte carlo, fourier, dll


## materi paling menarik
+ Runge-kutta orde 4 karena saya melihat metode tersebut dapat di aplikasikan pada banyak hal


## materi paling membosankan
+ Runge-kutta orde 4 karena diulang-ulang terus


## materi yang sudah dipami
+ Runge-kutta orde 4

## materi yang belum dipahami
+ monte carlo karena saya belum baca-baca dan explore lebih dalam


## contoh program
+ Buat suatu contoh program dalam Python dan sertakan di sini dengan hasil keluarnnya.


```python
# Mendefinisikan library
import numpy as np
import matplotlib.pyplot as plt

def F(t, x, y):
    return (-x + (x * y), y - (x * y))
    
# Mendefinisikan euler method
def eulerMethod(t_0, t_n, num_steps, x_0, y_0):
    h = abs(t_n - t_0)/num_steps
    t = np.linspace(t_0, t_n, num_steps + 1)
    x = np.zeros(num_steps + 1)
    y = np.zeros(num_steps + 1)
    x[0] = x_0
    y[0] = y_0
    for k in range(0, num_steps):
        (dx, dy) = F(t[k], x[k], y[k])
        x[k + 1] = x[k] + h * dx
        y[k + 1] = y[k] + h * dy
    return (x, y)
    
    
# Mendefinisikan Runge Kutta method
def rungeKutta(t_0, t_n, num_steps, x_0, y_0):
    h = abs(t_n - t_0)/num_steps
    t = np.linspace(t_0, t_n , num_steps + 1)
    x = np.zeros(num_steps + 1)
    y = np.zeros(num_steps + 1)
    x[0] = x_0
    y[0] = y_0
    for k in range(0, num_steps):
        (x1, y1) = F(t[k], x[k], y[k])
        (x2, y2) = F(t[k] + h/2, x[k] + x1 * h/2, y[k] + y1 * h/2)
        (x3, y3) = F(t[k] + h/2, x[k] + x2 * h/2, y[k] + y2 * h/2)
        (x4, y4) = F(t[k] + h, x[k] + x3 * h, y[k] + y3*h)
        x[k + 1] = x[k] + h * (x1 + 2 * x2 + 2 * x3 + x4)/6
        y[k + 1] = y[k] + h * (y1 + 2 * y2 + 2 * y3 + y4)/6
    return (x,y)
    
# Input nilai parameter yang dibutuhkan
t_0 = 0
t_n = 100
x_0 = 0.3
y_0 = 2
num_steps = 3000

# Plotting grafik yang diperoleh berdasarkan
# persamaan euler untuk visualisasi predator - prey
plt.figure(1)
(x_pt,y_pt) = eulerMethod(t_0, t_n, num_steps, x_0, y_0)
plt.plot(x_pt,y_pt,color='blue',label='Euler')
plt.title('Grafik Populasi Predator Terhadap Mangsa - Persamaan Euler')
plt.xlabel('Populasi Predator')
plt.ylabel('Populasi Mangsa')
plt.axis([-1, 5, -1, 5])
plt.savefig('Figure (1) Grafik Predator - Prey berdasarkan Persamaan Euler.png')
```

Hasilnya adalah
<img width="230" alt="Predator Prey" src="https://user-images.githubusercontent.com/97975571/197973220-7d1fb891-9a0c-460f-acf2-13507148406b.png">

## cara perkuliahan
+ Baru terjadi 2x kuliah setelah uts. Yang pertama saya nggak masuk karena nggak enak badan, yang kedua (tadi) tidak banyak yang disampaikan.


## topik sistem fisis
+ Sistem fisis yang cukup menarik bagi saya adalah tentang ekonofisika yang memiliki hubungan dengan pasar saham karena saya sering mengamati pergerakan saham dan ingin mencoba mencari sudut pandang lain.


## simulasi dan visualisasi
+ Tertarik. Sejauh ini saya mencari cari tentang metode LSTM. Metode tersebut dapat memprediksi harga saham kedepan nya.
