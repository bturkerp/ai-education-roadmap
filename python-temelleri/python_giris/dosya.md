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





