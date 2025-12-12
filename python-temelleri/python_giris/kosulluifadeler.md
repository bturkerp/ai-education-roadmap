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
x = 10

if x > 0:
    print("Pozitif")
else:
    print("Negatif veya Sıfır")
```

Çıktı: Pozitif olacaktır. 

### if-elif-else ile çoklu kontrol
```
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

### match-case ile tuple eşleştirme
```
nokta = (0, 1)

match nokta:
    case (0, 0):
        print("Orijin")
    case (0, y):
        print(f"x=0, y={y}")
    case (x, 0):
        print(f"x={x}, y=0")
    case _:
        print("Başka nokta")
```
Çıktı:
```
x=0, y=1
```

### match-case + guard kullanımı
```
x = 7

match x:
    case x if x % 2 == 0:
        print("Çift sayı")
    case x if x % 2 != 0:
        print("Tek sayı")
```
Çıktı: 
```
Tek sayı
```

## Özet

| Konu                | Python ≤3.9               | Python ≥3.10                   |
|--------------------|--------------------------|--------------------------------|
| Çoklu koşul         | if-elif-else            | if-elif-else veya match-case   |
| match-case          | Yok                     | Mevcut                         |
| case anahtar kelimesi | Yok                    | match-case içinde kullanılabilir |

> ⚠️ Not: `match-case` ve `case` yalnızca **Python 3.10 ve üzeri** sürümlerde çalışır.


## ÖRNEKLER
**Örnek 1:**
```
x = -3
durum = "Pozitif" if x > 0 else "Negatif veya sıfır"
print(durum)
```
Çıktı: 
```
Negatif veya sıfır
```
**Örnek 2: Mantıksal Nesne Kontrolü**
```
liste = []
sozluk = {"isim": "Ali"}

if liste:
    print("Liste dolu")
else:
    print("Liste boş")

if sozluk:
    print("Sözlük dolu")
```
Çıktı
```
Liste boş
Sözlük dolu
```
**Örnek 3: String İçerik Kontrolü**
```
mesaj = "Merhaba, Python!"

if "Python" in mesaj:
    print("Mesaj Python içeriyor")
if "Java" not in mesaj:
    print("Mesaj Java içermiyor")
```
Çıktı:
```
Mesaj Python içeriyor
Mesaj Java içermiyor
```

**Örnek 4: Liste Elemanlarını Koşullu Filtreleme**
```
sayilar = [1, -2, 3, -4, 5]
pozitifler = [x for x in sayilar if x > 0]
print(pozitifler)
```
Çıktı:
```
[1, 3, 5]
```

**Örnek 5: Dictionary ile Koşullu Değer Erişimi**
```
kullanici = {"isim": "Ayşe", "yas": 25}

if kullanici.get("yas", 0) >= 18:
    print("Reşit")
else:
    print("Reşit değil")
```
Çıktı: 
```
Reşit
```
**Örnek 6: İç İçe Koşullar + Mantıksal Operatörler**
```
a = 10
b = 20

if a > 0:
    if b > 10:
        print("a pozitif ve b 10'dan büyük")
```
Çıktı:
```
a pozitif ve b 10'dan büyük
```
**Örnek 7: match-case + Tuple Destructuring (Python 3.10+)**
```
nokta = (0, 5)

match nokta:
    case (0, y):
        print(f"x=0, y={y}")
    case (x, 0):
        print(f"x={x}, y=0")
    case _:
        print("Başka nokta")
```
Çıktı: 
```
x=0, y=5
```
