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
os.mkdir("d:/yeni_klasor")  # Tek dizin
os.makedirs("d:/a/b/c")  # İç içe dizinler (recursive)
os.makedirs("d:/dizin", exist_ok=True)  # Varsa hata vermez

# Dosya oluştur
with open("d:/yeni_dosya.txt", "w") as f:
    f.write("Merhaba")

# Dosya/dizin sil
os.remove("d:/yeni_dosya.txt")  # Dosya sil
os.rmdir("d:/yeni_klasor")  # Boş dizin sil
os.removedirs("d:/a/b/c")  # İç içe boş dizinleri sil
with open("d:/eski.txt", "w") as f:
    f.write("Merhaba")
with open("d:/kaynak.txt", "w") as f:
    f.write("Merhaba")

# Yeniden adlandır/taşı
os.rename("d:/eski.txt", "d:/yeni.txt")
os.replace("d:/kaynak.txt", "d:/hedef.txt")  # Üzerine yazar
```

#### 🔗 Path İşlemleri (os.path)
```
import os

dosya_yolu = "D:/COVID/CBU Dataset/Pozitif/Covid (1).jpg"

# Path parçalarını ayır
print(os.path.split(dosya_yolu))  # ('/home/user/dosyalar', 'resim.jpg')
print(os.path.dirname(dosya_yolu))  # /home/user/dosyalar
print(os.path.basename(dosya_yolu))  # resim.jpg
print(os.path.splitext(dosya_yolu))  # ('/home/user/dosyalar/resim', '.jpg')

# Path birleştirme
print(os.path.join("klasor", "alt", "dosya.txt"))  # klasor/alt/dosya.txt

# Path normalleştirme
print(os.path.normpath("a/./b/../c"))  # a/c
print(os.path.abspath("goreceli/yol"))  # Tam yol
print(os.path.relpath("/a/b/c", "/a"))  # b/c (relative path)

# Sürücü bilgisi (Windows)
if os.name == 'nt':  # Windows
    print(os.path.splitdrive("C:/Windows"))  # ('C:', '/Windows')
```
Çıktı:
```
('D:/COVID/CBU Dataset/Pozitif', 'Covid (1).jpg')
D:/COVID/CBU Dataset/Pozitif
Covid (1).jpg
('D:/COVID/CBU Dataset/Pozitif/Covid (1)', '.jpg')
klasor\alt\dosya.txt
a\c
C:\Users\b_tur\goreceli\yol
b\c
('C:', '/Windows')
```
