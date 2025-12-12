# Python Fonksiyonları

Fonksiyonlar, bir işlemi tekrar tekrar kullanmamızı sağlayan yapı taşlarıdır.  
Python’da fonksiyonlar `def` anahtar kelimesi ile tanımlanır.

---

## 1. Basit Fonksiyon

```
def selamla():
    print("Merhaba!")

selamla()
```
Çıktı:
```
Merhaba!
```
## 2. Parametre Alan Fonksiyon
```
def selamla(isim):
    print(f"Merhaba, {isim}!")

selamla("Ali")
selamla("Ayşe")
```
Çıktı:
```
Merhaba, Ali!
Merhaba, Ayşe!
```

## 3. Return ile Değer Döndüren Fonksiyon
```
def kare(x):
    return x ** 2

sonuc = kare(5)
print(sonuc)
```
Çıktı:
```
25
```

## 4. Varsayılan Parametreler (Default Arguments)
```
def selamla(isim="Kullanıcı"):
    print(f"Merhaba, {isim}!")

selamla()
selamla("Mehmet")
```
Çıktı:
```
Merhaba, Kullanıcı!
Merhaba, Mehmet!
```

## Anahtar argümanlar (Keyword Arguments)
```
def bilgiler(isim, yas):
    print(f"{isim} {yas} yaşında")

bilgiler(yas=30, isim="Ayşe")
bilgiler(isim="Mehmet", yas=50)
bilgiler("Hülya", yas=20)
```
Çıktı:
```
Ayşe 30 yaşında
Mehmet 50 yaşında
Hülya 20 yaşında
```

## *args – Belirsiz Sayıda Pozisyonel Parametre
```
def toplam(*sayilar):
    return sum(sayilar)

print(toplam(1, 2, 3))
print(toplam(4, 5))
```
Çıktı:
```
6
9
```

## **kwargs – Belirsiz Sayıda Anahtar Kelime Parametre
```
def bilgiler(**kwargs):
    for key, value in kwargs.items():
        print(f"{key}: {value}")

bilgiler(isim="Ali", yas=25, sehir="İzmir")
bilgiler(isim="Ayşe", yas=15)
```
Çıktı:
```
isim: Ali
yas: 25
sehir: İzmir
isim: Ayşe
yas: 15
```










