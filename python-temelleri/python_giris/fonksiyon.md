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
# Parametre Alan Fonksiyon

def selamla(isim):
    print(f"Merhaba, {isim}!")

selamla("Ali")
selamla("Ayşe")
