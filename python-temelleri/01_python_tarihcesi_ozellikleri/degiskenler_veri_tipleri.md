# 🐍 Python Eğitimi: Değişkenler ve Veri Tipleri

Bu bölümde, Python'da **değişkenlerin nasıl tanımlandığını** ve **temel veri tiplerini** öğreneceksiniz. Python, dinamik olarak yazılan (dynamically typed) bir dildir — yani bir değişkenin türünü açıkça belirtmenize gerek yoktur; Python bunu otomatik olarak algılar.

## 📌 İçindekiler
- [Değişken Nedir?](#değişken-nedir)
- [Değişken Tanımlama Kuralları](#değişken-tanımlama-kuralları)
- [Python’da Temel Veri Tipleri](#python’da-temel-veri-tipleri)
  - [1. Sayısal Tipler](#1-sayısal-tipler)
  - [2. Metin Tipleri](#2-metin-tipleri)
  - [3. Mantıksal Tipler](#3-mantıksal-tipler)
  - [4. Sıralı (Sequence) Tipler](#4-sıralı-sequence-tipler)
  - [5. Eşleme (Mapping) Tipi](#5-eşleme-mapping-tipi)
  - [6. Küme (Set) Tipleri](#6-küme-set-tipleri)
  - [7. İkili (Binary) Tipler](#7-ikili-binary-tipler)
- [Veri Tipini Nasıl Öğreniriz?](#veri-tipini-nasıl-öğreniriz)
- [Değişken Türünü Dönüştürme (Type Casting)](#değişken-türünü-dönüştürme-type-casting)
- [Önemli Hatırlatmalar](#önemli-hatırlatmalar)

---

## Değişken Nedir?

Bir **değişken**, bir veriyi (sayı, metin, liste vb.) bellekte saklamak için kullanılan bir isimdir.  
Python’da bir değişken oluşturmak için yalnızca `değişken_adı = değer` yazmanız yeterlidir.

```python
isim = "Ahmet"
yas = 25```

Bu örnekte:

    isim adlı bir değişkene "Ahmet" metni,
    yas adlı bir değişkene 25 sayısı atanmıştır.

Değişken Tanımlama Kuralları

    Harf veya alt çizgi (_) ile başlamalıdır.
        ✅ Geçerli: ad, _puan
        ❌ Geçersiz: 2ad, @puan
    Sadece harf, rakam ve alt çizgi içerebilir.
        ✅ Geçerli: toplam_puan1
        ❌ Geçersiz: toplam-puan, toplam puan
    Python anahtar kelimeleri (if, else, for vb.) kullanılamaz.
    Büyük/küçük harf duyarlıdır: Ad ≠ ad.
    Türkçe karakterler teknik olarak çalışsa da kullanılmamalıdır (taşınabilirlik ve kodlama sorunları).

Python’da Temel Veri Tipleri
1. Sayısal Tipler

    int: Tam sayılar  

    python
    1

float: Ondalıklı sayılar  

python
1

complex: Karmaşık sayılar  

python
1

2. Metin Tipleri

    str: Metin (string)  

    python
    1

3. Mantıksal Tipler

    bool: True veya False  

    python
    1

4. Sıralı (Sequence) Tipler

    list: Değiştirilebilir liste  

    python
    1

tuple: Değiştirilemez demet  

python
1

range: Sayı aralığı  

python
1

5. Eşleme (Mapping) Tipi

    dict: Anahtar-değer çiftleri  

    python
    1

6. Küme (Set) Tipleri

    set: Benzersiz, sırasız elemanlar  

    python
    1

frozenset: Değiştirilemez küme  

python
1

7. İkili (Binary) Tipler

    bytes: Değiştirilemez bayt dizisi  

    python
    1

bytearray: Değiştirilebilir bayt dizisi  

python
1

memoryview: Bellek verisine verimli erişim  

python
1

Veri Tipini Nasıl Öğreniriz?

python
1
2

Veya:

python
1int("10")        # → 10
float("3.14")    # → 3.14
str(42)          # → "42"
bool(1)          # → True
list("abc")      # → ['a', 'b', 'c']
tuple([1, 2])    # → (1, 2)
Değişken Türünü Dönüştürme (Type Casting)


    ⚠️ Geçersiz dönüşümler hata verir: int("merhaba") → ValueError

Önemli Hatırlatmalar

    Python’da her şey bir nesnedir.
    None özel bir değerdir: "hiçbir şey" anlamına gelir (NoneType).

    python
    1

Değişkenler bellekte referans olarak saklanır.
id() ile bellek adresi öğrenilebilir:

python
1

    ✨ İpucu: Kodlarınızı Google Colab
     veya yerel Python REPL ile deneyin.
    🔄 Sonraki konu: Operatörler ve ifadeler (aritmetik, karşılaştırma, mantıksal).

Yazar: [Senin Adın]
Lisans: MIT
Son Güncelleme: 12 Aralık 2025
