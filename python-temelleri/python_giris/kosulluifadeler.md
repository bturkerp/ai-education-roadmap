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

### Örnek 1: Basit if-else

```python
x = 10

if x > 0:
    print("Pozitif")
else:
    print("Negatif veya Sıfır")
