# 📄 Python JSON Dosya İşlemleri Rehberi
JSON (JavaScript Object Notation), veri alışverişi için hafif bir format.

## 📝 JSON'a Yazma
```
import json

veri = {
    "isim": "Ali",
    "yas": 25,
    "sehir": "İstanbul",
    "hobiler": ["spor", "müzik", "kitap"]
}

with open("kisi.json", "w", encoding="utf-8") as f:
    json.dump(veri, f, ensure_ascii=False, indent=4)
```

## 📖 JSON'dan Okuma
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

## 📋 Liste Formatında JSON
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

## 🔧 JSON Ayarları
```
import json

veri = {"isim": "Ali", "yas": 25}

# 1. İndent (girinti) ile yazma
with open("girintili.json", "w", encoding="utf-8") as f:
    json.dump(veri, f, indent=4, ensure_ascii=False)

# 2. Sıralı yazma
with open("sirali.json", "w", encoding="utf-8") as f:
    json.dump(veri, f, sort_keys=True, indent=2)

# 3. Tek satırda yazma
with open("tek_satir.json", "w", encoding="utf-8") as f:
    json.dump(veri, f, separators=(',', ':'))
```

## ➕ JSON'a Veri Ekleme
```
import json

# Mevcut veriyi oku
with open("kisiler.json", "r", encoding="utf-8") as f:
    kisiler = json.load(f)

# Yeni veri ekle
kisiler.append({"isim": "Zeynep", "yas": 28})

# Geri yaz
with open("kisiler.json", "w", encoding="utf-8") as f:
    json.dump(kisiler, f, ensure_ascii=False, indent=2)
```

## 🔍 JSON Doğrulama (Validasyon)
```
import json

json_string = '{"isim": "Ali", "yas": 25}'

# Geçerli JSON mu kontrol et
def json_kontrol(json_str):
    try:
        json.loads(json_str)
        print("✅ Geçerli JSON")
        return True
    except json.JSONDecodeError as e:
        print(f"❌ JSON hatası: {e}")
        return False

json_kontrol(json_string)
```
Çıktı: 
```
✅ Geçerli JSON
```

## 📊 CSV'den JSON'a Dönüşüm
```
import csv
import json

def csv_to_json(csv_dosya, json_dosya):
    veriler = []
    
    with open(csv_dosya, "r", encoding="utf-8") as f:
        okuyucu = csv.DictReader(f)
        for satir in okuyucu:
            veriler.append(satir)
    
    with open(json_dosya, "w", encoding="utf-8") as f:
        json.dump(veriler, f, ensure_ascii=False, indent=2)
    
    print(f"✅ {csv_dosya} → {json_dosya} dönüştürüldü")

# Kullanım
csv_to_json("kisiler.csv", "kisiler.json")
```
Çıktı: 
```
✅ kisiler.csv → kisiler.json dönüştürüldü
```

## 🔄 String ve JSON Dönüşümü
```
import json

# Python dict → JSON string
veri = {"isim": "Ali", "yas": 25}
json_string = json.dumps(veri, ensure_ascii=False, indent=2)
print("JSON String:", json_string)

# JSON string → Python dict
python_dict = json.loads(json_string)
print("Python Dict:", python_dict)
```
Çıktı: 
```
JSON String: {
  "isim": "Ali",
  "yas": 25
}
Python Dict: {'isim': 'Ali', 'yas': 25}
```

## ✅ Özet

| İşlem | Fonksiyon | Açıklama |
|-------|----------|----------|
| **Yazma** | `json.dump()` | Dosyaya yazar |
| **Okuma** | `json.load()` | Dosyadan okur |
| **String Yazma** | `json.dumps()` | String'e çevirir |
| **String Okuma** | `json.loads()` | String'den okur |
| **Türkçe Karakter** | `ensure_ascii=False` | Türkçe için gerekli |
| **Format** | `indent=2` | Okunaklı yazar |

---

## 💡 İpuçları

1. **`ensure_ascii=False`** Türkçe karakterler için şart  
2. **`indent`** parametresi okunabilirliği artırır  
3. JSON sadece belirli tipleri destekler: `dict`, `list`, `str`, `int`, `float`, `bool`, `None`  
4. Datetime gibi özel tipler JSON'a direk yazılamaz, string'e çevrilmeli





