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

```python
data = b"Merhaba Python!\nBinary dosya örneği."
with open("ornek.bin", "wb") as f:
    f.write(data)
```
