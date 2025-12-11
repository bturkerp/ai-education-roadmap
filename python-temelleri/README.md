# 📘  Python Programa Eğitimi

![Python Version](https://img.shields.io/badge/python-3.8%2B-blue)
![License](https://img.shields.io/badge/license-MIT-green)
![Contributions](https://img.shields.io/badge/contributions-welcome-brightgreen)


Bu Bölümde öncelikle python çalışma ortamını kurmak için gerekli uygulamaların yüklenmesi gösterilmiştir. Visual studio code ve miniconda uygulamalarının kuruluşu gösterilmiş ve conda ortamının cpu/gpu destekli kuruluşları gösterilmiştir. 

## [Visual Studio Code Uygulamasının Kuruluşu](01_visual-studio-code-kurulum.md)

## [Mini Conda Kurulumu, Ortam Oluşturma ve Gerekli Kütüphanelerin Kuruluşu:](02_Miniconda_kurulum.md)

Ardından python ile kodlama, örneklerle açıklanmıştır. 

## 📚 Kapsamlı Python Öğrenme Yol Haritası

Bu repository, sıfırdan ileri seviyeye Python programlama öğrenmek isteyenler için hazırlanmıştır. Visual Studio Code ve MiniConda kurulumundan başlayarak, profesyonel Python geliştiricisi olana kadar tüm konuları kapsar.

### 🎯 Hedef Kitle
- Programlamaya yeni başlayanlar
- Python öğrenmek isteyen diğer dil geliştiricileri
- Veri bilimi/Makine öğrenmesi için temel Python öğrenmek isteyenler
- Otomasyon scriptleri yazmak isteyenler

### 📖 İçindekiler

| Bölüm | Konu | Seviye | Tahmini Süre |
|-------|------|--------|--------------|
| 01 | Python Tarihçesi ve Özellikleri | Başlangıç | 1 saat |
| 02 | Python 2 vs Python 3 Farkları | Başlangıç | 1 saat |
| 03 | Python Kullanım Alanları | Başlangıç | 2 saat |
| 04 | Değişkenler ve Veri Tipleri | Başlangıç | 3 saat |
| 05 | Operatörler | Başlangıç | 2 saat |
| 06 | Kontrol Yapıları | Başlangıç | 3 saat |
| 07 | Fonksiyonlar | Orta | 4 saat |
| 08 | Modüller ve Paketler | Orta | 3 saat |
| 09 | Nesne Yönelimli Programlama | İleri | 6 saat |
| 10 | Hata Yönetimi | Orta | 2 saat |
| 11 | Dosya İşlemleri | Orta | 2 saat |
| 12 | Veritabanı İşlemleri | Orta | 3 saat |
| 13 | Web Scraping | İleri | 4 saat |
| 14 | API Geliştirme | İleri | 5 saat |
| 15 | Test Yazma | İleri | 3 saat |

### ⚙️ Kurulum Gereksinimleri

#### Zorunlu Yazılımlar:
1. **Python 3.8+** - [İndirme Linki](https://www.python.org/downloads/)
2. **Visual Studio Code** - [İndirme Linki](https://code.visualstudio.com/)
3. **MiniConda** - [İndirme Linki](https://docs.conda.io/en/latest/miniconda.html)

#### Önerilen VS Code Extension'ları:
```json
{
    "extensions": [
        "ms-python.python",
        "ms-python.vscode-pylance",
        "ms-python.black-formatter",
        "ms-python.isort",
        "ms-python.flake8",
        "ms-toolsai.jupyter",
        "formulahendry.code-runner"
    ]
}

Conda Environment Kurulumu:
bash
# 1. Environment oluşturma
```
conda create -n python_egitimi python=3.9
```
# 2. Environment'i aktif etme
```
conda activate python_egitimi
```
# 3. Gerekli paketleri yükleme
```
pip install -r requirements.txt
```
🚀 Hızlı Başlangıç
Repository'yi klonlayın:
```
bash
git clone https://github.com/kullaniciadi/python-egitimi.git
cd python-egitimi
```

Virtual environment oluşturun:
```
bash
python -m venv venv
# Windows
venv\Scripts\activate

# Linux/Mac
source venv/bin/activate
```

Gerekli paketleri yükleyin:
```
bash
pip install -r requirements.txt
```

İlk Python programınızı çalıştırın:
```
bash
python 01_python_tarihcesi_ozellikleri/merhaba.py
```

📝 Proje Yapısı
Her bölüm aşağıdaki yapıyı içerir:
```
text
bolum_adi/
├── README.md              # Konu anlatımı ve teorik bilgiler
├── ornekler.py            # Kod örnekleri
├── alistirmalar.py        # Pratik alıştırmalar
├── cozumler.py            # Alıştırma çözümleri
└── test_bolum.py          # Unit testler
```

🧪 Test Etme
Her bölüm için unit testler bulunmaktadır:
```
bash
# Tüm testleri çalıştır
python -m pytest

# Belirli bir bölümü test et
python -m pytest 04_degiskenler_veri_tipleri/test_degiskenler.py

# Coverage raporu al
python -m pytest --cov=. --cov-report=html
```
🤝 Katkıda Bulunma
Bu repository'yi fork edin

Yeni bir branch oluşturun (git checkout -b feature/yeni-ozellik)

Değişikliklerinizi commit edin (git commit -am 'Yeni özellik eklendi')

Branch'inizi push edin (git push origin feature/yeni-ozellik)

Pull Request oluşturun

📄 Lisans
Bu proje MIT lisansı altında lisanslanmıştır. Detaylar için LICENSE dosyasına bakın.

👨‍💻 Yazar
[Adınız] - GitHub Profiliniz

🙏 Teşekkürler
Python Yazılım Vakfı

Tüm açık kaynak katkıcıları

Bu eğitimi geliştirmeye yardım eden herkese

⭐ Bu repository'yi beğendiyseniz yıldız vermeyi unutmayın!


