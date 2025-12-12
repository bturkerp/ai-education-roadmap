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

### 🔗 Path İşlemleri (os.path)
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

### ⚙️ Sistem Bilgileri
```
import os

# İşletim sistemi
print(os.name)  # nt (Windows), posix (Linux/Mac)
print(os.environ)  # Çevre değişkenleri
print(os.environ.get("PATH"))  # PATH değişkeni
print(os.getlogin())  # Kullanıcı adı

# Satır sonu karakteri
print(repr(os.linesep))  # '\n' veya '\r\n'
```
Çıktı:
```
nt
environ({'ACSETUPSVCPORT': '23210', 'ALLUSERSPROFILE': 'C:\\ProgramData', 'APPDATA': 'C:\\Users\\b_tur\\AppData\\Roaming', 'CHROME_CRASHPAD_PIPE_NAME': '\\\\.\\pipe\\crashpad_15492_LMDPGBHEFTPSLTKV', 'COMMONPROGRAMFILES': 'C:\\Program Files\\Common Files', 'COMMONPROGRAMFILES(X86)': 'C:\\Program Files (x86)\\Common Files', 'COMMONPROGRAMW6432': 'C:\\Program Files\\Common Files', 'COMPUTERNAME': 'TURKER', 'COMSPEC': 'C:\\WINDOWS\\system32\\cmd.exe', 'CUDA_PATH': 'C:\\Program Files\\NVIDIA GPU Computing Toolkit\\CUDA\\v12.6', 'CUDA_PATH_V12_6': 'C:\\Program Files\\NVIDIA GPU Computing Toolkit\\CUDA\\v12.6', 'DRIVERDATA': 'C:\\Windows\\System32\\Drivers\\DriverData', 'EFC_16756_1262719628': '1', 'EFC_16756_1592913036': '1', 'EFC_16756_2283032206': '1', 'EFC_16756_2775293581': '1', 'EFC_16756_3789132940': '1', 'HOMEDRIVE': 'C:', 'HOMEPATH': '\\Users\\b_tur', 'LOCALAPPDATA': 'C:\\Users\\b_tur\\AppData\\Local', 'LOGONSERVER': '\\\\TURKER', 'NUMBER_OF_PROCESSORS': '32', 'NVTOOLSEXT_PATH': 'C:\\Program Files\\NVIDIA Corporation\\NvToolsExt\\', 'ONEDRIVE': 'C:\\Users\\b_tur\\OneDrive', 'OS': 'Windows_NT', 'PATH': 'C:\\Program Files\\NVIDIA GPU Computing Toolkit\\CUDA\\v12.6\\bin;C:\\Program Files\\NVIDIA GPU Computing Toolkit\\CUDA\\v12.6\\libnvvp;C:\\Program Files\\NVIDIA GPU Computing Toolkit\\CUDA\\v11.2\\bin;C:\\Program Files\\NVIDIA GPU Computing Toolkit\\CUDA\\v11.2\\libnvvp;C:\\WINDOWS\\system32;C:\\WINDOWS;C:\\WINDOWS\\System32\\Wbem;C:\\WINDOWS\\System32\\WindowsPowerShell\\v1.0\\;C:\\WINDOWS\\System32\\OpenSSH\\;C:\\Program Files\\dotnet\\;C:\\Program Files\\NVIDIA Corporation\\NVIDIA App\\NvDLISR;C:\\Program Files (x86)\\NVIDIA Corporation\\PhysX\\Common;C:\\Program Files\\NVIDIA Corporation\\Nsight Compute 2024.3.0\\;C:\\Program Files\\Git\\cmd;C:\\Users\\b_tur\\AppData\\Local\\Microsoft\\WindowsApps;C:\\Users\\b_tur\\AppData\\Local\\Programs\\Microsoft VS Code\\bin;C:\\Users\\b_tur\\.conda\\envs\\tf210;C:\\Users\\b_tur\\.conda\\envs\\tf210\\Scripts;C:\\Users\\b_tur\\.conda\\envs\\tf210\\Library\\bin;C:\\Program Files\\NVIDIA GPU Computing Toolkit\\CUDA\\v12.6\\bin;C:\\Program Files\\NVIDIA GPU Computing Toolkit\\CUDA\\v12.6\\libnvvp;', 'PATHEXT': '.COM;.EXE;.BAT;.CMD;.VBS;.VBE;.JS;.JSE;.WSF;.WSH;.MSC;.CPL', 'PROCESSOR_ARCHITECTURE': 'AMD64', 'PROCESSOR_IDENTIFIER': 'Intel64 Family 6 Model 183 Stepping 1, GenuineIntel', 'PROCESSOR_LEVEL': '6', 'PROCESSOR_REVISION': 'b701', 'PROGRAMDATA': 'C:\\ProgramData', 'PROGRAMFILES': 'C:\\Program Files', 'PROGRAMFILES(X86)': 'C:\\Program Files (x86)', 'PROGRAMW6432': 'C:\\Program Files', 'PSMODULEPATH': 'C:\\Users\\b_tur\\OneDrive\\Documents\\WindowsPowerShell\\Modules;C:\\Program Files\\WindowsPowerShell\\Modules;C:\\WINDOWS\\system32\\WindowsPowerShell\\v1.0\\Modules', 'PUBLIC': 'C:\\Users\\Public', 'RLSSVCPORT': '22112', 'SESSIONNAME': 'Console', 'SYSTEMDRIVE': 'C:', 'SYSTEMROOT': 'C:\\WINDOWS', 'TEMP': 'C:\\Users\\b_tur\\AppData\\Local\\Temp', 'TMP': 'C:\\Users\\b_tur\\AppData\\Local\\Temp', 'USERDOMAIN': 'TURKER', 'USERDOMAIN_ROAMINGPROFILE': 'TURKER', 'USERNAME': 'b_tur', 'USERPROFILE': 'C:\\Users\\b_tur', 'WINDIR': 'C:\\WINDOWS', 'TERM_PROGRAM': 'vscode', 'TERM_PROGRAM_VERSION': '1.107.0', 'LANG': 'en_US.UTF-8', 'COLORTERM': 'truecolor', 'GIT_ASKPASS': 'c:\\Users\\b_tur\\AppData\\Local\\Programs\\Microsoft VS Code\\resources\\app\\extensions\\git\\dist\\askpass.sh', 'VSCODE_GIT_ASKPASS_NODE': 'C:\\Users\\b_tur\\AppData\\Local\\Programs\\Microsoft VS Code\\Code.exe', 'VSCODE_GIT_ASKPASS_EXTRA_ARGS': '', 'VSCODE_GIT_ASKPASS_MAIN': 'c:\\Users\\b_tur\\AppData\\Local\\Programs\\Microsoft VS Code\\resources\\app\\extensions\\git\\dist\\askpass-main.js', 'VSCODE_GIT_IPC_HANDLE': '\\\\.\\pipe\\vscode-git-7327d241ff-sock', 'PYTHONSTARTUP': 'c:\\Users\\b_tur\\AppData\\Roaming\\Code\\User\\globalStorage\\ms-python.python\\pythonrc.py', 'PYTHON_BASIC_REPL': '1', 'VSCODE_INJECTION': '1', 'VSCODE_NONCE': '145a5a27-9691-4223-a3d3-67bc5a49a8f5', 'VSCODE_A11Y_MODE': '0', 'VSCODE_STABLE': '1'})
C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v12.6\bin;C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v12.6\libnvvp;C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v11.2\bin;C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v11.2\libnvvp;C:\WINDOWS\system32;C:\WINDOWS;C:\WINDOWS\System32\Wbem;C:\WINDOWS\System32\WindowsPowerShell\v1.0\;C:\WINDOWS\System32\OpenSSH\;C:\Program Files\dotnet\;C:\Program Files\NVIDIA Corporation\NVIDIA App\NvDLISR;C:\Program Files (x86)\NVIDIA Corporation\PhysX\Common;C:\Program Files\NVIDIA Corporation\Nsight Compute 2024.3.0\;C:\Program Files\Git\cmd;C:\Users\b_tur\AppData\Local\Microsoft\WindowsApps;C:\Users\b_tur\AppData\Local\Programs\Microsoft VS Code\bin;C:\Users\b_tur\.conda\envs\tf210;C:\Users\b_tur\.conda\envs\tf210\Scripts;C:\Users\b_tur\.conda\envs\tf210\Library\bin;C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v12.6\bin;C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v12.6\libnvvp;
b_tur
'\r\n'
```

