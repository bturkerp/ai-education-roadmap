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

