# Python Programlamaya Giriş

Python, öğrenmesi kolay, çok yönlü ve güçlü bir programlama dilidir. Web geliştirme, veri bilimi, yapay zekâ, otomasyon gibi birçok alanda kullanılır. Bu dosya, Python programlamaya yeni başlayanlar için temel bilgileri ve örnekleri içerir.

---

##  İlk Python Programı
1. Visual studio'yu açın. 
2. "File" menüsündeki "New File/Python File" seçin.
3. Örnek kodu kopyalayıp visual studio'da oluşturduğunuz boş sayfaya yapıştırın.
4. "File" menüsünden "Save" seçneği ile kaydedin.
5. Sağ üst köşedeki <img width="32" height="28" alt="image" src="https://github.com/user-attachments/assets/5dc9592a-d759-4414-b895-92a70d426f9c"/> tuşuna basarak kodu çalıştırın.

**Örnek: Merhaba Dünya**
```
python

print("Merhaba, Dünya!")
```

## 4. Yorum Satırları
Python'da yorum satırları # ile başlar. Yorumda yazanlar program işletimi sırasında dikkate alınmaz. Sadece bilgi verme 
amaçlı kullanılır. 
```
python

# Bu bir yorum satırıdır
print("Yorum satırları kodu etkilemez")
```

## [5. Değişkenler ve Veri Tipleri (Lütfen Detay İçin Tıklayınız)](degiskenlerveveritipleri.md)
Python’da değişkenler dinamik olarak oluşturulur ve veri tipleri otomatik atanır.
**Temel veri tipleri:**
- int → Tam sayılar
- float → Ondalıklı sayılar
- str → Metin (string)
- bool → Doğru / Yanlış değerler
Örnek: Değişkenler
```
python

x = 10        # int
y = 3.14      # float
isim = "Ali"  # str
aktif = True  # bool

print(x, y, isim, aktif)
```

## 6. Operatörler
Python’da matematiksel ve mantıksal işlemler için operatörler kullanılır.
**Matematiksel Operatörler:**
```
python

a = 10
b = 3

print(a + b)  # Toplama
print(a - b)  # Çıkarma
print(a * b)  # Çarpma
print(a / b)  # Bölme (float)
print(a // b) # Tam sayı bölme
print(a % b)  # Modül
print(a ** b) # Üs alma
```
**Mantıksal Operatörler:**
```
python

x = True
y = False

print(x and y)  # Mantıksal VE
print(x or y)   # Mantıksal VEYA
print(not x)    # Mantıksal DEĞİL
```

## 7. Koşul İfadeleri (if-else)
```
python

sayi = 10

if sayi > 0:
    print("Sayı pozitiftir")
elif sayi == 0:
    print("Sayı sıfırdır")
else:
    print("Sayı negatiftir")
```
Eğer sayı 0'dan büyükse "Sayı pozitifdir" eğer sayı 0 ise "Sayı sıfırdır" eksi halde "Sayı negatifdir" yazar.

## 8. Döngüler
**For Döngüsü:**
```
python

for i in range(5):
    print("Sayı:", i)
```

While Döngüsü:









