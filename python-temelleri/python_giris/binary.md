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
data = b"Merhaba Python!\nBinary dosya örneği."
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
Öıktı:
```
Merhaba Python!
Binary dosya örneği.
```











