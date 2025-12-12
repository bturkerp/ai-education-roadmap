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














