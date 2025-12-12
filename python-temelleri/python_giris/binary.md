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
data = b"Hello Python!\nBinary file example."
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
# Küçük dosyalar için
with open("ornek.bin", "rb") as kaynak:
    icerik = kaynak.read()

with open("kopya_ornek.bin", "wb") as hedef:
    hedef.write(icerik)

# Büyük dosyalar için (bellek dostu)
with open("buyuk_dosya.bin", "rb") as kaynak, \
     open("kopya_buyuk.bin", "wb") as hedef:
    
    while True:
        bolum = kaynak.read(4096)  # 4KB bloklar halinde oku
        if not bolum:
            break
        hedef.write(bolum)
```

## 🖼️ Resim Dosyası İşleme
```
# Resmi binary olarak kopyalama
with open("resim.jpg", "rb") as kaynak:
    resim_verisi = kaynak.read()

with open("kopya_resim.jpg", "wb") as hedef:
    hedef.write(resim_verisi)
```









