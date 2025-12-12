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
