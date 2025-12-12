# 📁 Python OS ve Pathlib Modülleri Rehberi
## 🗂️ OS MODÜLÜ (Sistem İşlemleri)
### 🔍 Dosya ve Dizin Kontrolü
```
import os

# Dosya/dizin var mı?
print(os.path.exists("kisiler.xml"))  # True/False

# Dosya mı?
print(os.path.isfile("kisiler.xml"))  # True

# Dizin mi?
print(os.path.isdir("klasor"))  # True

# Boyut (byte)
print(os.path.getsize("kisiler.xml"))  # 1024

# Son erişim/değiştirme zamanı
print(os.path.getatime("kisiler.xml"))  # timestamp
print(os.path.getmtime("kisiler.xml"))
```
Çıktı:
```
True
True
False
169
1765556124.344498
1765555225.5427828
```

### 📂 Dizin İşlemleri
```
import os

# Çalışma dizinini değiştir
os.chdir("C:/Users")  # Windows
os.chdir("/home/user")  # Linux/Mac

# Mevcut çalışma dizini
print(os.getcwd())

# Dizin içeriğini listele
print(os.listdir("."))  # Mevcut dizin
print(os.listdir(".."))  # Üst dizin

# Tüm dosyaları listele (alt dizinlerle)
for kok, dizinler, dosyalar in os.walk("."):
    print(f"Dizin: {kok}")
    print(f"Alt dizinler: {dizinler}")
    print(f"Dosyalar: {dosyalar}")
```
Çıktı:
```

```