### 🔐 Dosya İzinleri
```
import os
import stat

# İzinleri değiştir
os.chmod("kisiler.xml", stat.S_IRWXU)  # Sahibi: tüm izinler
os.chmod("kisiler.xml", stat.S_IRUSR | stat.S_IWUSR)  # Sahibi: okuma+yazma

# İzinleri oku
izinler = os.stat("kisiler.xml").st_mode
print(stat.filemode(izinler))  # -rw-r--r--

# Sahip bilgisi
print(os.stat("kisiler.xml").st_uid)  # User ID
print(os.stat("kisiler.xml").st_gid)  # Group ID
```
Çıktı: 
```
-rw-rw-rw-
0
0
```

## 🛣️ PATHLIB MODÜLÜ (Modern Yol İşlemleri)
### 🎯 Path Objesi Oluşturma
```
from pathlib import Path

# Path oluşturma yolları
p1 = Path("dosya.txt")  # Mevcut dizinde
p2 = Path("/home/user/dosya.txt")  # Tam yol
p3 = Path("klasor") / "alt" / "dosya.txt"  # Zincirleme
p4 = Path.cwd() / "dosya.txt"  # Mevcut dizinle birleştirme
p5 = Path.home() / "Desktop" / "dosya.txt"  # Home dizini

print(f"Home dizini: {Path.home()}")
print(f"Mevcut dizin: {Path.cwd()}")
```
Çıktı:
```
Home dizini: C:\Users\b_tur
Mevcut dizin: C:\Users\b_tur
```

