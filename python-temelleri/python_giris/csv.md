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



