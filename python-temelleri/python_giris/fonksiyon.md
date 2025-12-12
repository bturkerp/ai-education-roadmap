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
# 2. Parametre Alan Fonksiyon
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

# 3. Return ile Değer Döndüren Fonksiyon
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

# 4. Varsayılan Parametreler (Default Arguments)
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














