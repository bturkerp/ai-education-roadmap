**Açıklama:**
- `b` → byte literal, binary veriyi temsil eder
- `"wb"` → dosya yoksa oluşturur, varsa üzerine yazar
- `with` kullanımı dosyanın otomatik kapanmasını sağlar

---

## 📖 Binary Dosyadan Okuma

```
with open("ornek.bin", "rb") as f:
    icerik = f.read()
    print(icerik)
```
