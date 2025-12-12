#📊 Python CSV Dosya İşlemleri Rehberi
CSV (Comma-Separated Values) dosyaları, verileri tablo formatında saklamak için kullanılır.

📂 CSV Açma Modları

```
"r"   # Okuma (read)
"w"   # Yazma (write - üzerine yazar)
"a"   # Ekleme (append)
"r+"  # Okuma ve yazma
```

📝 CSV'ye Yazma
```
import csv

veriler = [
    ["İsim", "Yaş", "Şehir"],
    ["Ali", "25", "İstanbul"],
    ["Ayşe", "30", "Ankara"]
]

with open("kisiler.csv", "w", newline="", encoding="utf-8") as f:
    yazici = csv.writer(f)
    yazici.writerows(veriler)
```

📖 CSV'den Okuma
```
import csv

with open("kisiler.csv", "r", encoding="utf-8") as f:
    okuyucu = csv.reader(f)
    for satir in okuyucu:
        print(satir)
```
Çıktı:
```
['İsim', 'Yaş', 'Şehir']
['Ali', '25', 'İstanbul']
['Ayşe', '30', 'Ankara']
```

📋 Sözlük Formatında Okuma/Yazma
```
import csv
# Yazma
kisiler = [
    {"isim": "Ali", "yas": 25, "sehir": "İstanbul"},
    {"isim": "Ayşe", "yas": 30, "sehir": "Ankara"}
]

with open("kisiler_dict.csv", "w", newline="", encoding="utf-8") as f:
    alanlar = ["isim", "yas", "sehir"]
    yazici = csv.DictWriter(f, fieldnames=alanlar)
    yazici.writeheader()
    yazici.writerows(kisiler)

# Okuma
with open("kisiler_dict.csv", "r", encoding="utf-8") as f:
    okuyucu = csv.DictReader(f)
    for kayit in okuyucu:
        print(f"{kayit['isim']} - {kayit['yas']} - {kayit['sehir']}")
```
Çıktı
```
Ali - 25 - İstanbul
Ayşe - 30 - Ankara
```

🔧 Özel Ayraç Kullanma
```
import csv
# Noktalı virgül ile
with open("veri.csv", "w", newline="", encoding="utf-8") as f:
    yazici = csv.writer(f, delimiter=";")
    yazici.writerow(["İsim", "Yaş"])
    yazici.writerow(["Ali", "25"])

# Tab ile
with open("veri.tsv", "w", newline="", encoding="utf-8") as f:
    yazici = csv.writer(f, delimiter="\t")
    yazici.writerow(["İsim", "Yaş"])
    yazici.writerow(["Ali", "25"])
```
➕ CSV'ye Satır Ekleme
```
with open("kisiler.csv", "a", newline="", encoding="utf-8") as f:
    yazici = csv.writer(f)
    yazici.writerow(["Mehmet", "35", "İzmir"])
```

🔍 CSV Filtreleme
```
import csv
with open("kisiler.csv", "r", encoding="utf-8") as f:
    okuyucu = csv.reader(f)
    for satir in okuyucu:
        if satir[1] > "25":  # Yaşı 25'ten büyük olanlar
            print(satir)
```
Çıktı:
```
['İsim', 'Yaş', 'Şehir']
['Ayşe', '30', 'Ankara']
```

📊 Pandas ile CSV İşlemleri
```
import pandas as pd

# Okuma
df = pd.read_csv("kisiler.csv")
print(df)

# Yazma
df.to_csv("yeni_kisiler.csv", index=False)

# Filtreleme
buyuk_25 = df[df["Yaş"] > 25]
```
Çıktı:
```
   İsim  Yaş     Şehir
0   Ali   25  İstanbul
1  Ayşe   30    Ankara
```

🛠️ CSV Düzenleme
```
import csv

# Verileri oku
satirlar = []
with open("kisiler.csv", "r", encoding="utf-8") as f:
    okuyucu = csv.reader(f)
    for satir in okuyucu:
        # Her satıra "Ülke" sütunu ekle
        satir.append("Türkiye")
        satirlar.append(satir)

# Düzenlenmiş veriyi yaz
with open("kisiler_duzenli.csv", "w", newline="", encoding="utf-8") as f:
    yazici = csv.writer(f)
    yazici.writerows(satirlar)
```

