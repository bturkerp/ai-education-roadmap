# Python Operatörleri

Python'da operatörler, değişkenler veya değerler üzerinde işlem yapmamızı sağlar. Operatörler türlerine göre gruplandırılır.

---

## 1. Aritmetik Operatörler

| Operatör | Açıklama          | Örnek          |
|----------|-----------------|----------------|
| +        | Toplama          | 5 + 3 → 8      |
| -        | Çıkarma          | 5 - 3 → 2      |
| *        | Çarpma           | 5 * 3 → 15     |
| /        | Bölme (float)    | 5 / 2 → 2.5    |
| //       | Tam sayı bölme   | 5 // 2 → 2     |
| %        | Modül (kalan)    | 5 % 2 → 1      |
| **       | Üs alma          | 2 ** 3 → 8     |

**Örnek:**

```
python

a = 10
b = 3

print(a + b)   # 13
print(a - b)   # 7
print(a * b)   # 30
print(a / b)   # 3.3333333333333335
print(a // b)  # 3
print(a % b)   # 1
print(a ** b)  # 1000
```
## 2. Atama Operatörleri
| Operatör | Açıklama                  | Örnek     |
|----------|---------------------------|-----------|
| =        | Atama                     | a = 5     |
| +=       | Toplama ve atama          | a += 2    |
| -=       | Çıkarma ve atama          | a -= 2    |
| *=       | Çarpma ve atama           | a *= 2    |
| /=       | Bölme ve atama            | a /= 2    |
| //=      | Tam sayı bölme ve atama   | a //= 2   |
| %=       | Modül ve atama            | a %= 2    |
| **=      | Üs ve atama               | a **= 2   |

```
python

a = 10
a += 5  # a = a + 5
print(a)  # 15
a *= 2
print(a)  # 30
a %= 7
print(a)  # 2
```

## 3. Karşılaştırma Operatörleri
| Operatör | Açıklama          | Örnek           |
|----------|-----------------|----------------|
| ==       | Eşit mi?         | 5 == 5 → True  |
| !=       | Eşit değil mi?   | 5 != 3 → True  |
| >        | Büyük mü?        | 5 > 3 → True   |
| <        | Küçük mü?        | 5 < 3 → False  |
| >=       | Büyük veya eşit  | 5 >= 5 → True  |
| <=       | Küçük veya eşit  | 3 <= 5 → True  |

```
python

a = 5
b = 3

print(a == b)  # False
print(a != b)  # True
print(a > b)   # True
print(a < b)   # False
print(a >= 5)  # True
print(b <= 5)  # True
```

## 4. Mantıksal Operatörler
| Operatör | Açıklama               | Örnek               |
|----------|-----------------------|-------------------|
| and      | VE (iki şart doğruysa) | True and False → False |
| or       | VEYA (bir şart doğruysa)| True or False → True |
| not      | DEĞİL                  | not True → False  |

```
python

x = True
y = False

print(x and y)  # False
print(x or y)   # True
print(not x)    # False
```

## 5. Kimlik (Identity) Operatörleri
| Operatör | Açıklama             | Örnek          |
|----------|--------------------|----------------|
| is       | Aynı mı?           | a is b         |
| is not   | Farklı mı?         | a is not b     |

```
python

a = [1,2,3]
b = a
c = [1,2,3]

print(a is b)      # True
print(a is c)      # False
print(a is not c)  # True
```

## 6. Üyelik (Membership) Operatörleri
| Operatör | Açıklama           | Örnek                  |
|----------|------------------|-----------------------|
| in       | İçinde mi?        | 2 in [1,2,3] → True   |
| not in   | İçinde değil mi?  | 5 not in [1,2,3] → True |

```
python

liste = [1,2,3,4]

print(2 in liste)     # True
print(5 not in liste) # True
```

## 7. Bit Düzeyinde (Bitwise) Operatörler
| Operatör | Açıklama           | Örnek        |
|----------|------------------|-------------|
| &        | AND bit düzeyinde  | 5 & 3 → 1   |
| |        | OR bit düzeyinde   | 5 | 3 → 7   |
| ^        | XOR bit düzeyinde  | 5 ^ 3 → 6   |
| ~        | NOT bit düzeyinde  | ~5 → -6     |
| <<       | Sol kaydırma       | 5 << 1 → 10 |
| >>       | Sağ kaydırma       | 5 >> 1 → 2  |

```
python

a = 5  # 0101
b = 3  # 0011

print(a & b)   # 1
print(a | b)   # 7
print(a ^ b)   # 6
print(~a)      # -6
print(a << 1)  # 10
print(a >> 1)  # 2
```


