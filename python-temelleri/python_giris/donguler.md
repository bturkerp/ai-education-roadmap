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





