# 📜 Python XML Dosya İşlemleri Rehberi
XML (eXtensible Markup Language), veri saklama ve transferi için yapılandırılmış bir format.

## 🔧 Temel Kütüphaneler
```
import xml.etree.ElementTree as ET  # Standart kütüphane
# veya
from xml.dom import minidom        # DOM parser
```

## 📝 XML Oluşturma ve Yazma
```
import xml.etree.ElementTree as ET

# Kök element oluştur
root = ET.Element("kisiler")

# Alt elementler ekle
kisi1 = ET.SubElement(root, "kisi")
ET.SubElement(kisi1, "isim").text = "Ali"
ET.SubElement(kisi1, "yas").text = "25"
ET.SubElement(kisi1, "sehir").text = "İstanbul"

kisi2 = ET.SubElement(root, "kisi")
ET.SubElement(kisi2, "isim").text = "Ayşe"
ET.SubElement(kisi2, "yas").text = "30"

# XML ağacını oluştur
tree = ET.ElementTree(root)

# Dosyaya yaz
tree.write("kisiler.xml", encoding="utf-8", xml_declaration=True)
```

## 📖 XML Okuma
```
import xml.etree.ElementTree as ET

# XML dosyasını oku
tree = ET.parse("kisiler.xml")
root = tree.getroot()

# Tüm kişileri listele
for kisi in root.findall("kisi"):
    isim = kisi.find("isim").text
    yas = kisi.find("yas").text
    print(f"İsim: {isim}, Yaş: {yas}")
```

```

```