### 🔍 Kontrol ve Bilgi Alma
```
from pathlib import Path

p = Path("dosya.txt")

# Kontroller
print(p.exists())  # Var mı?
print(p.is_file())  # Dosya mı?
print(p.is_dir())  # Dizin mi?
print(p.is_absolute())  # Tam yol mu?
print(p.is_symlink())  # Sembolik link mi?

# Bilgiler
print(p.stat().st_size)  # Boyut
print(p.stat().st_mtime)  # Değişim zamanı
print(p.owner())  # Sahibi
print(p.group())  # Grubu
```
Çıktı:
```
True
True
False
True
False
169
1765555436.0935638
Traceback (most recent call last):
  File "C:\Users\b_tur\.conda\envs\tf\lib\pathlib.py", line 342, in owner
    import pwd
ModuleNotFoundError: No module named 'pwd'

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File "d:\input(x).py", line 15, in <module>
    print(p.owner())  # Sahibi
  File "C:\Users\b_tur\.conda\envs\tf\lib\pathlib.py", line 1103, in owner
    return self._accessor.owner(self)
  File "C:\Users\b_tur\.conda\envs\tf\lib\pathlib.py", line 345, in owner
    raise NotImplementedError("Path.owner() is unsupported on this system")
NotImplementedError: Path.owner() is unsupported on this system
```
Windows’ta Path.owner() ve Path.group() çalışmaz. Python’ın pwd modülü yalnızca Linux / macOS içindir. 
Windows’ta dosya sahibini öğrenmek için win32security (pywin32) kullanılır.
Bunun için öncelikle conda ortamında "pywin32" kütüphanesi kurulmalıdır:
```
pip install pywin32
```
Kurulum tamamlanınca kodu aşağıdaki şekilde değiştirin:
```
from pathlib import Path
import win32security
import ntsecuritycon as con
p = Path("d:/kisiler.xml")

# Kontroller
print(p.exists())  # Var mı?
print(p.is_file())  # Dosya mı?
print(p.is_dir())  # Dizin mi?
print(p.is_absolute())  # Tam yol mu?
print(p.is_symlink())  # Sembolik link mi?

# Bilgiler
print(p.stat().st_size)  # Boyut
print(p.stat().st_mtime)  # Değişim zamanı

def get_owner_windows(path):
    path = str(path)
    sd = win32security.GetFileSecurity(path, win32security.OWNER_SECURITY_INFORMATION)
    owner_sid = sd.GetSecurityDescriptorOwner()
    name, domain, type = win32security.LookupAccountSid(None, owner_sid)
    return f"{domain}\\{name}"

p = Path("ornek.bin")
print("Dosya Sahibi:", get_owner_windows(p))
```
Çıktı:
```
True
True
False
True
False
169
1765555436.0935638
Dosya Sahibi: TURKER\b_tur
```

