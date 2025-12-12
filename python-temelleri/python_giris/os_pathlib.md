# 📁 Python OS ve Pathlib Modülleri Rehberi
## 🗂️ OS MODÜLÜ (Sistem İşlemleri)
### 🔍 Dosya ve Dizin Kontrolü
```
import os

# Dosya/dizin var mı?
print(os.path.exists("dosya.txt"))  # True/False

# Dosya mı?
print(os.path.isfile("dosya.txt"))  # True

# Dizin mi?
print(os.path.isdir("klasor"))  # True

# Boyut (byte)
print(os.path.getsize("dosya.txt"))  # 1024

# Son erişim/değiştirme zamanı
print(os.path.getatime("dosya.txt"))  # timestamp
print(os.path.getmtime("dosya.txt"))
```
Çıktı:
```

```
