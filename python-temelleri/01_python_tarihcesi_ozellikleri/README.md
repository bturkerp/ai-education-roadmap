# 🐍 Python Eğitim Serisi

## 📋 İçindekiler

### 🔰 Başlangıç Seviyesi
1. [Python Tarihçesi ve Özellikleri](01_python_tarihcesi/README.md)
2. [Python Kurulumu ve Ortam Ayarları](02_kurulum/README.md)
3. [Python Temelleri](03_temeller/README.md)

### 📚 Temel Konular
4. [Değişkenler ve Veri Tipleri](04_degiskenler/README.md)
5. [Operatörler](05_operatorler/README.md)
6. [Kontrol Yapıları](06_kontrol_yapilari/README.md)
7. [Döngüler](07_donguler/README.md)

### 🛠️ Orta Seviye
8. [Fonksiyonlar](08_fonksiyonlar/README.md)
9. [Modüller ve Paketler](09_moduller/README.md)
10. [Dosya İşlemleri](10_dosya_islemleri/README.md)

### 🚀 İleri Seviye
11. [Nesne Yönelimli Programlama](11_oop/README.md)
12. [Hata Yönetimi](12_hata_yonetimi/README.md)
13. [Veritabanı İşlemleri](13_veritabani/README.md)

## 🚀 Hızlı Başlangıç

```bash
# Repository'yi klonlayın
git clone https://github.com/[kullanici_adi]/python-egitimi.git
cd python-egitimi

# Sanal ortam oluşturun
python -m venv venv

# Windows
venv\Scripts\activate

# Linux/Mac
source venv/bin/activate

# Gerekli paketleri yükleyin
pip install -r requirements.txt

# İlk dersle başlayın
cd 01_python_tarihcesi
python ornekler.py

📁 Proje Yapısı
text
python-egitimi/
├── 01_python_tarihcesi/
│   ├── README.md
│   ├── ornekler.py
│   ├── alistirmalar.py
│   └── cozumler/
├── 02_kurulum/
│   ├── README.md
│   ├── vscode_kurulumu.md
│   └── conda_kurulumu.md
├── requirements.txt
├── .gitignore
└── LICENSE
🤝 Katkıda Bulunma
Fork'layın

Feature branch oluşturun

Değişikliklerinizi commit edin

Branch'inizi push edin

Pull Request açın

📞 İletişim
Sorularınız için Issues kısmından ulaşabilirsiniz.

Eğitim serisi devam ediyor...

text

## 2. 01_python_tarihcesi/README.md

```markdown
# 1. Bölüm: Python Tarihçesi ve Özellikleri

## 📚 Bu Bölümde Öğrenecekleriniz:
- ✅ Python'un tarihçesi
- ✅ Python 2 vs Python 3 farkları
- ✅ Python'un kullanım alanları
- ✅ İlk Python programınız

## 🎯 Python Nedir?

Python, Guido van Rossum tarafından 1991'de oluşturulmuş bir programlama dilidir.

### Temel Özellikler:
```python
# 1. Kolay okunabilir
def merhaba(isim):
    return f"Merhaba {isim}!"

# 2. Dinamik tip sistemi
x = 10      # integer
x = "on"    # string

# 3. Zengin kütüphane desteği
import os, math, datetime, json
📅 Python Tarihçesi
Yıl	Olay
1989	Guido Python'u geliştirmeye başladı
1991	İlk sürüm (0.9.0)
2000	Python 2.0
2008	Python 3.0
2020	Python 2 desteği sona erdi
İlginç Bilgi: Python adı, Guido'nun sevdiği "Monty Python" komedi grubundan geliyor!

🔄 Python 2 vs Python 3
Ana Farklar:
python
# Python 2
print "Merhaba"   # print ifade
5 / 2 = 2         # tam sayı bölme

# Python 3
print("Merhaba")  # print fonksiyon
5 / 2 = 2.5       # float bölme
5 // 2 = 2        # tam bölme için //
Öneri: Yeni projelerde mutlaka Python 3 kullanın!

💼 Python Nerelerde Kullanılır?
1. 🌐 Web Geliştirme
python
# Flask ile web uygulaması
from flask import Flask
app = Flask(__name__)

@app.route('/')
def home():
    return 'Ana Sayfa'
2. 📊 Veri Bilimi
python
# Pandas ile veri analizi
import pandas as pd
veriler = pd.read_csv('data.csv')
print(veriler.head())
3. 🤖 Yapay Zeka
python
# Makine öğrenmesi
from sklearn.linear_model import LinearRegression
model = LinearRegression()
model.fit(X_train, y_train)
4. ⚡ Otomasyon
python
# Dosya işlemleri
import os
for dosya in os.listdir('.'):
    if dosya.endswith('.txt'):
        print(f"Bulundu: {dosya}")
🚀 Python'un Avantajları
Kolay öğrenilir - Sözdizimi temiz ve okunabilir

Çok yönlü - Her alanda kullanılabilir

Büyük topluluk - Yardım almak kolay

Ücretsiz - Tamamen açık kaynak

📝 İlk Python Programımız
ornekler.py dosyasını oluşturun:

python
# ornekler.py

# 1. Ekrana yazdırma
print("Merhaba Python!")

# 2. Değişkenler
isim = "Ahmet"
yas = 25
print(f"{isim} {yas} yaşında")

# 3. Matematik işlemleri
sayi1 = 10
sayi2 = 20
toplam = sayi1 + sayi2
print(f"10 + 20 = {toplam}")

# 4. Kullanıcıdan girdi alma
# ad = input("Adınız: ")
# print(f"Hoş geldin {ad}!")
Çalıştırmak için:

bash
python ornekler.py
🎯 Pratik Alıştırmalar
Alıştırma 1: Kişisel Bilgiler
Kullanıcıdan ad, yaş ve şehir bilgilerini alıp ekrana yazdıran program yazın.

Alıştırma 2: Hesap Makinesi
İki sayı alıp toplama, çıkarma, çarpma, bölme işlemlerini yapan program yazın.

Alıştırma 3: Python Sürümü
Python sürümünüzü kontrol eden program yazın.

🔗 Faydalı Kaynaklar
Python.org

Real Python

Python Türkiye

📌 Özet
✅ Python kolay öğrenilen bir dildir

✅ Python 3 kullanmalısınız

✅ Web, veri bilimi, AI gibi birçok alanda kullanılır

✅ İlk programınızı yazdınız!
