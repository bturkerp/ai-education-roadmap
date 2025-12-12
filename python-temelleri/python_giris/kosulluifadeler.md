# Python Koşul İfadeleri (if-else ve match-case)

Koşul ifadeleri, programın akışını belirli şartlara göre kontrol etmemizi sağlar.

---

## 1. if-elif-else Yapısı

Python'da temel koşul ifadeleri `if`, `elif` ve `else` ile yapılır.

| Yapı   | Açıklama |
|--------|----------|
| if     | Şart doğruysa çalıştırılır |
| elif   | Önceki if yanlışsa ve kendi şartı doğruysa çalıştırılır |
| else   | Önceki tüm şartlar yanlışsa çalıştırılır |

---

### Basit if-else

```
python

x = 10

if x > 0:
    print("Pozitif")
else:
    print("Negatif veya Sıfır")
```

Çıktı: Pozitif olacaktır. 

### if-elif-else ile çoklu kontrol
```
python

x=int(input("Lütfen bir tamsayı giriniz: "))
if x>0: 
    print("pozitif")
elif x==0:
    print("sıfır")
else:
    print("negatif")
```

### Mantıksal operatörler ile koşullar
```
python

a = 5
b = 10

if a > 0 and b > 0:
    print("Her ikisi de pozitif")
if a > 0 or b < 0:
    print("En az biri pozitif")
if not a < 0:
    print("a negatif değil")
```
Çıktı:
```
Her ikisi de pozitif
En az biri pozitif
a negatif değil
```

## İç içe if kullanımı
```
python

x = 15

if x > 0:
    print("Pozitif")
    if x % 2 == 0:
        print("Çift sayı")
    else:
        print("Tek sayı")
```
Çıktı: 
```
Pozitif
Tek sayı
```

## 2. match-case (Python 3.10+)
| Yapı     | Açıklama                             |
|----------|-------------------------------------|
| match    | Değişkeni kontrol eder               |
| case     | Belirli değere eşleşirse çalışır     |
| case _   | Hiçbir case eşleşmezse çalışır (default) |

### Basit match-case kullanımı
```
python

x = 2

match x:
    case 1:
        print("Bir")
    case 2:
        print("İki")
    case 3:
        print("Üç")
    case _:
        print("Diğer")
```
Çıktı:
```
İki
```

### String ile match-case
```
python

meyve = "elma"

match meyve:
    case "elma":
        print("Elma seçildi")
    case "armut":
        print("Armut seçildi")
    case _:
        print("Başka bir meyve")
```
Çıktı:
```
Elma seçildi
```






