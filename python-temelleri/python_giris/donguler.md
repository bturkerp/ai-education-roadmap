# Python Döngüler

Python’da döngüler, belirli işlemleri tekrar tekrar yapmak için kullanılır.  
İki temel döngü tipi vardır: `for` ve `while`.  

---

## 1. for Döngüsü

`for` döngüsü, iterable (liste, tuple, string, range vb.) üzerinde döner.

### In ile Basit for döngüsü

```
meyveler = ["elma", "armut", "muz"]

for meyve in meyveler:
    print(meyve)
```
Çıktı:
```
elma
armut
muz
```
### range() ile sayma
```
for i in range(5):
    print(i)
```
Çıktı:
```
0
1
2
3
4
```
### range(start, stop, step)
```
for i in range(2, 10, 2):
    print(i)
```
Çıktı:
```
2
4
6
8
```

##While Döngüsü
while döngüsü, koşul doğru olduğu sürece çalışır.
### Basit While Döngüsü
```
x = 0

while x < 5:
    print(x)
    x += 1
```
Çıktı:
```
0
1
2
3
4
```
### Koşul ve break
```
x = 0

while True:
    print(x)
    x += 1
    if x == 3:
        break
```
Çıktı:
```
0
1
2
```
### continue ile döngü atlama
```
for i in range(5):
    if i == 2:
        continue
    print(i)
```
Çıktı:
```
0
1
3
4
```

### for-else
- else bloğu, döngü normal şekilde tamamlanırsa çalışır.
- break ile çıkılırsa else çalışmaz.
```
for i in range(3):
    print(i)
else:
    print("Döngü tamamlandı")

```
Çıktı:
```
0
1
2
Döngü tamamlandı
```
break ile else atlama
```
for i in range(5):
    if i == 2:
        break
    print(i)
else:
    print("Döngü tamamlandı")
```
Çıktı:
```
0
1
```

### Nested (İç içe) Döngüler
```
for i in range(1, 4):
    for j in range(1, 4):
        print(f"i={i}, j={j}")
```
Çıktı:
```
i=1, j=1
i=1, j=2
i=1, j=3
i=2, j=1
i=2, j=2
i=2, j=3
i=3, j=1
i=3, j=2
i=3, j=3
```

### Döngü ile Liste Anlaması (List Comprehension)
```
sayilar = [1, 2, 3, 4, 5]
kareler = [x**2 for x in sayilar if x % 2 == 0]
print(kareler)
```
Koşula uyan sayılar 2 ve 4 olduğu için Çıktı:

```
[4, 16]
```

### Döngüde Fonksiyon Kullanımı
```
def selamla(isim):
    return f"Merhaba, {isim}!"

isimler = ["Ali", "Ayşe", "Mehmet"]

for isim in isimler:
    print(selamla(isim))

```
Çıktı:
```
Merhaba, Ali!
Merhaba, Ayşe!
Merhaba, Mehmet!
```

### Sonsuz Döngü
- while True: ile sonsuz döngü oluşturulur.
- break ile sonlandırılır.
```
x = 0
while True:
    print(x)
    x += 1
    if x >= 3:
        break
```
x=4 olduğunda break komutu çalışarak döngüyü kırmasa bu döngü sonsuza kadar çalışırdı. Çıktı:
```
0
1
2
```
### Döngü ve Dictionary
```
ogrenciler = {"Ali": 90, "Ayşe": 85, "Mehmet": 70}

for isim, notu in ogrenciler.items():
    print(f"{isim} -> {notu}")
```
Çıktı:
```
Ali -> 90
Ayşe -> 85
Mehmet -> 70
```
### Döngü ile String İşleme
```
kelime = "Python"

for harf in kelime:
    print(harf)
```
Çıktı:
```
P
y
t
h
o
n
```
### Örnekler
***Örnek 1: Çarpım Tablosu (Nested Loops)**
```
for i in range(1, 6):
    for j in range(1, 6):
        print(f"{i}x{j}={i*j}", end="\t")
    print()
```
Çıktı:
```
1x1=1    1x2=2    1x3=3    1x4=4    1x5=5
2x1=2    2x2=4    2x3=6    2x4=8    2x5=10
3x1=3    3x2=6    3x3=9    3x4=12   3x5=15
4x1=4    4x2=8    4x3=12   4x4=16   4x5=20
5x1=5    5x2=10   5x3=15   5x4=20   5x5=25
```

***Örnek 2: Fibonacci Serisi (while ile)**
```
n = 10
a, b = 0, 1
sayac = 0

while sayac < n:
    print(a, end=" ")
    a, b = b, a + b
    sayac += 1
```
Çıktı:
```
0 1 1 2 3 5 8 13 21 34
```
**Örnek 3: Liste İçinde Liste (2D Matrix İşleme)**
```
matris = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]

for satir in matris:
    for eleman in satir:
        print(eleman, end=" ")
    print()
```
Çıktı:
```
1 2 3 
4 5 6 
7 8 9 
```

**Örnek 4: Break ve Continue ile Karmaşık Koşul**
```
for i in range(1, 21):
    if i == 15:
        break
    if i % 2 != 0:
        continue
    print(i)
```
Çıktı:
```
2
4
6
8
10
12
14
```

**Örnek 5: Dictionary + Döngü + Koşul**
Öğrenci notlarına göre harf notu atama
```
ogrenciler = {"Ali": 92, "Ayşe": 75, "Mehmet": 64, "Fatma": 58}
harf_notu = {}

for isim, notu in ogrenciler.items():
    if notu >= 90:
        harf_notu[isim] = "AA"
    elif notu >= 80:
        harf_notu[isim] = "BA"
    elif notu >= 70:
        harf_notu[isim] = "BB"
    elif notu >= 60:
        harf_notu[isim] = "CB"
    else:
        harf_notu[isim] = "FF"

print(harf_notu)
```
Çıktı:
```
{'Ali': 'AA', 'Ayşe': 'BB', 'Mehmet': 'CB', 'Fatma': 'FF'}
```

**Örnek 6: Döngü + enumerate ile İndeks Kullanımı**
```
isimler = ["Ali", "Ayşe", "Mehmet", "Fatma"]

for index, isim in enumerate(isimler, start=1):
    print(f"{index}. {isim}")
```
Çıktı:
```
1. Ali
2. Ayşe
3. Mehmet
4. Fatma
```

**Örnek 7: Döngü + else + break ile Asal Sayı Kontrolü**
```
n = 17

for i in range(2, n):
    if n % i == 0:
        print(f"{n} asal değil")
        break
else:
    print(f"{n} asal sayı")
```
Çıktı:
```
17 asal sayı
```

**Örnek 8: List Comprehension ile Koşullu Döngü**
```
sayilar = list(range(1, 21))
kareler = [x**2 for x in sayilar if x % 3 == 0]
print(kareler)
```
Program sayilar dizisinde 3'ün katları olan sayıların karesini alarak yazdırırır. Çıktı:
```
[9, 36, 81, 144, 225, 324]
```

**Örnek 9: Döngü ile String Manipülasyonu**
```
kelime = "python programming"

for harf in kelime:
    if harf == "a":
        continue
    print(harf.upper(), end="")
```
Çıktı:
```
PYTHON PROGRMMING
```


