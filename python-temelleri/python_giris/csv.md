📊 Python CSV Dosya İşlemleri Rehberi
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

