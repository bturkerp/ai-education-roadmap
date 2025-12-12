# Python 2 vs Python 3

Python 2 ve Python 3, Python dilinin iki ana sürümüdür.  
Python 2 artık resmi olarak **2020 yılında desteklenmemektedir**, bu nedenle yeni projelerde Python 3 kullanılması önerilir.  

Bu dosya Python 2 ve Python 3 arasındaki temel farkları, örnekleri ve geçiş ipuçlarını içerir.

---

## 1. Print Fonksiyonu

**Python 2:**

```
python

print "Merhaba, Dünya"
```
Not: Python 3’te print bir fonksiyondur ve parantez zorunludur.

## 2. Integer Bölme

**Python 2:**
```
python

print(5 / 2)   # 2
print(5 // 2)  # 2
print(5 / 2.0) # 2.5
```

**Python 3:**
```
python

print(5 / 2)   # 2.5
print(5 // 2)  # 2
```

Python 3’te / her zaman float döner, tam sayı bölme için // kullanılır.


## 3. Unicode ve Stringler

**Python 2:**
```
python

s = "merhaba"       # ASCII string
u = u"merhaba"      # Unicode string
```

**Python 3:**
```
python

s = "merhaba"       # Unicode string (varsayılan)
b = b"merhaba"      # Byte string
```

## 4. Range ve Xrange
**Python 2:**
```
python

for i in range(5):  # Liste döndürür
    print(i)

for i in xrange(5): # Hafıza dostu generator
    print(i)
```

**Python 3:**
```
python
for i in range(5):  # Hafıza dostu iterable
    print(i)
```
Python 3’te xrange yoktur, range generator benzeri çalışır.

## 5. Hata Yönetimi (Exception)
**Python 2:**
```
python

try:
    1/0
except ZeroDivisionError, e:
    print e
```
**Python 3:**
```
python

try:
    1/0
except ZeroDivisionError as e:
    print(e)
```

## 6. input ve raw_input
**Python 2:**

```
python

x = raw_input("Bir şey gir: ")  # String alır
y = input("Bir sayı gir: ")     # Python ifadesi olarak alır
```

**Python 3:**
```
python

x = input("Bir şey gir: ")      # Tüm girdiler string
y = int(input("Bir sayı gir: ")) # Tip dönüşümü ile sayı
```

## 7. Modül İsimleri ve Fonksiyonları

- Python 2: urllib, urllib2
- Python 3: urllib.request, urllib.parse
- Python 2: dict.iteritems()
- Python 3: dict.items()
- Python 3’e next() fonksiyonu eklendi (.next() yerine)

## 8. Karakter Kodlaması
- Python 2: UTF-8 için # -*- coding: utf-8 -*- gerekir
- Python 3: Varsayılan olarak UTF-8 desteklenir

## 9. Tip Kontrolü
**Python 2:**
```
python

type(5)        # <type 'int'>
type(u"abc")   # <type 'unicode'>
```

**Python 3:**
```
python

type(5)        # <class 'int'>
type("abc")    # <class 'str'>
```

## 10. Geçiş İpuçları
- Python 2 kodunu Python 3’e taşımak için 2to3 aracı kullanılabilir:
```
bash

2to3 -w script.py
```
- Print, exception, integer bölme ve input fonksiyonu dikkat edilmesi gereken alanlardır.
- Modern kütüphaneler (NumPy, pandas) artık Python 3 uyumludur.
## Özet Tablo
| Konu                | Python 2                  | Python 3                     |
|--------------------|--------------------------|-------------------------------|
| Print              | `print "Merhaba"`        | `print("Merhaba")`           |
| Bölme `/`           | Integer bölme            | Float bölme                  |
| String             | ASCII default, `u""`     | Unicode default              |
| Range              | `range/xrange`           | `range` (generator)          |
| input/raw_input     | `input/raw_input`        | `input` (string)             |
| Exception          | `except E, e`            | `except E as e`              |
| Modüller            | `urllib, urllib2`        | `urllib.request, urllib.parse` |