## ✅ Özet

| İşlem | Kütüphane/Fonksiyon | Notlar |
|-------|-------------------|--------|
| **Okuma** | `csv.reader()` | Satır listesi olarak okur |
| **Okuma** | `csv.DictReader()` | Sözlük formatında okur |
| **Yazma** | `csv.writer()` | Listeleri CSV'ye yazar |
| **Yazma** | `csv.DictWriter()` | Sözlükleri CSV'ye yazar |
| **Hızlı İşlem** | `pandas.read_csv()` | Büyük veriler için |
| **Yazma** | `pandas.to_csv()` | DataFrame'den CSV'ye |

---

## 💡 İpuçları

1. **`newline=""`** parametresi satır sonu sorunlarını önler  
2. **`encoding="utf-8"`** Türkçe karakterler için gereklidir  
3. **DictReader/DictWriter** sütun isimleriyle çalışmayı kolaylaştırır  
4. **Pandas** büyük CSV dosyaları için daha hızlıdır

## 1. Özel Karakter Problemleri
```
import csv
# Tırnak işareti içeren veriler
with open("problemli.csv", "w", newline="", encoding="utf-8") as f:
    yazici = csv.writer(f, quoting=csv.QUOTE_ALL)  # Tüm alanları tırnak içine al
    yazici.writerow(['Ali "Büyük"', '25,5 yaş', 'İstanbul;Kadıköy'])
```

## 2. Farklı CSV Formatları
```
import csv
# quotechar: Tırnak karakterini değiştirme
with open("farkli.csv", "w", newline="", encoding="utf-8") as f:
    yazici = csv.writer(f, delimiter=";", quotechar="'", quoting=csv.QUOTE_MINIMAL)
```

## 3. Hata Yönetimi
```
import csv

try:
    with open("olmayan.csv", "r") as f:
        okuyucu = csv.reader(f)
except FileNotFoundError:
    print("Dosya bulunamadı!")
except csv.Error as e:
    print(f"CSV okuma hatası: {e}")
```
Çıktı:
```
Dosya bulunamadı!
```

## 4. Büyük Dosyalarla Çalışma
```
import csv
# Streaming ile okuma (hafıza dostu)
def buyuk_csv_oku(dosya_adi):
    with open(dosya_adi, "r", encoding="utf-8") as f:
        okuyucu = csv.reader(f)
        for satir in okuyucu:
            yield satir  # Generator kullanımı

# Kullanım
for satir in buyuk_csv_oku("cok_buyuk.csv"):
    print(satir)
```

## 5. CSV Doğrulama (Validasyon)
```
import csv

def csv_kontrol_et(dosya_adi):
    with open(dosya_adi, "r", encoding="utf-8") as f:
        okuyucu = csv.reader(f)
        satirlar = list(okuyucu)
        
        sutun_sayisi = len(satirlar[0])
        hata_yok = True
        
        for i, satir in enumerate(satirlar[1:], start=2):
            if len(satir) != sutun_sayisi:
                print(f"{i}. satırda sütun sayısı farklı")
                hata_yok = False
        
        if hata_yok:
            print("✅ Dosya düzgün")

# Kullanım
csv_kontrol_et("yeni_kisiler.csv")
```
Çıktı:
```
✅ Dosya düzgün
```

## 6. CSV'den JSON'a Dönüşüm
```
import csv
import json

def csv_to_json(csv_dosya, json_dosya):
    with open(csv_dosya, "r", encoding="utf-8") as f:
        okuyucu = csv.DictReader(f)
        veriler = list(okuyucu)
    
    with open(json_dosya, "w", encoding="utf-8") as f:
        json.dump(veriler, f, ensure_ascii=False, indent=2)
csv_to_json("problemli.csv", "problemli.json")
```



