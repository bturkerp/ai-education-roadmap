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
Aynı işlemi farklı verilerle kullanmamızı sağlar.
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
Fonksiyonun sadece bir çıktı üretmesini ve bu çıktıyı başka işlemlerde kullanabilmeyi sağlar.
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

## 5. Anahtar argümanlar (Keyword Arguments)
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

## 6. *args – Belirsiz Sayıda Pozisyonel Parametre
Fonksiyonun belirsiz sayıda parametre almasını sağlar.
*args → pozisyonel parametreleri listeler
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

## 7. **kwargs – Belirsiz Sayıda Anahtar Kelime Parametre
Fonksiyonun belirsiz sayıda parametre almasını sağlar.
**kwargs → anahtar kelime parametreleri dictionary olarak alır
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

## 8. Lambda Fonksiyonları (Anonim Fonksiyon)
Küçük, tek satırlık fonksiyonlar yazmak için idealdir.
Genellikle map, filter veya kısa hesaplamalarda tercih edilir.
```
kare = lambda x: x**2
topla = lambda a, b: a+b

print(kare(5))
print(topla(3, 7))
```
Çıktı:
```
25
10
```
Neden lambda?
- Fonksiyonu tekrar kullanmayacak ama kısa ve hızlı bir işlem yapmak istiyorsak
- Kodun okunabilirliğini artırır, gereksiz def tanımı yapmamıza gerek kalmaz
  
## 9. Nested (İç İçe) Fonksiyonlar
Fonksiyon içinde fonksiyon tanımlayarak, lokal bir hesaplama veya yardımcı işlevi kapsülleyebiliriz.
```
def dis_fonksiyon(x):
    def ic_fonksiyon(y):
        return y**2
    return ic_fonksiyon(x) + 1

print(dis_fonksiyon(5))

```
Çıktı:
```
26
```

## 10. Recursion (Özyinelemeli Fonksiyon)
Bir işlemi kendi kendini çağırarak çözmek.
Örnek: Faktöriyel, Fibonacci, ağaç veya dizin yapısı işleme.
- Fonksiyon kendisini çağırır.
- Örnek: Faktöriyel hesaplama
```
def faktoriyel(n):
    if n == 0 or n == 1:
        return 1
    else:
        return n * faktoriyel(n-1)

print(faktoriyel(5))
```
Çıktı:
```
120
```

## 11. Fonksiyon ile Liste İşleme
List comprehension ve fonksiyonları birleştirerek daha temiz ve kısa kod yazabiliriz.
```
def kareler(liste):
    return [x**2 for x in liste]

sayilar = [1, 2, 3, 4]
print(kareler(sayilar))
```
Çıktı:
```
[1, 4, 9, 16]
```

## 12. Fonksiyonları Başka Fonksiyonlara Parametre Olarak Gönderme
Fonksiyonları başka fonksiyonlara argüman olarak gönderebiliriz.
Bu, yüksek seviyeli fonksiyonlar veya callback mantığı için kullanışlıdır.
```
def selamla():
    return "Merhaba!"

def mesaj(fonk):
    print(fonk() + " Python!")

mesaj(selamla)
```
Çıktı:
```
Merhaba! Python!
```

## 13. Fonksiyon İle Koşullu İşlem
```
def buyukten_kucuge(a, b):
    if a > b:
        return a
    else:
        return b

print(buyukten_kucuge(10, 20))
```
Çıktı:
```
20
```
