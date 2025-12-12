# 🗄️ Python İkili Dosyalar (Binary Files)

Python'da ikili dosyalar (binary files), genellikle resim, ses, video veya özel veri formatları için kullanılır.  
Metin dosyalarının aksine, binary dosyalar ham veri olarak okunur ve yazılır.

---

## 📂 Binary Dosya Açma Modları

| Mod | Açıklama |
|-----|----------|
| `"rb"` | Binary okuma (read binary) |
| `"wb"` | Binary yazma (write binary) - varsa üzerine yazar |
| `"ab"` | Binary ekleme (append binary) |
| `"rb+"` | Binary okuma ve yazma |

> **Not:** Binary modda okuma/yazma yapılırken veriler `bytes` tipindedir.

---

## ✍️ Binary Dosyaya Yazma

```
turkish_text = "Merhaba Python!\nBinary dosya örneği."
data = turkish_text.encode("utf-8")
with open("ornek.bin", "wb") as f:
    f.write(data)
```
Açıklama:
- b → byte literal, binary veriyi temsil eder
- "wb" → dosya yoksa oluşturur, varsa üzerine yazar
- with kullanımı dosyanın otomatik kapanmasını sağlar

## 🔄 Binary Veriyi Metne Çevirme
```
with open("ornek.bin", "rb") as f:
    icerik = f.read()
    metin_hal = icerik.decode("utf-8")
    print(metin_hal)
```
çıktı:
```
Merhaba Python!
Binary dosya örneği.
```

## 📋 Binary Dosya Kopyalama
```
buyuk_veri = b"X" * 10000  
with open("buyuk.bin", "wb") as f:
    f.write(buyuk_veri)

data = b"Merhaba Python!"
with open("dosya.bin", "wb") as f:
    f.write(data)

with open("dosya.bin", "rb") as f:
    okunan = f.read()
    print(okunan)  

with open("dosya.bin", "rb") as kaynak:
    with open("kopya.bin", "wb") as hedef:
        hedef.write(kaynak.read())

with open("buyuk.bin", "rb") as kaynak, open("kopya_buyuk.bin", "wb") as hedef:
    while bolum := kaynak.read(4096):  # 4KB bloklar
        hedef.write(bolum)
print("Kopyalama tamamlandı!")
```

## 🖼️ Resim Dosyası İşleme
```
# Resmi binary olarak kopyalama
with open("resim.jpg", "rb") as kaynak:
    resim_verisi = kaynak.read()

with open("kopya_resim.jpg", "wb") as hedef:
    hedef.write(resim_verisi)
```

## 🔍 Binary Veriyi Analiz Etme
```
with open("ornek.bin", "rb") as f:
    icerik = f.read()
    
    # Byte sayısı
    print(f"Toplam byte: {len(icerik)}")
    
    # İlk 10 byte'ı hex olarak göster
    print(f"İlk 10 byte (hex): {icerik[:10].hex()}")
    
    # İlk 10 byte'ı decimal olarak göster
    print(f"İlk 10 byte (decimal): {list(icerik[:10])}")
```
Çıktı: 
```
Toplam byte: 38
İlk 10 byte (hex): 4d657268616261205079
İlk 10 byte (decimal): [77, 101, 114, 104, 97, 98, 97, 32, 80, 121]
```








