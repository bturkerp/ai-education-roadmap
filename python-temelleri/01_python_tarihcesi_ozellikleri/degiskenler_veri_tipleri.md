# Python Değişkenler ve Veri Tipleri

## Değişken Nedir?
Veri saklamak için kullanılan isimli bellek alanı.

**Örnek:**
```
python
ad = "Ahmet"
yas = 25
boy = 1.75
ogrenci = True
```

Temel Veri Tipleri
1. Integer (int) - Tam Sayılar
python
# Tam sayı örnekleri
sayi = 42
negatif = -15
buyuk = 1_000_000  # Okunabilirlik için alt çizgi

# İşlemler
toplam = 10 + 5      # 15
fark = 20 - 8        # 12
carpim = 4 * 6       # 24
bolum = 15 // 4      # 3 (tam bölme)
kalan = 15 % 4       # 3
us = 2 ** 3          # 8 (2^3)
2. Float (float) - Ondalıklı Sayılar
python
# Float örnekleri
pi = 3.14159
sıcaklık = -5.5
buyuk_float = 2.5e6  # 2,500,000
kucuk_float = 1.5e-3 # 0.0015

# Hassasiyet sorunu
print(0.1 + 0.2)  # 0.30000000000000004

# Çözüm
from decimal import Decimal
print(Decimal('0.1') + Decimal('0.2'))  # 0.3
3. String (str) - Metinler
python
# String oluşturma
isim = "Ali"
cumle = 'Python öğreniyorum'
cok_satir = """Bu
çok satırlı
bir string"""

# String işlemleri
print(len(isim))           # 3
print(isim.upper())        # ALI
print(isim.lower())        # ali
print("Python".replace("P", "J"))  # Jython

# String birleştirme
ad = "Ahmet"
soyad = "Yılmaz"
tam_ad = ad + " " + soyad  # Ahmet Yılmaz

# String formatlama
yas = 25
print(f"{ad} {yas} yaşında")        # Ahmet 25 yaşında
print("{} {} yaşında".format(ad, yas))
4. Boolean (bool) - Mantıksal Değerler
python
# Boolean değerler
dogru = True
yanlis = False

# Boolean dönüşüm
print(bool(0))      # False
print(bool(1))      # True
print(bool(""))     # False
print(bool("a"))    # True
print(bool([]))     # False
print(bool([1]))    # True

# Karşılaştırma operatörleri
print(5 > 3)    # True
print(5 == 5)   # True
print(5 != 3)   # True
print(5 <= 10)  # True

# Mantıksal operatörler
print(True and False)   # False
print(True or False)    # True
print(not True)         # False
5. List (liste) - Sıralı Koleksiyon
python
# Liste oluşturma
sayilar = [1, 2, 3, 4, 5]
meyveler = ["elma", "armut", "kiraz"]
karisik = [1, "iki", 3.0, True]

# Liste işlemleri
meyveler.append("muz")      # Sonuna ekle
meyveler.insert(1, "portakal")  # Belirli pozisyona ekle
meyveler.remove("armut")    # Değeri sil
son_eleman = meyveler.pop() # Son elemanı al ve sil
uzunluk = len(meyveler)     # Liste uzunluğu

# Liste dilimleme
print(sayilar[0])      # 1 (ilk eleman)
print(sayilar[-1])     # 5 (son eleman)
print(sayilar[1:4])    # [2, 3, 4] (1'den 4'e kadar)
print(sayilar[:3])     # [1, 2, 3] (baştan 3'e kadar)
print(sayilar[2:])     # [3, 4, 5] (2'den sona kadar)
6. Tuple (demet) - Değiştirilemez Liste
python
# Tuple oluşturma
renkler = ("kırmızı", "yeşil", "mavi")
koordinat = (10, 20)
tek_eleman = (42,)  # Virgül önemli!

# Tuple işlemleri
print(renkler[0])      # kırmızı
print(len(renkler))    # 3
print("kırmızı" in renkler)  # True

# Tuple unpacking
x, y = koordinat  # x=10, y=20
7. Dictionary (sözlük) - Anahtar-Değer Çiftleri
python
# Sözlük oluşturma
ogrenci = {
    "ad": "Ahmet",
    "yas": 25,
    "numara": 12345,
    "notlar": [85, 90, 78]
}

# Sözlük işlemleri
print(ogrenci["ad"])           # Ahmet
print(ogrenci.get("ad"))       # Ahmet
print(ogrenci.get("adres", "Belirtilmemiş"))  # Varsayılan değer

