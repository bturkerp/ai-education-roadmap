# Python Özellikleri

## 1. Yüksek Seviyeli Dil
Python, insan diline yakın bir sözdizimine sahiptir.

**Avantajları:**
- Okunabilirlik yüksek
- Az kodla çok iş
- Bakımı kolay

**Python Örneği:**
```python
sayilar = [1, 2, 3, 4, 5]
toplam = sum(sayilar)
ortalama = toplam / len(sayilar)
2. Yorumlanan Dil
Python kodu satır satır yorumlanır.

Avantajları:

Hızlı geliştirme

Platform bağımsız

Kolay hata ayıklama

Dezavantajları:

Derlenmiş dillere göre yavaş

Interpreter gerektirir

Çalışma Süreci:

Python kodu yazılır

Interpreter satır satır okur

Bytecode'a çevrilir

Sanal makinede çalıştırılır

3. Dinamik Tip Sistemi
Değişken tipleri çalışma zamanında belirlenir.

Örnek:

python
x = 10          # integer
x = "Python"    # string
x = 3.14        # float
x = [1, 2, 3]   # list
Avantajları:

Esneklik

Hızlı prototipleme

Dezavantajları:

Runtime hataları

Tip kontrolü yok

4. Platform Bağımsız
Aynı kod farklı sistemlerde çalışır.

Desteklenen Platformlar:

Windows

Linux

macOS

Raspberry Pi

Örnek:

python
import sys
print(f"Platform: {sys.platform}")
5. Açık Kaynak
Python tamamen açık kaynaklıdır.

Özellikleri:

Ücretsiz kullanım

Kaynak kodları açık

Topluluk katkısı

6. Zengin Standart Kütüphane
200+ modül standart olarak gelir.

Önemli Modüller:

python
import os        # İşletim sistemi
import json      # JSON işlemleri
import datetime  # Tarih-zaman
import math      # Matematik
import re        # Düzenli ifadeler
7. Geniş Topluluk
Büyük ve aktif geliştirici topluluğu.

Kaynaklar:

Stack Overflow

GitHub

Python Türkiye

PyPI

8. Çoklu Paradigma
Farklı programlama yaklaşımlarını destekler.

Desteklenen Paradigmalar:

Yordamsal

python
def topla(a, b):
    return a + b
Nesne Yönelimli

python
class Hesap:
    def topla(self, a, b):
        return a + b
Fonksiyonel

python
from functools import reduce
toplam = reduce(lambda x, y: x + y, [1, 2, 3])
9. Duck Typing
"Eğer ördek gibi yürüyor ve vaklıyorsa, o bir ördektir."

Örnek:

python
class Kedi:
    def ses(self):
        return "Miyav"

def ses_cikar(hayvan):
    print(hayvan.ses())

kedi = Kedi()
ses_cikar(kedi)  # Miyav
10. List Comprehensions
Kompakt liste oluşturma.

Örnek:

python
# Geleneksel
kareler = []
for x in range(10):
    kareler.append(x**2)

# Pythonic
kareler = [x**2 for x in range(10)]
11. Otomatik Bellek Yönetimi
Garbage Collection otomatik çalışır.

Örnek:

python
import gc
liste = [1, 2, 3]
liste = None  # Bellek otomatik temizlenir
gc.collect()  # Manuel temizleme
12. Decorator'lar
Fonksiyonları genişletme.

Örnek:

python
def zaman_olc(func):
    import time
    def wrapper():
        basla = time.time()
        func()
        bitir = time.time()
        print(f"Süre: {bitir-basla}s")
    return wrapper

@zaman_olc
def islem():
    time.sleep(1)

islem()  # Süre: 1.00s
13. Generator'lar
Bellek dostu iterasyon.

Örnek:

python
def sayi_uret(n):
    for i in range(n):
        yield i

for sayi in sayi_uret(1000000):
    # Bellekte tüm liste tutulmaz
    print(sayi)
14. Context Manager'lar
Kaynak yönetimi.

Örnek:

python
with open('dosya.txt', 'r') as f:
    icerik = f.read()
# Dosya otomatik kapanır
15. Geniş Ekosistem
PyPI'da 400,000+ paket.

Popüler Paketler:

bash
pip install django      # Web
pip install numpy       # Bilimsel
pip install pandas      # Veri analizi
pip install tensorflow  # Makine öğrenmesi
16. Entegrasyon
Diğer dillerle uyumlu.

Entegrasyonlar:

C/C++ (Cython)

Java (Jython)

.NET (IronPython)

Özet
Python'un Güçlü Yönleri:
✅ Kolay öğrenilir

✅ Zengin kütüphane

✅ Platform bağımsız

✅ Büyük topluluk

✅ Hızlı geliştirme

Zayıf Yönleri:
❌ Performans sınırlı

❌ Mobil geliştirme zayıf

❌ GIL multi-threading'i sınırlar

❌ Runtime hataları

Kullanım Alanları:
İyi: Web, veri bilimi, AI, otomasyon

Orta: Oyun geliştirme

Zayıf: Yüksek performans sistemler
