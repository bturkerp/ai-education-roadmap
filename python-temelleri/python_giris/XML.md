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
İsim: Ali, Yaş: 25
İsim: Ayşe, Yaş: 30
```

## 🔍 Element Bulma
```
import xml.etree.ElementTree as ET

tree = ET.parse("kisiler.xml")
root = tree.getroot()

# İlk kisi elementi
ilk_kisi = root.find("kisi")

# Tüm kisi elementleri
tum_kisiler = root.findall("kisi")

# İsmi Ali olan kişi
ali = root.find(".//kisi[isim='Ali']")

# XPath kullanarak
yas_25 = root.findall(".//kisi[yas='25']")
```

## ✏️ XML Düzenleme
```
import xml.etree.ElementTree as ET

tree = ET.parse("kisiler.xml")
root = tree.getroot()

# Yeni kişi ekle
yeni_kisi = ET.SubElement(root, "kisi")
ET.SubElement(yeni_kisi, "isim").text = "Mehmet"
ET.SubElement(yeni_kisi, "yas").text = "35"

# Yaşını güncelle
for kisi in root.findall("kisi"):
    if kisi.find("isim").text == "Ali":
        kisi.find("yas").text = "26"

# Kaydet
tree.write("kisiler_guncel.xml", encoding="utf-8")
```