ogrenci["email"] = "ahmet@mail.com"  # Yeni anahtar ekle
ogrenci["yas"] = 26              # Değer güncelle
silinen = ogrenci.pop("numara")  # Anahtarı sil

# Anahtarlar ve değerler
print(ogrenci.keys())    # dict_keys(['ad', 'yas', 'notlar', 'email'])
print(ogrenci.values())  # dict_values(['Ahmet', 26, [85, 90, 78], 'ahmet@mail.com'])
print(ogrenci.items())   # dict_items([('ad', 'Ahmet'), ('yas', 26), ...])
8. Set (küme) - Tekrarsız Elemanlar
python
# Küme oluşturma
sayilar = {1, 2, 3, 4, 5}
meyveler = {"elma", "armut", "kiraz"}

# Küme işlemleri
meyveler.add("muz")      # Eleman ekle
meyveler.remove("armut") # Eleman sil
meyveler.discard("portakal")  # Varsa sil, yoksa hata verme

# Küme operasyonları
A = {1, 2, 3, 4}
B = {3, 4, 5, 6}

print(A | B)  # Birleşim: {1, 2, 3, 4, 5, 6}
print(A & B)  # Kesişim: {3, 4}
print(A - B)  # Fark: {1, 2}
print(A ^ B)  # Simetrik fark: {1, 2, 5, 6}

Tip Kontrolü ve Dönüşümü
Tip Kontolü:
python
print(type(42))           # <class 'int'>
print(type(3.14))         # <class 'float'>
print(type("Python"))     # <class 'str'>
print(type(True))         # <class 'bool'>
print(type([1,2,3]))      # <class 'list'>
print(type((1,2,3)))      # <class 'tuple'>
print(type({"a": 1}))     # <class 'dict'>
print(type({1,2,3}))      # <class 'set'>
Tip Dönüşümü:
python
# String'den diğer tiplere
sayi_str = "42"
sayi_int = int(sayi_str)      # 42
sayi_float = float(sayi_str)  # 42.0

# Integer'dan diğer tiplere
sayi = 42
sayi_str = str(sayi)          # "42"
sayi_float = float(sayi)      # 42.0
sayi_bool = bool(sayi)        # True

# Listeden tuple'a ve tersi
liste = [1, 2, 3]
demet = tuple(liste)          # (1, 2, 3)
yeni_liste = list(demet)      # [1, 2, 3]

# String'den listeye
metin = "Python"
liste_metin = list(metin)     # ['P', 'y', 't', 'h', 'o', 'n']
Değişken İsimlendirme Kuralları
Geçerli İsimler:
python
ad = "Ahmet"
_soyad = "Yılmaz"
yas1 = 25
ogrenci_notu = 85.5
PI = 3.14  # Sabit değer (geleneksel)
Geçersiz İsimler:
python
# 1yas = 25        # Rakamla başlayamaz
# ad-soyad = "Ali" # Tire içeremez
# class = "A"      # Keyword olamaz
# ad soyad = "Ali" # Boşluk içeremez
İyi İsimlendirme Örnekleri:
python
# Açıklayıcı isimler
ogrenci_adi = "Ahmet"
toplam_not = 250
ortalama_not = toplam_not / 5

# Sabit değerler (büyük harf)
PI = 3.14159
MAX_OGRENCI = 100
None (Boş Değer)
python
# None değeri
bos_deger = None
tanimsiz = None

# None kontrolü
def kullanici_bul(id):
    if id == 1:
        return {"ad": "Ahmet", "yas": 25}
    return None

sonuc = kullanici_bul(999)
if sonuc is None:
    print("Kullanıcı bulunamadı")
Dinamik Tip Sistemi
python
# Python'da değişken tipleri değiştirilebilir
x = 10          # x şimdi int
print(type(x))  # <class 'int'>

x = "Python"    # x şimdi str
print(type(x))  # <class 'str'>

x = [1, 2, 3]   # x şimdi list
print(type(x))  # <class 'list'>

Özet Tablosu
Veri Tipi	Örnek	Değiştirilebilir	Sıralı	Açıklama
int	42	-	-	Tam sayı
float	3.14	-	-	Ondalıklı sayı
str	"Python"	Hayır	Evet	Metin
bool	True	-	-	Mantıksal
list	[1, 2, 3]	Evet	Evet	Değiştirilebilir liste
tuple	(1, 2, 3)	Hayır	Evet	Değiştirilemez liste
dict	{"a": 1}	Evet	Hayır	Anahtar-değer çiftleri
set	{1, 2, 3}	Evet	Hayır	Tekrarsız elemanlar
