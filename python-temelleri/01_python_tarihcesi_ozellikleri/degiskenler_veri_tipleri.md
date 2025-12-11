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

## 2.5 Eşleme Tipi: dict (Sözlük)
- Anahtar-değer (key-value) çiftleriyle çalışır.
- Anahtarlar değiştirilemez olmalı (str, int, tuple olabilir).
- Değiştirilebilir, sırasız (Python 3.7+’da ekleme sırasına göre sıralı).

```
python

kullanıcı = {
    "isim": "Türker",
    "yas": 28,
    "aktif": True
}

print(kullanıcı["isim"])  # Türker

# Yeni anahtar ekleme
kullanıcı["şehir"] = "İstanbul"

# .get ile güvenli erişim
print(kullanıcı.get("telefon", "Belirtilmemiş"))  # Belirtilmemiş
```

## 2.6 Küme (Set) Tipleri

### set – Küme
Sırasız, değiştirilebilir, yinelenen eleman içermeyen koleksiyon.

```
python

meyveler = {"elma", "muz", "portakal"}
meyveler.add("çilek")
meyveler.add("elma")  # Tekrar eklenmez!
print(meyveler)  # {'çilek', 'muz', 'elma', 'portakal'} (sıra değişebilir)

# Küme işlemleri
a = {1, 2, 3}
b = {3, 4, 5}
print(a | b)  # Birleşim: {1, 2, 3, 4, 5}
print(a & b)  # Kesişim: {3}
```

### frozenset – Değiştirilemez Küme
    set gibi ama sözlük anahtarı olarak kullanılabilir.
```
python

donmuş = frozenset([1, 2, 3])
# donmuş.add(4) → AttributeError
```

## 2.7 İkili (Binary) Tipler
### bytes – Bayt Dizisi
Değiştirilemez, 0–255 arası tam sayılardan oluşur.
    
```
python

b = b"Merhaba"
print(b[0])  # 77 → 'M'nin ASCII değeri
print(type(b))  # <class 'bytes'>
```

### bytearray – Değiştirilebilir Bayt Dizisi
```
python

ba = bytearray(b"Merhaba")
ba[0] = 75  # 'K' ASCII'si
print(ba)  # bytearray(b'Kerhaba')
```

### memoryview – Bellek Görünümü
Büyük verilerde kopyalama yapılmadan erişim sağlar (performans için).

```
python

veri = bytearray(b"Python")
görünüm = memoryview(veri)
print(görünüm[0])  # 80
```

## 2.8 NoneType – None
- "Hiçbir şey"i temsil eder.
- Fonksiyon bir şey döndürmezse None döner.

```
python

sonuç = print("Merhaba")  # print None döner
print(sonuç)  # None
print(type(None))  # <class 'NoneType'>
```
None bir singletontur: None is None → True


## Tür Kontrolü ve Dönüşümü

### type() ve isinstance()
```
python

x = 42
print(type(x) == int)        # True
print(isinstance(x, int))    # True (önerilen)
```

### Tür Dönüştürme (Type Casting)
```
python

# Sayı ↔ Metin
sayi = int("42")         # str → int
metin = str(42)          # int → str

# Ondalıklı ↔ Tam
x = float(5)             # 5.0
y = int(3.9)             # 3 (keser, yuvarlamaz!)

# Liste ↔ Demet
liste = list((1, 2, 3))  # (1, 2, 3) → [1, 2, 3]
demet = tuple([1, 2, 3]) # [1, 2, 3] → (1, 2, 3)

# İkili ↔ Metin
b = "Türker".encode("utf-8")   # str → bytes
s = b.decode("utf-8")          # bytes → str
```

## 2.10 Değişken Kimliği ve Referanslar
Python’da değişkenler nesnelere referanstır:
```
python

a = [1, 2, 3]
b = a
b.append(4)
print(a)  # [1, 2, 3, 4] → çünkü a ve b aynı nesneyi gösterir

# Kimlik (bellek adresi)
print(id(a) == id(b))  # True
```
Değiştirilebilir nesnelerde dikkat! Kopya almak için:
```
python

import copy
b = copy.deepcopy(a)
```

🎯 Özet Tablosu

| Kategori           | Tip(ler)                              | Değiştirilebilir mi? | Sıralı mı? | Yinelenen Elemanlara İzin Verir mi? |
|--------------------|----------------------------------------|----------------------|------------|--------------------------------------|
| Sayısal            | `int`, `float`, `complex`             | Hayır                | –          | –                                    |
| Metin              | `str`                                 | Hayır                | Evet       | Evet                                 |
| Mantıksal          | `bool`                                | Hayır                | –          | –                                    |
| Sıralı             | `list`, `tuple`, `range`              | `list`: Evet<br>`tuple`, `range`: Hayır | Evet       | `list`, `tuple`: Evet<br>`range`: Evet (otomatik ardışık) |
| Eşleme             | `dict`                                | Evet                 | Python 3.7+: Evet | Anahtar: Hayır<br>Değer: Evet          |
| Küme               | `set`, `frozenset`                    | `set`: Evet<br>`frozenset`: Hayır | Hayır      | Hayır                                |
| İkili (Binary)     | `bytes`, `bytearray`, `memoryview`    | `bytes`: Hayır<br>`bytearray`, `memoryview`: Evet | Evet | Evet                                 |
| Boş (Null)         | `None` (`NoneType`)                   | –                    | –          | –                                    |

🧪 Alıştırma (Kendin Dene!)

1. Adını, yaşını, boyunu ve öğrencimi olduğunu içeren bir dict oluştur.
2. Bu sözlüğü kullanarak "Merhaba, ben Türker. 28 yaşındayım, boyum 1.75m ve öğrenci değilim." şeklinde bir cümle üret.
3. Aşağıdaki ifadelerin sonuçlarını tahmin et, sonra çalıştır:
        * bool([])
        * bool("False")
        * int(3.9)
        * str(10) + str(20)
        * list(range(0, 10, 2))
