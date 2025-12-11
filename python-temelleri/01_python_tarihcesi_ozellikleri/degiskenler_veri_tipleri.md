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
