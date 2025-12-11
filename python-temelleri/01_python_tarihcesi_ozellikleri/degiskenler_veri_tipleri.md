**🐍 Python Eğitimi: Değişkenler ve Veri Tipleri (Tam Kapsamlı)**

#🔹 1. Değişken Nedir?

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

#🔹 2. Python’da Tüm Yerleşik Veri Tipleri

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

## 🔸 2.1 Sayısal Tipler
### 🔹 int – Tam Sayılar
Sınırsız uzunlukta, pozitif/negatif tam sayılar.

```
python

x = 42
y = -1000
z = 0
print(type(x))  # <class 'int'>
```

    Python 3'te long tipi yoktur; int sonsuz duyarlılıkta çalışır.

###🔹 float – Ondalıklı Sayılar

64-bit IEEE 754 double precision (yaklaşık 15–17 anlamlı basamak).