### 📂 Path Parçaları
```
from pathlib import Path

p = Path("/home/user/dosyalar/resim.jpg")

# Parçalara ayırma
print(p.name)  # resim.jpg
print(p.stem)  # resim (uzantısız)
print(p.suffix)  # .jpg
print(p.suffixes)  # ['.tar', '.gz'] (birden fazla uzantı)
print(p.parent)  # /home/user/dosyalar
print(p.parents[0])  # Bir üst: /home/user/dosyalar
print(p.parents[1])  # İki üst: /home/user
print(p.anchor)  # Kök: / (Linux) veya C:\ (Windows)
print(p.parts)  # ('/', 'home', 'user', 'dosyalar', 'resim.jpg')
```
Çıktı:
```
resim.jpg
resim
.jpg
['.jpg']
\home\user\dosyalar
\home\user\dosyalar
\home\user
\
('\\', 'home', 'user', 'dosyalar', 'resim.jpg')
```

### 📝 Dosya/Dizin İşlemleri
```
from pathlib import Path

# Dizin oluştur
Path("d:/yeni_klasor").mkdir()
Path("d:/a/b/c").mkdir(parents=True, exist_ok=True)  # İç içe oluştur

# Dosya oluştur
Path("d:/dosya.txt").touch()  # Boş dosya
Path("d:/dosya.txt").write_text("Merhaba Dünya", encoding="utf-8")

# Dosya okuma/yazma
icerik = Path("d:/dosya.txt").read_text(encoding="utf-8")
Path("d:/dosya.txt").write_text("Yeni içerik", encoding="utf-8")

# Binary okuma/yazma
data = Path("D:/COVID/CBU Dataset/Negatif/Non-Covid (1).jpg").read_bytes()
Path("kopya.jpg").write_bytes(data)

# Yeniden adlandır/taşı
Path("d:/dosya.txt").rename("d:/yeni.txt")
Path("d:/yeni.txt").replace("d:/hedef.txt")

# Silme
Path("d:/hedef.txt").unlink()  # Dosya sil
Path("d:/yeni_klasor").rmdir()  # Boş dizin sil
```

### 🔍 Dosya Arama ve Filtreleme
```
from pathlib import Path

# Tüm dosyaları listele
for dosya in Path(".").iterdir():
    print(dosya)

# Sadece .txt dosyaları
txt_dosyalari = list(Path(".").glob("*.txt"))

# Rekürsif arama (alt dizinlerde)
tum_txt_dosyalari = list(Path(".").rglob("*.txt"))

# Pattern matching
py_dosyalari = Path(".").glob("**/*.py")  # Tüm .py dosyaları

# Filtreleme
for dosya in Path(".").iterdir():
    if dosya.is_file() and dosya.suffix == ".txt":
        print(f"Text dosyası: {dosya}")
    elif dosya.is_dir():
        print(f"Dizin: {dosya}")
```
Çıktı:
```
-1.14-windows.xml
.android
.conda
.cupy
.
.
.
Dizin: vscode-remote-wsl
Dizin: weights
Text dosyası: yeni_dosya.txt
Dizin: yeni_klasor
```

### 🧩 Path Manipülasyonu
```
from pathlib import Path

# Path birleştirme
p = Path("/home/user")
yeni_yol = p / "dosyalar" / "resim.jpg"

# Parent ile gezinme
p = Path("/a/b/c/d.txt")
print(p.parent)  # /a/b/c
print(p.parent.parent)  # /a/b

# Relative path
p1 = Path("/home/user/dosyalar")
p2 = Path("/home/user/dosyalar/resimler/foto.jpg")
print(p2.relative_to(p1))  # resimler/foto.jpg

# Path'i değiştir
p = Path("/home/user/eski.txt")
yeni_p = p.with_name("yeni.txt")  # isim değiştir
yeni_p = p.with_suffix(".jpg")  # uzantı değiştir
yeni_p = p.with_stem("yenibaslik")  # stem değiştir
```
Çıktı:
```
\a\b\c
\a\b
resimler\foto.jpg
```









