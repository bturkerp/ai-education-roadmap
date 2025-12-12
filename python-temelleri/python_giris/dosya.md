# Python Dosya İşlemleri (File I/O)

Python’da dosya işlemleri, **okuma, yazma, ekleme ve silme** gibi temel işlemleri kapsar.  
Bu eğitimde **kod örnekleri + açıklama** ile tüm temel dosya fonksiyonları gösterilmektedir.

---

## 1. Dosya Açma (`open()`)

```
dosya = open("ornek.txt", "w")  # 'w' → yazma modu
dosya.write("Merhaba Python!\n")
dosya.close()
```

Açıklama:
- "w" → yazma modu, dosya yoksa oluşturur, varsa üzerine yazar.
- "r" → okuma, "a" → ekleme modu.
- Dosya işiniz bittiğinde her zaman kapatın.

## 2. Dosyaya Yazma (write)
```
with open("veri.txt", "w") as f:
    f.write("Python öğreniyorum.\n")
    f.write("Dosya işlemleri çok kolay!\n")
```
Açıklama:
- with bloğu → otomatik dosya kapatma (close() gerekmez).
- \n → satır sonu.

## 3. Dosyadan Okuma (read)
```
with open("veri.txt", "r") as f:
    icerik = f.read()
print(icerik)
```
Açıklama: read() → dosyanın tamamını string olarak okur.

## 4. Satır Satır Okuma (readline, readlines)
```
with open("veri.txt", "r") as f:
    print(f.readline())
    print(f.readline())

with open("veri.txt", "r") as f:
    satirlar = f.readlines()
    print(satirlar)
```
Çıktı:
```
Python öğreniyorum.
Dosya işlemleri çok kolay!
['Python öğreniyorum.\n', 'Dosya işlemleri çok kolay!\n']
```

## Dosyaya Ekleme (append)
```
with open("veri.txt", "a") as f:
    f.write("Yeni bir satır eklendi.\n")
```

## 6. Dosya Var mı Kontrol Etme (try-except)
```
try:
    with open("olmayan.txt", "r") as f:
        print(f.read())
except FileNotFoundError:
    print("Dosya bulunamadı!")
```
Hata oluşursa program durmaz, istisna yakalanır.

## 7. Dosya Silme (os modülü)
```
import os

if os.path.exists("veri.txt"):
    os.remove("veri.txt")
    print("Dosya silindi.")
else:
    print("Dosya bulunamadı.")
```
## 8. Dosya İçinde Arama
```
with open("veri.txt", "r") as f:
    for satir in f:
        if "Python" in satir:
            print(satir.strip())
```
strip() → satır sonundaki \n karakterini temizler.

## 9. Önemli Dosya Modları

| Mod         | Açıklama                         |
|------------|---------------------------------|
| "r"        | Okuma                            |
| "w"        | Yazma (varsa üzerine yazar)      |
| "a"        | Ekleme                           |
| "x"        | Oluşturma, dosya varsa hata verir |
| "rb"/"wb"/"ab" | Binary modda okuma/yazma/ekleme |

---

## Özet

Bu bölümde, Python ile:

- Dosya açma ve kapama  
- Okuma ve yazma  
- Satır satır okuma  
- Ekleme  
- Hata yakalama  
- Dosya silme ve arama  

gibi temel ve ileri düzey dosya işlemlerini öğrendik.
## Örnek
```
import os
import csv
import json
from pathlib import Path
import shutil

# 1️⃣ Basit Yazma ve Okuma
with open("ornek.txt", "w") as f:
    f.write("Python dosya işlemleri öğreniyorum.\n")
    f.write("Bu satır ikinci satır.\n")

with open("ornek.txt", "r") as f:
    print("📄 Dosya içeriği:")
    print(f.read())

# 2️⃣ Satır Satır Okuma
with open("ornek.txt", "r") as f:
    print("📄 Satır satır okuma:")
    for satir in f:
        print(satir.strip())

# 3️⃣ Dosyaya Ekleme
with open("ornek.txt", "a") as f:
    f.write("Bu bir ekleme satırıdır.\n")

# 4️⃣ Dosya Var mı Kontrol Etme
dosya = "ornek.txt"
if os.path.exists(dosya):
    print(f"{dosya} dosyası mevcut, boyutu: {os.path.getsize(dosya)} bytes")
else:
    print(f"{dosya} bulunamadı!")

# 5️⃣ Binary Dosya İşlemi
# Küçük örnek için aynı metin dosyasını binary olarak kopyalayalım
with open("ornek.txt", "rb") as kaynak:
    icerik = kaynak.read()

with open("kopya_ornek.txt", "wb") as hedef:
    hedef.write(icerik)
```

## İleri Düzey Dosya İşlemleri
- [İkili Dosyalar (Binary Files) (Detay İçin Tıklayın Lütfen)](binary.md)
- [CSV Dosyalar (Detay İçin Tıklayın Lütfen)](csv.md)
- JSON Dosyalar
- XML Dosyalar
- os ve pathlib kullanımı
- Dosya Okuma Optimzasyonu
- Context manager (with) kullanımı
