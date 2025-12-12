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
