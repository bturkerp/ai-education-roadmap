📄 Python JSON Dosya İşlemleri Rehberi
JSON (JavaScript Object Notation), veri alışverişi için hafif bir format.

📝 JSON'a Yazma
```
import json

veri = {
    "isim": "Ali",
    "yas": 25,
    "sehir": "İstanbul",
    "hobiler": ["spor", "müzik", "kitap"]
}

# JSON dosyasına yaz
with open("kisi.json", "w", encoding="utf-8") as f:
    json.dump(veri, f, ensure_ascii=False, indent=4)
```

📖 JSON'dan Okuma
```
import json

with open("kisi.json", "r", encoding="utf-8") as f:
    veri = json.load(f)

print(veri["isim"])  # Ali
print(veri["hobiler"][0])  # spor
```
Çıktı:
```
Ali
spor
```

📋 Liste Formatında JSON
```
import json

kisiler = [
    {"isim": "Ali", "yas": 25},
    {"isim": "Ayşe", "yas": 30},
    {"isim": "Mehmet", "yas": 35}
]

# Yazma
with open("kisiler.json", "w", encoding="utf-8") as f:
    json.dump(kisiler, f, ensure_ascii=False, indent=2)

# Okuma
with open("kisiler.json", "r", encoding="utf-8") as f:
    kisiler_okunan = json.load(f)
    for kisi in kisiler_okunan:
        print(kisi["isim"], kisi["yas"])
```
Çıktı:

```
Ali 25
Ayşe 30
Mehmet 35
```















