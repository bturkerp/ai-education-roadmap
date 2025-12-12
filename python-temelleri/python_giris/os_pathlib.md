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
D:\quantum NN
['Best Model.docx', ..., '~$Sunu1.pptx', '~WRD0122.tmp', '~WRL3927.tmp']
['$RECYCLE.BIN', ... , '__pycache__', '~$eplearnin ortamı.docx']
Dizin: .
Alt dizinler: []
Dosyalar: ['Best Model.docx', ..., '~$st Model.docx', '~$Sunu1.pptx', '~WRD0122.tmp', '~WRL3927.tmp']
```
#### 📝 Dosya/Dizin Oluşturma/Silme
```
import os

# Dizin oluştur
os.mkdir("yeni_klasor")  # Tek dizin
os.makedirs("a/b/c")  # İç içe dizinler (recursive)
os.makedirs("dizin", exist_ok=True)  # Varsa hata vermez

# Dosya oluştur
with open("yeni_dosya.txt", "w") as f:
    f.write("Merhaba")

# Dosya/dizin sil
os.remove("dosya.txt")  # Dosya sil
os.rmdir("bos_klasor")  # Boş dizin sil
os.removedirs("a/b/c")  # İç içe boş dizinleri sil

# Yeniden adlandır/taşı
os.rename("eski.txt", "yeni.txt")
os.replace("kaynak.txt", "hedef.txt")  # Üzerine yazar
```
