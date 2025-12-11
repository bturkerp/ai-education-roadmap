**🐍 Python Eğitimi: Değişkenler ve Veri Tipleri (Tam Kapsamlı)**

# 1. Değişken Nedir?

Python’da değişken, bir veriyi bellekte saklamak için kullandığın isimli bir referanstır. Değişken tanımlamak için = atama operatörünü kullanırsın:
```
python

isim = "Türker"
yas = 28
```

📌 Kurallar:
- Harf (a–z, A–Z) veya alt çizgi (_) ile başlamalı.
- Rakamla başlayamaz: 1degisken ❌ → degisken1 ✅
- Sadece alfanümerik karakterler ve _ içerebilir.
- Anahtar kelimelerle çakışmamalı (if, for, class vs.)
- Büyük/küçük harf duyarlıdır: Isim ≠ isim
- Türkçe karakterler teknik olarak çalışsa da, proje taşınabilirliği için önerilmez.

💡 PEP8 tavsiyesi: Değişken isimleri snake_case olmalı: ogrenci_sayisi

# 2. Python’da Tüm Yerleşik Veri Tipleri

Python’da her şey bir nesnedir, ve her nesnenin bir türü (type) vardır. Temel veri tipleri 7 ana kategoriye ayrılır:

- Sayısal Tipler: int, float, complex  
- Metin Tipi: str  
- Mantıksal Tip: bool  
- Sıralı Tipler: list, tuple, range  
- Eşleme Tipi: dict  
- Küme Tipleri: set, frozenset  
- İkili (Binary) Tipler: bytes, bytearray, memoryview  
- Boş Tip: NoneType (None değeri)

Aşağıda her birini detaylı örneklerle inceleyeceğiz.

##  2.1 Sayısal Tipler
### int – Tam Sayılar
Sınırsız uzunlukta, pozitif/negatif tam sayılar.

```
python

x = 42
y = -1000
z = 0
print(type(x))  # <class 'int'>
```

Python 3'te long tipi yoktur; int sonsuz duyarlılıkta çalışır.

### float – Ondalıklı Sayılar

64-bit IEEE 754 double precision (yaklaşık 15–17 anlamlı basamak).

```
python

pi = 3.14159
negatif = -0.001
bilimsel = 1.23e4  # 1.23 × 10⁴ = 12300.0
print(bilimsel)  # 12300.0
print(type(pi))  # <class 'float'>
```
⚠️ Dikkat: 0.1 + 0.2 == 0.3 → False! (Kayan nokta hassasiyeti nedeniyle)
```
python

print(0.1 + 0.2)  # 0.30000000000000004
```
### Complex – Karmaşık Sayılar

Gerçek (real) ve sanal (imag) kısımdan oluşur. j sanal birimi temsil eder.

```
python

c = 3 + 4j
print(c.real)   # 3.0
print(c.imag)   # 4.0
print(type(c))  # <class 'complex'>

# Alternatif oluşturma
c2 = complex(2, -5)  # 2 - 5j
```

## 2.2 Metin Tipi: str
   Temel Özellikler
- Tek (') veya çift (") tırnakla tanımlanır.
- Değiştirilemez (immutable).
- Unicode destekler.

```
python

ad = "Türker"
selam = 'Merhaba, "arkadaş"!'
çift_tırnak = "O, 'evet' dedi."
çok_satırlı = """Bu
çok
satırlı
bir stringtir."""
```
### Kaçış Dizileri (Escape Sequences)

```
python

print("Satır\nbaşı")     # Yeni satır
print("Sekme\tkarakteri") # Sekme
print("C:\\Users\\Türker") # Ters eğik çizgi
print(r"Ham string: C:\Users\Türker")  # r ile escape'leri iptal et
```

### Diziler ve İndeksleme
```
python

s = "Python"
print(s[0])    # 'P'
print(s[-1])   # 'n'
print(s[1:4])  # 'yth'
```

### String Formatlama

- .format()
- f-string (Python 3.6+)
    
```
python

isim = "Türker"
yas = 28

# f-string (önerilen)
print(f"Merhaba, ben {isim}, {yas} yaşındayım.")

# .format()
print("Merhaba, ben {}, {} yaşındayım.".format(isim, yas))
```

## 2.3 Mantıksal Tip: bool
Sadece iki değeri vardır: True ve False (büyük harfle!).

```
python

aktif = True
pasif = False
print(type(aktif))  # <class 'bool'>
```
    Not: Python’da her nesne "doğru" (truthy) veya "yanlış" (falsy) olarak değerlendirilebilir:
- False, 0, 0.0, "", [], {}, None → falsy
- Geri kalan her şey → truthy

```
python

print(bool(0))       # False
print(bool(" "))     # True (boş değil!)
print(bool([]))      # False
```

## 2.4 Sıralı (Sequence) Tipler

### list – Liste
    Değiştirilebilir, sıralı, yinelenen elemanlara izin verir.

```
python

renkler = ["kırmızı", "yeşil", "mavi"]
sayılar = [1, 2, 3, 2]  # yinelenen olabilir
karışık = ["Türker", 28, True]

# Eleman ekleme
renkler.append("sarı")
print(renkler)  # ['kırmızı', 'yeşil', 'mavi', 'sarı']
```

### tuple – Demet
```
python

koordinat = (10, 20)
tek_eleman = (5,)  # Virgül şart!
boş_tuple = ()

# Değiştirilemez!
# koordinat[0] = 15 → TypeError
```

## range – Aralık
- Bellek verimli ardışık sayı üretir.
- Genellikle döngülerde kullanılır.

```
python

r = range(5)        # 0, 1, 2, 3, 4
r2 = range(2, 8)    # 2, 3, 4, 5, 6, 7
r3 = range(0, 10, 2)  # 0, 2, 4, 6, 8

print(list(r3))  # [0, 2, 4, 6, 8]
```













