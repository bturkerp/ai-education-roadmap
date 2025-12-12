# Python Operatörleri

Python'da operatörler, değişkenler veya değerler üzerinde işlem yapmamızı sağlar. Operatörler türlerine göre gruplandırılır.

---

## 1. Aritmetik Operatörler

| Operatör | Açıklama          | Örnek          |
|----------|-----------------|----------------|
| `+`      | Toplama          | `5 + 3` → 8    |
| `-`      | Çıkarma          | `5 - 3` → 2    |
| `*`      | Çarpma           | `5 * 3` → 15   |
| `/`      | Bölme (float)    | `5 / 2` → 2.5  |
| `//`     | Tam sayı bölme   | `5 // 2` → 2   |
| `%`      | Modül (kalan)    | `5 % 2` → 1    |
| `**`     | Üs alma          | `2 ** 3` → 8   |

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

## 2. Atama Operatörleri
| Operatör | Açıklama              | Örnek     |
|----------|---------------------|-----------|
| =        | Atama               | a = 5     |
| +=       | Toplama ve atama     | a += 2    |
| -=       | Çıkarma ve atama     | a -= 2    |
| *=       | Çarpma ve atama      | a *= 2    |
| /=       | Bölme ve atama       | a /= 2    |
| //=      | Tam sayı bölme ve atama | a //= 2 |
| %=       | Modül ve atama       | a %= 2    |
| **=      | Üs ve atama          | a **= 2   |

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
