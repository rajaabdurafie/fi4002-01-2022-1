# 1021XABC
NamaLengkap


## materi sebelumnya
+ Tuliskan materi-materi sebelumnya yang telah diberikan dalam kuliah ini.


## materi paling menarik
+ Tuliskan materi yang paling menarik yang telah diberikan dan jelaskan mengapa menarik.


## materi paling membosankan
+ Tuliskan materi yang telah diberikan yang paling membosankan dan jelaskan alasannya.


## materi yang sudah dipami
+ Tuliskan materi-materi yang telah dipahami.


## materi yang belum dipahami
+ Tuliskan materi-materi yang masih belum dipahami dan bagian mana yang belum serta ingin dipahami.


## contoh program
+ Buat suatu contoh program dalam Python dan sertakan di sini dengan hasil keluarnnya.

```python
# contoh program python

def integrate(F,x,y,xStop,h):
    def runkut4(F,x,y,h):
        k0 = F(x, y)
        k1 = F(x + h / 2.0, y + k0 / 2.0)
        k2 = F(x + h / 2.0, y + k1 / 2.0)
        k3 = F(x + h, y + k2)
        return h*(k0+2.0*k1+2.0*k2+k3)/6.0

    X = []
    Y = []
    X.append(x)
    Y.append(y)
    while x < xStop:
        h = min(h, xStop)
        y = y + runkut4(F,x,y,h)
        x = x + h
        X.append(x)
        Y.append(y)
    return np.array(X),np.array(Y)


m = 3727.379
E = 20
V = 0
h_bar = 197.3269804
alpha = 2*m*(E-V)/(h_bar*h_bar)

def F(x,y):
    F = - alpha*y
    return F

x = 0.0
xStop = 50
y = 0.1
h = 0.1
X,Y = integrate(F,x,y,xStop,h)

plt.plot(X,Y,'o-')
plt.xlabel('x');plt.ylabel('V')

Hasilnya adalah

```
```


## cara perkuliahan
+ Tuliskan pendapat Anda mengenai cara perkuliahan selama ini dan cantumkan usulan untuk perkuliahan setelah UTS.


## topik sistem fisis
+ Tuliskan sistem fisis yang menarik bagi Anda untuk dikaji lebih dalam dan jelaskan alasannya mengapa.


## simulasi dan visualisasi
+ Apakah Anda tertarik dengan simulasi dan visualisasi? Jelaskan topik yang ingin Anda simulasikan / visualisasikan serta cantumkan alasannya dan perkiraan pusataka Python yang perlu digunakan.
